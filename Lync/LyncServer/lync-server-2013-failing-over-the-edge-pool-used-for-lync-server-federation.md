---
title: 'Lync Server 2013: Failover del pool di server perimetrali utilizzato per la federazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="143db-102">Failover del pool di server perimetrali utilizzato per la federazione di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143db-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="143db-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="143db-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="143db-104">Se il pool di Edge in cui è configurata la Federazione di Lync Server è configurato, è necessario cambiare la Federazione per usare un pool di bordi diverso per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="143db-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="143db-105">Non superato il pool di Edge usato per la Federazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="143db-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="143db-106">In un server front-end aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="143db-106">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="143db-107">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server attualmente configurato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="143db-107">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="143db-108">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="143db-108">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="143db-109">In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="143db-109">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="143db-110">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="143db-110">Click **OK**.</span></span>

3.  <span data-ttu-id="143db-111">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server che si desidera utilizzare per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="143db-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="143db-112">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="143db-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="143db-113">In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="143db-113">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="143db-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="143db-114">Click **OK**.</span></span>

5.  <span data-ttu-id="143db-115">Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="143db-115">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="143db-116">Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="143db-116">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="143db-117">Al termine della pubblicazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="143db-117">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="143db-118">Nell'Edge Server aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="143db-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="143db-119">Fare clic su **Installa o aggiorna Lync Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="143db-119">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="143db-120">Fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="143db-120">Click **Run Again**.</span></span>

7.  <span data-ttu-id="143db-121">In configurazione componenti di Lync Server fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="143db-121">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="143db-122">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="143db-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="143db-123">Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="143db-123">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="143db-124">Fare clic su **fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="143db-124">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="143db-125">Se il sito che contiene il pool di Edge non riuscito contiene server front-end ancora in corso, è necessario aggiornare il servizio servizi di conferenza Web e il servizio di conferenza telefonica a/V in questi pool di front-end per usare un pool di Edge in un sito remoto ancora in corso.</span><span class="sxs-lookup"><span data-stu-id="143db-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="143db-126">Per altre informazioni, vedere [modifica del pool di bordi associato a un pool Front-end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="143db-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="143db-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="143db-127">See Also</span></span>


[<span data-ttu-id="143db-128">Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143db-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="143db-129">Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143db-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="143db-130">Ripristino di emergenza dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="143db-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

