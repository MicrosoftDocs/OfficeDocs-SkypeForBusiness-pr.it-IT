---
title: 'Lync Server 2013: Ruoli del server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8c5b052defcdc1d60ef9900c283f9f50b3809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="f6084-102">Ruoli del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6084-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6084-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f6084-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f6084-104">Ogni server che esegue Lync Server esegue uno o più *ruoli del server*.</span><span class="sxs-lookup"><span data-stu-id="f6084-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="f6084-105">Un ruolo del server è un set definito di funzionalità di Lync Server fornite da tale server.</span><span class="sxs-lookup"><span data-stu-id="f6084-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="f6084-106">Non è necessario distribuire tutti i ruoli del server disponibili nella rete.</span><span class="sxs-lookup"><span data-stu-id="f6084-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="f6084-107">Installare solo i ruoli del server che contengono la funzionalità desiderata.</span><span class="sxs-lookup"><span data-stu-id="f6084-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="f6084-108">Anche se non si ha familiarità con i ruoli del server in Lync Server, lo strumento di pianificazione può guidare la soluzione migliore per i server che è necessario distribuire, in base alle caratteristiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="f6084-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="f6084-109">Questa sezione fornisce una breve panoramica dei ruoli del server e delle caratteristiche generali fornite:</span><span class="sxs-lookup"><span data-stu-id="f6084-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="f6084-110">Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f6084-110">Standard Edition Server</span></span>

  - <span data-ttu-id="f6084-111">Server front-end e server back-end</span><span class="sxs-lookup"><span data-stu-id="f6084-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="f6084-112">Edge Server</span><span class="sxs-lookup"><span data-stu-id="f6084-112">Edge Server</span></span>

  - <span data-ttu-id="f6084-113">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f6084-113">Mediation Server</span></span>

  - <span data-ttu-id="f6084-114">Director</span><span class="sxs-lookup"><span data-stu-id="f6084-114">Director</span></span>

  - <span data-ttu-id="f6084-115">Server front end di chat persistente</span><span class="sxs-lookup"><span data-stu-id="f6084-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="f6084-116">Archivio Chat persistente (server back-end della chat persistente)</span><span class="sxs-lookup"><span data-stu-id="f6084-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="f6084-117">Archivio conformità della chat persistente (server back end di conformità della chat persistente)</span><span class="sxs-lookup"><span data-stu-id="f6084-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="f6084-118">Per la maggior parte dei ruoli del server, per la scalabilità e la disponibilità elevata è possibile distribuire *pool* di più server tutti in grado di eseguire lo stesso ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="f6084-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="f6084-119">Ogni server in un pool deve eseguire un ruolo o ruoli del server identico.</span><span class="sxs-lookup"><span data-stu-id="f6084-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="f6084-120">Per la maggior parte dei tipi di pool in Lync Server, è necessario distribuire un bilanciamento del carico per diffondere il traffico tra i vari server del pool.</span><span class="sxs-lookup"><span data-stu-id="f6084-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="f6084-121">Lync Server supporta il bilanciamento del carico DNS (Domain Name System) e il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="f6084-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="f6084-122">Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f6084-122">Standard Edition Server</span></span>

<span data-ttu-id="f6084-123">Il server Standard Edition è progettato per piccole organizzazioni e per progetti pilota di grandi organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f6084-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="f6084-124">Consente di eseguire in un singolo server molte delle funzionalità di Lync Server, inclusi i database necessari.</span><span class="sxs-lookup"><span data-stu-id="f6084-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="f6084-125">In questo modo è possibile avere la funzionalità Lync Server per un costo inferiore, ma non offre una vera soluzione a elevata disponibilità.</span><span class="sxs-lookup"><span data-stu-id="f6084-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="f6084-126">Il server Standard Edition consente di usare messaggistica istantanea, presenza, conferenza e VoIP aziendale, tutti in uso in un server.</span><span class="sxs-lookup"><span data-stu-id="f6084-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="f6084-127">Per una soluzione a disponibilità elevata, usare Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f6084-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="f6084-128">Server front-end e server back-end</span><span class="sxs-lookup"><span data-stu-id="f6084-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="f6084-129">In Lync Server Enterprise Edition il server front-end è il ruolo del server principale ed esegue molte funzioni di base di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6084-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="f6084-130">Il server front-end, insieme ai server back-end, sono gli unici ruoli del server necessari per la distribuzione di Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f6084-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="f6084-131">Un *pool Front End* è un set di server front-end, configurati in modo identico, che collaborano per creare servizi per un gruppo di utenti comune.</span><span class="sxs-lookup"><span data-stu-id="f6084-131">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="f6084-132">Un pool di più server con lo stesso ruolo offre funzionalità di failover e scalabilità.</span><span class="sxs-lookup"><span data-stu-id="f6084-132">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="f6084-133">Il server front-end include le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6084-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="f6084-134">Autenticazione e registrazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="f6084-134">User authentication and registration</span></span>

  - <span data-ttu-id="f6084-135">Informazioni sulla presenza e scambio di schede contatto</span><span class="sxs-lookup"><span data-stu-id="f6084-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="f6084-136">Servizi Rubrica e espansione della lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f6084-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="f6084-137">Funzionalità di messaggistica istantanea, incluse le conferenze di messaggistica istantanea a più parti</span><span class="sxs-lookup"><span data-stu-id="f6084-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="f6084-138">Servizi di conferenza Web, servizi di conferenza telefonica con accesso esterno PSTN e servizi di conferenza A/V (se distribuiti)</span><span class="sxs-lookup"><span data-stu-id="f6084-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="f6084-139">Hosting di applicazioni, per entrambe le applicazioni incluse in Lync Server (ad esempio, assistente per i servizi di conferenza e Response Group Application) e applicazioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="f6084-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="f6084-140">Facoltativamente, il monitoraggio consente di raccogliere le informazioni sull'utilizzo sotto forma di record dettagli chiamata (CDRs) e record di errore di chiamata (CER).</span><span class="sxs-lookup"><span data-stu-id="f6084-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="f6084-141">Queste informazioni forniscono le metriche relative alla qualità dei contenuti multimediali (audio e video) che attraversano la rete sia per le chiamate vocali aziendali che per le conferenze A/V.</span><span class="sxs-lookup"><span data-stu-id="f6084-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="f6084-142">Componenti Web per le attività basate sul Web supportate, ad esempio Web Scheduler e Join Launcher.</span><span class="sxs-lookup"><span data-stu-id="f6084-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="f6084-143">Facoltativamente, l'archiviazione consente di archiviare le comunicazioni ISTANTANEe e il contenuto della riunione per motivi di conformità.</span><span class="sxs-lookup"><span data-stu-id="f6084-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="f6084-144">Per informazioni dettagliate, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f6084-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="f6084-145">In Lync Server 2010 e versioni precedenti, il monitoraggio e l'archiviazione erano ruoli server distinti, non collocati nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="f6084-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="f6084-146">Facoltativamente, se è abilitata la chat persistente, i servizi Web di chat persistente per la gestione delle chat room e i servizi Web di chat persistenti per caricare/scaricare file.</span><span class="sxs-lookup"><span data-stu-id="f6084-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="f6084-147">I pool Front-End sono anche l'archivio principale per i dati dell'utente e della conferenza.</span><span class="sxs-lookup"><span data-stu-id="f6084-147">Front End Pools are also the primary store for user and conference data.</span></span> <span data-ttu-id="f6084-148">Le informazioni su ogni utente vengono replicate tra tre server front-end nel pool ed è stato eseguito il backup dei server back-end.</span><span class="sxs-lookup"><span data-stu-id="f6084-148">Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="f6084-149">Inoltre, un pool Front-end della distribuzione esegue anche il *server di gestione centrale*, che gestisce e distribuisce i dati di configurazione di base in tutti i server che esegue Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6084-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="f6084-150">Il server di gestione centrale offre anche Lync Server Management Shell e funzionalità di trasferimento file.</span><span class="sxs-lookup"><span data-stu-id="f6084-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="f6084-151">I server back-end sono server di database che esegue Microsoft SQL Server che includono i servizi di database per il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="f6084-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="f6084-152">I server back-end fungono da archivi di backup per i dati dell'utente e della conferenza del pool e sono gli archivi principali di altri database, ad esempio il database Response Group.</span><span class="sxs-lookup"><span data-stu-id="f6084-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="f6084-153">È possibile avere un singolo server back-end, ma una soluzione che usa il mirroring di SQL Server è consigliata per il failover.</span><span class="sxs-lookup"><span data-stu-id="f6084-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="f6084-154">I server back-end non eseguono alcun software Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6084-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f6084-155">Non è consigliabile collocare i database di Lync Server con altri database.</span><span class="sxs-lookup"><span data-stu-id="f6084-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="f6084-156">In questo caso, la disponibilità e le prestazioni potrebbero essere interessate.</span><span class="sxs-lookup"><span data-stu-id="f6084-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="f6084-157">Le informazioni archiviate nei database del server back-end includono le informazioni sulla presenza, gli elenchi di contatti degli utenti, i dati di conferenza, inclusi i dati permanenti sullo stato di tutte le conferenze correnti e i dati relativi alla pianificazione delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="f6084-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="f6084-158">Edge Server</span><span class="sxs-lookup"><span data-stu-id="f6084-158">Edge Server</span></span>

<span data-ttu-id="f6084-159">Edge Server consente agli utenti di comunicare e collaborare con utenti esterni ai firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6084-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="f6084-160">Questi utenti esterni possono includere gli utenti dell'organizzazione che attualmente lavorano fuori sede, utenti provenienti da organizzazioni partner federate e utenti esterni che sono stati invitati a partecipare a conferenze ospitate nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6084-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="f6084-161">Edge Server consente inoltre la connettività ai servizi di connettività per messaggistica istantanea pubblica, tra cui Windows\!Live, AOL, Yahoo e Google Talk.</span><span class="sxs-lookup"><span data-stu-id="f6084-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="f6084-162">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="f6084-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f6084-163">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f6084-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f6084-164">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="f6084-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="f6084-165">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f6084-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f6084-166">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="f6084-166">has been announced.</span></span> <span data-ttu-id="f6084-167">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f6084-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="f6084-168">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="f6084-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f6084-169">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f6084-169">Messenger.</span></span> <span data-ttu-id="f6084-170">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="f6084-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="f6084-171">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="f6084-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f6084-172">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="f6084-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f6084-173">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="f6084-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="f6084-174">La distribuzione di Edge Server consente inoltre ai servizi di mobilità, che supportano le funzionalità di Lync nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="f6084-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="f6084-175">Gli utenti possono usare i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="f6084-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="f6084-176">I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e le chiamate perse.</span><span class="sxs-lookup"><span data-stu-id="f6084-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="f6084-177">La funzionalità mobilità supporta anche le *notifiche push* per i dispositivi mobili che non supportano le applicazioni in uso in background.</span><span class="sxs-lookup"><span data-stu-id="f6084-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="f6084-178">Una notifica push è una notifica inviata a un dispositivo mobile su un evento che si verifica mentre un'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="f6084-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="f6084-179">I server Edge includono anche un proxy XMPP (Extensible Messaging and Presence Protocol) completamente integrato, con un gateway XMPP incluso nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="f6084-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="f6084-180">Puoi configurare questi componenti XMPP per consentire agli utenti di Lync Server 2013 di aggiungere contatti da partner basati su XMPP, ad esempio Google Talk, per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="f6084-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="f6084-181">Per informazioni dettagliate, vedere [pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f6084-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="f6084-182">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f6084-182">Mediation Server</span></span>

<span data-ttu-id="f6084-183">Mediation Server è un componente necessario per l'implementazione di servizi di conferenza telefonica con accesso esterno e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f6084-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="f6084-184">Mediation Server traduce la segnalazione e, in alcune configurazioni, il contenuto multimediale tra l'infrastruttura di Lync Server interna e un gateway PSTN (Public Switched Telephone Network), IP-PBX o un trunk SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="f6084-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="f6084-185">È possibile eseguire Mediation Server nello stesso server del server front-end oppure separato in un pool di Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="f6084-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="f6084-186">Per informazioni dettagliate, vedere [Componente Mediation Server in Lync server 2013](lync-server-2013-mediation-server-component.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f6084-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="f6084-187">Director</span><span class="sxs-lookup"><span data-stu-id="f6084-187">Director</span></span>

<span data-ttu-id="f6084-188">Gli amministratori possono eseguire l'autenticazione delle richieste degli utenti di Lync Server, ma non gli account degli utenti privati o offre servizi di conferenza o presenza.</span><span class="sxs-lookup"><span data-stu-id="f6084-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="f6084-189">Gli amministratori sono più utili per migliorare la sicurezza nelle distribuzioni che consentono l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="f6084-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="f6084-190">Il Director può eseguire l'autenticazione delle richieste prima di inviarle ai server interni.</span><span class="sxs-lookup"><span data-stu-id="f6084-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="f6084-191">Nel caso di un attacco di negazione del servizio, l'attacco termina con il direttore e non raggiunge i server front-end.</span><span class="sxs-lookup"><span data-stu-id="f6084-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="f6084-192">Per informazioni dettagliate, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f6084-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="f6084-193">Ruoli del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="f6084-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="f6084-194">La chat persistente consente agli utenti di partecipare a conversazioni multiparte, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f6084-194">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="f6084-195">Il server front end di chat persistente esegue il servizio di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f6084-195">The Persistent Chat Front End Server runs the persistent chat service.</span></span> <span data-ttu-id="f6084-196">Il server di back-end della chat persistente archivia i dati della cronologia chat e le informazioni sulle categorie e le chat room.</span><span class="sxs-lookup"><span data-stu-id="f6084-196">The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms.</span></span> <span data-ttu-id="f6084-197">Il server back end di conformità della chat persistente opzionale può archiviare il contenuto della chat e gli eventi di conformità ai fini della conformità.</span><span class="sxs-lookup"><span data-stu-id="f6084-197">The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="f6084-198">I server che eseguono Lync Server Standard Edition possono eseguire anche la chat persistente collocata nello stesso server.</span><span class="sxs-lookup"><span data-stu-id="f6084-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="f6084-199">Non è possibile collocare il server front-end della chat persistente con Enterprise Edition Front End Server.</span><span class="sxs-lookup"><span data-stu-id="f6084-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="f6084-200">Per informazioni dettagliate, vedere [pianificazione per il server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6084-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f6084-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6084-201">See Also</span></span>


[<span data-ttu-id="f6084-202">Componente Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6084-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="f6084-203">Pianificazione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6084-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="f6084-204">Pianificazione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6084-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="f6084-205">Scenari per il server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6084-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="f6084-206">Pianificazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6084-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

