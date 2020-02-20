---
title: 'Lync Server 2013: failover del pool di server perimetrali utilizzato per la Federazione di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4e374337f261c6747bc1b147c9f2e02fa51efe3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="23b4e-102">Failover del pool di server perimetrali utilizzato per la Federazione di Lync ServerAnalysis in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23b4e-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23b4e-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="23b4e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="23b4e-104">Se il pool di server perimetrali in cui è stato configurata la federazione di Lync Server diventa non disponibile, è necessario modificare la federazione in modo da utilizzare un pool di server perimetrali diverso, affinché la federazione funzioni.</span><span class="sxs-lookup"><span data-stu-id="23b4e-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="23b4e-105">Failover del pool di server perimetrali utilizzato per la federazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="23b4e-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="23b4e-p101">In un Front End Server aprire Generatore di topologie. Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="23b4e-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="23b4e-p102">In **Modifica proprietà** in **Generale** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="23b4e-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="23b4e-p103">Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali che si desidera utilizzare per la federazione. Scegliere **Modifica proprietà**</span><span class="sxs-lookup"><span data-stu-id="23b4e-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="23b4e-p104">In **Modifica proprietà** in **Generale** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="23b4e-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="23b4e-p105">Fare clic su **Azione**, selezionare **Topologia** e **Pubblica**. Quando viene richiesto in **Pubblicare la topologia** fare clic su **Avanti**. Dopo il completamento della pubblicazione fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="23b4e-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="23b4e-p106">Nel server perimetrale aprire la Distribuzione guidata di Lync Server. Fare clic su **Installa o aggiorna il sistema Lync Server** e quindi su **Installazione o rimozione componenti di Lync Server**. Fare clic su **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="23b4e-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="23b4e-p107">In Installazione componenti di Lync Server fare clic su **Avanti**. Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione. Al termine della distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **Fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="23b4e-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="23b4e-125">Se il sito che contiene il pool di server perimetrali in errore contiene Front End Server ancora in esecuzione, è necessario aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End per l'utilizzo di un pool di server perimetrali in un sito remoto ancora funzionante.</span><span class="sxs-lookup"><span data-stu-id="23b4e-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="23b4e-126">Per ulteriori informazioni, vedere [Changing the Edge pool associato a un pool Front end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="23b4e-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23b4e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b4e-127">See Also</span></span>


[<span data-ttu-id="23b4e-128">Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="23b4e-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="23b4e-129">Failover del pool di server perimetrali utilizzato per la Federazione di Lync o la Federazione XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23b4e-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="23b4e-130">Ripristino di emergenza del server perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23b4e-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

