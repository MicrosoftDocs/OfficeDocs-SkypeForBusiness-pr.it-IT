---
title: 'Lync Server 2013: configurare i siti di rete per il servizio di controllo di ammissione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f449d26515c6790ec8582676ca57ed897f12dc40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="58498-102">Configurazione dei siti di rete per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58498-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58498-103">_**Ultimo argomento modificato:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="58498-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="58498-104">Se sono stati già creati siti di rete per il servizio per chiamate di emergenza (E9-1-1) o per il bypass multimediale, è possibile modificare i siti di rete esistenti per applicare un profilo di criteri di larghezza di banda utilizzando il cmdlet <STRONG>Set-CsNetworkSite</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="58498-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="58498-105">Per un esempio di come modificare un sito di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="58498-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="58498-p102">I *siti di rete* sono gli uffici o le postazioni in ogni area di rete delle distribuzioni del servizio Controllo di ammissione di chiamata (CAC), del servizio per chiamate di emergenza E9-1-1 e del bypass multimediale. Utilizzare le procedure seguenti per creare siti di rete da allineare ai siti di rete nella topologia di rete di esempio per il servizio Controllo di ammissione di chiamata. In queste procedure viene illustrato come creare e configurare siti di rete vincolati dalla larghezza di banda WAN che quindi richiedono criteri di larghezza di banda per limitare il flusso di traffico audio o video in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="58498-p102">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments. Use the following procedures to create network sites that align to network sites in the example network topology for CAC. These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="58498-109">Nella distribuzione di esempio del servizio Controllo di ammissione di chiamata, il Nord America ha sei siti.</span><span class="sxs-lookup"><span data-stu-id="58498-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="58498-110">Tre di questi siti sono vincolati dalla larghezza di banda WAN: Reno, Portland e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="58498-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="58498-111">Gli altri tre siti, *non* vincolati dalla larghezza di banda WAN, sono: New York, Chicago e Detroit.</span><span class="sxs-lookup"><span data-stu-id="58498-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="58498-112">Per un esempio di come creare o modificare gli altri siti di rete, vedere [creare o modificare un sito di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="58498-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="58498-113">Per visualizzare la topologia di rete di esempio, vedere [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="58498-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="58498-114">Nella procedura seguente, Lync Server Management Shell viene utilizzato per creare un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="58498-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="58498-115">Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server per creare un sito di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="58498-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="58498-116">Per creare siti di rete per il servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="58498-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="58498-117">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="58498-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="58498-118">Eseguire il cmdlet **New-CsNetworkSite** per creare i siti di rete e applicare un profilo di criteri di larghezza di banda appropriato a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="58498-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="58498-119">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="58498-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="58498-120">Per completare la creazione dei siti di rete per l'intera topologia di esempio, ripetere il passaggio 2 per i siti di rete vincolati dalla larghezza di banda nelle aree EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="58498-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

