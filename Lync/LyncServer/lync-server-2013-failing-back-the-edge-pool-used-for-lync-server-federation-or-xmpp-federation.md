---
title: Failover del pool di server perimetrali utilizzato per la Federazione o la Federazione XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3531e50efec5d981249e892c692a20095bef9eff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="b3bca-102">Failover del pool di server perimetrali utilizzato per la Federazione di Lync o la Federazione XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3bca-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3bca-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b3bca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b3bca-104">Dopo la riconnessione di un pool di server perimetrali utilizzato per ospitare la federazione e in cui si era verificato un problema, eseguire questa procedura per il failback della route di federazione di Lync Server e/o della route di federazione XMPP in modo che venga riutilizzato questo pool di server perimetrali ripristinato.</span><span class="sxs-lookup"><span data-stu-id="b3bca-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="b3bca-105">Failback della federazione a un pool di server perimetrali ripristinato</span><span class="sxs-lookup"><span data-stu-id="b3bca-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="b3bca-106">Avviare i servizi Edge nel pool di server perimetrali che è nuovamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="b3bca-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="b3bca-107">Se si desidera eseguire il failback della route di federazione di Lync Server per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3bca-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b3bca-p101">In un server Front End aprire Generatore di topologie. Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali attualmente configurato per la federazione. Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b3bca-p102">In **Generale** in **Modifica proprietà** deselezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="b3bca-p103">Espandere **Pool di server perimetrali** e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali originale che si desidera utilizzare di nuovo per la federazione. Scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b3bca-p104">In **Generale** in **Modifica proprietà** selezionare **Abilita federazione per pool di server perimetrali (porta 5061)**. Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="b3bca-p105">Fare clic su **Azione**, selezionare **Topologia** e **Pubblica**. Quando viene richiesto in **Pubblicare la topologia** fare clic su **Avanti**. Dopo il completamento della pubblicazione fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="b3bca-p106">Nel server perimetrale aprire la Distribuzione guidata di Lync Server. Fare clic su **Installa o aggiorna il sistema Lync Server** e quindi su **Installazione o rimozione componenti di Lync Server**. Fare clic su **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="b3bca-p107">In Installazione componenti di Lync Server fare clic su **Avanti**. Nella schermata di riepilogo verranno mostrate le azioni man mano che vengono eseguite. Al termine della distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili. Fare clic su **Fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="b3bca-127">Se si desidera eseguire il failback della route di federazione XMPP per l'utilizzo del server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3bca-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b3bca-128">Eseguire il cmdlet seguente in modo che la route di federazione XMPP punti di nuovo al pool di server perimetrali che ospiterà la federazione XMPP, in questo esempio EdgeServer1:</span><span class="sxs-lookup"><span data-stu-id="b3bca-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="b3bca-129">In questo esempio Site1 indica il sito contenente il pool di server perimetrali che ospiterà ora la route di federazione XMPP, mentre EdgeServer1.contoso.com indica l'FQDN di un server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="b3bca-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="b3bca-p108">Se non si dispone già di un record SRV DNS per la federazione XMPP che viene risolto nel pool di server perimetrali che ospiterà ora la federazione XMPP, aggiungerlo come indicato nell'esempio seguente. Il valore di porta del record SRV deve essere 5269.</span><span class="sxs-lookup"><span data-stu-id="b3bca-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="b3bca-132">Nel server DNS esterno modificare il record A DNS della federazione XMPP in modo che punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b3bca-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="b3bca-133">Verificare che la porta 5269 del pool di server perimetrali che ora ospita la federazione XMPP sia aperta esternamente.</span><span class="sxs-lookup"><span data-stu-id="b3bca-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="b3bca-134">Se i pool Front End sono rimasti in esecuzione nel sito contenente il pool di server perimetrali in cui si è verificato l'errore e che è stato ripristinato, aggiornare il servizio Web Conferencing e il servizio A/V Conferencing in questi pool Front End in modo che riutilizzino i pool di server perimetrali nel sito locale.</span><span class="sxs-lookup"><span data-stu-id="b3bca-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="b3bca-135">Per ulteriori informazioni, vedere [Changing the Edge pool associato a un pool Front end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b3bca-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="b3bca-136">Se si era verificato un errore anche nel pool Front End nello stesso sito del pool di server perimetrali con errore, è ora possibile utilizzare Invoke–CsPoolFailback per eseguire il failback del pool Front End.</span><span class="sxs-lookup"><span data-stu-id="b3bca-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3bca-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3bca-137">See Also</span></span>


[<span data-ttu-id="b3bca-138">Failover del pool di server perimetrali utilizzato per la Federazione di Lync ServerAnalysis in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3bca-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="b3bca-139">Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b3bca-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="b3bca-140">Ripristino di emergenza del server perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3bca-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

