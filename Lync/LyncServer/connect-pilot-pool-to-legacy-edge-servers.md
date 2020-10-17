---
title: Connettere il pool pilota ai server legacy di Edge Server
description: Connettere il pool pilota ai server perimetrali legacy.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede2256efabf561be6b3f99543437087cb5c3890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550272"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="3988c-103">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="3988c-103">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3988c-104">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="3988c-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="3988c-105">Dopo aver distribuito Lync Server 2013, è necessario configurare una route di federazione per il sito.</span><span class="sxs-lookup"><span data-stu-id="3988c-105">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="3988c-106">Per utilizzare la route federata utilizzata da Lync Server 2010, è necessario che Lync Server 2013 sia configurato per l'utilizzo di questa route.</span><span class="sxs-lookup"><span data-stu-id="3988c-106">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="3988c-107">Per abilitare il sito Lync Server 2013 per l'utilizzo del server Director e Edge della distribuzione di Lync Server 2010, utilizzare Generatore di topologie per associare il pool perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="3988c-107">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="3988c-108">Per associare il pool di server perimetrali legacy tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="3988c-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="3988c-109">Aprire **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="3988c-109">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="3988c-110">Selezionare il sito, disponibile direttamente sotto il nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3988c-110">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="3988c-111">Scegliere **Modifica proprietà** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="3988c-111">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="3988c-112">Nel riquadro sinistro selezionare **Route di federazione**.</span><span class="sxs-lookup"><span data-stu-id="3988c-112">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="3988c-113">In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare Lync Server 2010 Director o il server perimetrale di Lync Server 2010 se non è elencato alcun Director.</span><span class="sxs-lookup"><span data-stu-id="3988c-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="3988c-114">![Modifica proprietà, pagina Route di Federazione](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifica proprietà, pagina Route di Federazione")</span><span class="sxs-lookup"><span data-stu-id="3988c-114">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="3988c-115">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="3988c-115">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="3988c-116">In Generatore di topologie, nel nodo Lync Server 2013, passare al **Server Standard Edition** o **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3988c-116">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="3988c-117">In **Associazioni** selezionare la casella di controllo accanto ad **Associa pool di server perimetrali (per componenti multimediali)**.</span><span class="sxs-lookup"><span data-stu-id="3988c-117">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="3988c-118">Selezionare il server perimetrale legacy nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3988c-118">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="3988c-119">![Finestra di dialogo Modifica proprietà, selezione del perimetro legacy](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Finestra di dialogo Modifica proprietà, selezione del perimetro legacy")</span><span class="sxs-lookup"><span data-stu-id="3988c-119">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="3988c-120">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="3988c-120">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="3988c-121">In  \*\*Generatore di topologie \*\* selezionare il nodo di primo livello  **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3988c-121">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="3988c-122">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3988c-122">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="3988c-123">Al termine della Pubblicazione guidata \*\*\*\* fare clic su  \*\*Fine \*\*.</span><span class="sxs-lookup"><span data-stu-id="3988c-123">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

