---
title: Tradurre numeri di telefono per l'instradamento diretto
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri come configurare il routing diretto del sistema telefonico Microsoft.
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727768"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Tradurre numeri di telefono in un formato alternativo

Questo articolo descrive come tradurre i numeri per le chiamate in uscita e in ingresso in un formato alternativo. Questo è il passaggio 4 della procedura seguente per configurare il routing diretto:

- Passaggio 1. [Connettere SBC con Sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per routing diretto, voce e segreteria telefonica](direct-routing-enable-users.md)   
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- **Passaggio 4. Tradurre numeri in un formato alternativo**   (questo articolo)

Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto](direct-routing-configure.md).

A volte gli amministratori del tenant potrebbero voler modificare il numero per le chiamate in uscita e/o in ingresso in base ai modelli creati per garantire l'interoperabilità con i controller dei confini della sessione. Questo articolo descrive come specificare un criterio Regole di traduzione numeri per tradurre i numeri in un formato alternativo. 

È possibile usare il criterio Regole di traduzione numeri per tradurre i numeri per gli elementi seguenti:

- Chiamate in ingresso: chiamate da un endpoint PSTN (chiamante) a un client di Teams (chiamato)
- Chiamate in uscita: chiamate da un client di Teams (chiamante) a un endpoint PSTN (chiamato)

Il criterio viene applicato a livello di SBC. È possibile assegnare più regole di traduzione a un server SBC, che vengono applicate nell'ordine in cui vengono visualizzate quando vengono elencate in PowerShell. È anche possibile modificare l'ordine delle regole nei criteri.

Per creare, modificare, visualizzare ed eliminare le regole di modifica del numero, utilizza i cmdlet [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) e [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) .

Per assegnare, configurare ed elencare le regole di modifica dei numeri negli SBC, usa i cmdlet [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) e [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) insieme ai parametri InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules e OutboundPSTNNumberTranslationRules.

> [!NOTE]
> Il numero totale massimo di regole di traduzione è 400, la lunghezza massima del nome del parametro di traduzione è di 100 simboli, la lunghezza massima dei criteri del parametro di traduzione è di 1024 simboli e la lunghezza massima di traduzione dei parametri di traduzione è di 256 simboli.


## <a name="example-sbc-configuration"></a>Esempio di configurazione SBC

Per questo scenario, viene eseguito il cmdlet New-CsOnlinePSTNGateway per creare la configurazione SBC seguente:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Le regole di traduzione assegnate a SBC sono riepilogate nella tabella seguente:

|Nome  |Modello |Conversione  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^\+1(\d{10})$          | $1         |

Negli esempi seguenti sono presenti due utenti, Alice e Bob. Alice è un utente di Teams il cui numero è +1 206 555 0100. Davide è un utente PSTN il cui numero è +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Esempio 1: Chiamata in entrata a un numero di dieci cifre

Davide chiama Alice utilizzando un numero di dieci cifre diverso da E.164. Bob compone 2065550100 per raggiungere Alice.
SBC usa 2065550100 nelle intestazioni RequestURI e To e 4255550100 nell'intestazione Da.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|Requesturi  |INVITA sip:2065550100@sbc.contoso.com|INVITA sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|A    |A: \<sip:2065550100@sbc.contoso.com>|A: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|DA   |DA: \<sip:4255550100@sbc.contoso.com>|DA: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Esempio 2: Chiamata in entrata a un numero di quattro cifre

Davide chiama Alice usando un numero di quattro cifre. Bob compone 0100 per raggiungere Alice.
SBC usa 0100 nelle intestazioni RequestURI e To e 4255550100 nell'intestazione Da.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|Requesturi  |INVITA sip:0100@sbc.contoso.com          |INVITA sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|A    |A: \<sip:0100@sbc.contoso.com>|A: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|DA   |DA: \<sip:4255550100@sbc.contoso.com>|DA: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Esempio 3: Chiamata in uscita con un numero diverso da E.164 di dieci cifre

Alice chiama Bob usando un numero di dieci cifre. Alice compone 425 555 0100 per raggiungere Bob.
SBC è configurato per l'uso di numeri a dieci cifre non E.164 sia per gli utenti di Teams che per gli utenti PSTN.

In questo scenario, un piano di chiamata traduce il numero prima di inviarlo all'interfaccia routing diretto. Quando Alice immette 425 555 0100 nel client Teams, il numero viene convertito in +14255550100 dal piano di chiamata nazionale. I numeri risultanti sono una normalizzazione cumulativa delle regole del dial plan e delle regole di traduzione di Teams. Le regole di traduzione di Teams eliminano il "+1" aggiunto dal piano di chiamata.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|Requesturi  |INVITA sip:+14255550100@sbc.contoso.com          |INVITA sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|A    |A: \<sip:+14255550100@sbc.contoso.com>|A: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|DA   |DA: \<sip:+12065550100@sbc.contoso.com>|DA: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Esempio 4: Chiamata in uscita con un numero non E.164 a quattro cifre

Alice chiama Bob usando un numero di quattro cifre. Alice usa 0100 per raggiungere Bob dalle chiamate o usando un contatto.
SBC è configurato per utilizzare numeri a quattro cifre non E.164 per gli utenti di Teams e numeri di dieci cifre per gli utenti PSTN. Il piano di chiamata non viene applicato in questo scenario.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|Requesturi  |INVITA sip:0100@sbc.contoso.com           |INVITA sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|A    |A: \<sip:0100@sbc.contoso.com>|A: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|DA   |DA: \<sip:+12065550100@sbc.contoso.com>|DA: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
