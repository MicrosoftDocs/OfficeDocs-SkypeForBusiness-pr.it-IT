---
title: "Lync Server 2013: visualizzazione delle informazioni sul collegamento di un'area di rete"
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
ms.openlocfilehash: 7046f4f405bc3ece0170c4d598369828b47aa910
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="63050-102">Visualizzazione delle informazioni sul collegamento area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63050-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63050-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="63050-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="63050-104">È possibile visualizzare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="63050-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="63050-105">Le aree di una rete sono collegate mediante una connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="63050-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="63050-106">È possibile utilizzare il pannello di controllo di Lync Server per visualizzare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="63050-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="63050-107">Per informazioni dettagliate sulla creazione o la modifica di un collegamento area di rete, vedere [Configuring Network Region Links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="63050-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="63050-108">Per visualizzare un collegamento area di rete nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="63050-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="63050-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="63050-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="63050-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63050-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63050-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="63050-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63050-112">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Collegamento area**.</span><span class="sxs-lookup"><span data-stu-id="63050-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="63050-113">Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="63050-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63050-114">È possibile visualizzare informazioni su un collegamento aree alla volta.</span><span class="sxs-lookup"><span data-stu-id="63050-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="63050-115">Scegliere **Elimina** dal menu **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="63050-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="63050-116">Visualizzazione delle informazioni sul collegamento area di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="63050-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="63050-117">È possibile visualizzare i collegamenti area di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="63050-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="63050-118">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63050-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="63050-119">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="63050-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="63050-120">Per visualizzare informazioni su un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="63050-120">To view network region link information</span></span>

  - <span data-ttu-id="63050-121">Per visualizzare informazioni su tutti i collegamenti dell'area di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="63050-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="63050-122">Il comando restituisce informazioni simili a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="63050-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="63050-123">Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="63050-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63050-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63050-124">See Also</span></span>


[<span data-ttu-id="63050-125">Configurazione di collegamenti di sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63050-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

