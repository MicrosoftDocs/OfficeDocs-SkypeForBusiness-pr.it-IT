---
title: 'Lync Server 2013: creare collegamenti area di rete'
description: 'Lync Server 2013: creare collegamenti area di rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6510d252ac1534a3a8e9f14d56acc8d0d8b60a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553937"
---
# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="13ff1-103">Creare collegamenti area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ff1-103">Create network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13ff1-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="13ff1-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="13ff1-p101">Le aree all'interno di una rete sono collegate tramite connettività fisica WAN. Un *collegamento di aree di rete* crea un collegamento tra due aree configurate per Controllo di ammissione di chiamata e imposta i limiti di larghezza di banda per il traffico audio e video tra tali aree.</span><span class="sxs-lookup"><span data-stu-id="13ff1-p101">Regions within a network are linked through physical WAN connectivity. A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="13ff1-107">Per informazioni dettagliate sull'utilizzo dei collegamenti tra aree di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="13ff1-107">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="13ff1-108">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="13ff1-108">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="13ff1-109">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="13ff1-109">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="13ff1-110">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="13ff1-110">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="13ff1-111">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="13ff1-111">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="13ff1-112">Nella topologia di esempio è presente un collegamento tra il Nord America e le aree APAC e un collegamento tra le aree EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="13ff1-112">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="13ff1-113">Ognuno di questi collegamenti tra aree geografiche è vincolato dalla larghezza di banda della WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento area nell' [esempio seguente: raccolta dei requisiti per il controllo di ammissione di chiamata nella sezione Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) della documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="13ff1-113">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="13ff1-114">Per creare collegamenti area di rete utilizzando Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="13ff1-114">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="13ff1-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="13ff1-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="13ff1-p103">Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti area di rete e applicare i profili di criteri di larghezza di banda appropriati. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="13ff1-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="13ff1-118">Per creare collegamenti area di rete utilizzando il pannello di controllo Lync Server</span><span class="sxs-lookup"><span data-stu-id="13ff1-118">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="13ff1-119">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13ff1-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13ff1-120">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="13ff1-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="13ff1-121">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="13ff1-121">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="13ff1-122">Fare clic sul pulsante di spostamento **Collegamento area**.</span><span class="sxs-lookup"><span data-stu-id="13ff1-122">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="13ff1-123">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="13ff1-123">Click **New**.</span></span>

5.  <span data-ttu-id="13ff1-124">Nella pagina **Nuovo collegamento area di rete** fare clic su **Nome** e quindi digitare un nome per il collegamento area di rete.</span><span class="sxs-lookup"><span data-stu-id="13ff1-124">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="13ff1-125">Fare clic su **area di rete \# 1**e quindi fare clic sull'area di rete nell'elenco che si desidera collegare all'area di rete \# 2.</span><span class="sxs-lookup"><span data-stu-id="13ff1-125">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="13ff1-126">Fare clic su **area di rete \# 2**e quindi fare clic su un'area di rete nell'elenco che si desidera collegare all'area di rete \# 1.</span><span class="sxs-lookup"><span data-stu-id="13ff1-126">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="13ff1-127">Facoltativamente, fare clic su **Criteri larghezza di banda** e selezionare il profilo di criteri di larghezza di banda che si desidera applicare al collegamento area di rete.</span><span class="sxs-lookup"><span data-stu-id="13ff1-127">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="13ff1-128">Applicare criteri di larghezza di banda solo se il collegamento area di rete è vincolato dalla larghezza di banda e si desidera utilizzare CAC per controllare il traffico multimediale su tale collegamento.</span><span class="sxs-lookup"><span data-stu-id="13ff1-128">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="13ff1-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="13ff1-129">Click **Commit**.</span></span>

10. <span data-ttu-id="13ff1-130">Per completare la creazione dei collegamenti area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="13ff1-130">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
