---
title: Visualizzare le informazioni di configurazione del trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi.
ms.openlocfilehash: 0ccbf86891d6265298411ad2f90988123529b614
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816905"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Visualizzare le informazioni di configurazione del trunk in Skype for Business Server

Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi.

- Se il bypass multimediale deve essere abilitato nei trunk.
- Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).
- Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.

Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN).

**Per visualizzare le informazioni di configurazione del trunk SIP tramite il pannello di controllo di Skype for Business Server**

1. Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale**e quindi su **configurazione trunk**.
2. Nella scheda **configurazione trunk** verrà visualizzato un elenco di tutte le raccolte di impostazioni di configurazione trunk; per ogni raccolta verranno visualizzati i valori per le proprietà **nome**, **ambito**, **stato**e **bypass multimediale** , insieme al numero di **utilizzi PSTN**, **alle regole**per il numero di chiamate e alle **regole numeriche** associate alla raccolta. Per visualizzare altri dettagli su una raccolta di impostazioni di configurazione trunk, fare clic sulla raccolta di interesse, fare clic su **modifica**e quindi su **Mostra dettagli**. Tieni presente che puoi visualizzare informazioni dettagliate solo per una raccolta di impostazioni di configurazione trunk alla volta.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione del trunk SIP tramite i cmdlet di Windows PowerShell

Le impostazioni di configurazione trunk SIP possono essere visualizzate con Skype for Business Server PowerShell e il cmdlet Get-CsTrunkConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft http://go.microsoft.com/fwlink/p/?linkId=255876Lync Server 2010 con Remote PowerShell" at. SOSTITUISCI O RIMUOVI QUESTO COLLEGAMENTO.


**Per visualizzare le informazioni di configurazione del trunk SIP**

Per visualizzare informazioni su tutte le impostazioni di configurazione del trunk SIP, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:

`Get-CsTrunkConfiguration`

Questo restituirà informazioni simili alla seguente:

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



