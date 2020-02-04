---
title: "Lync Server 2013: creare collegamenti all'area di rete"
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
ms.openlocfilehash: f40b9d569cbc571fe931a53b6f399b6273efd055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="3f37f-102">Creare collegamenti all'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f37f-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f37f-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3f37f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3f37f-104">Le aree all'interno di una rete sono collegate tramite connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="3f37f-104">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="3f37f-105">Un *collegamento all'area di rete* crea un collegamento tra due aree geografiche configurate per il controllo di ammissione alle chiamate (CAC) e imposta le limitazioni della larghezza di banda per il traffico audio e video tra queste aree.</span><span class="sxs-lookup"><span data-stu-id="3f37f-105">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="3f37f-106">Per informazioni dettagliate sull'uso dei collegamenti all'area di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f37f-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="3f37f-107">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3f37f-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="3f37f-108">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3f37f-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="3f37f-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3f37f-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="3f37f-110">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="3f37f-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="3f37f-111">La topologia di esempio include un collegamento tra le aree Nord America e APAC e un collegamento tra le aree EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="3f37f-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="3f37f-112">Ognuno di questi collegamenti di area geografica è vincolato dalla larghezza di banda WAN, come descritto nella tabella informazioni sulla larghezza di banda del collegamento di area nell' [esempio: raccogliere i requisiti per il controllo di ammissione delle chiamate nella sezione Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) della documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3f37f-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="3f37f-113">Per creare collegamenti all'area geografica di rete tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="3f37f-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="3f37f-114">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3f37f-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3f37f-115">Eseguire il cmdlet New-CsNetworkRegionLink per creare i collegamenti all'area geografica e applicare i profili dei criteri di larghezza di banda appropriati.</span><span class="sxs-lookup"><span data-stu-id="3f37f-115">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="3f37f-116">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3f37f-116">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="3f37f-117">Per creare collegamenti all'area geografica di rete tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3f37f-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3f37f-118">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f37f-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3f37f-119">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3f37f-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="3f37f-120">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="3f37f-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="3f37f-121">Fare clic sul pulsante di spostamento **collegamento area geografica** .</span><span class="sxs-lookup"><span data-stu-id="3f37f-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="3f37f-122">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3f37f-122">Click **New**.</span></span>

5.  <span data-ttu-id="3f37f-123">Nella pagina **New Region link** fare clic su **nome** e quindi digitare un nome per il collegamento all'area di rete.</span><span class="sxs-lookup"><span data-stu-id="3f37f-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="3f37f-124">Fare clic su **area \#di rete 1**e quindi sull'area di rete nell'elenco che si vuole collegare all'area \#di rete 2.</span><span class="sxs-lookup"><span data-stu-id="3f37f-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="3f37f-125">Fare clic su **area geografica \#di rete 2**e quindi fare clic su un'area di rete nell'elenco che si \#vuole collegare all'area geografica di rete 1.</span><span class="sxs-lookup"><span data-stu-id="3f37f-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="3f37f-126">Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi selezionare il profilo dei criteri di larghezza di banda che si vuole applicare al collegamento all'area di rete.</span><span class="sxs-lookup"><span data-stu-id="3f37f-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="3f37f-127">Applicare un criterio di larghezza di banda solo se il collegamento all'area di rete è vincolato dalla larghezza di banda e si vuole usare CAC per controllare il traffico multimediale sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="3f37f-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="3f37f-128">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3f37f-128">Click **Commit**.</span></span>

10. <span data-ttu-id="3f37f-129">Per completare la creazione di collegamenti di area di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="3f37f-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
