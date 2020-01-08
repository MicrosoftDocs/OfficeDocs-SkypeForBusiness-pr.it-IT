---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc42c645548ea9bad072da5f18643271a9eceeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="9a71e-102">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="9a71e-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a71e-103">_**Argomento Ultima modifica:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="9a71e-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="9a71e-104">Dopo la distribuzione di Lync Server 2013, è necessario configurare una route federativo per il sito.</span><span class="sxs-lookup"><span data-stu-id="9a71e-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="9a71e-105">Per usare la route federata usata da Lync Server 2010, è necessario configurare Lync Server 2013 per usare questa route.</span><span class="sxs-lookup"><span data-stu-id="9a71e-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="9a71e-106">Per consentire al sito di Lync Server 2013 di usare il Director e il server perimetrale della distribuzione di Lync Server 2010, usare generatore di topologie per associare il pool di Edge legacy.</span><span class="sxs-lookup"><span data-stu-id="9a71e-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="9a71e-107">Per associare il pool di Edge legacy tramite Generatore di topologia</span><span class="sxs-lookup"><span data-stu-id="9a71e-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="9a71e-108">Aprire **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="9a71e-109">Selezionare il sito, che si trova direttamente sotto il nodo **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="9a71e-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="9a71e-110">Nel menu **azioni** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="9a71e-111">Nel riquadro sinistro selezionare **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="9a71e-112">In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare il director di Lync Server 2010 o Lync Server 2010 Edge Server se non è elencato alcun amministratore.</span><span class="sxs-lookup"><span data-stu-id="9a71e-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="9a71e-113">Modificare le proprietà, le proprietà della ![pagina Route federativo](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg ", la pagina della route federativo")</span><span class="sxs-lookup"><span data-stu-id="9a71e-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="9a71e-114">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="9a71e-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="9a71e-115">In Generatore di topologia, nel nodo Lync Server 2013, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="9a71e-116">In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="9a71e-117">Nell'elenco selezionare il server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="9a71e-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="9a71e-118">![Finestra di dialogo Modifica proprietà, selezione]della(images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "finestra di dialogo Modifica proprietà bordo legacy, selezione del bordo legacy")</span><span class="sxs-lookup"><span data-stu-id="9a71e-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="9a71e-119">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="9a71e-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="9a71e-120">In **Generatore di topologie**selezionare il nodo di primo livello, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="9a71e-121">Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="9a71e-122">Al termine della **pubblicazione guidata** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="9a71e-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

