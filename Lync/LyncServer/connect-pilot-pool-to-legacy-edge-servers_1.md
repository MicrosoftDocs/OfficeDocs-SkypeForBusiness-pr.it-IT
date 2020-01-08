---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="fedf7-102">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="fedf7-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fedf7-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fedf7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fedf7-104">Dopo la distribuzione di Lync Server 2013, una route federativa per il sito non è configurata.</span><span class="sxs-lookup"><span data-stu-id="fedf7-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="fedf7-105">Per usare la route federata usata da Office Communications Server 2007 R2, è necessario configurare Lync Server 2013 per l'uso della route.</span><span class="sxs-lookup"><span data-stu-id="fedf7-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="fedf7-106">Per consentire al sito di Lync Server 2013 di usare il Director e il server perimetrale di BackCompatSite, usare generatore di topologie per associare il pool di Edge legacy.</span><span class="sxs-lookup"><span data-stu-id="fedf7-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="fedf7-107">Per associare il pool di Edge legacy tramite Generatore di topologia</span><span class="sxs-lookup"><span data-stu-id="fedf7-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="fedf7-108">Aprire la topologia del pool di piloti in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="fedf7-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="fedf7-109">Selezionare il sito di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fedf7-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="fedf7-110">Nel menu **azione** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fedf7-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="fedf7-111">In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare Office Communications Server 2007 R2 Director o Office Communications Server 2007 R2 Edge Server se non è elencato alcun amministratore.</span><span class="sxs-lookup"><span data-stu-id="fedf7-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="fedf7-112">Finestra ![di dialogo Modifica proprietà, pagina Route federativo pagina](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "modifica proprietà, Route federativo")</span><span class="sxs-lookup"><span data-stu-id="fedf7-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="fedf7-113">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="fedf7-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="fedf7-114">In Generatore di topologia, nel nodo Lync Server 2013, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fedf7-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="fedf7-115">In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**.</span><span class="sxs-lookup"><span data-stu-id="fedf7-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="fedf7-116">Nell'elenco selezionare l'interfaccia Edge Server per BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="fedf7-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="fedf7-117">![Finestra di dialogo Modifica proprietà,](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "finestra di dialogo Modifica proprietà") generale pagina generale</span><span class="sxs-lookup"><span data-stu-id="fedf7-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="fedf7-118">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="fedf7-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="fedf7-119">In **Generatore di topologie**selezionare il nodo di primo livello, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fedf7-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="fedf7-120">Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fedf7-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="fedf7-121">Al termine della **pubblicazione guidata** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="fedf7-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

