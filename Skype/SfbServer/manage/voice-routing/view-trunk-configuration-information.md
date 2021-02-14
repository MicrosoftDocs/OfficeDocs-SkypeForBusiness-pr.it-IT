---
title: Visualizzare le informazioni sulla configurazione dei trunk in Skype for Business Server
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
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="d7fd6-103">Visualizzare le informazioni sulla configurazione dei trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d7fd6-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="d7fd6-104">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="d7fd6-105">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="d7fd6-106">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="d7fd6-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="d7fd6-107">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="d7fd6-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="d7fd6-108">Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione dei trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="d7fd6-109">Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="d7fd6-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="d7fd6-110">**Per visualizzare le informazioni di configurazione dei trunk SIP tramite il Pannello di controllo di Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="d7fd6-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="d7fd6-111">Nel Pannello di controllo di Skype for Business Server fare clic su **Routing vocale** e quindi su **Configurazione trunk.**</span><span class="sxs-lookup"><span data-stu-id="d7fd6-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="d7fd6-112">Nella scheda **Configurazione trunk** verrà visualizzato un elenco di tutte le raccolte di impostazioni di configurazione trunk. per ogni raccolta verranno visualizzati i valori per le proprietà **Name,** **Scope,** **State** e  **Media Bypass,**  insieme al numero di utilizzi **PSTN,** alle regole dei numeri chiamanti e alle regole dei numeri chiamati associate alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="d7fd6-113">Per visualizzare ulteriori dettagli su una raccolta di impostazioni di configurazione trunk, fare clic sulla raccolta di interesse, su **Modifica** e quindi su **Mostra dettagli.**</span><span class="sxs-lookup"><span data-stu-id="d7fd6-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="d7fd6-114">Si noti che è possibile visualizzare informazioni dettagliate solo per una raccolta di impostazioni di configurazione trunk alla volta.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d7fd6-115">Visualizzazione delle informazioni di configurazione dei trunk SIP tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7fd6-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d7fd6-116">Le impostazioni di configurazione dei trunk SIP possono essere visualizzate utilizzando Skype for Business Server PowerShell e il cmdlet Get-CsTrunkConfiguration configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="d7fd6-117">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="d7fd6-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog di Lync Server Windows PowerShell "Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell" all'indirizzo https://go.microsoft.com/fwlink/p/?linkId=255876 .</span><span class="sxs-lookup"><span data-stu-id="d7fd6-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="d7fd6-119">SOSTITUIRE O RIMUOVERE QUESTO COLLEGAMENTO.</span><span class="sxs-lookup"><span data-stu-id="d7fd6-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="d7fd6-120">**Per visualizzare le informazioni di configurazione dei trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="d7fd6-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="d7fd6-121">Per visualizzare informazioni su tutte le impostazioni di configurazione dei trunk SIP, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="d7fd6-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="d7fd6-122">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7fd6-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="d7fd6-123">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="d7fd6-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



