---
title: 'Lync Server 2013: Ripristino di emergenza dei server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="908fd-102">Ripristino di emergenza dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="908fd-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="908fd-103">_**Argomento Ultima modifica:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="908fd-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="908fd-104">Come per gli altri ruoli del server, il modo migliore per garantire elevata disponibilità agli Edge Server consiste nel distribuire più Edge Server nei pool di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="908fd-104">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site.</span></span> <span data-ttu-id="908fd-105">Se si abbassa un server perimetrale, gli altri server del pool continueranno a includere servizi Edge.</span><span class="sxs-lookup"><span data-stu-id="908fd-105">If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="908fd-106">Per abilitare le procedure di ripristino di emergenza, è necessario disporre di pool di Edge Server distinti distribuiti in siti distinti.</span><span class="sxs-lookup"><span data-stu-id="908fd-106">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites.</span></span> <span data-ttu-id="908fd-107">Non è necessario associare in modo esplicito i pool di bordi come si fa con i pool di front-end, ma avere più pool di bordi offre ancora la disponibilità a continuare se un intero pool di bordi scende.</span><span class="sxs-lookup"><span data-stu-id="908fd-107">You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down.</span></span> <span data-ttu-id="908fd-108">Nelle sezioni seguenti sono disponibili informazioni dettagliate sul ripristino di emergenza per le varie funzioni di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="908fd-108">The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="908fd-109">Accesso remoto</span><span class="sxs-lookup"><span data-stu-id="908fd-109">Remote Access</span></span>

<span data-ttu-id="908fd-110">Se si hanno più siti, ognuno con un pool di Edge Server e un intero pool di bordi non riesce, i servizi di accesso remoto continueranno a funzionare senza bisogno di un'azione di amministratore.</span><span class="sxs-lookup"><span data-stu-id="908fd-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="908fd-111">Quando si creano pool di bordi in siti diversi, non è possibile usare lo stesso nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="908fd-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="908fd-112">Ogni pool di bordi deve avere nomi di dominio completi univoci (interni ed esterni).</span><span class="sxs-lookup"><span data-stu-id="908fd-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="908fd-113">I pool di bordi non usano regole di pubblicazione del proxy inverso per comunicare con i server front-end.</span><span class="sxs-lookup"><span data-stu-id="908fd-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="908fd-114">Il failover automatico si verifica quando il client esegue di nuovo una query sui record del servizio DNS di accesso remoto e gli utenti remoti vengono instradati agli Edge Server in un altro sito.</span><span class="sxs-lookup"><span data-stu-id="908fd-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="908fd-115">Il client tenta ogni FQDN del bordo esterno in base alla priorità dei record SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="908fd-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="908fd-116">Affinché il failover funzioni correttamente, verificare che il firewall consenta ai server front-end di ogni pool di comunicare con tutti i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="908fd-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="908fd-117">Federazione</span><span class="sxs-lookup"><span data-stu-id="908fd-117">Federation</span></span>

<span data-ttu-id="908fd-118">Per le relazioni federative con altre organizzazioni che gestiscono Lync Server, le richieste di federazione in ingresso continueranno a funzionare purché si disponga di soluzioni come Geo-DNS GTM.</span><span class="sxs-lookup"><span data-stu-id="908fd-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="908fd-119">È importante comprendere che il failover federativo non offre il failover con priorità nei record SRV.</span><span class="sxs-lookup"><span data-stu-id="908fd-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="908fd-120">Una soluzione fornita in precedenza può aiutare a fornire funzionalità di ripristino di emergenza per la Federazione in ingresso.</span><span class="sxs-lookup"><span data-stu-id="908fd-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="908fd-121">La Federazione in uscita viene sempre configurata tramite un pool Edge o un server perimetrale pubblicato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="908fd-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="908fd-122">Se il pool di Edge è sceso, è necessario usare generatore di topologie per modificare la route della Federazione in uscita per usare un pool di bordi ancora in corso.</span><span class="sxs-lookup"><span data-stu-id="908fd-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="908fd-123">Per informazioni dettagliate, vedere [errori nel pool di Edge usato per la federazione Lync Server in Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="908fd-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="908fd-124">Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="908fd-124">XMPP Federation</span></span>

<span data-ttu-id="908fd-125">Per la Federazione XMPP, il traffico in uscita e in uscita non riuscirà se il pool di bordi designato come gateway federativo XMPP scende.</span><span class="sxs-lookup"><span data-stu-id="908fd-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="908fd-126">Per rendere di nuovo possibile il lavoro della Federazione XMPP, devi modificare la Federazione XMPP per usare un pool di bordi diverso.</span><span class="sxs-lookup"><span data-stu-id="908fd-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="908fd-127">Per informazioni dettagliate, vedere [errori nel pool di Edge usato per la Federazione XMPP in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="908fd-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="908fd-128">Il pool di Edge non riesce ma il pool Front-End è ancora in corso</span><span class="sxs-lookup"><span data-stu-id="908fd-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="908fd-129">Se un pool di Edge non riesce in un sito, ma il pool Front-end in tale sito è ancora in esecuzione, sarà necessario cambiare il pool Front-end per usare un pool di bordi diverso in un sito diverso mentre il primo pool Edge è in calo.</span><span class="sxs-lookup"><span data-stu-id="908fd-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="908fd-130">Per altre informazioni, vedere [modifica del pool di bordi associato a un pool Front-end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="908fd-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

