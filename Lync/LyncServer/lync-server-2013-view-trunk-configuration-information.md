---
title: 'Lync Server 2013: visualizzare le informazioni di configurazione del trunk'
description: 'Lync Server 2013: visualizzare le informazioni di configurazione del trunk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b4e1d3063d65f8c27ad231f063249748046f759
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565432"
---
# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="9da6c-103">Visualizzare le informazioni di configurazione del trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9da6c-103">View trunk configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9da6c-104">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9da6c-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9da6c-p101">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9da6c-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="9da6c-107">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="9da6c-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="9da6c-108">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="9da6c-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="9da6c-109">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="9da6c-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="9da6c-110">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="9da6c-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="9da6c-111">Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="9da6c-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="9da6c-112">Per visualizzare le informazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="9da6c-112">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9da6c-113">Nel pannello di controllo di Lync Server, fare clic su **routing vocale** e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="9da6c-113">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="9da6c-114">Nella scheda **configurazione trunk** verrà visualizzato un elenco di tutte le raccolte di impostazioni di configurazione trunk; per ogni raccolta verranno visualizzati i valori per le proprietà **Name**, **scope**, **state**e **media bypass** , oltre al numero di **utilizzi PSTN**, **alle regole dei numeri di chiamata**e alle **regole dei numeri denominate** associate all'insieme.</span><span class="sxs-lookup"><span data-stu-id="9da6c-114">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="9da6c-115">Per visualizzare ulteriori dettagli su una raccolta di impostazioni di configurazione del trunk, fare clic sulla raccolta di interesse, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9da6c-115">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="9da6c-116">Si noti che è possibile visualizzare informazioni dettagliate solo per una raccolta di impostazioni di configurazione del trunk alla volta.</span><span class="sxs-lookup"><span data-stu-id="9da6c-116">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9da6c-117">Visualizzazione delle informazioni di configurazione del trunk SIP tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9da6c-117">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9da6c-118">È possibile visualizzare le impostazioni di configurazione del trunk SIP utilizzando Lync Server PowerShell e il cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9da6c-118">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="9da6c-119">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9da6c-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="9da6c-120">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="9da6c-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="9da6c-121">Per visualizzare le informazioni di configurazione del trunk SIP</span><span class="sxs-lookup"><span data-stu-id="9da6c-121">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="9da6c-122">Per visualizzare informazioni su tutte le impostazioni di configurazione del trunk SIP, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9da6c-122">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="9da6c-123">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="9da6c-123">That will return information similar to this:</span></span>
    
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

</div>

<span data-ttu-id="9da6c-124">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9da6c-124">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

