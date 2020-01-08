---
title: 'Lync Server 2013: visualizzare le informazioni di configurazione del trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf496382ed33b95e8de9f387a8623fb0984ed28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="b6e0c-102">Visualizzare le informazioni di configurazione del trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e0c-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6e0c-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b6e0c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b6e0c-104">Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="b6e0c-105">Queste impostazioni eseguono operazioni come specifica:</span><span class="sxs-lookup"><span data-stu-id="b6e0c-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="b6e0c-106">Se il bypass multimediale deve essere abilitato nei trunk.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="b6e0c-107">Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="b6e0c-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="b6e0c-108">Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b6e0c-109">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b6e0c-110">Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="b6e0c-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="b6e0c-111">Per visualizzare le informazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b6e0c-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b6e0c-112">Nel pannello di controllo di Lync Server fare clic su **routing vocale** e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="b6e0c-113">Nella scheda **configurazione trunk** verrà visualizzato un elenco di tutte le raccolte di impostazioni di configurazione trunk; per ogni raccolta verranno visualizzati i valori per le proprietà **nome**, **ambito**, **stato**e **bypass multimediale** , insieme al numero di **utilizzi PSTN**, **alle regole**per il numero di chiamate e alle **regole numeriche** associate alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="b6e0c-114">Per visualizzare altri dettagli su una raccolta di impostazioni di configurazione trunk, fare clic sulla raccolta di interesse, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="b6e0c-115">Tieni presente che puoi visualizzare informazioni dettagliate solo per una raccolta di impostazioni di configurazione trunk alla volta.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b6e0c-116">Visualizzazione delle informazioni di configurazione del trunk SIP tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6e0c-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b6e0c-117">Le impostazioni di configurazione trunk SIP possono essere visualizzate tramite Lync Server PowerShell e il cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="b6e0c-118">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="b6e0c-119">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="b6e0c-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="b6e0c-120">Per visualizzare le informazioni di configurazione del trunk SIP</span><span class="sxs-lookup"><span data-stu-id="b6e0c-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="b6e0c-121">Per visualizzare informazioni su tutte le impostazioni di configurazione del trunk SIP, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="b6e0c-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="b6e0c-122">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b6e0c-122">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="b6e0c-123">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="b6e0c-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

