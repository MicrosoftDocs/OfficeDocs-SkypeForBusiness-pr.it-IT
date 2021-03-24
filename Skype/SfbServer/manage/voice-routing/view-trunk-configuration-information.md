---
title: Visualizzare le informazioni sulla configurazione trunk in Skype for Business Server
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
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102992"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Visualizzare le informazioni sulla configurazione trunk in Skype for Business Server

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi.

- Se abilitare il bypass multimediale nei trunk.
- Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).
- Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).

**Per visualizzare le informazioni di configurazione dei trunk SIP tramite il Pannello di controllo di Skype for Business Server**

1. Nel Pannello di controllo di Skype for Business Server fare clic su **Routing vocale** e quindi su **Configurazione trunk.**
2. Nella scheda **Configurazione trunk** verrà visualizzato un elenco di tutte le raccolte di impostazioni di configurazione trunk. per ogni raccolta verranno visualizzati i valori per le proprietà  **Name,** **Scope,** **State** e Media **bypass,** insieme al numero di utilizzi **PSTN,** **alle** regole dei numeri chiamanti e alle regole numeri chiamate associate alla raccolta. Per visualizzare ulteriori dettagli su una raccolta di impostazioni di configurazione trunk, fare clic sulla raccolta di interesse, su **Modifica** e quindi **su Mostra dettagli.** Si noti che è possibile visualizzare informazioni dettagliate solo per una raccolta di impostazioni di configurazione trunk alla volta.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione dei trunk SIP tramite Windows PowerShell cmdlet

Le impostazioni di configurazione dei trunk SIP possono essere visualizzate tramite PowerShell di Skype for Business Server e il cmdlet Get-CsTrunkConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog di Lync Server Windows PowerShell "Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell" all'indirizzo https://go.microsoft.com/fwlink/p/?linkId=255876 . SOSTITUIRE O RIMUOVERE QUESTO COLLEGAMENTO.


**Per visualizzare le informazioni di configurazione dei trunk SIP**

Per visualizzare informazioni su tutte le impostazioni di configurazione dei trunk SIP, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:

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
Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsTrunkConfiguration.](/powershell/module/skype/Get-CsTrunkConfiguration)