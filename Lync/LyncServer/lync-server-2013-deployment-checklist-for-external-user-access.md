---
title: "Lync Server 2013: Elenco di controllo di distribuzione per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="386cd-102">Elenco di controllo di distribuzione per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="386cd-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="386cd-103">_**Argomento Ultima modifica:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="386cd-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="386cd-104">Prima di distribuire la rete perimetrale e implementare il supporto per gli utenti esterni, è necessario che siano già stati distribuiti i server interni di Microsoft Lync Server 2013, incluso un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="386cd-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="386cd-105">Se si prevede di distribuire gli amministratori facoltativi nella rete interna, è consigliabile distribuirli anche prima della distribuzione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="386cd-106">Per informazioni dettagliate sul processo di distribuzione di Director, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="386cd-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="386cd-107">Microsoft Lync Server 2013 include strumenti per facilitare la pianificazione e la distribuzione di server interni e Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="386cd-108">Al termine della topologia, pubblicare la definizione della topologia risultante nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="386cd-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="386cd-109">A questo scopo, devi essere un membro del gruppo **Domain Admins** e del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="386cd-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="386cd-110">**Strumento di pianificazione**   Office Communications Server 2007 R2 include uno strumento di pianificazione e uno strumento di pianificazione del bordo che è possibile usare per facilitare la progettazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="386cd-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="386cd-111">In Lync Server 2010 questi due strumenti sono stati combinati in un unico strumento di pianificazione con funzionalità e funzionalità aggiuntive, ad esempio la raccolta di un numero di utenti pianificato, requisiti vocali, tipi di accesso utente esterno e opzioni federative.</span><span class="sxs-lookup"><span data-stu-id="386cd-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="386cd-112">È inoltre possibile pianificare i parametri di rete dell'infrastruttura, ad esempio indirizzi IP, tipi di bilanciamento del carico e altre considerazioni sulla rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="386cd-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="386cd-113">\*\*\*\*   Generatore di topologia di Lync Server 2013 Builder di topologia consente di definire la topologia e i componenti.</span><span class="sxs-lookup"><span data-stu-id="386cd-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="386cd-114">Generatore di topologia è essenziale per la distribuzione di server che esegue Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="386cd-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="386cd-115">Generatore di topologia pubblica i risultati in un Central Management store usato per configurare tutti i server che usano Lync Server 2013 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="386cd-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="386cd-116">Non è possibile installare Lync Server 2013 nei server senza usare generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="386cd-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="386cd-117">Se hai progettato la topologia di Edge durante il processo di pianificazione, incluso l'esecuzione di generatore di topologie per definire la topologia di Edge, puoi usare questi risultati per avviare la distribuzione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="386cd-118">Se non è stata completata la creazione della topologia di Edge o si vogliono modificare le informazioni specificate in precedenza, è necessario terminare l'uso di generatore di topologie prima di procedere con altri passaggi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="386cd-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="386cd-119">Per informazioni dettagliate su come compilare la topologia, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="386cd-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="386cd-120">Per informazioni dettagliate sullo strumento di pianificazione e sul generatore di topologie, vedere [inizio del processo di pianificazione per Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="386cd-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="386cd-121">La tabella seguente offre una panoramica del processo di distribuzione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="386cd-122">Per esaminare le decisioni di pianificazione che devono essere effettuate prima di distribuire l'accesso degli utenti esterni, vedere [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="386cd-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="386cd-123">Le informazioni nella tabella seguente sono informate su una nuova distribuzione.</span><span class="sxs-lookup"><span data-stu-id="386cd-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="386cd-124">Se sono stati distribuiti Edge Server in un ambiente Lync Server 2010, Office Communications Server 2007 R2 o Office Communications Server 2007, vedere la pagina relativa alla <A href="migration.md">migrazione</A> per informazioni dettagliate sulla migrazione a lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="386cd-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="386cd-125">La migrazione non è supportata da versioni precedenti a Office Communications Server 2007 R2, tra cui Office Communications Server 2007, Live Communications Server 2005 e Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="386cd-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="386cd-126">Per migliorare le prestazioni e la sicurezza di Edge Server e per facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce la rete perimetrale e i server Edge:</span><span class="sxs-lookup"><span data-stu-id="386cd-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="386cd-127">Distribuire Edge Server solo dopo aver testato e verificato l'operazione di Lync Server 2013 all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="386cd-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="386cd-128">È consigliabile distribuire Edge Server in un gruppo di lavoro anziché in un dominio.</span><span class="sxs-lookup"><span data-stu-id="386cd-128">We recommend that you deploy Edge Servers in a workgroup rather than a domain.</span></span> <span data-ttu-id="386cd-129">Questo semplifica l'installazione e mantiene i servizi di dominio Active Directory fuori dalla rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="386cd-129">Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network.</span></span> <span data-ttu-id="386cd-130">L'individuazione di servizi di dominio Active Directory nella rete perimetrale può presentare un rischio significativo per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="386cd-130">Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="386cd-131">L'aggiunta di un server perimetrale a un dominio completamente presente nella rete perimetrale è supportata, ma sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="386cd-131">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended.</span></span> <span data-ttu-id="386cd-132">Un server perimetrale come parte del dominio interno viola i limiti di rete attendibili, dove Internet è meno attendibile, la rete perimetrale è più attendibile di Internet e la rete interna è più attendibile.</span><span class="sxs-lookup"><span data-stu-id="386cd-132">An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted.</span></span> <span data-ttu-id="386cd-133">Un server perimetrale come membro del dominio fa automaticamente parte della rete più attendibile, ma risiede in una rete meno attendibile (il perimetro).</span><span class="sxs-lookup"><span data-stu-id="386cd-133">An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="386cd-134">Processo di distribuzione per Edge Server</span><span class="sxs-lookup"><span data-stu-id="386cd-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="386cd-135">Fase</span><span class="sxs-lookup"><span data-stu-id="386cd-135">Phase</span></span></th>
<th><span data-ttu-id="386cd-136">Passaggi</span><span class="sxs-lookup"><span data-stu-id="386cd-136">Steps</span></span></th>
<th><span data-ttu-id="386cd-137">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="386cd-137">Permissions</span></span></th>
<th><span data-ttu-id="386cd-138">Documentazione</span><span class="sxs-lookup"><span data-stu-id="386cd-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="386cd-139">Creare la topologia di Edge appropriata e determinare i componenti appropriati.</span><span class="sxs-lookup"><span data-stu-id="386cd-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="386cd-140">Eseguire Generatore di topologie per configurare le impostazioni del server perimetrale e creare e pubblicare la topologia e quindi usare Lync Server Management Shell per esportare il file di configurazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="386cd-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="386cd-141">Gruppo <strong>Domain Admins</strong> e <strong>RTCUniversalServerAdmins</strong> o <strong>CsAdmins</strong> Group</span><span class="sxs-lookup"><span data-stu-id="386cd-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="386cd-142">Puoi definire una topologia usando un account che è un membro del gruppo utenti locali, ma la pubblicazione di una topologia richiede un account che sia membro del gruppo <STRONG>Domain Admins</STRONG> e del gruppo <STRONG>RTCUniversalServerAdmins</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="386cd-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="386cd-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Creazione di una topologia di Edge e Director in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="386cd-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="386cd-144">Prepararsi per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="386cd-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="386cd-145">Verificare che i prerequisiti di sistema vengano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="386cd-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="386cd-146">Configurare gli indirizzi IP (IPv4 e IPv6, se usati) per le interfacce di rete sia interne che pubbliche in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="386cd-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="386cd-147">Configurare i record DNS interni ed esterni (host A e AAAA per IPv4 e IPv6), inclusa la configurazione del suffisso DNS nel computer da distribuire come server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="386cd-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="386cd-148">Opzionale Creare e installare certificati pubblici.</span><span class="sxs-lookup"><span data-stu-id="386cd-148">(Optional) Create and install public certificates.</span></span> <span data-ttu-id="386cd-149">Il tempo necessario per ottenere i certificati dipende dall'autorità di certificazione (CA) che emette il certificato.</span><span class="sxs-lookup"><span data-stu-id="386cd-149">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="386cd-150">Se non si esegue questo passaggio a questo punto, è necessario eseguire questa operazione durante l'installazione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-150">If you do not perform this step at this point, you must do it during Edge Server installation.</span></span> <span data-ttu-id="386cd-151">I servizi Edge Server non possono essere avviati finché non vengono ottenuti e installati certificati.</span><span class="sxs-lookup"><span data-stu-id="386cd-151">The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="386cd-152">Disposizione del supporto per la connettività di messaggistica istantanea pubblica, se la distribuzione prevede il supporto delle comunicazioni con Windows Live, AOL o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="386cd-152">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo!</span></span> <span data-ttu-id="386cd-153">utenti.</span><span class="sxs-lookup"><span data-stu-id="386cd-153">users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="386cd-154">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="386cd-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="386cd-155">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="386cd-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="386cd-156">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="386cd-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="386cd-157">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="386cd-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="386cd-158">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="386cd-158">has been announced.</span></span> <span data-ttu-id="386cd-159">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="386cd-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="386cd-160">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="386cd-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="386cd-161">Messenger.</span><span class="sxs-lookup"><span data-stu-id="386cd-161">Messenger.</span></span> <span data-ttu-id="386cd-162">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="386cd-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="386cd-163">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="386cd-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="386cd-164">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="386cd-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="386cd-165">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="386cd-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="386cd-166">Supporto di Provision per il supporto XMPP e federativo per Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, se la distribuzione utilizzerà questi</span><span class="sxs-lookup"><span data-stu-id="386cd-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="386cd-167">Configurare i firewall.</span><span class="sxs-lookup"><span data-stu-id="386cd-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="386cd-168">Appropriato per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="386cd-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="386cd-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparazione per l'installazione di server nella rete perimetrale per Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="386cd-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="386cd-170">Configurare il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="386cd-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="386cd-171">Configurare il proxy inverso (ad esempio, per Microsoft Forefront Threat Management Gateway 2010 o Microsoft Internet Security and Acceleration (ISA) Server con Service Pack 1) nella rete perimetrale, ottenere i certificati pubblici necessari e configurare il regole di pubblicazione Web nel server proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="386cd-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="386cd-172">Preparare il proxy inverso per i servizi di mobilità se si è pianificati per la mobilità e si distribuiscono i servizi di mobilità nel pool Front-end o nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="386cd-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="386cd-173">Amministratore del gruppo <strong>Administrators</strong> o reverse proxy</span><span class="sxs-lookup"><span data-stu-id="386cd-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="386cd-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurazione di server proxy inverso per Lync Server 2013</a> nella documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="386cd-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="386cd-175">Configurare un Director (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="386cd-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="386cd-176">Opzionale Installare e configurare uno o più direttori nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="386cd-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="386cd-177">Gruppo <strong>amministratori</strong></span><span class="sxs-lookup"><span data-stu-id="386cd-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="386cd-178"><a href="lync-server-2013-setting-up-the-director.md">Configurazione del Director in Lync Server 2013</a> nella documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="386cd-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="386cd-179">Configurare Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="386cd-180">Installare il software prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="386cd-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="386cd-181">Trasportare il file di configurazione della topologia esportata in ogni Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="386cd-182">Installare il software Lync Server 2013 in ogni Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="386cd-183">Configurare gli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="386cd-184">Richiedere e installare certificati per ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="386cd-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="386cd-185">Avviare i servizi Edge Server.</span><span class="sxs-lookup"><span data-stu-id="386cd-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="386cd-186">Gruppo <strong>amministratori</strong></span><span class="sxs-lookup"><span data-stu-id="386cd-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="386cd-187"><a href="lync-server-2013-setting-up-edge-servers.md">Configurazione di Edge Server in Lync server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="386cd-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="386cd-188">Configurare la distribuzione per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="386cd-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="386cd-189">Usare il pannello di controllo di Lync Server per configurare il supporto per ognuna delle opzioni seguenti (se applicabile):</span><span class="sxs-lookup"><span data-stu-id="386cd-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="386cd-190">Inoltro multimediale</span><span class="sxs-lookup"><span data-stu-id="386cd-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="386cd-191">Route federativo</span><span class="sxs-lookup"><span data-stu-id="386cd-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="386cd-192">Accesso remoto agli utenti</span><span class="sxs-lookup"><span data-stu-id="386cd-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="386cd-193">Federazione con Lync Server, Office Communications Server e Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="386cd-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="386cd-194">Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="386cd-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="386cd-195">Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="386cd-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="386cd-196">Utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="386cd-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="386cd-197">Configurare gli account utente per l'accesso degli utenti remoti, la Federazione, la connettività per messaggistica istantanea pubblica, il supporto utenti XMPP e Anonymous (se applicabile)</span><span class="sxs-lookup"><span data-stu-id="386cd-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="386cd-198">Gruppo <strong>RTCUniversalServerAdmins</strong> o account utente assegnato al ruolo <strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="386cd-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="386cd-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="386cd-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="386cd-200">Verificare la configurazione del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="386cd-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="386cd-201">Verificare la connettività del server e la replica dei dati di configurazione dai server interni.</span><span class="sxs-lookup"><span data-stu-id="386cd-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="386cd-202">Verificare che gli utenti esterni possano connettersi, inclusi gli utenti remoti, gli utenti nei domini federati, gli utenti di messaggistica istantanea pubblica e gli utenti anonimi, in base alle esigenze della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="386cd-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="386cd-203">Verificare la configurazione e la comunicazione con l'analizzatore connettività remota di Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="386cd-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="386cd-204">Risolvere i problemi di configurazione e comunicazione</span><span class="sxs-lookup"><span data-stu-id="386cd-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="386cd-205">Per la verifica della replica, il gruppo <strong>RTCUniversalServerAdmins</strong> o l'account utente assegnato al ruolo <strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="386cd-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="386cd-206">Per la verifica della connettività degli utenti, un utente per ogni tipo di accesso utente esterno supportato</span><span class="sxs-lookup"><span data-stu-id="386cd-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="386cd-207">Utenti remoti</span><span class="sxs-lookup"><span data-stu-id="386cd-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="386cd-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifica della distribuzione di Edge in Lync Server 2013</a> nella documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="386cd-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

