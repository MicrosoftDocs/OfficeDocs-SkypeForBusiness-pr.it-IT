---
title: Tradurre i numeri di telefono per l'instradamento diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri come configurare l'instradamento diretto del Sistema telefonico Microsoft.
ms.openlocfilehash: 7d48e9163dd5927cbeddf4a4104d2382e69e7e2b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369161"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Tradurre i numeri di telefono in un formato alternativo

Questo articolo descrive come tradurre i numeri per le chiamate in uscita e in entrata in un formato alternativo.  Questo è il passaggio 4 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Collegare il servizio SBC al Sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria telefonica](direct-routing-enable-users.md)   
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- **Passaggio 4. Tradurre i numeri in un formato alternativo**   (questo articolo)

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)

A volte gli amministratori del tenant potrebbero voler modificare il numero delle chiamate in uscita e/o in entrata in base ai modelli creati per garantire l'interoperabilità con i controller dei confini della sessione (SBC). Questo articolo descrive come specificare un criterio Regole di traduzione numeri per tradurre i numeri in un formato alternativo. 

È possibile usare il criterio Regole di traduzione numeri per tradurre i numeri in uno dei modi seguenti:

- Chiamate in entrata: chiamate da un endpoint PSTN (chiamante) a un client Teams (chiamato)
- Chiamate in uscita: chiamate da un client (chiamante) di Teams a un endpoint PSTN (chiamato)

Il criterio viene applicato a livello di SBC. È possibile assegnare più regole di traduzione a un SBC, che vengono applicate nell'ordine in cui vengono visualizzate quando vengono elencate in PowerShell. È anche possibile modificare l'ordine delle regole nel criterio.

Per creare, modificare, visualizzare ed eliminare regole di modifica del numero, usare i cmdlet [New-CsTeamsTranslationRule,](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule) [Set-CsTeamsTranslationRule,](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule.](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule)

Per assegnare, configurare ed elencare regole di modifica dei numeri in SBCs, usare i cmdlet [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) e [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) insieme ai cmdlet InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, and OutboundPSTNNumberTranslationRules parameters.

> [!NOTE]
> Il numero massimo totale di regole di traduzione è 400, la lunghezza massima dei nomi dei parametri di traduzione è 100 simboli, la lunghezza massima dei criteri dei parametri di traduzione è 1024 simboli e la lunghezza massima della traduzione dei parametri di traduzione è 256 simboli.


## <a name="example-sbc-configuration"></a>Esempio di configurazione SBC

Per questo scenario, il ```New-CsOnlinePSTNGateway``` cmdlet viene eseguito per creare la configurazione SBC seguente:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Le regole di traduzione assegnate al campo SBC sono riepilogate nella tabella seguente:

|Nome  |Motivo |Conversione  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

Negli esempi seguenti ci sono due utenti, Alice e Bob. Alice è un utente di Teams il cui numero è +1 206 555 0100. Bob è un utente PSTN il cui numero è +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Esempio 1: Chiamata in ingresso a un numero di dieci cifre

Bob chiama Alice usando un numero non E.164 a dieci cifre. Bob compone il numero 2065550100 per raggiungere Alice.
SBC usa 2065550100 nelle intestazioni RequestURI e To e 4255550100 nell'intestazione Da.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:2065550100@sbc.contoso.com|INVITA sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|A    |A: \<sip:2065550100@sbc.contoso.com>|A: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|Da   |Da: \<sip:4255550100@sbc.contoso.com>|Da: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Esempio 2: Chiamata in ingresso a un numero a quattro cifre

Bob chiama Alice usando un numero di quattro cifre. Bob compone 0100 per raggiungere Alice.
SBC usa 0100 nelle intestazioni RequestURI e To e 4255550100 nell'intestazione From.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:0100@sbc.contoso.com          |INVITA sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|A    |A: \<sip:0100@sbc.contoso.com>|A: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|Da   |Da: \<sip:4255550100@sbc.contoso.com>|Da: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Esempio 3: Chiamata in uscita con un numero non E.164 di dieci cifre

Alice chiama Bob usando un numero di dieci cifre. Alice compone il numero 425 555 0100 per raggiungere Bob.
SBC è configurato per l'uso di numeri a dieci cifre non E.164 per gli utenti di Teams e PSTN.

In questo scenario, un piano di chiamata traduce il numero prima di inviarlo all'interfaccia di instradamento diretto. Quando Alice immette 425 555 0100 nel client di Teams, il numero viene convertito in +14255550100 dal dial plan del Paese. I numeri risultanti sono una normalizzazione cumulativa delle regole del piano di chiamata e delle regole di traduzione di Teams. Le regole di traduzione di Teams rimuovono il "+1" aggiunto dal piano di chiamata.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:+14255550100@sbc.contoso.com          |INVITA sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|A    |A: \<sip:+14255550100@sbc.contoso.com>|A: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|Da   |Da: \<sip:+12065550100@sbc.contoso.com>|Da: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Esempio 4: Chiamata in uscita con un numero non E.164 di quattro cifre

Alice chiama Bob usando un numero di quattro cifre. Alice usa 0100 per raggiungere Bob da Chiamate o tramite un contatto.
SBC è configurato per l'uso di numeri a quattro cifre non E.164 per gli utenti di Teams e numeri di dieci cifre per gli utenti PSTN. Il piano di chiamata non viene applicato in questo scenario.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:0100@sbc.contoso.com           |INVITA sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|A    |A: \<sip:0100@sbc.contoso.com>|A: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|Da   |Da: \<sip:+12065550100@sbc.contoso.com>|Da: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
