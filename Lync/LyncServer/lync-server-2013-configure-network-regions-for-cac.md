---
title: 'Lync Server 2013: configurare le aree di rete per CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="b4a08-102">Configurare le aree di rete per CAC in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a08-102">Configure network regions for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a08-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b4a08-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b4a08-104">Se sono già state create aree di rete per il E9-1-1 o il bypass multimediale, è possibile modificare le aree di rete esistenti aggiungendo le impostazioni specifiche del controllo di ammissione di chiamata tramite il cmdlet <STRONG>Set-CsNetworkRegion</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b4a08-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="b4a08-105">Per un esempio di come modificare un'area geografica di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a08-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b4a08-106">Le *aree di rete* sono gli hub di rete o le backbone usate per la configurazione di CAC, E9-1-1 e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="b4a08-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="b4a08-107">Usare la procedura seguente per creare aree di rete che si allineano alle aree di rete nella topologia di rete di esempio per CAC.</span><span class="sxs-lookup"><span data-stu-id="b4a08-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="b4a08-108">Per visualizzare la topologia di rete di esempio, vedere [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b4a08-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="b4a08-109">La topologia di rete di esempio per CAC include tre aree geografiche: Nord America, EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="b4a08-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="b4a08-110">Ogni area geografica ha un sito centrale specificato.</span><span class="sxs-lookup"><span data-stu-id="b4a08-110">Each region has a specified central site.</span></span> <span data-ttu-id="b4a08-111">Per l'area Nord America, il sito centrale designato è denominato CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="b4a08-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="b4a08-112">La procedura seguente mostra un esempio di come usare il cmdlet **New-CsNetworkRegion** per creare l'area Nord America.</span><span class="sxs-lookup"><span data-stu-id="b4a08-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4a08-113">Nella procedura seguente viene usato Lync Server Management Shell per creare un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="b4a08-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="b4a08-114">Per informazioni dettagliate sull'uso del pannello di controllo di Lync Server per creare un'area di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4a08-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="b4a08-115">Per creare un'area di rete per il controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="b4a08-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="b4a08-116">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b4a08-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b4a08-117">Per ogni area geografica che è necessario creare, eseguire il cmdlet **New-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="b4a08-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="b4a08-118">Ad esempio, per creare l'area Nord America, eseguire:</span><span class="sxs-lookup"><span data-stu-id="b4a08-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="b4a08-119">Ripetere il passaggio 2 per creare le aree di rete, EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="b4a08-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

