---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="0eff8-102">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="0eff8-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eff8-103">_**Argomento Ultima modifica:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0eff8-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0eff8-104">Dopo la distribuzione di Lync Server 2013, è necessario configurare una route federativo per il sito.</span><span class="sxs-lookup"><span data-stu-id="0eff8-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="0eff8-105">Per usare la route federata usata da Lync Server 2010, è necessario configurare Lync Server 2013 per usare questa route.</span><span class="sxs-lookup"><span data-stu-id="0eff8-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="0eff8-106">Per consentire al sito di Lync Server 2013 di usare il Director e il server perimetrale della distribuzione di Lync Server 2010, usare generatore di topologie per associare il pool di Edge legacy.</span><span class="sxs-lookup"><span data-stu-id="0eff8-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="0eff8-107">Per associare il pool di Edge legacy tramite Generatore di topologia</span><span class="sxs-lookup"><span data-stu-id="0eff8-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="0eff8-108">Aprire **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="0eff8-109">Selezionare il sito, che si trova direttamente sotto il nodo **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="0eff8-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="0eff8-110">Nel menu **azioni** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="0eff8-111">Nel riquadro sinistro selezionare **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="0eff8-112">In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare il director di Lync Server 2010 o Lync Server 2010 Edge Server se non è elencato alcun amministratore.</span><span class="sxs-lookup"><span data-stu-id="0eff8-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="0eff8-113">![Modifica proprietà - Pagina Route di federazione](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Modifica proprietà - Pagina Route di federazione")</span><span class="sxs-lookup"><span data-stu-id="0eff8-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="0eff8-114">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="0eff8-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="0eff8-115">In Generatore di topologia, nel nodo Lync Server 2013, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="0eff8-116">In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="0eff8-117">Nell'elenco selezionare il server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="0eff8-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="0eff8-118">![Finestra di dialogo Modifica proprietà - Selezione del server perimetrale legacy](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Selezione del server perimetrale legacy")</span><span class="sxs-lookup"><span data-stu-id="0eff8-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="0eff8-119">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="0eff8-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="0eff8-120">In **Generatore di topologie**selezionare il nodo di primo livello, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="0eff8-121">Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="0eff8-122">Al termine della **pubblicazione guidata** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="0eff8-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

