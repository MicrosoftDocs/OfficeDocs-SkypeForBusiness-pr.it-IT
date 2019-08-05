---
title: Panoramica delle caratteristiche (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione
ms.openlocfilehash: 2ebaadf752dc0e53ac76668dcffa47adbef06feb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189140"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="eeeea-103">Panoramica delle caratteristiche (strumento di pianificazione)</span><span class="sxs-lookup"><span data-stu-id="eeeea-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="eeeea-104">Progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="eeeea-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="eeeea-105">È possibile usare la pagina **siti centrali** dello strumento di pianificazione per progettare la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="eeeea-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="eeeea-106">È possibile creare due distribuzioni centralizzate o distribuite.</span><span class="sxs-lookup"><span data-stu-id="eeeea-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="eeeea-107">Una distribuzione centralizzata ha un solo sito centrale, che ospita tutti gli utenti di Skype for business nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eeeea-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="eeeea-108">Una distribuzione distribuita include più di un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="eeeea-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="eeeea-109">Se si distribuisce Skype for Business Server in più siti centrali, verrà immesso il numero di utenti in ogni sito centrale nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eeeea-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="eeeea-110">Per completare la definizione del sito centrale, è prima di tutto necessario specificare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eeeea-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="eeeea-111">**Nome sito** Immettere il nome del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="eeeea-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="eeeea-112">**Numero di utenti** Immettere il numero di utenti, inclusi gli utenti nei siti di succursale ospitati nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="eeeea-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="eeeea-113">**Utenti cloud homed** Immettere il numero di utenti assegnati al sito centrale da Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="eeeea-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="eeeea-114">Elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="eeeea-114">UI Elements</span></span>

<span data-ttu-id="eeeea-115">Gli elementi rimanenti sono stati popolati con le risposte fornite alle domande presentate nella procedura guidata \*\*\*\* Guida introduttiva oppure, se la procedura guidata è stata ignorata, popolata automaticamente dallo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eeeea-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="eeeea-116">Collaborazione online</span><span class="sxs-lookup"><span data-stu-id="eeeea-116">Online Collaboration</span></span>

 <span data-ttu-id="eeeea-117">La **collaborazione online** contiene le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eeeea-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="eeeea-118">**Messaggistica istantanea e presenza**</span><span class="sxs-lookup"><span data-stu-id="eeeea-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="eeeea-119">La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale nei propri computer usando messaggi basati su testo.</span><span class="sxs-lookup"><span data-stu-id="eeeea-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="eeeea-120">Sono supportate entrambe le sessioni di messaggistica istantanea a due parti e a più parti.</span><span class="sxs-lookup"><span data-stu-id="eeeea-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="eeeea-121">La presenza fornisce informazioni agli utenti sullo stato degli altri nella rete.</span><span class="sxs-lookup"><span data-stu-id="eeeea-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="eeeea-122">Lo stato presenza di un utente fornisce informazioni utili per consentire ad altri utenti di determinare se l'utente è online e come contattare meglio l'utente.</span><span class="sxs-lookup"><span data-stu-id="eeeea-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="eeeea-123">Ad esempio, un utente che partecipa a una riunione è il più possibile contattato tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="eeeea-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="eeeea-124">**Conferenze audio e video**</span><span class="sxs-lookup"><span data-stu-id="eeeea-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="eeeea-125">I servizi di conferenza audio/video (A/V) consentono conferenze audio e video in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="eeeea-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="eeeea-126">**Servizi di conferenza telefonica con accesso esterno**</span><span class="sxs-lookup"><span data-stu-id="eeeea-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="eeeea-127">I servizi di conferenza telefonica con accesso esterno consentono agli utenti di partecipare a un/V da un telefono della rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="eeeea-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="eeeea-128">I servizi di conferenza telefonica con accesso esterno richiedono la distribuzione delle applicazioni del servizio di conferenza e dell'annuncio.</span><span class="sxs-lookup"><span data-stu-id="eeeea-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="eeeea-129">**Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="eeeea-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="eeeea-130">I servizi di conferenza Web consentono agli utenti aziendali interni ed esterni al firewall di creare e partecipare a conferenze in tempo reale ospitate nei server interni.</span><span class="sxs-lookup"><span data-stu-id="eeeea-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="eeeea-131">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="eeeea-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="eeeea-132">La chat persistente consente a più utenti di partecipare a conversazioni in cui pubblicano e accedono a contenuti su argomenti specifici, inclusi testo, collegamenti e file.</span><span class="sxs-lookup"><span data-stu-id="eeeea-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="eeeea-133">Anche se gli utenti possono comunicare in tempo reale durante una sessione, il contenuto di ogni sessione è persistente, il che significa che continuerà a essere disponibile dopo la fine di una sessione.</span><span class="sxs-lookup"><span data-stu-id="eeeea-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="eeeea-134">Utenti</span><span class="sxs-lookup"><span data-stu-id="eeeea-134">Users</span></span>

 <span data-ttu-id="eeeea-135">**Gli utenti** contengono le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eeeea-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="eeeea-136">**Organizzazione interna**</span><span class="sxs-lookup"><span data-stu-id="eeeea-136">**Internal organization**</span></span>
    
- <span data-ttu-id="eeeea-137">**Federazione con altre organizzazioni**</span><span class="sxs-lookup"><span data-stu-id="eeeea-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="eeeea-138">**Federazione con versioni precedenti**</span><span class="sxs-lookup"><span data-stu-id="eeeea-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="eeeea-139">**Federazione con provider di servizi di messaggistica istantanea pubblici** Consente agli utenti dell'organizzazione di stabilire comunicazioni con provider di servizi di messaggistica istantanea pubblici come MSN, Yahoo! e AOL.</span><span class="sxs-lookup"><span data-stu-id="eeeea-139">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="eeeea-140">È necessaria una licenza separata per stabilire la Federazione con le reti di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="eeeea-140">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="eeeea-141">**Federazione con provider di servizi basato su XMPP**</span><span class="sxs-lookup"><span data-stu-id="eeeea-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="eeeea-142">Skype for Business Server 2015 introduce un proxy XMPP completamente integrato (distribuito sugli Edge Server) e un gateway XMPP distribuito nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="eeeea-142">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="eeeea-143">È possibile distribuire l'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentirà agli utenti di Skype for Business Server 2015 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="eeeea-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="eeeea-144">**Mobilità**</span><span class="sxs-lookup"><span data-stu-id="eeeea-144">**Mobility**</span></span>
    
    <span data-ttu-id="eeeea-145">Quando si distribuisce il servizio di mobilità di Skype for Business Server 2015, gli utenti possono usare i dispositivi mobili supportati Apple iOS, Android, Windows Phone o Nokia per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="eeeea-145">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="eeeea-146">**Cassetta postale di Exchange W15**</span><span class="sxs-lookup"><span data-stu-id="eeeea-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="eeeea-147">Skype for Business Server 2015 consente di archiviare i messaggi della segreteria telefonica nella messaggistica unificata di Exchange. i messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="eeeea-147">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="eeeea-148">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="eeeea-148">Voice</span></span>

 <span data-ttu-id="eeeea-149">La **voce** contiene le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eeeea-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="eeeea-150">**VoIP aziendale**</span><span class="sxs-lookup"><span data-stu-id="eeeea-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="eeeea-151">Enterprise Voice è la soluzione VoIP basata su software di Microsft.</span><span class="sxs-lookup"><span data-stu-id="eeeea-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="eeeea-152">Enterprise Voice consente agli utenti di usare Skype for business per effettuare una telefonata dal proprio computer.</span><span class="sxs-lookup"><span data-stu-id="eeeea-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="eeeea-153">**Messaggistica unificata di Exchange**</span><span class="sxs-lookup"><span data-stu-id="eeeea-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="eeeea-154">La messaggistica unificata di Exchange combina la posta vocale e la posta elettronica in un'unica infrastruttura di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="eeeea-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="eeeea-155">Skype for Business Server 2015 usa la messaggistica unificata di Exchange per fornire risposte alle chiamate, accesso sottoscrittore, notifica delle chiamate e servizi di operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="eeeea-155">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="eeeea-156">Se si usano questi servizi, sarà necessario integrare Exchange UM e Skype for Business Server in una topologia di Active Directory condivisa.</span><span class="sxs-lookup"><span data-stu-id="eeeea-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="eeeea-157">Opzioni di distribuzione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="eeeea-157">Additional Deployment Options</span></span>

 <span data-ttu-id="eeeea-158">Le **Opzioni di distribuzione aggiuntive** contengono le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eeeea-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="eeeea-159">**Disponibilità elevata**</span><span class="sxs-lookup"><span data-stu-id="eeeea-159">**High Availability**</span></span>
    
    <span data-ttu-id="eeeea-160">La disponibilità elevata consente ai server di standby di supportare il failover.</span><span class="sxs-lookup"><span data-stu-id="eeeea-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="eeeea-161">**Ripristino di emergenza**</span><span class="sxs-lookup"><span data-stu-id="eeeea-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="eeeea-162">Le misure per il ripristino di emergenza consentono di associare i pool Front-end situati in due centri dati.</span><span class="sxs-lookup"><span data-stu-id="eeeea-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="eeeea-163">**Monitoraggio**</span><span class="sxs-lookup"><span data-stu-id="eeeea-163">**Monitoring**</span></span>
    
    <span data-ttu-id="eeeea-164">Il monitoraggio acquisisce i record dettagli chiamata correlati alle sessioni di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="eeeea-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="eeeea-165">Raccoglie anche metriche da sessioni audio e video presso gli endpoint dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="eeeea-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="eeeea-166">Server di monitoraggio offre statistiche sull'utilizzo, tendenze e statistiche di qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="eeeea-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="eeeea-167">**Archiviazione**</span><span class="sxs-lookup"><span data-stu-id="eeeea-167">**Archiving**</span></span>
    
    <span data-ttu-id="eeeea-168">Archiviazione archivia le conversazioni e le conferenze di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="eeeea-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="eeeea-169">**Integrazione dell'archiviazione di Exchange**</span><span class="sxs-lookup"><span data-stu-id="eeeea-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="eeeea-170">Se si hanno utenti residenti in Exchange 2013 e le relative cassette postali sono state inserite in blocco sul posto, è possibile selezionare l'opzione per l'integrazione dello spazio di archiviazione di Skype for Business Server 2015 con lo spazio di archiviazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="eeeea-170">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="eeeea-171">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="eeeea-171">**IPv4**</span></span>
    
    <span data-ttu-id="eeeea-172">Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="eeeea-172">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="eeeea-173">A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili sono esauriti. Per questo motivo, molti nuovi dispositivi si spostano nell'uso degli indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="eeeea-173">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="eeeea-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="eeeea-174">**IPv6**</span></span>
    
    <span data-ttu-id="eeeea-175">Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di usare solo 32 bit, gli indirizzi IPv6 usano 128 bit.</span><span class="sxs-lookup"><span data-stu-id="eeeea-175">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="eeeea-176">Questo fornisce non solo un nuovo set di indirizzi, ma anche un numero molto più grande.</span><span class="sxs-lookup"><span data-stu-id="eeeea-176">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="eeeea-177">**Servizio Web aggiornamento dispositivi**</span><span class="sxs-lookup"><span data-stu-id="eeeea-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="eeeea-178">Il servizio Web Update per dispositivi offre un modo automatizzato per aggiornare tutti i dispositivi, ad esempio Skype for business per Windows Phone, distribuiti all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eeeea-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="eeeea-179">Applicazioni server</span><span class="sxs-lookup"><span data-stu-id="eeeea-179">Server Applications</span></span>

 <span data-ttu-id="eeeea-180">Le **applicazioni server** contengono le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eeeea-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="eeeea-181">**Response Group**</span><span class="sxs-lookup"><span data-stu-id="eeeea-181">**Response Group**</span></span>
    
    <span data-ttu-id="eeeea-182">L'applicazione Response Group risponde e distribuisce automaticamente le chiamate a un agente helpdesk disponibile.</span><span class="sxs-lookup"><span data-stu-id="eeeea-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="eeeea-183">**Annuncio**</span><span class="sxs-lookup"><span data-stu-id="eeeea-183">**Announcement**</span></span>
    
    <span data-ttu-id="eeeea-184">Se si prevede di distribuire VoIP aziendale, è consigliabile essere in grado di configurare la modalità di gestione delle chiamate telefoniche se il numero composto è valido ma non è assegnato a un'area comune dell'utente.</span><span class="sxs-lookup"><span data-stu-id="eeeea-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="eeeea-185">Gli amministratori possono configurare il servizio di annunci in modo che le chiamate vengano trasferite a una destinazione predeterminata (numero di telefono o URI SIP) oppure Riproduci un annuncio audio o entrambi.</span><span class="sxs-lookup"><span data-stu-id="eeeea-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="eeeea-186">L'uso del servizio annunci evita la situazione in cui un chiamante effettua una chiamata errata e sente un tono di occupato o il client SIP riceve un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="eeeea-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="eeeea-187">La funzionalità del servizio di annuncio è una caratteristica PBX tipica.</span><span class="sxs-lookup"><span data-stu-id="eeeea-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="eeeea-188">**Parcheggio di chiamata**</span><span class="sxs-lookup"><span data-stu-id="eeeea-188">**Call Park**</span></span>
    
    <span data-ttu-id="eeeea-189">L'applicazione Call Park consente a un utente di VoIP aziendale di effettuare una chiamata in attesa da un telefono e quindi di ricevere la chiamata da un altro telefono senza legare le risorse al telefono che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eeeea-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="eeeea-190">L'applicazione Call Park è utile quando un utente deve trasferire una chiamata, ma il destinatario specifico non è noto.</span><span class="sxs-lookup"><span data-stu-id="eeeea-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="eeeea-191">**Assistente conferenza**</span><span class="sxs-lookup"><span data-stu-id="eeeea-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="eeeea-192">L'applicazione per i servizi di conferenza include funzionalità di conferenza audio per gli utenti telefonici senza il servizio di un provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="eeeea-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="eeeea-193">**Annuncio conferenza**</span><span class="sxs-lookup"><span data-stu-id="eeeea-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="eeeea-194">L'applicazione di annunci per conferenze produce toni che segnalano quando gli utenti entrano o lasciano una conferenza, nonché le notifiche agli utenti del telefono quando sono attivati o disattivati.</span><span class="sxs-lookup"><span data-stu-id="eeeea-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="eeeea-195">**Controllo ammissione chiamata**</span><span class="sxs-lookup"><span data-stu-id="eeeea-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="eeeea-196">Il controllo di ammissione di chiamata (CAC), noto anche come gestione della larghezza di banda WAN, consente di evitare una qualità scadente dell'esperienza per gli utenti sulle reti congestionate determinando, in base alla larghezza di banda disponibile, se consentire e nuove sessioni di comunicazioni in tempo reale stabilito.</span><span class="sxs-lookup"><span data-stu-id="eeeea-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="eeeea-197">CAC controlla solo il traffico in tempo reale e non influisce sul traffico dei dati.</span><span class="sxs-lookup"><span data-stu-id="eeeea-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="eeeea-198">Se una nuova sessione vocale o video supera i limiti di larghezza di banda assegnati a una WAN, la sessione viene bloccata oppure (solo per le chiamate telefoniche) viene reinstradata alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="eeeea-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

