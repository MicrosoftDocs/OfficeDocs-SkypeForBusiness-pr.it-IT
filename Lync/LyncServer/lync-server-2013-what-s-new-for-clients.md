---
title: 'Lync Server 2013: Novità per i client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="367ca-102">Novità per i client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="367ca-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="367ca-103">_**Argomento Ultima modifica:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="367ca-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="367ca-104">Microsoft Lync 2013 offre un'interfaccia utente riprogettata e importanti nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="367ca-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="367ca-105">Per gli amministratori, il client è ora incluso nel programma di installazione di Office, offrendo un approccio più snello alla distribuzione di Office e alla personalizzazione dei client nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="367ca-106">Per una visualizzazione illustrata degli aggiornamenti dell'interfaccia utente di Lync 2013, vedere "Novità di Lync 2013" <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>in.</span><span class="sxs-lookup"><span data-stu-id="367ca-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="367ca-107">Integrazione con l'installazione di Office</span><span class="sxs-lookup"><span data-stu-id="367ca-107">Integration with Office Setup</span></span>

<span data-ttu-id="367ca-108">Il client Lync 2013 e il componente aggiuntivo riunione online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, sono ora inclusi nel programma di installazione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="367ca-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="367ca-109">Nelle versioni precedenti di Lync e Office Communicator è possibile usare le proprietà di Windows Installer per personalizzare e controllare l'installazione di Office.</span><span class="sxs-lookup"><span data-stu-id="367ca-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="367ca-110">Poiché Lync 2013 è integrato con l'installazione di Office, è possibile usare i metodi seguenti per personalizzare la configurazione di Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="367ca-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="367ca-111">Usare lo strumento di personalizzazione di Office</span><span class="sxs-lookup"><span data-stu-id="367ca-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="367ca-112">Usare il file config. XML per eseguire attività di installazione</span><span class="sxs-lookup"><span data-stu-id="367ca-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="367ca-113">Usare le opzioni della riga di comando di configurazione</span><span class="sxs-lookup"><span data-stu-id="367ca-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="367ca-114">Il programma di installazione di Lync 2013 non disinstalla versioni precedenti di Lync o Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="367ca-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="367ca-115">Il client Lync 2013 installa affiancato ad altri client Lync o Office Communicator</span><span class="sxs-lookup"><span data-stu-id="367ca-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="367ca-116">Per informazioni dettagliate, vedere [distribuzione di client Lync in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="367ca-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="367ca-117">Distribuzione di criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="367ca-117">Group Policy Deployment</span></span>

<span data-ttu-id="367ca-118">Poiché Lync 2013 è ora incluso nel programma di installazione di Office, il metodo per la distribuzione delle impostazioni dei criteri di gruppo di Lync è cambiato.</span><span class="sxs-lookup"><span data-stu-id="367ca-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="367ca-119">Nelle versioni precedenti di Lync e Office Communicator si poteva usare Communicator. adm per definire le impostazioni dei criteri di gruppo, mentre in Lync 2013 è ora possibile usare i modelli di amministrazione ADMX e ADML di Lync forniti insieme ai criteri di gruppo di Office Modelli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="367ca-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="367ca-120">Per informazioni dettagliate, vedere [impostazioni di criteri di gruppo per Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="367ca-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="367ca-121">Aggiornamenti del componente aggiuntivo per la pianificazione di Outlook</span><span class="sxs-lookup"><span data-stu-id="367ca-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="367ca-122">Il componente aggiuntivo riunione online per Lync 2013 include la personalizzazione dell'invito alla riunione e le nuove opzioni della riunione.</span><span class="sxs-lookup"><span data-stu-id="367ca-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="367ca-123">Gli amministratori possono personalizzare gli inviti alle riunioni dell'organizzazione aggiungendo un logo personalizzato, un URL di supporto, un URL di dichiarazione di non responsabilità legale o un testo del piè di pagina personalizzato.</span><span class="sxs-lookup"><span data-stu-id="367ca-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="367ca-124">Per informazioni dettagliate, vedere [personalizzazione del componente aggiuntivo riunione online in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="367ca-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="367ca-125">I nuovi controlli di silenziamento dei partecipanti consentono agli organizzatori della riunione di pianificare le conferenze che hanno l'audio e il video dei partecipanti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="367ca-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="367ca-126">Plug-in infrastruttura desktop virtuale</span><span class="sxs-lookup"><span data-stu-id="367ca-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="367ca-127">Il client Lync 2013 ora supporta l'audio e il video in un ambiente VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="367ca-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="367ca-128">Un utente può connettere un dispositivo audio o video, ad esempio un auricolare o una fotocamera, al computer locale, ad esempio un thin client o un computer riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="367ca-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="367ca-129">L'utente può connettersi alla macchina virtuale, accedere al client Lync 2013 in esecuzione nella macchina virtuale e partecipare a comunicazioni audio e video in tempo reale, come se il client è in esecuzione localmente.</span><span class="sxs-lookup"><span data-stu-id="367ca-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="367ca-130">Le caratteristiche seguenti sono supportate in un ambiente desktop virtuale:</span><span class="sxs-lookup"><span data-stu-id="367ca-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="367ca-131">Integrazione di dispositivi per audio e video, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="367ca-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="367ca-132">Chiamare i controlli dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="367ca-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="367ca-133">Integrazione della presenza nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="367ca-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="367ca-134">Supporto di più HID (Human Interface Device)</span><span class="sxs-lookup"><span data-stu-id="367ca-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="367ca-135">Supporto per la posizione e i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="367ca-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="367ca-136">Supporto per tutte le modalità di Lync, tra cui messaggistica istantanea, audio, video, condivisione applicazioni, condivisione desktop, condivisione di PowerPoint, lavagna e trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="367ca-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="367ca-137">Supporto audio e video in chiamate da persona a persona e conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="367ca-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="367ca-138">Per informazioni sulla distribuzione del plug-in VDI, vedere [distribuzione del plug-in Lync VDI in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="367ca-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="367ca-139">Miglioramenti video</span><span class="sxs-lookup"><span data-stu-id="367ca-139">Video Enhancements</span></span>

<span data-ttu-id="367ca-140">Diverse nuove funzionalità migliorano significativamente l'esperienza video per i partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="367ca-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="367ca-141">Il video viene migliorato con il rilevamento dei volti e l'inquadratura intelligente, in modo che il video di un partecipante si muova per mantenerli al centro della cornice.</span><span class="sxs-lookup"><span data-stu-id="367ca-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="367ca-142">Il video ad alta definizione è ora supportato in chiamate a due parti e conferenze multiparte.</span><span class="sxs-lookup"><span data-stu-id="367ca-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="367ca-143">Gli utenti possono provare risoluzioni fino a HD 1080P.</span><span class="sxs-lookup"><span data-stu-id="367ca-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="367ca-144">I partecipanti possono scegliere tra diversi layout delle riunioni: la visualizzazione raccolta Mostra tutte le immagini o i video dei partecipanti; La visualizzazione relatore Mostra il contenuto della riunione e solo il video o l'immagine del relatore corrente; La visualizzazione presentazione Mostra solo il contenuto della riunione; La visualizzazione compatta Mostra solo i controlli della riunione.</span><span class="sxs-lookup"><span data-stu-id="367ca-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="367ca-145">Con la nuova caratteristica raccolta, i partecipanti possono vedere più feed video contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="367ca-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="367ca-146">Se la conferenza include più di cinque partecipanti, i feed video dei partecipanti più attivi verranno visualizzati nella riga superiore e le immagini verranno visualizzate per gli altri partecipanti.</span><span class="sxs-lookup"><span data-stu-id="367ca-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="367ca-147">I partecipanti possono usare il blocco video per selezionare uno o più feed video disponibili per essere sempre visibili.</span><span class="sxs-lookup"><span data-stu-id="367ca-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="367ca-148">I relatori possono usare la caratteristica Spotlight video per selezionare il feed video di una persona in modo che tutti i partecipanti alla riunione vedano solo questo partecipante.</span><span class="sxs-lookup"><span data-stu-id="367ca-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="367ca-149">Integrazione di chat room</span><span class="sxs-lookup"><span data-stu-id="367ca-149">Chat Room Integration</span></span>

<span data-ttu-id="367ca-150">Lync 2013 integra ora le funzionalità fornite in precedenza da Lync 2010 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="367ca-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="367ca-151">Un client di chat di gruppo separato non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="367ca-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="367ca-152">Dall'interno di Lync 2013 gli utenti possono cercare chat room, aggiungere chat room ai loro contatti, monitorare l'attività delle chat room e leggere e pubblicare messaggi.</span><span class="sxs-lookup"><span data-stu-id="367ca-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="367ca-153">Gli utenti possono creare feed di argomenti in modo che vengano avvisati se qualcuno in una delle chat room aggiunge un post contenente parole chiave specifiche.</span><span class="sxs-lookup"><span data-stu-id="367ca-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="367ca-154">Con la nuova pagina delle opzioni della **chat persistente** , gli utenti possono impostare avvisi e suoni di notifica che si applicano quando le persone inviano messaggi alle chat room.</span><span class="sxs-lookup"><span data-stu-id="367ca-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="367ca-155">Aggiornamenti di Lync Web App</span><span class="sxs-lookup"><span data-stu-id="367ca-155">Lync Web App Updates</span></span>

<span data-ttu-id="367ca-156">Lync Web App è il client di conferenza basato sul Web per le riunioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="367ca-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="367ca-157">In questa versione, l'aggiunta di audio e video per computer a Lync Web App offre un'esperienza di riunione completa per tutti coloro che non hanno un client Lync installato localmente.</span><span class="sxs-lookup"><span data-stu-id="367ca-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="367ca-158">I partecipanti alla riunione hanno accesso a tutte le caratteristiche di collaborazione e condivisione e ai controlli della riunione relatore.</span><span class="sxs-lookup"><span data-stu-id="367ca-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="367ca-159">Quando un utente tenta di partecipare a una riunione ma non ha un client installato localmente, viene aperta Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="367ca-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="367ca-160">Se si vogliono consentire altre opzioni per partecipare alla riunione, è possibile configurare la pagina di partecipazione alla riunione; vedere [configurazione della pagina di partecipazione alla riunione in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="367ca-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="367ca-161">A causa dei miglioramenti apportati a Lync Web App, una versione aggiornata di Attendeee non è disponibile per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="367ca-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="367ca-162">Lync Web App è il client preferito per i partecipanti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="367ca-163">Non è necessaria un'installazione client locale, anche se le funzionalità audio, video e condivisione richiedono un plug-in da installare al primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="367ca-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="367ca-164">Aggiornamenti di Lync 2013 per i client mobili</span><span class="sxs-lookup"><span data-stu-id="367ca-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="367ca-165">Oltre alla presenza avanzata, ai contatti e alle funzionalità di messaggistica istantanea, i client mobili di Lync 2013 ora supportano le chiamate vocali e video tramite Internet e le connessioni dati cellulari.</span><span class="sxs-lookup"><span data-stu-id="367ca-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="367ca-166">Con un singolo tocco del collegamento alla riunione in un elemento del calendario, gli utenti di dispositivi mobili possono partecipare a riunioni vocali e video di Lync.</span><span class="sxs-lookup"><span data-stu-id="367ca-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="367ca-167">Per altre informazioni sui client di Lync 2013 per dispositivi mobili, vedere [pianificazione per i client mobili in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="367ca-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="367ca-168">Aggiornamenti dell'interfaccia utente di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="367ca-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="367ca-169">Aggiornamenti per l'accessibilità</span><span class="sxs-lookup"><span data-stu-id="367ca-169">Accessibility Updates</span></span>

<span data-ttu-id="367ca-170">Lync 2013 include diverse nuove funzionalità di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="367ca-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="367ca-171">Lync 2013 supporta la risoluzione a DPI elevata, consentendo agli utenti di scalare testo e grafica per 125% e 150% punti per pollice.</span><span class="sxs-lookup"><span data-stu-id="367ca-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="367ca-172">Lync offre un supporto a contrasto elevato in modo che l'interfaccia utente rimanga completamente funzionante quando viene usata con temi a contrasto elevato in Windows.</span><span class="sxs-lookup"><span data-stu-id="367ca-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="367ca-173">Lync offre più di 100 tasti di scelta rapida in modo che gli utenti possano accedere a funzioni importanti senza mouse.</span><span class="sxs-lookup"><span data-stu-id="367ca-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="367ca-174">Ad esempio, gli utenti possono premere ALT + C per accettare una chiamata oppure ALT + I per ignorarla, senza dover TAB o impostare lo stato di attivazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="367ca-175">Premendo (ALT + Q) termina una chiamata, (CTRL + N) avvia OneNote e (Alt + T) apre il menu strumenti.</span><span class="sxs-lookup"><span data-stu-id="367ca-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="367ca-176">L'ampio supporto per la lettura dello schermo in Lync 2013 assicura che tutte le notifiche, le richieste in arrivo e i messaggi istantanei vengano lette ad alta voce quando è abilitata un'utilità per la lettura</span><span class="sxs-lookup"><span data-stu-id="367ca-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="367ca-177">Presenza durante la condivisione</span><span class="sxs-lookup"><span data-stu-id="367ca-177">Presence While Sharing</span></span>

<span data-ttu-id="367ca-178">Quando Lync rileva che un utente sta condividendo, Lync assegna automaticamente all'utente uno stato presenza.</span><span class="sxs-lookup"><span data-stu-id="367ca-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="367ca-179">Questo stato blocca tutte le comunicazioni in arrivo, a meno che al mittente non sia assegnata la relazione di privacy del gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="367ca-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="367ca-180">Se l'utente usa la funzionalità di condivisione interamente su un monitor secondario, Lync non assegna uno stato presenza di presentazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="367ca-181">Aggiornamenti della finestra di conversazione</span><span class="sxs-lookup"><span data-stu-id="367ca-181">Conversation Window Updates</span></span>

<span data-ttu-id="367ca-182">La finestra di conversazione riprogettata consente di accedere più rapidamente alle caratteristiche importanti.</span><span class="sxs-lookup"><span data-stu-id="367ca-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="367ca-183">Con la nuova funzionalità delle conversazioni a schede, gli utenti possono ora conservare tutti i loro messaggi istantanei e le chat room in una sola finestra di conversazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="367ca-184">Le schede lungo il lato sinistro della finestra di conversazione consentono agli utenti di spostarsi facilmente tra tutte le conversazioni attive.</span><span class="sxs-lookup"><span data-stu-id="367ca-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="367ca-185">Gli utenti possono estrarre una singola conversazione in una finestra separata e quindi ridimensionare la finestra.</span><span class="sxs-lookup"><span data-stu-id="367ca-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="367ca-186">Possono anche riportare la finestra nella finestra principale della conversazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="367ca-187">Lync 2013 riapre le conversazioni di un utente quando l'utente si disconnette e torna a Lync.</span><span class="sxs-lookup"><span data-stu-id="367ca-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="367ca-188">Gli utenti possono aggiungere rapidamente messaggi istantanei, video, condivisione di programmi, condivisione desktop o strumenti di conferenza Web (lavagna, note riunione, blocchi appunti condivisi e allegati) a qualsiasi conversazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="367ca-189">In una riunione in cui viene condiviso il video o il contenuto, gli utenti possono visualizzare il video della riunione o il contenuto condiviso, quindi ridimensionare la finestra.</span><span class="sxs-lookup"><span data-stu-id="367ca-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="367ca-190">Aggiornamenti della finestra principale di Lync</span><span class="sxs-lookup"><span data-stu-id="367ca-190">Lync Main Window Updates</span></span>

<span data-ttu-id="367ca-191">Il nuovo aspetto semplificato mantiene le caratteristiche familiari, ad esempio **quello che succede oggi?** campo Nota, il selettore di stato e il selettore della **posizione** .</span><span class="sxs-lookup"><span data-stu-id="367ca-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="367ca-192">Quando sono abilitate le chat room, gli utenti vedranno una nuova icona **chat room** nella pagina principale di Lync.</span><span class="sxs-lookup"><span data-stu-id="367ca-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="367ca-193">Con l'icona **chat room** , gli utenti possono accedere rapidamente alle chat room e ai filtri.</span><span class="sxs-lookup"><span data-stu-id="367ca-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="367ca-194">Gli utenti possono fare clic sulle icone della visualizzazione per passare alla visualizzazione **contatti** , alla visualizzazione **chat room** , alla visualizzazione **conversazioni** o alla visualizzazione **telefono** .</span><span class="sxs-lookup"><span data-stu-id="367ca-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="367ca-195">Se gli utenti hanno eseguito la migrazione a Exchange 2013, possono caricare un'immagine ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="367ca-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="367ca-196">Visualizzazione contatti e aggiornamenti della scheda contatto</span><span class="sxs-lookup"><span data-stu-id="367ca-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="367ca-197">Lync 2013 offre agli utenti diversi modi per visualizzare i contatti e i gruppi nella visualizzazione **contatti** .</span><span class="sxs-lookup"><span data-stu-id="367ca-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="367ca-198">Con il nuovo archivio contatti unificato, dopo la migrazione dei contatti Lync degli utenti a Exchange 2013, gli utenti possono accedere ai propri contatti e gestirli da Lync 2013, Outlook o Outlook Web App e i loro preferiti rimarranno sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="367ca-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="367ca-199">Ad esempio, se un utente aggiunge un contatto ai Preferiti in Outlook, il contatto viene visualizzato nel gruppo Preferiti in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="367ca-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="367ca-200">Se sono stati aggiunti e configurati il proxy XMPP e il gateway XMPP, gli utenti possono aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="367ca-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="367ca-201">Un nuovo **Add a contact che non è presente nella funzionalità organizzazione** offre agli utenti un modo semplice per aggiungere persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="367ca-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="367ca-202">Un nuovo gruppo di **Preferiti** consente agli utenti di creare un elenco di utenti contatti più spesso per velocizzare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="367ca-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="367ca-203">Gli utenti possono usare la nuova pagina Opzioni **elenco contatti** per scegliere in che modo gli utenti vogliono ordinare e visualizzare i contatti.</span><span class="sxs-lookup"><span data-stu-id="367ca-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="367ca-204">Gli utenti possono selezionare una visualizzazione espansa a due righe che mostra le immagini dei contatti o una visualizzazione a una riga ridotta.</span><span class="sxs-lookup"><span data-stu-id="367ca-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="367ca-205">Gli utenti possono anche ordinare i contatti in ordine alfabetico o in base alla disponibilità.</span><span class="sxs-lookup"><span data-stu-id="367ca-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="367ca-206">Aggiornamenti per le conferenze</span><span class="sxs-lookup"><span data-stu-id="367ca-206">Conferencing Updates</span></span>

<span data-ttu-id="367ca-207">Lync 2013 offre diversi miglioramenti alle funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="367ca-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="367ca-208">A seconda del tipo di riunione, gli utenti possono ora disattivare il pubblico e consentire o bloccare la condivisione di video durante la pianificazione della riunione.</span><span class="sxs-lookup"><span data-stu-id="367ca-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="367ca-209">Queste opzioni sono disponibili nella pagina delle **Opzioni della riunione** e sono consigliate per riunioni di grandi dimensioni con più di 20 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="367ca-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="367ca-210">I controlli audio facili da usare nella sala riunioni consentono all'utente di controllare le opzioni audio, ad esempio mute, riattivazioni, modifica dispositivo e così via.</span><span class="sxs-lookup"><span data-stu-id="367ca-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="367ca-211">Quando si condividono programmi, gli utenti possono selezionare più programmi da condividere se è necessario usare più di un programma.</span><span class="sxs-lookup"><span data-stu-id="367ca-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="367ca-212">Gli utenti possono ora caricare presentazioni che contengono clip video caricando il file di PowerPoint e puntando il mouse sulla diapositiva per visualizzare i controlli video, ad esempio riproduzione, pausa e controlli audio.</span><span class="sxs-lookup"><span data-stu-id="367ca-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="367ca-213">Durante una riunione, gli utenti possono unire un'altra conversazione aperta alla riunione usando **Unisci questa chiamata nel** menu **altre opzioni** (..**.**).</span><span class="sxs-lookup"><span data-stu-id="367ca-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="367ca-214">Per visualizzare i nomi dei partecipanti, gli utenti possono posizionare il puntatore del mouse sul pulsante **Visualizza partecipanti** oppure fare clic su **Mostra elenco** partecipanti per ancorare il pannello alla riunione.</span><span class="sxs-lookup"><span data-stu-id="367ca-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="367ca-215">A seconda del tipo di riunione, gli utenti possono scegliere tra diverse visualizzazioni di contenuti e partecipanti.</span><span class="sxs-lookup"><span data-stu-id="367ca-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="367ca-216">Le registrazioni delle riunioni vengono salvate automaticamente in un formato che viene riprodotto in Windows Media Player (MP4).</span><span class="sxs-lookup"><span data-stu-id="367ca-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="367ca-217">Gli utenti possono condividere facilmente il file con chiunque o usare la caratteristica **pubblica** in Gestione registrazioni per pubblicare la registrazione in un percorso condiviso.</span><span class="sxs-lookup"><span data-stu-id="367ca-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="367ca-218">OneNote consente di collaborare a una riunione con nuovi modi.</span><span class="sxs-lookup"><span data-stu-id="367ca-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="367ca-219">Durante una riunione, gli utenti possono prendere appunti con OneNote per uso personale dopo la riunione oppure usare i blocchi appunti condivisi e modificare la collaborazione con i partecipanti alla riunione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="367ca-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="367ca-220">Tutti i membri del team possono accedere alle note condivise per fornire informazioni, idee Brainstorm o usare le pagine del blocco appunti come lavagna virtuale.</span><span class="sxs-lookup"><span data-stu-id="367ca-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="367ca-221">Le persone e il contenuto condiviso nella riunione vengono aggiunti automaticamente alle note.</span><span class="sxs-lookup"><span data-stu-id="367ca-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="367ca-222">Gli utenti possono spostarsi tra i tipi di contenuto usando **Condividi contenuto e conduci attività di riunione** nella parte inferiore della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="367ca-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="367ca-223">Gli utenti possono anche usare il menu **Gestisci contenuto presentabile** per scegliere il contenuto che si vuole condividere.</span><span class="sxs-lookup"><span data-stu-id="367ca-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="367ca-224">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="367ca-224">See Also</span></span>


[<span data-ttu-id="367ca-225">Pianificazione per i client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="367ca-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

