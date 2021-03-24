---
title: Panoramica delle funzionalità (Strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Strumento di pianificazione di Skype for Business Server
ms.openlocfilehash: 4084d263a693a064e06a814d2fab4542ca3142c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093324"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="1124b-103">Panoramica delle funzionalità (Strumento di pianificazione)</span><span class="sxs-lookup"><span data-stu-id="1124b-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="1124b-104">Strumento di pianificazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1124b-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="1124b-105">È possibile utilizzare la **pagina Siti** centrali dello Strumento di pianificazione per progettare la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1124b-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="1124b-106">È possibile creare due distribuzioni centralizzate o distribuite.</span><span class="sxs-lookup"><span data-stu-id="1124b-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="1124b-107">Una distribuzione centralizzata ha un solo sito centrale, che include tutti gli utenti Skype for Business dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1124b-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="1124b-108">Una distribuzione distribuita include più di un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="1124b-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="1124b-109">Se si distribuisce Skype for Business Server in più siti centrali, si immetterà il numero di utenti in ogni sito centrale nello Strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1124b-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="1124b-110">Per completare la definizione del sito centrale, è innanzitutto necessario fornire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1124b-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="1124b-111">**Nome sito** Immettere il nome del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="1124b-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="1124b-112">**Numero di utenti** Immettere il numero di utenti, inclusi gli utenti dei siti di succursale ospitati nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="1124b-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="1124b-113">**Utenti ospitati nel cloud** Immettere il numero di utenti ospitati nel sito centrale da Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="1124b-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="1124b-114">Elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1124b-114">UI Elements</span></span>

<span data-ttu-id="1124b-115">Gli elementi rimanenti sono stati popolati con le  risposte fornite alle domande presentate nella procedura guidata Per iniziare oppure, se la procedura guidata è stata ignorata, vengono popolate automaticamente dallo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1124b-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="1124b-116">Collaborazione online</span><span class="sxs-lookup"><span data-stu-id="1124b-116">Online Collaboration</span></span>

 <span data-ttu-id="1124b-117">**La collaborazione** online contiene le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1124b-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="1124b-118">**Messaggistica istantanea e presenza**</span><span class="sxs-lookup"><span data-stu-id="1124b-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="1124b-119">La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale sui propri computer utilizzando messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="1124b-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="1124b-120">Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti.</span><span class="sxs-lookup"><span data-stu-id="1124b-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="1124b-121">La presenza fornisce agli utenti informazioni sullo stato di altri utenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="1124b-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="1124b-122">Lo stato di presenza di un utente fornisce informazioni per aiutare gli altri a determinare se l'utente è online e come contattare al meglio l'utente.</span><span class="sxs-lookup"><span data-stu-id="1124b-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="1124b-123">Ad esempio, un utente che si trova in una riunione viene contattato tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1124b-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="1124b-124">**Conferenze audio e video**</span><span class="sxs-lookup"><span data-stu-id="1124b-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="1124b-125">Le conferenze audio/video (A/V) consentono conferenze audio e video in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="1124b-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="1124b-126">**Chiamate in conferenza**</span><span class="sxs-lookup"><span data-stu-id="1124b-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="1124b-127">Le conferenze telefoniche con accesso esterno consentono agli utenti di partecipare a un A/V da un telefono sulla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="1124b-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="1124b-128">Per le conferenze telefoniche con accesso esterno è necessario distribuire le applicazioni Operatore conferenza e Servizio annuncio conferenza.</span><span class="sxs-lookup"><span data-stu-id="1124b-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="1124b-129">**Conferenze Web**</span><span class="sxs-lookup"><span data-stu-id="1124b-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="1124b-130">Le conferenze Web consentono agli utenti aziendali all'interno e all'esterno del firewall di creare e partecipare a conferenze in tempo reale ospitate nei server interni.</span><span class="sxs-lookup"><span data-stu-id="1124b-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="1124b-131">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="1124b-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="1124b-132">Persistent Chat consente a più utenti di partecipare a conversazioni in cui pubblicano e accedono a contenuto su argomenti specifici, tra cui testo, collegamenti e file.</span><span class="sxs-lookup"><span data-stu-id="1124b-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="1124b-133">Nonostante gli utenti possano comunicare in tempo reale durante una sessione, il contenuto di ogni sessione può essere salvato in modo permanente e quindi restare disponibile anche al termine di una sessione.</span><span class="sxs-lookup"><span data-stu-id="1124b-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="1124b-134">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1124b-134">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1124b-135">La stessa funzionalità è disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="1124b-135">The same functionality is available in Teams.</span></span> <span data-ttu-id="1124b-136">Per ulteriori informazioni, vedere [Aggiornamento da Skype for Business a Microsoft Teams.](/MicrosoftTeams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="1124b-136">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="1124b-137">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1124b-137">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
    
### <a name="users"></a><span data-ttu-id="1124b-138">Utenti</span><span class="sxs-lookup"><span data-stu-id="1124b-138">Users</span></span>

 <span data-ttu-id="1124b-139">**Gli** utenti contengono le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1124b-139">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="1124b-140">**Organizzazione interna**</span><span class="sxs-lookup"><span data-stu-id="1124b-140">**Internal organization**</span></span>
    
- <span data-ttu-id="1124b-141">**Federazione con altre organizzazioni**</span><span class="sxs-lookup"><span data-stu-id="1124b-141">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="1124b-142">**Federazione con versioni precedenti**</span><span class="sxs-lookup"><span data-stu-id="1124b-142">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="1124b-143">**Federazione con provider di servizi di messaggistica istantanea pubblici** Consente agli utenti dell'organizzazione di stabilire comunicazioni con provider di servizi di messaggistica istantanea pubblici come MSN, Yahoo!e AOL.</span><span class="sxs-lookup"><span data-stu-id="1124b-143">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="1124b-144">Per stabilire la federazione con reti di messaggistica istantanea pubbliche, è necessaria una licenza separata.</span><span class="sxs-lookup"><span data-stu-id="1124b-144">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="1124b-145">**Federazione con provider di servizi basati su XMPP**</span><span class="sxs-lookup"><span data-stu-id="1124b-145">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="1124b-146">Skype for Business Server 2015 ha introdotto un proxy XMPP completamente integrato (distribuito nei server perimetrali) e un gateway XMPP distribuito nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="1124b-146">Skype for Business Server 2015 introduced a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="1124b-147">È possibile distribuire L'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentiranno agli utenti di Skype for Business Server di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="1124b-147">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="1124b-148">**Mobilità**</span><span class="sxs-lookup"><span data-stu-id="1124b-148">**Mobility**</span></span>
    
    <span data-ttu-id="1124b-149">Quando distribuisci il servizio per dispositivi mobili Skype for Business Server, gli utenti possono usare i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="1124b-149">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="1124b-150">**Cassetta postale di Exchange W15**</span><span class="sxs-lookup"><span data-stu-id="1124b-150">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="1124b-151">Skype for Business Server consente di archiviare i messaggi della segreteria telefonica nella messaggistica unificata di Exchange. tali messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cartelle Posta in arrivo degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1124b-151">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1124b-152">La messaggistica unificata di Exchange nota in precedenza non è più disponibile in Exchange 2019, ma è comunque possibile utilizzare Sistema telefonico per registrare i messaggi vocali e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente.</span><span class="sxs-lookup"><span data-stu-id="1124b-152">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="1124b-153">Per [ulteriori informazioni, vedere Plan Cloud Voicemail service.](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="1124b-153">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="voice"></a><span data-ttu-id="1124b-154">Voce</span><span class="sxs-lookup"><span data-stu-id="1124b-154">Voice</span></span>

 <span data-ttu-id="1124b-155">**Voice** contiene le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1124b-155">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="1124b-156">**VoIP aziendale**</span><span class="sxs-lookup"><span data-stu-id="1124b-156">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="1124b-157">VoIP aziendale è la soluzione VoIP basata su software di Microsft.</span><span class="sxs-lookup"><span data-stu-id="1124b-157">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="1124b-158">VoIP aziendale consente agli utenti di usare Skype for Business per eseguire una chiamata telefonica dal computer.</span><span class="sxs-lookup"><span data-stu-id="1124b-158">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="1124b-159">**Messaggistica unificata di Exchange**</span><span class="sxs-lookup"><span data-stu-id="1124b-159">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="1124b-160">La messaggistica unificata di Exchange combina la posta vocale e la posta elettronica in un'unica infrastruttura di messaggistica.</span><span class="sxs-lookup"><span data-stu-id="1124b-160">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="1124b-161">Skype for Business Server 2015 utilizza la messaggistica unificata di Exchange per fornire servizi di risposta alle chiamate, accesso sottoscrittore, notifica di chiamata e operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="1124b-161">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="1124b-162">Se si utilizzano questi servizi, sarà necessario integrare la messaggistica unificata di Exchange e Skype for Business Server in una topologia di Active Directory condivisa.</span><span class="sxs-lookup"><span data-stu-id="1124b-162">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1124b-163">La messaggistica unificata di Exchange nota in precedenza non è più disponibile in Exchange 2019, ma è comunque possibile utilizzare Sistema telefonico per registrare i messaggi vocali e quindi lasciare la registrazione nella cassetta postale di Exchange di un utente.</span><span class="sxs-lookup"><span data-stu-id="1124b-163">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="1124b-164">Per [ulteriori informazioni, vedere Plan Cloud Voicemail service.](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)</span><span class="sxs-lookup"><span data-stu-id="1124b-164">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="1124b-165">Opzioni di distribuzione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1124b-165">Additional Deployment Options</span></span>

 <span data-ttu-id="1124b-166">**Opzioni di distribuzione aggiuntive** contiene le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1124b-166">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="1124b-167">**Disponibilità elevata**</span><span class="sxs-lookup"><span data-stu-id="1124b-167">**High Availability**</span></span>
    
    <span data-ttu-id="1124b-168">La disponibilità elevata abilita i server di standby per il supporto del failover.</span><span class="sxs-lookup"><span data-stu-id="1124b-168">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="1124b-169">**Ripristino d'emergenza**</span><span class="sxs-lookup"><span data-stu-id="1124b-169">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="1124b-170">Le misure di ripristino di emergenza consentono di associare pool Front End situati in due datacenter.</span><span class="sxs-lookup"><span data-stu-id="1124b-170">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="1124b-171">**Monitoraggio**</span><span class="sxs-lookup"><span data-stu-id="1124b-171">**Monitoring**</span></span>
    
    <span data-ttu-id="1124b-172">Il monitoraggio acquisisce i record dettagli chiamata correlati alle sessioni di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="1124b-172">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="1124b-173">Raccoglie anche le metriche dalle sessioni audio e video agli endpoint dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="1124b-173">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="1124b-174">Monitoring Server fornisce statistiche di utilizzo, tendenze e statistiche sulla qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="1124b-174">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="1124b-175">**Archiviazione**</span><span class="sxs-lookup"><span data-stu-id="1124b-175">**Archiving**</span></span>
    
    <span data-ttu-id="1124b-176">L'archiviazione archivia conversazioni e conferenze di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="1124b-176">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="1124b-177">**Integrazione dell'archiviazione di Exchange**</span><span class="sxs-lookup"><span data-stu-id="1124b-177">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="1124b-178">Se si dispone di utenti ospitati in Exchange e le relative cassette postali sono state messe In-Place blocco, è possibile selezionare l'opzione per integrare l'archiviazione di Skype for Business Server con l'archiviazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="1124b-178">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="1124b-179">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="1124b-179">**IPv4**</span></span>
    
    <span data-ttu-id="1124b-180">Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="1124b-180">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="1124b-181">A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili si sono eseguiti. Per questo, molti nuovi dispositivi stanno passando all'uso di indirizzi IPv6.</span><span class="sxs-lookup"><span data-stu-id="1124b-181">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="1124b-182">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="1124b-182">**IPv6**</span></span>
    
    <span data-ttu-id="1124b-183">Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di utilizzare solo 32 bit, gli indirizzi IPv6 utilizzano 128 bit.</span><span class="sxs-lookup"><span data-stu-id="1124b-183">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="1124b-184">In questo modo non solo viene fornito un nuovo set di indirizzi, ma anche un numero molto maggiore di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="1124b-184">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="1124b-185">**Servizio Web di aggiornamento del dispositivo**</span><span class="sxs-lookup"><span data-stu-id="1124b-185">**Device Update Web service**</span></span>
    
    <span data-ttu-id="1124b-186">Il servizio Web Aggiornamento dispositivi offre un modo automatico per aggiornare tutti i dispositivi, ad esempio Skype for Business per Windows Phone, distribuiti all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1124b-186">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="1124b-187">Applicazioni server</span><span class="sxs-lookup"><span data-stu-id="1124b-187">Server Applications</span></span>

 <span data-ttu-id="1124b-188">**Le applicazioni server** contengono le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1124b-188">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="1124b-189">**Response Group**</span><span class="sxs-lookup"><span data-stu-id="1124b-189">**Response Group**</span></span>
    
    <span data-ttu-id="1124b-190">L'applicazione Response Group risponde automaticamente e distribuisce le chiamate a un agente dell'helpdesk disponibile.</span><span class="sxs-lookup"><span data-stu-id="1124b-190">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="1124b-191">**Annuncio**</span><span class="sxs-lookup"><span data-stu-id="1124b-191">**Announcement**</span></span>
    
    <span data-ttu-id="1124b-192">Se si prevede di distribuire VoIP aziendale, è possibile configurare la modalità di gestione delle chiamate telefoniche se il numero composto è valido ma non assegnato a un'area comune dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1124b-192">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="1124b-193">Gli amministratori possono configurare il servizio annunci in modo che queste chiamate si trasferiscono a una destinazione predeterminata (numero di telefono o URI SIP) o riproducino un annuncio audio o entrambi.</span><span class="sxs-lookup"><span data-stu-id="1124b-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="1124b-194">L'utilizzo del servizio Annuncio evita la situazione in cui un chiamante fa un'errata diagnosi e sente un segnale di occupato o il client SIP riceve un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="1124b-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="1124b-195">La funzionalità del servizio Annuncio è una tipica funzionalità PBX.</span><span class="sxs-lookup"><span data-stu-id="1124b-195">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="1124b-196">**Parcheggio di chiamata**</span><span class="sxs-lookup"><span data-stu-id="1124b-196">**Call Park**</span></span>
    
    <span data-ttu-id="1124b-197">L'applicazione Parcheggio di chiamata consente a un utente VoIP aziendale di mettere in attesa una chiamata da un telefono e quindi di ricevere la chiamata da un altro telefono senza creare un collegamento tra le risorse del telefono che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1124b-197">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="1124b-198">L'applicazione Parcheggio di chiamata è utile quando un utente deve trasferire una chiamata, ma il destinatario specifico è sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1124b-198">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="1124b-199">**Operatore conferenza**</span><span class="sxs-lookup"><span data-stu-id="1124b-199">**Conference Attendant**</span></span>
    
    <span data-ttu-id="1124b-200">L'applicazione Operatore conferenza offre funzionalità di audioconferenza agli utenti di telefonia senza il servizio di un provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="1124b-200">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="1124b-201">**Annuncio conferenza**</span><span class="sxs-lookup"><span data-stu-id="1124b-201">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="1124b-202">L'applicazione Annuncio conferenza produce toni che segnalano quando gli utenti entrano o abbandonano una conferenza, nonché notifiche agli utenti di telefonia quando vengono disattivati o disattivati.</span><span class="sxs-lookup"><span data-stu-id="1124b-202">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="1124b-203">**Servizio Controllo di ammissione di chiamata**</span><span class="sxs-lookup"><span data-stu-id="1124b-203">**Call Admission Control**</span></span>
    
    <span data-ttu-id="1124b-204">Il servizio Controllo di ammissione di chiamata ( CAC), noto anche come gestione della larghezza di banda WAN, consente di evitare una scarsa qualità dell'esperienza per gli utenti su reti congestionate determinando, in base alla larghezza di banda disponibile, se consentire o meno la creazione di nuove sessioni di comunicazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="1124b-204">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1124b-205">Il controllo di ammissione di chiamata controlla solo il traffico in tempo reale e non influisce sul traffico dati.</span><span class="sxs-lookup"><span data-stu-id="1124b-205">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="1124b-206">Se una nuova sessione vocale o video supera i limiti di larghezza di banda allocati su una rete WAN, la sessione viene bloccata o (solo per le chiamate telefoniche) reindirizzata alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="1124b-206">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
