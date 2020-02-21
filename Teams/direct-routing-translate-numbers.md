---
title: Tradurre i numeri di telefono per il routing diretto
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
description: Informazioni su come configurare il routing diretto di Microsoft Phone System.
ms.openlocfilehash: 2b675948153589c73fa545a95ac785b716b55265
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157983"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Tradurre i numeri di telefono in un formato alternativo

Questo articolo descrive come tradurre i numeri per le chiamate in uscita e in ingresso in un formato alternativo.  Questo è il passaggio 4 dei passaggi seguenti per la configurazione del routing diretto:

- Passaggio 1. [Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md) 
- Passaggio 2. [Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica](direct-routing-enable-users.md)   
- Passaggio 3. [Configurare il routing vocale](direct-routing-voice-routing.md)
- **Passaggio 4. Tradurre i numeri in un formato alternativo** (questo articolo)

Per informazioni su tutti i passaggi necessari per la configurazione del routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).

Talvolta gli amministratori del tenant possono decidere di modificare il numero per le chiamate in uscita e/o in entrata in base agli schemi creati per garantire l'interoperabilità con i controller di bordo di sessione (SBCs). In questo articolo viene descritto come specificare un criterio per la traduzione dei numeri in un formato alternativo. 

È possibile usare i criteri di regole per la traduzione dei numeri per tradurre il numero per i seguenti:

- Chiamate in ingresso: chiamate da un endpoint PSTN (chiamante) a un client di Teams (chiamato)
- Chiamate in uscita: chiamate da un client di Teams (chiamante) a un endpoint PSTN (chiamato)

Il criterio viene applicato a livello SBC. È possibile assegnare più regole di traduzione a un SBC, che vengono applicate nell'ordine in cui vengono visualizzate durante l'elenco in PowerShell. È anche possibile modificare l'ordine delle regole nel criterio.

Per creare, modificare, visualizzare ed eliminare le regole di manipolazione dei numeri, usare i cmdlet [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)e [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Per assegnare, configurare e modificare le regole di manipolazione dei numeri in SBCs, usare i cmdlet [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) e [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) insieme a InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRulesList, InboundPSTNNumberTranslationRulesList, OutboundTeamsNumberTranslationRulesList e OutboundPSTNNumberTranslationRulesList parametri.


## <a name="example-sbc-configuration"></a>Configurazione SBC di esempio

Per questo scenario, il ```New-CsOnlinePSTNGateway``` cmdlet viene eseguito per creare la configurazione SBC seguente:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

Nella tabella seguente vengono riepilogate le regole di traduzione assegnate a SBC:

|Nome  |Modello |Conversione  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+ 1 $1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

Negli esempi seguenti sono disponibili due utenti, Alice e Roberto. Alice è un utente di teams il cui numero è + 1 206 555 0100. Roberto è un utente PSTN il cui numero è + 1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Esempio 1: chiamata in ingresso a un numero a dieci cifre

Roberto chiama Alice usando un numero di dieci cifre diverso da E. 164. Bob compone 2065550100 per raggiungere Alice.
SBC USA 2065550100 in RequestURI e in Headers e 4255550100 nell'intestazione from.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:2065550100@sbc.contoso.com|INVITARE sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|A    |A: \<SIP:2065550100@sbc.contoso.com>|A: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|Da   |DA: \<SIP:4255550100@sbc.contoso.com>|DA: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Esempio 2: chiamata in ingresso a un numero a quattro cifre

Roberto chiama Alice usando un numero a quattro cifre. Bob compone 0100 per raggiungere Alice.
SBC USA 0100 in RequestURI e in Headers e 4255550100 nell'intestazione from.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:0100@sbc.contoso.com          |INVITARE sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|A    |A: \<SIP:0100@sbc.contoso.com>|A: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|Da   |DA: \<SIP:4255550100@sbc.contoso.com>|DA: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Esempio 3: chiamata in uscita con un numero non E. 164 a dieci cifre

Alice chiama Roberto usando un numero a dieci cifre. Alice compone 425 555 0100 per raggiungere Bob.
SBC è configurato per l'uso di numeri di dieci cifre diversi da E. 164 sia per i team che per gli utenti PSTN.

In questo scenario, un dial plan converte il numero prima di inviarlo all'interfaccia Direct routing. Quando Alice immette 425 555 0100 nel client teams, il numero viene convertito in + 14255550100 tramite il dial plan paese. I numeri risultanti sono una normalizzazione cumulativa delle regole del dial plan e della traduzione di teams. Le regole di traduzione di teams eliminano il "+ 1" aggiunto dal dial plan.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:+14255550100@sbc.contoso.com          |INVITARE sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|A    |A: \<SIP:+14255550100@sbc.contoso.com>|A: \<SIP:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|Da   |DA: \<SIP:+12065550100@sbc.contoso.com>|DA: \<SIP:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Esempio 4: chiamata in uscita con un numero non E. 164 a quattro cifre

Alice chiama Roberto usando un numero a quattro cifre. Alice USA 0100 per raggiungere Roberto da chiamate o tramite un contatto.
SBC è configurato per l'uso di numeri a quattro cifre non E. 164 per gli utenti di team e per i numeri a dieci cifre per gli utenti PSTN. Il dial plan non viene applicato in questo scenario.


|Intestazione  |Originale |Intestazione tradotta |Parametro e regola applicati  |
|---------|---------|---------|---------|
|RequestURI  |INVITARE sip:0100@sbc.contoso.com           |INVITARE sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|A    |A: \<SIP:0100@sbc.contoso.com>|A: \<SIP:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|Da   |DA: \<SIP:+12065550100@sbc.contoso.com>|DA: \<SIP:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
