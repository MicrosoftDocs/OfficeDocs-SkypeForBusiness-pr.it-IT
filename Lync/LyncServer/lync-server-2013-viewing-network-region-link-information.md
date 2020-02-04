---
title: "Lync Server 2013: visualizzazione delle informazioni sul collegamento all'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="df3f8-102">Visualizzazione delle informazioni sul collegamento all'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df3f8-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df3f8-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="df3f8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="df3f8-104">È possibile visualizzare i collegamenti tra due aree di rete come parte del controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="df3f8-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="df3f8-105">Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network).</span><span class="sxs-lookup"><span data-stu-id="df3f8-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="df3f8-106">È possibile usare il pannello di controllo di Lync Server per visualizzare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="df3f8-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="df3f8-107">Per informazioni dettagliate su come creare o modificare il collegamento all'area di rete, vedere [configurazione dei collegamenti all'area di rete in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="df3f8-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="df3f8-108">Per visualizzare un collegamento all'area di rete nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="df3f8-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="df3f8-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="df3f8-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df3f8-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df3f8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="df3f8-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df3f8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="df3f8-112">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="df3f8-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="df3f8-113">Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="df3f8-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df3f8-114">Puoi visualizzare solo le informazioni su un collegamento all'area geografica alla volta.</span><span class="sxs-lookup"><span data-stu-id="df3f8-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="df3f8-115">Nel menu **modifica** selezionare **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="df3f8-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df3f8-116">Visualizzazione delle informazioni sul collegamento all'area di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df3f8-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="df3f8-117">È possibile visualizzare i collegamenti all'area di rete usando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="df3f8-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="df3f8-118">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df3f8-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="df3f8-119">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="df3f8-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="df3f8-120">Per visualizzare le informazioni sul collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="df3f8-120">To view network region link information</span></span>

  - <span data-ttu-id="df3f8-121">Per visualizzare informazioni su tutti i collegamenti dell'area di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="df3f8-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="df3f8-122">Questo comando restituisce informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="df3f8-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="df3f8-123">Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="df3f8-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df3f8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df3f8-124">See Also</span></span>


[<span data-ttu-id="df3f8-125">Configurazione di collegamenti ai siti di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df3f8-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

