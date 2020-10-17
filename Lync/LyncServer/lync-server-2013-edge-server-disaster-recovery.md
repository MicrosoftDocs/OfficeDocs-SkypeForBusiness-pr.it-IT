---
title: 'Lync Server 2013: ripristino di emergenza del server perimetrale'
description: 'Lync Server 2013: ripristino di emergenza del server perimetrale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db084cae9b692ebc9d70660984275aa34096b7d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551662"
---
# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="3cca7-103">Ripristino di emergenza del server perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cca7-103">Edge Server disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cca7-104">_**Ultimo argomento modificato:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="3cca7-104">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="3cca7-p101">Come per gli altri ruoli del server, il modo migliore per garantire la disponibilità elevata dei server perimetrali consiste nel distribuire più server perimetrali in pool in ogni sito. In caso di blocco di un server perimetrale, i servizi Edge verranno forniti dagli altri server del pool.</span><span class="sxs-lookup"><span data-stu-id="3cca7-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="3cca7-p102">Per abilitare le procedure di ripristino di emergenza è necessario distribuire pool di server perimetrali distinti in siti separati. Non è necessario accoppiare esplicitamente i pool di server perimetrali come nel caso dei pool Front End, poiché la semplice presenza di più pool di server perimetrali consente di proseguire il lavoro anche in caso di blocco di un intero pool di server perimetrali. Nelle sezioni seguenti sono disponibili informazioni dettagliate sul ripristino di emergenza per le varie funzioni dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="3cca7-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="3cca7-110">Accesso remoto</span><span class="sxs-lookup"><span data-stu-id="3cca7-110">Remote Access</span></span>

<span data-ttu-id="3cca7-111">Se si dispone di più siti, ognuno con un pool di server perimetrali e un intero pool di perimetri ha esito negativo, i servizi di accesso remoto continueranno a funzionare senza l'intervento dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="3cca7-111">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="3cca7-112">Quando si creano pool di server perimetrali in siti diversi, non è possibile utilizzare lo stesso nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="3cca7-112">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="3cca7-113">Ogni pool di server perimetrali deve disporre di FQDN univoci (interno ed esterno).</span><span class="sxs-lookup"><span data-stu-id="3cca7-113">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="3cca7-114">I pool di server perimetrali non utilizzano le regole di pubblicazione del proxy inverso per comunicare con i front-end.</span><span class="sxs-lookup"><span data-stu-id="3cca7-114">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="3cca7-115">Il failover automatico si verifica quando il client riesegue la query sui record del servizio DNS di accesso remoto e gli utenti remoti vengono instradati ai server perimetrali in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="3cca7-115">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="3cca7-116">Il client tenta ogni FQDN del perimetro esterno in base alla priorità dei record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="3cca7-116">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3cca7-117">Affinché il failover funzioni correttamente, verificare che il firewall consenta ai front end server di ogni pool di comunicare con tutti i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="3cca7-117">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="3cca7-118">Federazione</span><span class="sxs-lookup"><span data-stu-id="3cca7-118">Federation</span></span>

<span data-ttu-id="3cca7-119">Per le relazioni di federazione con altre organizzazioni che eseguono Lync Server, le richieste di federazione in ingresso continueranno a funzionare fino a quando si dispone di soluzioni come Geo-DNS GTM.</span><span class="sxs-lookup"><span data-stu-id="3cca7-119">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="3cca7-120">È importante comprendere che il failover federativo non fornisce il failover con priorità nei record SRV.</span><span class="sxs-lookup"><span data-stu-id="3cca7-120">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="3cca7-121">Una soluzione fornita in precedenza può aiutare a fornire le funzionalità di ripristino di emergenza per la Federazione in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3cca7-121">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="3cca7-122">La federazione in uscita viene sempre configurata attraverso un server perimetrale o un pool di server perimetrali pubblicato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3cca7-122">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="3cca7-123">Se tale pool è inattivo, è necessario utilizzare il Generatore di topologie per modificare la route di federazione in ingresso in modo che venga utilizzato un pool di server perimetrali ancora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3cca7-123">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="3cca7-124">Per informazioni dettagliate, vedere [failover del pool di server perimetrali utilizzato per la Federazione di Lync in Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="3cca7-124">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="3cca7-125">Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="3cca7-125">XMPP Federation</span></span>

<span data-ttu-id="3cca7-126">Per la federazione XMPP, in caso di blocco del pool di server perimetrali designato come gateway XMPP si verificherà un errore sia nel traffico in ingresso che in quello in uscita.</span><span class="sxs-lookup"><span data-stu-id="3cca7-126">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="3cca7-127">Per ripristinare il funzionamento della federazione XMPP è necessario modificarla in modo che venga utilizzato un pool di server perimetrali diverso.</span><span class="sxs-lookup"><span data-stu-id="3cca7-127">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="3cca7-128">Per informazioni dettagliate, vedere [failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="3cca7-128">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="3cca7-129">Il pool di server perimetrali è in errore, ma il pool Front End è ancora in esecuzione</span><span class="sxs-lookup"><span data-stu-id="3cca7-129">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="3cca7-130">Se un pool di server perimetrali di un sito è in errore, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario modificare il pool Front End in modo che durante il periodo di non disponibilità del primo pool venga utilizzato un pool di server perimetrali diverso presso un altro sito.</span><span class="sxs-lookup"><span data-stu-id="3cca7-130">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="3cca7-131">Per ulteriori informazioni, vedere [Changing the Edge pool associato a un pool Front end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="3cca7-131">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

