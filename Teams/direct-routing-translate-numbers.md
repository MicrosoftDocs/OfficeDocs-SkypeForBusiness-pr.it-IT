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
description: Informazioni su come configurare Telefono Microsoft routing diretto di sistema.
ms.openlocfilehash: ff560ca9417e5386819a90961562520da94d5cfcd65bd5348bd7718601610bf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337414"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Tradurre i numeri di telefono in un formato alternativo

Questo articolo descrive come tradurre i numeri per le chiamate in uscita e in ingresso in un formato alternativo.  Questo è il passaggio 4 della procedura seguente per la configurazione del routing diretto:

- Passaggio 1. [Connessione SBC con Telefono Microsoft sistema e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica](direct-routing-enable-users.md)   
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- **Passaggio 4. Tradurre i numeri in un formato alternativo**   (questo articolo)

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)

A volte gli amministratori del tenant possono voler modificare il numero delle chiamate in uscita e/o in ingresso in base ai modelli creati per garantire l'interoperabilità con i session border controller (SBC). Questo articolo descrive come specificare un criterio Regole di conversione numeri per tradurre i numeri in un formato alternativo. 

È possibile usare il criterio Regole di conversione numeri per tradurre i numeri per gli elementi seguenti:

- Chiamate in ingresso: chiamate da un endpoint PSTN (chiamante) a un client Teams (chiamato)
- Chiamate in uscita: chiamate da un client Teams (chiamante) a un endpoint PSTN (chiamato)

Il criterio viene applicato a livello di SBC. È possibile assegnare più regole di traduzione a un SBC, che vengono applicate nell'ordine in cui vengono visualizzate quando vengono elencate in PowerShell. È anche possibile modificare l'ordine delle regole nel criterio.

Per creare, modificare, visualizzare ed eliminare regole di modifica dei numeri, usare i cmdlet [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule.](/powershell/module/skype/remove-csteamstranslationrule)

Per assegnare, configurare ed elencare le regole di modifica dei numeri negli SBC, usare i cmdlet [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) e [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) insieme ai cmdlet InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules e OutboundPSTNNumberTranslationRules.

> [!NOTE]
> Il numero massimo totale di regole di conversione è 400, la lunghezza massima del nome del parametro di traduzione è 100 simboli, la lunghezza massima del modello di parametro di traduzione è 1024 simboli e la lunghezza massima di traduzione dei parametri di traduzione è 256 simboli.


## <a name="example-sbc-configuration"></a>Esempio di configurazione SBC

Per questo scenario, il ```New-CsOnlinePSTNGateway``` cmdlet viene eseguito per creare la configurazione SBC seguente:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Le regole di traduzione assegnate a SBC sono riepilogate nella tabella seguente:

|Nome  |Motivo |Conversione  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$ 1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

Negli esempi seguenti sono presenti due utenti, Alice e Luca. Alice è un utente Teams il cui numero è +1 206 555 0100. Luca è un utente PSTN il cui numero è +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Esempio 1: chiamata in ingresso a un numero a dieci cifre

Luca chiama Alice usando un numero a dieci cifre non E.164. Bob chiama 2065550100 per raggiungere Alice.
SBC usa 2065550100 nelle intestazioni RequestURI e To e 4255550100 nell'intestazione From.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:2065550100@sbc.contoso.com|INVITA sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|A    |A: \<sip:2065550100@sbc.contoso.com>|A: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|Da   |Da: \<sip:4255550100@sbc.contoso.com>|Da: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Esempio 2: Chiamata in ingresso a un numero a quattro cifre

Luca chiama Alice usando un numero a quattro cifre. Luca chiama 0100 per raggiungere Alice.
SBC usa 0100 nelle intestazioni RequestURI e To 4255550100 nell'intestazione From.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:0100@sbc.contoso.com          |INVITA sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|A    |A: \<sip:0100@sbc.contoso.com>|A: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|Da   |Da: \<sip:4255550100@sbc.contoso.com>|Da: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Esempio 3: Chiamata in uscita con un numero non E.164 di dieci cifre

Alice chiama Luca usando un numero di dieci cifre. Alice compone il numero 425 555 0100 per raggiungere Luca.
SBC è configurato per l'uso di numeri a dieci cifre non E.164 per gli utenti Teams e PSTN.

In questo scenario, un dial plan traduce il numero prima di inviarlo all'interfaccia di routing diretto. Quando Alice immette 425 555 0100 nel client Teams, il numero viene convertito in +14255550100 dal piano di chiamata del paese. I numeri risultanti sono una normalizzazione cumulativa delle regole del piano di chiamata e Teams di traduzione. Le Teams di traduzione rimuovono il "+1" aggiunto dal piano di chiamata.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:+14255550100@sbc.contoso.com          |INVITA sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|A    |A: \<sip:+14255550100@sbc.contoso.com>|A: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|Da   |Da: \<sip:+12065550100@sbc.contoso.com>|Da: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Esempio 4: Chiamata in uscita con un numero non E.164 a quattro cifre

Alice chiama Luca usando un numero a quattro cifre. Alice usa 0100 per raggiungere Luca da Chiamate o tramite un contatto.
SBC è configurato per l'uso di numeri a quattro cifre diversi da E.164 per gli utenti Teams e di dieci cifre per gli utenti PSTN. Il piano di chiamata non viene applicato in questo scenario.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITA sip:0100@sbc.contoso.com           |INVITA sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|A    |A: \<sip:0100@sbc.contoso.com>|A: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|Da   |Da: \<sip:+12065550100@sbc.contoso.com>|Da: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)