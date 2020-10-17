---
title: 'Lync Server 2013: visualizzazione delle informazioni sulle aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7222afb226a211609423cb3c5ad1e40383de67e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535723"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="0f802-102">Visualizzazione delle informazioni sulle aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f802-102">Viewing network region information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f802-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0f802-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0f802-104">Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="0f802-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="0f802-105">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="0f802-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="0f802-106">Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0f802-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="0f802-107">È possibile utilizzare il pannello di controllo di Lync Server per visualizzare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="0f802-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="0f802-108">Per le aree di rete sono disponibili impostazioni che determinano se sono consentiti percorsi alternativi attraverso Internet per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="0f802-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="0f802-109">Le informazioni in questo argomento descrivono come visualizzare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="0f802-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="0f802-110">Per informazioni dettagliate sulla creazione o la modifica delle aree di rete esistenti, vedere [creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="0f802-111">Per visualizzare informazioni su un'area di rete con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="0f802-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0f802-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0f802-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0f802-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f802-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0f802-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0f802-115">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area**.</span><span class="sxs-lookup"><span data-stu-id="0f802-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="0f802-116">Nella pagina **Area** fare clic sull'area che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0f802-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f802-117">È possibile visualizzare una sola area alla volta.</span><span class="sxs-lookup"><span data-stu-id="0f802-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="0f802-118">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0f802-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0f802-119">Visualizzazione delle informazioni sulle aree di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f802-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0f802-120">È possibile visualizzare le informazioni sulle aree di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="0f802-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="0f802-121">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f802-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0f802-122">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="0f802-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="0f802-123">Per visualizzare le informazioni sulle aree di rete</span><span class="sxs-lookup"><span data-stu-id="0f802-123">To view network region information</span></span>

  - <span data-ttu-id="0f802-124">Per visualizzare informazioni su tutte le aree di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="0f802-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="0f802-125">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f802-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="0f802-126">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="0f802-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f802-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f802-127">See Also</span></span>


[<span data-ttu-id="0f802-128">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f802-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="0f802-129">Eliminazione di aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f802-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

