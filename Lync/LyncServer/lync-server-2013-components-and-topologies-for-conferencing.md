---
title: 'Lync Server 2013: Componenti e topologie per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ca54d-102">Componenti e topologie per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca54d-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca54d-103">_**Argomento Ultima modifica:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="ca54d-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="ca54d-104">Quando si seleziona conferenza in Generatore di topologia, le conferenze vengono distribuite come parte del server front-end o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ca54d-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="ca54d-105">I servizi di conferenza telefonica con accesso esterno e la condivisione di PowerPoint richiedono componenti e configurazioni aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="ca54d-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="ca54d-106">Nelle sezioni seguenti vengono descritti i componenti e le topologie supportate per le conferenze Web, i servizi di conferenza A/V e i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ca54d-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="ca54d-107">Componenti supportati</span><span class="sxs-lookup"><span data-stu-id="ca54d-107">Supported Components</span></span>

<span data-ttu-id="ca54d-108">Gli unici componenti per le conferenze Web e le conferenze A/V richiedono i server front-end dell'organizzazione o i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ca54d-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="ca54d-109">Per un elenco dei requisiti hardware e software per i server front-end e Standard Edition, vedere [hardware supportato per il supporto di Lync server 2013](lync-server-2013-supported-hardware.md) e [del software server e dell'infrastruttura in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="ca54d-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="ca54d-110">Lync Server 2013 usa Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ca54d-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="ca54d-111">Per informazioni dettagliate sull'installazione e la configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="ca54d-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="ca54d-112">Oltre ai requisiti per le conferenze Web e le conferenze telefoniche con accesso esterno, i servizi di conferenza telefonica per i servizi di audioconferenza utilizzano i seguenti componenti di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ca54d-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="ca54d-113">**Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni UC (Unified Communications).</span><span class="sxs-lookup"><span data-stu-id="ca54d-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="ca54d-114">I servizi di conferenza telefonica con accesso esterno usano due applicazioni UC che richiedono il servizio applicazione: Assistente conferenza e Annuncio conferenza.</span><span class="sxs-lookup"><span data-stu-id="ca54d-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="ca54d-115">Il servizio applicazione viene installato e attivato per impostazione predefinita in ogni server front-end in un pool Front-end e in ogni server Standard Edition quando si distribuisce un carico di lavoro per le conferenze e si seleziona l'opzione di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ca54d-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="ca54d-116">\*\*\*\*   L'applicazione per i servizi di conferenza con operatore di conferenza è un'applicazione di comunicazioni unificata che accetta chiamate PSTN (Public Switched Telephone Network), riproduce le richieste e partecipa alle chiamate a una conferenza a/V.</span><span class="sxs-lookup"><span data-stu-id="ca54d-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="ca54d-117">L'applicazione Operatore Conferenza viene installata e attivata per impostazione predefinita quando si distribuisce un carico di lavoro per conferenze e si seleziona l'opzione conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ca54d-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="ca54d-118">\*\*\*\* L'applicazione per l'annuncio di servizi di conferenza telefonica per l'annuncio di conferenza è un'applicazione di comunicazioni unificata che riproduce i toni e chiede ai partecipanti PSTN su determinate azioni, ad esempio quando i partecipanti partecipano o abbandonano una conferenza, i partecipanti vengono disattivati o riabilitati, qualcuno entra nella sala di conferenza o la conferenza è bloccata o sbloccata.   </span><span class="sxs-lookup"><span data-stu-id="ca54d-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="ca54d-119">L'applicazione di annunci conferenza supporta anche i comandi DTMF (Dual-Tone Multifrequency) dalla tastiera del telefono.</span><span class="sxs-lookup"><span data-stu-id="ca54d-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="ca54d-120">L'applicazione di annunci conferenza viene automaticamente installata e attivata per impostazione predefinita quando si distribuisce un carico di lavoro per le conferenze e si seleziona l'opzione conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ca54d-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="ca54d-121">**Pagina delle impostazioni**   dei servizi di conferenza telefonica con accesso esterno la pagina delle impostazioni per i servizi di conferenza telefonica con accesso esterno consente di visualizzare i numeri di accesso esterno con le lingue disponibili, le informazioni sulla conferenza assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in conferenza e supporta la gestione del PIN (Personal Identification Number) e delle informazioni di conferenza assegnate.</span><span class="sxs-lookup"><span data-stu-id="ca54d-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="ca54d-122">La pagina Impostazioni conferenza telefonica con accesso esterno viene installata automaticamente come parte dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="ca54d-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="ca54d-123">**I servizi di conferenza telefonica con accesso esterno a Lync Server 2013, Mediation Server e PSTN Gateway**   richiedono un Mediation Server per tradurre i segnali (e gli elementi multimediali, in alcune configurazioni) tra Lync Server 2013 e il gateway PSTN, oltre a un gateway PSTN per la traduzione di segnali e elementi multimediali tra il server Mediation e il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca54d-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="ca54d-124">Per i servizi di conferenza telefonica con accesso esterno, è necessario distribuire almeno un Mediation Server e almeno una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca54d-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="ca54d-125">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="ca54d-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="ca54d-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="ca54d-126">IP-PBX</span></span>
    
      - <span data-ttu-id="ca54d-127">Session Border Controller (SBC) (per un provider di servizi di telefonia Internet a cui ci si connette configurando un trunk SIP)</span><span class="sxs-lookup"><span data-stu-id="ca54d-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca54d-128">Se si sta distribuendo anche VoIP aziendale, Mediation Server e gateway PSTN fanno parte della distribuzione VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ca54d-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="ca54d-129">Se non si sta distribuendo VoIP aziendale, è necessario distribuire almeno un Mediation Server e almeno un gateway PSTN, IP-PBX o SBC per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ca54d-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="ca54d-130">\*\*\*\*   Archivio file Store viene usato per i file audio dei nomi registrati.</span><span class="sxs-lookup"><span data-stu-id="ca54d-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="ca54d-131">File Store è un componente standard in tutte le distribuzioni Enterprise Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ca54d-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="ca54d-132">\*\*\*\* L'archivio utente dell'archivio utente viene usato per archiviare i pin di 2013 di Lync Server.   </span><span class="sxs-lookup"><span data-stu-id="ca54d-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="ca54d-133">Vengono hashati i pin.</span><span class="sxs-lookup"><span data-stu-id="ca54d-133">PINs are hashed.</span></span> <span data-ttu-id="ca54d-134">L'archivio utenti è un componente standard in tutte le distribuzioni Enterprise Edition o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ca54d-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="ca54d-135">**Pannello di controllo di Lync Server**   alcune impostazioni di accesso esterno possono essere configurate tramite il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca54d-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="ca54d-136">**Lync Server Management Shell**   tutte le impostazioni di accesso esterno possono essere configurate usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ca54d-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="ca54d-137">I cmdlet di Lync Server Management Shell sono disponibili per la distribuzione, la configurazione, l'uso, il monitoraggio e la risoluzione dei problemi relativi all'applicazione per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ca54d-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="ca54d-138">Per informazioni dettagliate sui cmdlet specifici, vedere documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ca54d-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="ca54d-139">Topologie supportate</span><span class="sxs-lookup"><span data-stu-id="ca54d-139">Supported Topologies</span></span>

<span data-ttu-id="ca54d-140">In Lync Server 2013 il server che gestisce i servizi di conferenza viene sempre collocato con i server front-end o i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ca54d-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="ca54d-141">Durante la distribuzione iniziale, generatore di topologia offre la possibilità di includere i servizi di conferenza nella topologia.</span><span class="sxs-lookup"><span data-stu-id="ca54d-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="ca54d-142">È anche possibile usare generatore di topologie per aggiungere servizi di conferenza a una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="ca54d-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="ca54d-143">Per informazioni dettagliate, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="ca54d-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="ca54d-144">Chiamata in conferenza Toplogies</span><span class="sxs-lookup"><span data-stu-id="ca54d-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="ca54d-145">È possibile distribuire i servizi di conferenza telefonica con accesso esterno nelle topologie e nelle configurazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca54d-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="ca54d-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ca54d-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="ca54d-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ca54d-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="ca54d-148">Con o senza VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="ca54d-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="ca54d-149">È possibile distribuire il servizio applicazione, l'applicazione per i servizi di conferenza e l'applicazione di annunci di conferenza in un sito centrale, ma non in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="ca54d-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca54d-150">Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario distribuirla in tutti i pool in cui si distribuiscono le conferenze di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca54d-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="ca54d-151">Non è necessario assegnare numeri di accesso in tutti i pool, ma è necessario distribuire la funzionalità di conferenza telefonica tramite accesso esterno in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="ca54d-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="ca54d-152">Questo requisito supporta la caratteristica nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Lync Server 2013 in un pool diverso.</span><span class="sxs-lookup"><span data-stu-id="ca54d-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="ca54d-153">Topologie supportate per Lync Server 2013 e Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="ca54d-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="ca54d-154">Lync Server 2013 offre i modi seguenti per configurare Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="ca54d-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="ca54d-155">A seconda delle proprie esigenze, è possibile:</span><span class="sxs-lookup"><span data-stu-id="ca54d-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="ca54d-156">**Installare sia Lync Server 2013 che Office Web Apps Server in locale dietro il firewall dell'organizzazione e nella stessa area di rete.**</span><span class="sxs-lookup"><span data-stu-id="ca54d-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="ca54d-157">Con questa topologia, l'accesso esterno a Office Web Apps Server verrà fornito tramite il server proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="ca54d-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="ca54d-158">Sia Lync Server 2013 che Office Web Apps Server (o una farm di Office Web Apps Server) sono installati in locale e dietro il firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca54d-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="ca54d-159">In teoria, è consigliabile installare Office Web Apps Server nella stessa area di rete di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca54d-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="ca54d-160">I client Lync esterni possono connettersi a Lync Server 2013 e a Office Web Apps Server usando un server proxy inverso, che è un server che accetta richieste da Internet e le inoltra alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="ca54d-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="ca54d-161">I client interni non devono usare il server proxy inverso perché possono connettersi direttamente a Office Web Apps Server. Questa topologia funziona meglio se si vuole usare una farm di server Office Web Apps dedicata che viene usata solo da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca54d-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="ca54d-162">**Uso di un server Office Web Apps distribuito esternamente**</span><span class="sxs-lookup"><span data-stu-id="ca54d-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="ca54d-163">In questa topologia Lync Server 2013 viene distribuito in locale e usa un server di Office Web Apps distribuito all'esterno dell'area di rete di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca54d-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="ca54d-164">Questo problema può verificarsi quando il server Office Web Apps è condiviso tra più applicazioni della società e viene distribuito in una rete che richiede a Lync Server di usare l'interfaccia esterna di Office Web Apps Server e viceversa.</span><span class="sxs-lookup"><span data-stu-id="ca54d-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="ca54d-165">Non è necessario installare un server proxy inverso; tutte le richieste di Office Web Apps Server a Lync Server 2013 vengono invece instradate tramite il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="ca54d-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="ca54d-166">Sia i client Lync interni che quelli esterni si connettono a Office Web Apps Server usando l'URL esterno.</span><span class="sxs-lookup"><span data-stu-id="ca54d-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="ca54d-167">Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)** in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ca54d-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="ca54d-168">Per altri dettagli [, vedere Configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="ca54d-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="ca54d-169">Indipendentemente dalla topologia selezionata, è fondamentale che vengano aperte le porte del firewall corrette.</span><span class="sxs-lookup"><span data-stu-id="ca54d-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="ca54d-170">È necessario assicurarsi che i nomi DNS, gli indirizzi IP e le porte non vengano bloccati dai firewall nel server Office Web Apps, nel servizio di bilanciamento del carico o in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca54d-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca54d-171">Un'altra opzione per fornire l'accesso esterno a Office Web Apps Server consiste nel distribuire il server nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="ca54d-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="ca54d-172">Se si sceglie di eseguire questa operazione, tieni presente che la configurazione del server Office Web Apps richiede che il computer server sia membro del dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ca54d-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="ca54d-173">A meno che i criteri di rete non consentano ai computer della rete perimetrale di essere membri del dominio Active Directory, è consigliabile non installare Office Web Apps Server nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="ca54d-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="ca54d-174">È invece necessario installare Office Web Apps Server nella rete interna e consentire l'accesso degli utenti esterni tramite il server proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="ca54d-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

