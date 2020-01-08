---
title: "Lync Server 2013: visualizzazione delle informazioni relative all'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52baf7c9dca4d663630bbf0cb17384916f5a953e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="84ec5-102">Visualizzazione delle informazioni relative all'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84ec5-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ec5-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="84ec5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="84ec5-104">Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="84ec5-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="84ec5-105">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="84ec5-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="84ec5-106">Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC).</span><span class="sxs-lookup"><span data-stu-id="84ec5-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="84ec5-107">È possibile usare il pannello di controllo di Lync Server per visualizzare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="84ec5-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="84ec5-108">Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="84ec5-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="84ec5-109">Usare questo argomento per visualizzare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="84ec5-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="84ec5-110">Per informazioni dettagliate sulla creazione o la modifica di aree di rete esistenti, vedere [creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="84ec5-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="84ec5-111">Per visualizzare informazioni su un'area geografica di rete con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="84ec5-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="84ec5-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="84ec5-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="84ec5-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="84ec5-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="84ec5-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="84ec5-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="84ec5-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="84ec5-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="84ec5-116">Nella pagina **area geografica** fare clic sull'area che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="84ec5-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84ec5-117">È possibile visualizzare una sola area alla volta.</span><span class="sxs-lookup"><span data-stu-id="84ec5-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="84ec5-118">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="84ec5-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="84ec5-119">Visualizzazione delle informazioni relative all'area di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="84ec5-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="84ec5-120">Per visualizzare le informazioni relative all'area di rete, è possibile usare Windows PowerShell e il cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="84ec5-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="84ec5-121">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84ec5-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="84ec5-122">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="84ec5-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="84ec5-123">Per visualizzare le informazioni relative all'area di rete</span><span class="sxs-lookup"><span data-stu-id="84ec5-123">To view network region information</span></span>

  - <span data-ttu-id="84ec5-124">Per visualizzare informazioni su tutte le aree geografiche di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="84ec5-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="84ec5-125">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="84ec5-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="84ec5-126">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="84ec5-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84ec5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84ec5-127">See Also</span></span>


[<span data-ttu-id="84ec5-128">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84ec5-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="84ec5-129">Eliminazione delle aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84ec5-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

