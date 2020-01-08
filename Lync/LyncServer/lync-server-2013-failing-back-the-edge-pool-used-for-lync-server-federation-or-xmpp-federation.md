---
title: Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="4ce25-102">Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ce25-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ce25-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4ce25-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4ce25-104">Dopo che un pool di Edge non riuscito usato per ospitare la Federazione è stato riportato online, usare questa procedura per non tornare più alla route federativo di Lync Server e/o alla route della Federazione XMPP per usare di nuovo questo pool di Edge ripristinato.</span><span class="sxs-lookup"><span data-stu-id="4ce25-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="4ce25-105">Riattivazione della Federazione in un pool Edge ripristinato</span><span class="sxs-lookup"><span data-stu-id="4ce25-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="4ce25-106">Nel pool di Edge ora disponibile di nuovo, avviare i servizi Edge.</span><span class="sxs-lookup"><span data-stu-id="4ce25-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="4ce25-107">Se si vuole ripristinare la route federativo di Lync Server per l'uso del server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ce25-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="4ce25-108">In un server front-end aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="4ce25-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="4ce25-109">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server attualmente configurato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="4ce25-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="4ce25-110">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="4ce25-111">In **modifica proprietà** in **generale**deselezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="4ce25-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="4ce25-113">Espandere **pool di bordi**e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool di Edge Server originale che si vuole usare per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="4ce25-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="4ce25-114">Selezionare **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="4ce25-115">In **modifica proprietà** in **generale**Selezionare **Abilita federazione per questo pool di bordi (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="4ce25-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="4ce25-117">Fare clic su **azione**, selezionare **topologia**, quindi **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="4ce25-118">Quando viene richiesto di **pubblicare la topologia**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="4ce25-119">Al termine della pubblicazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="4ce25-120">Nell'Edge Server aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ce25-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="4ce25-121">Fare clic su **Installa o aggiorna Lync Server System**, quindi fare clic su **Imposta o Rimuovi componenti di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="4ce25-122">Fare di nuovo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="4ce25-123">In configurazione componenti di Lync Server fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ce25-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="4ce25-124">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="4ce25-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="4ce25-125">Dopo aver completato la distribuzione, fare clic su **Visualizza log** per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="4ce25-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="4ce25-126">Fare clic su **fine** per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4ce25-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="4ce25-127">Se si vuole eseguire il failover della route federativa XMPP per usare il server perimetrale ripristinato, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ce25-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="4ce25-128">Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP al pool Edge che ora ospiterà la Federazione XMPP (in questo esempio, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="4ce25-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="4ce25-129">In questo esempio, Microsoft1 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer1.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.</span><span class="sxs-lookup"><span data-stu-id="4ce25-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="4ce25-130">Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4ce25-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="4ce25-131">Questo record SRV deve avere un valore di porta 5269.</span><span class="sxs-lookup"><span data-stu-id="4ce25-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="4ce25-132">Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4ce25-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="4ce25-133">Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.</span><span class="sxs-lookup"><span data-stu-id="4ce25-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="4ce25-134">Se i pool Front-End sono rimasti in uso nel sito che contiene il pool di bordi non riuscito ed è stato ripristinato, è necessario aggiornare il servizio di Web Conferencing e il servizio di conferenza telefonica a/V in questi pool di front-end per usare di nuovo i pool di bordi nel sito locale.</span><span class="sxs-lookup"><span data-stu-id="4ce25-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="4ce25-135">Per altre informazioni, vedere [modifica del pool di bordi associato a un pool Front-end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="4ce25-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="4ce25-136">Se il pool Front-end nello stesso sito del pool di Edge non è riuscito anche, è ora possibile usare Invoke-CsPoolFailback per non eseguire il backup del pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="4ce25-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ce25-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ce25-137">See Also</span></span>


[<span data-ttu-id="4ce25-138">Failover del pool di server perimetrali utilizzato per la federazione di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ce25-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="4ce25-139">Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ce25-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="4ce25-140">Ripristino di emergenza dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ce25-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

