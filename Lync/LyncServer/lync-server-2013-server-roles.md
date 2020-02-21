---
title: Ruoli del server Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e153e41e0c5d452ec136daf2ad46d4ea67541d83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="d2be7-102">Ruoli del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2be7-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2be7-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="d2be7-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="d2be7-104">Ogni server che esegue Lync Server esegue uno o più *ruoli del server*.</span><span class="sxs-lookup"><span data-stu-id="d2be7-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="d2be7-105">Un ruolo del server è un set definito di funzionalità di Lync Server fornite da tale server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="d2be7-106">Non è necessario distribuire nella rete tutti i ruoli del server disponibili.</span><span class="sxs-lookup"><span data-stu-id="d2be7-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="d2be7-107">Installare solo i ruoli del server che contengono le funzionalità desiderate.</span><span class="sxs-lookup"><span data-stu-id="d2be7-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="d2be7-108">Anche se non si ha familiarità con i ruoli del server in Lync Server, lo strumento di pianificazione è in grado di guidare la soluzione migliore per i server che è necessario distribuire, in base alle caratteristiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="d2be7-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="d2be7-109">Questa sezione contiene una breve panoramica dei ruoli del server e delle caratteristiche generali che offrono:</span><span class="sxs-lookup"><span data-stu-id="d2be7-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="d2be7-110">server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d2be7-110">Standard Edition Server</span></span>

  - <span data-ttu-id="d2be7-111">Front End Server e server di back-end</span><span class="sxs-lookup"><span data-stu-id="d2be7-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="d2be7-112">Edge Server</span><span class="sxs-lookup"><span data-stu-id="d2be7-112">Edge Server</span></span>

  - <span data-ttu-id="d2be7-113">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d2be7-113">Mediation Server</span></span>

  - <span data-ttu-id="d2be7-114">Director</span><span class="sxs-lookup"><span data-stu-id="d2be7-114">Director</span></span>

  - <span data-ttu-id="d2be7-115">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="d2be7-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="d2be7-116">Persistent Chat Store (Server di back-end della chat persistente)</span><span class="sxs-lookup"><span data-stu-id="d2be7-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="d2be7-117">Persistent Chat Compliance Store (Compliance server di back-end della chat persistente)</span><span class="sxs-lookup"><span data-stu-id="d2be7-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="d2be7-118">Per la maggior parte dei ruoli del server, ai fini di scalabilità e disponibilità elevata è possibile distribuire *pool* di più server che eseguono tutti lo stesso ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="d2be7-119">Ogni server in un pool deve eseguire uno o più ruoli del server identici.</span><span class="sxs-lookup"><span data-stu-id="d2be7-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="d2be7-120">Per la maggior parte dei tipi di pool in Lync Server, è necessario distribuire un bilanciamento del carico per diffondere il traffico tra i vari server del pool.</span><span class="sxs-lookup"><span data-stu-id="d2be7-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="d2be7-121">Lync Server supporta il bilanciamento del carico DNS (Domain Name System) e i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d2be7-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="d2be7-122">Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d2be7-122">Standard Edition Server</span></span>

<span data-ttu-id="d2be7-123">Il server Standard Edition è progettato per piccole imprese e per progetti pilota di grandi imprese.</span><span class="sxs-lookup"><span data-stu-id="d2be7-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="d2be7-124">Consente di eseguire in un singolo server molte delle funzionalità di Lync Server, inclusi i database necessari.</span><span class="sxs-lookup"><span data-stu-id="d2be7-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="d2be7-125">In questo modo è possibile disporre di funzionalità di Lync Server per un costo inferiore, ma non fornisce una vera soluzione a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="d2be7-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="d2be7-126">Il server Standard Edition consente di utilizzare la messaggistica istantanea, la presenza, la conferenza e la VoIP aziendale, tutti in esecuzione su un server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="d2be7-127">Per una soluzione a disponibilità elevata, utilizzare Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d2be7-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="d2be7-128">Front End Server e server di back-end</span><span class="sxs-lookup"><span data-stu-id="d2be7-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="d2be7-129">In Lync Server Enterprise Edition, il front end server è il ruolo del server di base ed esegue molte funzioni di Basic Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="d2be7-130">Il front end server, insieme ai server back-end, sono gli unici ruoli del server necessari per la distribuzione di Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d2be7-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="d2be7-p106">Un *pool Front End* è un insieme di server Front End Server, configurati in modo identico, che funzionano insieme per offrire servizi per un gruppo comune di utenti. Un pool di server multipli che eseguono lo stesso ruolo garantisce funzionalità di scalabilità e failover.</span><span class="sxs-lookup"><span data-stu-id="d2be7-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="d2be7-133">Front End Server include le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2be7-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="d2be7-134">Autenticazione utente e registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="d2be7-134">User authentication and registration</span></span>

  - <span data-ttu-id="d2be7-135">Scambio di informazioni sulla presenza e schede contatto</span><span class="sxs-lookup"><span data-stu-id="d2be7-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="d2be7-136">Espansione dei servizi Rubrica e delle liste di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d2be7-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="d2be7-137">Funzionalità di messaggistica istantanea, incluse conferenze di messaggistica istantanea con più partecipanti</span><span class="sxs-lookup"><span data-stu-id="d2be7-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="d2be7-138">Web conferencing, conferenza PSTN con accesso esterno e conferenza A/V (se distribuita)</span><span class="sxs-lookup"><span data-stu-id="d2be7-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="d2be7-139">Hosting di applicazioni, per entrambe le applicazioni incluse in Lync Server (ad esempio, operatore conferenza e Response Group Application) e applicazioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="d2be7-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="d2be7-140">Facoltativamente, il monitoraggio, per raccogliere informazioni sull'utilizzo informazioni in forma di registrazione dettagli chiamata (CDR) e registrazione errori di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d2be7-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="d2be7-141">Queste informazioni forniscono metriche sulla qualità dei file multimediali (audio e video) che attraversano la rete sia per le chiamate VoIP aziendali sia per le conferenze A/V.</span><span class="sxs-lookup"><span data-stu-id="d2be7-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="d2be7-142">Componenti Web per il supporto di attività basate sul Web come Utilità di pianificazione Web e Join Launcher.</span><span class="sxs-lookup"><span data-stu-id="d2be7-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="d2be7-143">Facoltativamente, l'archiviazione consente di archiviare le comunicazioni di messaggistica istantanea e il contenuto delle riunioni per motivi di conformità.</span><span class="sxs-lookup"><span data-stu-id="d2be7-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="d2be7-144">Per informazioni dettagliate, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d2be7-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="d2be7-145">In Lync Server 2010 e versioni precedenti, il monitoraggio e l'archiviazione erano ruoli del server distinti, non collocati in front end server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="d2be7-146">Facoltativamente, se la chat persistente è abilitata, Servizi Web della chat persistente per la gestione delle chat room e Servizi Web della chat persistente per l'upload e il download dei file.</span><span class="sxs-lookup"><span data-stu-id="d2be7-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="d2be7-p109">I Front End Pool rappresentano inoltre il principale percorso di archiviazione per i dati di utenti e conferenze. Le informazioni relative a ciascun utente sono replicate tra i tre Front End Server nel pool, e il backup è eseguito nei server di back-end.</span><span class="sxs-lookup"><span data-stu-id="d2be7-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="d2be7-149">Inoltre, un pool Front end nella distribuzione esegue anche il *server di gestione centrale*, che consente di gestire e distribuire i dati di configurazione di base in tutti i server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="d2be7-150">Il server di gestione centrale fornisce anche Lync Server Management Shell e le funzionalità di trasferimento dei file.</span><span class="sxs-lookup"><span data-stu-id="d2be7-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="d2be7-151">I server back-end sono server di database che eseguono Microsoft SQL Server che forniscono i servizi di database per il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="d2be7-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="d2be7-152">I server di back-end assumono il ruolo di archivi per il back up dei dati utente e di conferenza del pool, e rappresentano gli archivi principali per altri database, tra cui il database dei Response Group.</span><span class="sxs-lookup"><span data-stu-id="d2be7-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="d2be7-153">È possibile disporre di un solo server back-end, ma una soluzione che utilizza il mirroring di SQL Server è consigliata per il failover.</span><span class="sxs-lookup"><span data-stu-id="d2be7-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="d2be7-154">I server back-end non eseguono alcun software Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2be7-155">Non è consigliabile collocare i database di Lync Server con altri database.</span><span class="sxs-lookup"><span data-stu-id="d2be7-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="d2be7-156">In caso contrario, disponibilità e prestazioni potrebbero risentirne.</span><span class="sxs-lookup"><span data-stu-id="d2be7-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="d2be7-157">Le informazioni archiviate nei database del server di back-end includono informazioni sulla presenza, elenchi di contatti degli utenti, dati sulle conferenze, ad esempio dati persistenti sullo stato di tutte le conferenze correnti, e dati di pianificazione delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="d2be7-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="d2be7-158">Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="d2be7-158">Edge Server</span></span>

<span data-ttu-id="d2be7-159">Server perimetrale consente agli utenti di comunicare e collaborare con utenti esterni ai firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2be7-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="d2be7-160">Questi utenti esterni possono includere gli utenti dell'organizzazione che attualmente lavorano fuori sede, gli utenti provenienti da organizzazioni partner federate e gli utenti esterni che sono stati invitati a partecipare a conferenze ospitate nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="d2be7-161">Edge Server consente inoltre la connettività ai servizi di connettività di messaggistica istantanea pubblica, tra cui Windows\!Live, AOL, Yahoo e Google Talk.</span><span class="sxs-lookup"><span data-stu-id="d2be7-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d2be7-162">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="d2be7-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d2be7-163">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="d2be7-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d2be7-164">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="d2be7-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="d2be7-165">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="d2be7-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d2be7-166">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="d2be7-166">has been announced.</span></span> <span data-ttu-id="d2be7-167">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d2be7-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d2be7-168">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="d2be7-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d2be7-169">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="d2be7-169">Messenger.</span></span> <span data-ttu-id="d2be7-170">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="d2be7-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="d2be7-171">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="d2be7-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d2be7-172">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="d2be7-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d2be7-173">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="d2be7-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d2be7-174">La distribuzione del server perimetrale attiva inoltre i servizi di mobilità, che supportano le funzionalità di Lync nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="d2be7-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="d2be7-175">Gli utenti possono utilizzare dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="d2be7-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="d2be7-176">I dispositivi mobili inoltre supportano alcune funzionalità di VoIP aziendale, tra cui la possibilità di partecipare a una conferenza mediante clic del mouse, la chiamata tramite ufficio, il numero unico, la segreteria telefonica e le chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="d2be7-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="d2be7-177">La funzionalità per dispositivi mobili inoltre supporta le *notifiche push* per i dispositivi mobili che non supportano le applicazioni eseguite in background.</span><span class="sxs-lookup"><span data-stu-id="d2be7-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="d2be7-178">Una notifica push è una notifica inviata a un dispositivo mobile relativamente a un evento che si verifica mentre un'applicazione per dispositivi mobili non è attiva.</span><span class="sxs-lookup"><span data-stu-id="d2be7-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="d2be7-179">I server perimetrali includono inoltre un proxy XMPP (Extensible Messaging and Presence Protocol) pienamente integrato, con gateway XMPP incluso sui Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="d2be7-180">È possibile configurare questi componenti XMPP per consentire agli utenti di Lync Server 2013 di aggiungere contatti da partner basati su XMPP (come Google Talk) per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="d2be7-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="d2be7-181">Per informazioni dettagliate, vedere [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d2be7-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="d2be7-182">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d2be7-182">Mediation Server</span></span>

<span data-ttu-id="d2be7-183">Mediation Server è un componente necessario per l'implementazione delle conferenze telefoniche con accesso esterno e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d2be7-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="d2be7-184">Mediation Server converte i segnali e, in alcune configurazioni, i supporti tra l'infrastruttura di Lync Server interna e un gateway PSTN (Public Switched Telephone Network), IP-PBX o un trunk SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="d2be7-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="d2be7-185">È possibile eseguire Mediation Server collocato sullo stesso server del Front End Server, o separato in un pool Mediation Server indipendente.</span><span class="sxs-lookup"><span data-stu-id="d2be7-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="d2be7-186">Per informazioni dettagliate, vedere [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d2be7-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="d2be7-187">Director</span><span class="sxs-lookup"><span data-stu-id="d2be7-187">Director</span></span>

<span data-ttu-id="d2be7-188">Gli amministratori possono autenticare le richieste degli utenti di Lync Server, ma non gli account utente di casa o fornire servizi di conferenza o presenza.</span><span class="sxs-lookup"><span data-stu-id="d2be7-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="d2be7-189">I direttori sono molto utili per migliorare la sicurezza nelle distribuzioni che consentono l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d2be7-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="d2be7-190">Il Director può eseguire l'autenticazione delle richieste prima di inviarle ai server interni.</span><span class="sxs-lookup"><span data-stu-id="d2be7-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="d2be7-191">Nel caso di un attacco Denial-of-Service, l'attacco termina con il Director e non raggiunge i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="d2be7-192">Per informazioni dettagliate, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d2be7-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="d2be7-193">Ruoli del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="d2be7-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="d2be7-p121">La Chat persistente consente di partecipare a conversazioni tra più partecipanti basate su argomenti, e permanenti nel tempo. I servizi di chat persistente sono eseguiti dal Front End Server della chat persistente. Il server back-end della chat persistente salva i dati della cronologia delle chat e le informazioni relative a categorie e chat room. Il Compliance server di back-end della chat persistente, facoltativo, può archiviare il contenuto della chat e gli eventi di conformità ai fini della conformità stessa.</span><span class="sxs-lookup"><span data-stu-id="d2be7-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="d2be7-198">Nei server che eseguono Lync Server Standard Edition è inoltre possibile eseguire la chat persistente collocata nello stesso server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="d2be7-199">Non è possibile collocare il front end server di Persistent Chat con Enterprise Edition Front End Server.</span><span class="sxs-lookup"><span data-stu-id="d2be7-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="d2be7-200">Per informazioni dettagliate, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d2be7-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2be7-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2be7-201">See Also</span></span>


[<span data-ttu-id="d2be7-202">Componente Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2be7-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="d2be7-203">Pianificazione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2be7-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="d2be7-204">Pianificazione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2be7-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="d2be7-205">Scenari per il Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2be7-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="d2be7-206">Pianificazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2be7-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

