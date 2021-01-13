---
title: Visualizzare le informazioni di configurazione del trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi.
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826166"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Visualizzare le informazioni di configurazione del trunk in Skype for Business Server

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi.

- Se abilitare il bypass multimediale nei trunk.
- Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).
- Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).

**Per visualizzare le informazioni di configurazione del trunk SIP tramite il pannello di controllo di Skype for Business Server**

1. Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale** e quindi su **configurazione trunk**.
2. Nella scheda **configurazione trunk** verrà visualizzato un elenco di tutte le raccolte di impostazioni di configurazione trunk. per ogni raccolta verranno visualizzati i valori per le proprietà **Name**, **scope**, **state** e **media bypass** , oltre al numero di **utilizzi PSTN**, **alle regole dei numeri di chiamata** e alle **regole dei numeri denominate** associate all'insieme. Per visualizzare ulteriori dettagli su una raccolta di impostazioni di configurazione del trunk, fare clic sulla raccolta di interesse, fare clic su **modifica** e quindi su **Mostra dettagli**. Si noti che è possibile visualizzare informazioni dettagliate solo per una raccolta di impostazioni di configurazione del trunk alla volta.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione del trunk SIP tramite i cmdlet di Windows PowerShell

Le impostazioni di configurazione del trunk SIP possono essere visualizzate utilizzando Skype for Business Server PowerShell e il cmdlet Get-CsTrunkConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876 . SOSTITUISCI O RIMUOVI QUESTO COLLEGAMENTO.


**Per visualizzare le informazioni di configurazione del trunk SIP**

Per visualizzare informazioni su tutte le impostazioni di configurazione del trunk SIP, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:

```powershell
Get-CsTrunkConfiguration
```

Verranno restituite informazioni simili alle seguenti:

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
Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .



