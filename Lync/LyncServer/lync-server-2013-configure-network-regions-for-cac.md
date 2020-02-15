---
title: 'Lync Server 2013: configurare le aree di rete per il servizio di controllo di ammissione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acafaca86af1943d2614349ff42f04fa87faddaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="b1354-102">Configurare le aree di rete per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1354-102">Configure network regions for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1354-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b1354-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b1354-104">Se sono state già create aree di rete per il servizio di emergenza (E9-1-1) o per il bypass multimediale, è possibile modificare le aree di rete esistenti aggiungendo impostazioni specifiche del servizio Controllo di ammissione di chiamata utilizzando il cmdlet <STRONG>Set-CsNetworkRegion</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b1354-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="b1354-105">Per un esempio di come modificare un'area di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b1354-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b1354-106">Le *aree di rete* sono hub o backbone di rete che si utilizzano nella configurazione del servizio Controllo di ammissione di chiamata, nel servizio di emergenza (E9-1-1) e nel bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="b1354-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="b1354-107">Eseguire la procedura seguente per creare aree di rete allineate a quelle dell'esempio di topologia di rete per il servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b1354-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="b1354-108">Per visualizzare la topologia di rete di esempio, vedere [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b1354-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="b1354-109">L'esempio di topologia di rete per il servizio Controllo di ammissione di chiamata include tre aree: Nord America, EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="b1354-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="b1354-110">Per ogni area è specificato un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="b1354-110">Each region has a specified central site.</span></span> <span data-ttu-id="b1354-111">Per il Nord America, il sito centrale designato è denominato CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="b1354-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="b1354-112">Nella procedura seguente è illustrato un esempio di come utilizzare il cmdlet **New-CsNetworkRegion** per creare l'area del Nord America.</span><span class="sxs-lookup"><span data-stu-id="b1354-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1354-113">Nella procedura seguente, Lync Server Management Shell viene utilizzato per creare un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="b1354-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="b1354-114">Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server per creare un'area di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b1354-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="b1354-115">Per creare un'area di reste per il servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="b1354-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="b1354-116">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b1354-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b1354-117">Eseguire il cmdlet **New-CsNetworkRegion** per ogni area che è necessario creare.</span><span class="sxs-lookup"><span data-stu-id="b1354-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="b1354-118">Ad esempio, per creare l'area del Nord America, eseguire:</span><span class="sxs-lookup"><span data-stu-id="b1354-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="b1354-119">Ripetere il passaggio 2 per creare le aree di rete di EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="b1354-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

