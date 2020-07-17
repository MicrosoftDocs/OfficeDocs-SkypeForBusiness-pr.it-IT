---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="24ff5-102">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="24ff5-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24ff5-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="24ff5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="24ff5-104">Dopo la distribuzione di Lync Server 2013, non è configurata una route di federazione per il sito.</span><span class="sxs-lookup"><span data-stu-id="24ff5-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="24ff5-105">Per utilizzare la route federata utilizzata da Office Communications Server 2007 R2, è necessario che Lync Server 2013 sia configurato per l'utilizzo di questa route.</span><span class="sxs-lookup"><span data-stu-id="24ff5-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="24ff5-106">Per abilitare il sito di Lync Server 2013 per l'utilizzo del server Director e Edge di BackCompatSite, utilizzare Generatore di topologie per associare il pool perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="24ff5-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="24ff5-107">Per associare il pool di server perimetrali legacy tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="24ff5-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="24ff5-108">Aprire la topologia del pool pilota in Generatore tipologie</span><span class="sxs-lookup"><span data-stu-id="24ff5-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="24ff5-109">Selezionare il sito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24ff5-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="24ff5-110">Scegliere  \*\*Modifica proprietà \*\* dal menu  \*\*Azioni \*\*.</span><span class="sxs-lookup"><span data-stu-id="24ff5-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="24ff5-111">In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare il Director di Office Communications Server 2007 R2 o il server perimetrale di Office Communications Server 2007 R2 se non è elencato alcun Director.</span><span class="sxs-lookup"><span data-stu-id="24ff5-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="24ff5-112">![Finestra di dialogo Modifica proprietà, pagina Route di Federazione](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina Route di Federazione")</span><span class="sxs-lookup"><span data-stu-id="24ff5-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="24ff5-113">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="24ff5-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="24ff5-114">In Generatore di topologie, nel nodo Lync Server 2013, passare al **Server Standard Edition** o **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="24ff5-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="24ff5-115">In  \*\*Associazioni \*\* selezionare la casella di controllo accanto ad  \*\*Associa pool di server perimetrali (per componenti multimediali) \*\*.</span><span class="sxs-lookup"><span data-stu-id="24ff5-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="24ff5-116">Nell'elenco, selezionare l'interfaccia del server perimetrale per BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="24ff5-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="24ff5-117">![Finestra di dialogo Modifica proprietà, pagina generale](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Finestra di dialogo Modifica proprietà, pagina generale")</span><span class="sxs-lookup"><span data-stu-id="24ff5-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="24ff5-118">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="24ff5-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="24ff5-119">In  \*\*Generatore di topologie \*\* selezionare il nodo di primo livello  **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="24ff5-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="24ff5-120">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="24ff5-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="24ff5-121">Al termine della Pubblicazione guidata \*\*\*\* fare clic su  \*\*Fine \*\*.</span><span class="sxs-lookup"><span data-stu-id="24ff5-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

