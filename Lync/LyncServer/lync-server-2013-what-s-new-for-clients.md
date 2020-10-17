---
title: 'Lync Server 2013: novità per i client'
description: 'Lync Server 2013: novità per i client.'
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
ms.openlocfilehash: 90c1b93666b556c7ce7c4f3d94bea583dbf9b1a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546132"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="76dd7-103">Novità per i client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76dd7-103">What's new for clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76dd7-104">_**Ultimo argomento modificato:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="76dd7-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="76dd7-105">Microsoft Lync 2013 dispone di un'interfaccia utente riprogettata e di nuove importanti caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="76dd7-105">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="76dd7-106">Per gli amministratori, il client è ora incluso nel programma di installazione di Office, offrendo un approccio più semplificato alla distribuzione di Office e alla personalizzazione dei client nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-106">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76dd7-107">Per una visualizzazione illustrata degli aggiornamenti dell'interfaccia utente di Lync 2013, vedere "What ' s New in Lync 2013" at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> .</span><span class="sxs-lookup"><span data-stu-id="76dd7-107">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="76dd7-108">Integrazione con l'installazione di Office</span><span class="sxs-lookup"><span data-stu-id="76dd7-108">Integration with Office Setup</span></span>

<span data-ttu-id="76dd7-109">Il client Lync 2013 e il componente aggiuntivo per riunioni online per Lync 2013, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, sono ora entrambi inclusi nel programma di installazione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="76dd7-109">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="76dd7-110">Nelle versioni precedenti di Lync e Office Communicator, è possibile utilizzare le proprietà di Windows Installer per personalizzare e controllare l'installazione di Office.</span><span class="sxs-lookup"><span data-stu-id="76dd7-110">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="76dd7-111">Poiché Lync 2013 è integrato con l'installazione di Office, è possibile utilizzare i metodi seguenti per personalizzare il programma di installazione di Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="76dd7-111">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="76dd7-112">Utilizzare lo Strumento di personalizzazione di Office</span><span class="sxs-lookup"><span data-stu-id="76dd7-112">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="76dd7-113">Utilizzare il file Config.xml per eseguire le attività di installazione</span><span class="sxs-lookup"><span data-stu-id="76dd7-113">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="76dd7-114">Utilizzare le opzioni della riga di comando del programma di installazione</span><span class="sxs-lookup"><span data-stu-id="76dd7-114">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76dd7-115">Il programma di installazione di Lync 2013 non disinstalla le versioni precedenti di Lync o Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="76dd7-115">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="76dd7-116">Il client Lync 2013 installa affiancati con altri client Lync o Office Communicator</span><span class="sxs-lookup"><span data-stu-id="76dd7-116">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="76dd7-117">Per informazioni dettagliate, vedere [Deploying Lync Clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="76dd7-117">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="76dd7-118">Distribuzione di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="76dd7-118">Group Policy Deployment</span></span>

<span data-ttu-id="76dd7-119">Poiché Lync 2013 è ora incluso nel programma di installazione di Office, il metodo per la distribuzione delle impostazioni di criteri di gruppo di Lync è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="76dd7-119">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="76dd7-120">Nelle versioni precedenti di Lync e Office Communicator, è possibile utilizzare il file Communicator. adm per definire le impostazioni di criteri di gruppo, mentre in Lync 2013 è ora consentito utilizzare i modelli amministrativi di Lync ADMX e ADML forniti insieme ai modelli amministrativi di criteri di gruppo di Office.</span><span class="sxs-lookup"><span data-stu-id="76dd7-120">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="76dd7-121">Per ulteriori informazioni, vedere [impostazioni di criteri di gruppo per Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="76dd7-121">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="76dd7-122">Aggiornamenti del componente aggiuntivo di Outlook per la pianificazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="76dd7-122">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="76dd7-123">Il componente aggiuntivo per riunioni online per Lync 2013 include la personalizzazione dell'invito alla riunione e le nuove opzioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-123">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="76dd7-124">Gli amministratori possono personalizzare gli inviti alle riunioni dell'organizzazione aggiungendo un logo personalizzato, un URL di supporto, un URL per la dichiarazione di non responsabilità legale o un testo personalizzato per il piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="76dd7-124">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="76dd7-125">Per ulteriori informazioni, vedere [personalizzazione del componente aggiuntivo per riunioni online in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="76dd7-125">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="76dd7-126">I nuovi controlli per la disattivazione dell'audio dei partecipanti consentono agli organizzatori delle riunioni di disattivare l'audio e il video dei partecipanti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76dd7-126">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="76dd7-127">Plug-in VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="76dd7-127">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="76dd7-128">Il client Lync 2013 supporta ora l'audio e il video in un ambiente VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="76dd7-128">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="76dd7-129">Un utente può connettere un dispositivo audio o video (ad esempio un auricolare o una videocamera) al computer locale (ad esempio un thin client o un computer ricondizionato).</span><span class="sxs-lookup"><span data-stu-id="76dd7-129">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="76dd7-130">L'utente può connettersi alla macchina virtuale, accedere al client Lync 2013 in esecuzione nella macchina virtuale e partecipare alla comunicazione audio e video in tempo reale come se il client è in esecuzione localmente.</span><span class="sxs-lookup"><span data-stu-id="76dd7-130">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="76dd7-131">In un ambiente desktop virtuale sono supportate le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="76dd7-131">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="76dd7-132">Integrazione dei dispositivi per audio e video, incluso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="76dd7-132">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="76dd7-133">Controlli di chiamata dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="76dd7-133">Call controls from the device</span></span>
    
      - <span data-ttu-id="76dd7-134">Integrazione della presenza nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="76dd7-134">Presence integration on the device</span></span>
    
      - <span data-ttu-id="76dd7-135">Supporto di più HID (Human Interface Device)</span><span class="sxs-lookup"><span data-stu-id="76dd7-135">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="76dd7-136">Supporto di servizi di geolocalizzazione ed emergenza.</span><span class="sxs-lookup"><span data-stu-id="76dd7-136">Location and emergency services support.</span></span>

  - <span data-ttu-id="76dd7-137">Supporto per tutte le modalità di Lync, tra cui messaggistica istantanea, audio, video, condivisione applicazioni, condivisione del desktop, condivisione di PowerPoint, lavagna e trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="76dd7-137">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="76dd7-138">Supporto di audio e video nelle chiamate e nelle conferenze telefoniche a due.</span><span class="sxs-lookup"><span data-stu-id="76dd7-138">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="76dd7-139">Per informazioni sulla distribuzione del plug-in VDI, vedere [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="76dd7-139">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="76dd7-140">Miglioramenti relativi alle funzionalità video</span><span class="sxs-lookup"><span data-stu-id="76dd7-140">Video Enhancements</span></span>

<span data-ttu-id="76dd7-141">Molte nuove funzionalità migliorano in modo sostanziale l'esperienza video per i partecipanti alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="76dd7-141">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="76dd7-142">Le funzionalità video sono ottimizzate con rilevamento dei volti e framing intelligente, in modo che il video del partecipante si sposti automaticamente in modo che il volto rimanga centrato nel fotogramma.</span><span class="sxs-lookup"><span data-stu-id="76dd7-142">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="76dd7-p107">È ora supportato il video ad alta definizione per le chiamate a due e le conferenze con più partecipanti. Gli utenti potranno usufruire di risoluzioni fino a 1080p HD.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="76dd7-145">I partecipanti possono scegliere tra diversi layout per le riunioni. Con la visualizzazione Raccolta vengono visualizzati i video o le immagini di tutti i partecipanti. Nella visualizzazione relatore viene mostrato il contenuto della riunione e solo il video o l'immagine del relatore corrente. La visualizzazione presentazione mostra solo il contenuto della riunione e la visualizzazione compatta include solo i controlli per la riunione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-145">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="76dd7-p108">Con la nuova funzionalità Raccolta, i partecipanti possono visualizzare più feed video contemporaneamente. Se alla conferenza partecipano più di cinque persone, nella prima riga saranno visualizzati solo i feed video dei partecipanti più attivi, mentre per gli altri partecipanti verranno visualizzate le immagini.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="76dd7-148">I partecipanti possono scegliere di bloccare il video per selezionare uno o più feed video tra quelli disponibili, in modo che siano sempre visibili.</span><span class="sxs-lookup"><span data-stu-id="76dd7-148">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="76dd7-149">I relatori possono utilizzare la funzionalità di video in evidenza per selezionare il feed video di una persona in modo che tutti gli altri partecipanti alla riunione vedano solo il video di tale partecipante.</span><span class="sxs-lookup"><span data-stu-id="76dd7-149">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="76dd7-150">Integrazione delle chat room</span><span class="sxs-lookup"><span data-stu-id="76dd7-150">Chat Room Integration</span></span>

<span data-ttu-id="76dd7-151">Lync 2013 ora integra le funzionalità precedentemente fornite da Lync 2010 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="76dd7-151">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="76dd7-152">Non è più necessario un client Group Chat separato.</span><span class="sxs-lookup"><span data-stu-id="76dd7-152">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="76dd7-153">Dall'interno di Lync 2013, gli utenti possono cercare chat room, aggiungere chat room ai propri contatti, monitorare l'attività della chat e leggere e inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="76dd7-153">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="76dd7-154">Gli utenti possono creare feed di argomenti in modo da ricevere notifica nel caso qualcuno nelle chat room seguite aggiunga un post con parole chiave specifiche.</span><span class="sxs-lookup"><span data-stu-id="76dd7-154">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="76dd7-155">Con la nuova pagina di opzioni **Chat persistente** gli utenti possono impostare avvisi e suoni di notifica applicabili al post di messaggi nelle loro chat room.</span><span class="sxs-lookup"><span data-stu-id="76dd7-155">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="76dd7-156">Aggiornamenti di Lync Web App</span><span class="sxs-lookup"><span data-stu-id="76dd7-156">Lync Web App Updates</span></span>

<span data-ttu-id="76dd7-157">Lync Web App è il client di conferenza basato sul Web per le riunioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="76dd7-157">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="76dd7-158">In questa versione l'aggiunta di audio e video per computer a Lync Web App offre un'esperienza di riunione completa per tutti gli utenti che non dispongono di un client Lync installato localmente.</span><span class="sxs-lookup"><span data-stu-id="76dd7-158">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="76dd7-159">I partecipanti alla riunione hanno accesso a tutte le funzionalità di collaborazione e condivisione, oltre ai controlli della riunione per il relatore.</span><span class="sxs-lookup"><span data-stu-id="76dd7-159">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="76dd7-160">Quando un utente tenta di partecipare a una riunione ma non dispone di un client installato localmente, viene aperto Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="76dd7-160">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="76dd7-161">Se si desidera consentire ulteriori opzioni per l'adesione alla riunione, è possibile configurare la pagina di partecipazione alla riunione; vedere [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-161">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="76dd7-162">A causa dei miglioramenti apportati a Lync Web App, una versione aggiornata di Attendee non è disponibile per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="76dd7-162">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="76dd7-163">Lync Web App è il client preferito per i partecipanti all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-163">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="76dd7-164">Non è richiesta l'installazione di un client locale, anche se per le funzionalità audio, video e di condivisione è necessario installare un plug-in al primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="76dd7-164">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="76dd7-165">Lync 2013 per gli aggiornamenti dei client mobili</span><span class="sxs-lookup"><span data-stu-id="76dd7-165">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="76dd7-166">Oltre alla presenza avanzata, ai contatti e alle funzionalità di messaggistica istantanea, i client per dispositivi mobili Lync 2013 ora offrono chiamate vocali e video su Internet e sulle connessioni dati telefoniche.</span><span class="sxs-lookup"><span data-stu-id="76dd7-166">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="76dd7-167">Con un singolo tocco del collegamento alla riunione in un elemento del calendario, gli utenti di dispositivi mobili possono partecipare alle riunioni video e vocali di Lync.</span><span class="sxs-lookup"><span data-stu-id="76dd7-167">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="76dd7-168">Per ulteriori informazioni sui client di Lync 2013 per dispositivi mobili, vedere [Planning for Mobile Clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="76dd7-168">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="76dd7-169">Aggiornamenti dell'interfaccia utente di Lync 2013</span><span class="sxs-lookup"><span data-stu-id="76dd7-169">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="76dd7-170">Aggiornamenti dell'accessibilità</span><span class="sxs-lookup"><span data-stu-id="76dd7-170">Accessibility Updates</span></span>

<span data-ttu-id="76dd7-171">Lync 2013 include diverse nuove funzionalità di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="76dd7-171">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="76dd7-172">Lync 2013 supporta la risoluzione ad alto DPI, consentendo agli utenti di scalare il testo e la grafica per il 125% e 150% punti per pollice.</span><span class="sxs-lookup"><span data-stu-id="76dd7-172">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="76dd7-173">Lync fornisce un supporto a contrasto elevato, in modo che l'interfaccia utente rimanga completamente funzionante quando viene utilizzata con temi con contrasto elevato in Windows.</span><span class="sxs-lookup"><span data-stu-id="76dd7-173">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="76dd7-174">Lync offre più di 100 tasti di scelta rapida in modo che gli utenti possano accedere a funzioni importanti senza un mouse.</span><span class="sxs-lookup"><span data-stu-id="76dd7-174">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="76dd7-175">È ad esempio possibile premere ALT+C per accettare una chiamata o ALT+I per ignorarla, senza doversi spostare con TAB o impostare lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="76dd7-175">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="76dd7-176">Premendo ALT+Q si interrompe una chiamata, con CTRL+N si avvia OneNote e ALT+T consente di aprire il menu Strumenti.</span><span class="sxs-lookup"><span data-stu-id="76dd7-176">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="76dd7-177">Il supporto per i lettori di schermo estensivo in Lync 2013 garantisce che tutte le notifiche, le richieste in arrivo e i messaggi istantanei vengano lette ad alta voce quando è abilitato un lettore schermo.</span><span class="sxs-lookup"><span data-stu-id="76dd7-177">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="76dd7-178">Stato presenza durante la condivisione</span><span class="sxs-lookup"><span data-stu-id="76dd7-178">Presence While Sharing</span></span>

<span data-ttu-id="76dd7-179">Quando Lync rileva che un utente sta condividendo, Lync assegna automaticamente all'utente lo stato di presenza di una presentazione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-179">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="76dd7-180">Questo stato blocca tutte le comunicazioni in arrivo, a meno che al mittente non sia assegnata la relazione di privacy Gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="76dd7-180">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="76dd7-181">Se l'utente utilizza la funzionalità di condivisione interamente su un monitor secondario, Lync non assegna uno stato di presenza di presentazione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-181">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="76dd7-182">Aggiornamenti della finestra di conversazione</span><span class="sxs-lookup"><span data-stu-id="76dd7-182">Conversation Window Updates</span></span>

<span data-ttu-id="76dd7-183">La finestra di conversazione riprogettata consente di accedere più rapidamente a funzionalità importanti.</span><span class="sxs-lookup"><span data-stu-id="76dd7-183">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="76dd7-p116">Con la nuova funzionalità per le conversazioni su schede, gli utenti possono ora mantenere tutti i messaggi istantanei e le chat room in una singola finestra di conversazione. Le schede lungo il lato sinistro di questa finestra consentono agli utenti di spostarsi facilmente tra tutte le conversazioni attive.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="76dd7-p117">Gli utenti possono disancorare una singola conversazione visualizzandola in una finestra separata e poi ridimensionare la finestra. È inoltre possibile riancorare la finestra alla finestra di conversazione principale.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="76dd7-188">Lync 2013 consente di riaprire le conversazioni di un utente quando l'utente esegue l'accesso e la firma di nuovo in Lync.</span><span class="sxs-lookup"><span data-stu-id="76dd7-188">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="76dd7-189">Gli utenti possono aggiungere rapidamente gli strumenti per messaggi istantanei, video, condivisione dei programmi, condivisione del desktop o conferenze Web (lavagna, note delle riunioni, blocchi appunti condivisi e allegati) a qualsiasi conversazione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-189">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="76dd7-190">In una riunione con video o contenuto condiviso, gli utenti possono disancorare il video o il contenuto condiviso della riunione e quindi ridimensionare la finestra.</span><span class="sxs-lookup"><span data-stu-id="76dd7-190">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="76dd7-191">Aggiornamenti della finestra principale di Lync</span><span class="sxs-lookup"><span data-stu-id="76dd7-191">Lync Main Window Updates</span></span>

<span data-ttu-id="76dd7-192">Il nuovo aspetto ottimizzato conserva caratteristiche familiari come il campo note **Cosa succede oggi**, il selettore di stato e il selettore **Imposta la posizione**.</span><span class="sxs-lookup"><span data-stu-id="76dd7-192">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="76dd7-193">Quando le chat room sono abilitate, gli utenti visualizzano una nuova icona delle **chat room** nella pagina principale di Lync.</span><span class="sxs-lookup"><span data-stu-id="76dd7-193">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="76dd7-194">Con l'icona**Chat room** gli utenti possono accedere rapidamente a chat room e filtri.</span><span class="sxs-lookup"><span data-stu-id="76dd7-194">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="76dd7-195">È possibile fare clic sulle icone delle visualizzazioni per passare rapidamente alla visualizzazione **Contatti**, **Chat room**, **Conversazioni** o **Telefono**.</span><span class="sxs-lookup"><span data-stu-id="76dd7-195">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="76dd7-196">Se gli utenti sono stati migrati a Exchange 2013, è possibile caricare un'immagine ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-196">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="76dd7-197">Aggiornamenti della visualizzazione Contatti e dei biglietti da visita</span><span class="sxs-lookup"><span data-stu-id="76dd7-197">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="76dd7-198">Lync 2013 offre agli utenti diversi modi per visualizzare i contatti e i gruppi nella visualizzazione **contatti** .</span><span class="sxs-lookup"><span data-stu-id="76dd7-198">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="76dd7-199">Con il nuovo archivio contatti unificato, dopo la migrazione dei contatti Lync degli utenti a Exchange 2013, gli utenti possono accedere e gestire i propri contatti da Lync 2013, Outlook o Outlook Web App e i loro preferiti rimangono sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="76dd7-199">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="76dd7-200">Ad esempio, se un utente aggiunge un contatto ai Preferiti in Outlook, il contatto viene visualizzato nel gruppo Preferiti in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="76dd7-200">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="76dd7-201">Se si aggiungono e configurano il proxy XMPP e il gateway XMPP, gli utenti possono aggiungere contatti dai partner XMPP per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="76dd7-201">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="76dd7-202">La nuova funzionalità **Aggiungi contatto esterno all'organizzazione** consente di aggiungere facilmente persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-202">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="76dd7-203">Un nuovo gruppo **Preferiti** consente agli utenti di creare un elenco di persone contattate più di frequente per accedervi più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="76dd7-203">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="76dd7-p120">È possibile utilizzare la nuova pagina di opzioni **Elenco contatti** per scegliere la modalità di ordinamento e visualizzazione dei contatti. È possibile selezionare una visualizzazione espansa su due righe che include le immagini dei contatti oppure una visualizzazione ridotta su una riga. Gli utenti possono inoltre disporre i contatti in ordine alfabetico o di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="76dd7-207">Aggiornamenti per le conferenze</span><span class="sxs-lookup"><span data-stu-id="76dd7-207">Conferencing Updates</span></span>

<span data-ttu-id="76dd7-208">Lync 2013 offre numerosi miglioramenti alle funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="76dd7-208">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="76dd7-p121">A seconda del tipo di riunione, è ora possibile disattivare l'audio per il pubblico e consentire o impedire la condivisione del video in fase di pianificazione della riunione. Queste opzioni sono disponibili nella pagina **Opzioni riunione** ed è consigliabile utilizzarle per riunioni con più di 20 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="76dd7-211">I controlli audio di facile utilizzo nella sala riunioni consentono di controllare le opzioni per l'audio, ad esempio disattivare l'audio, riattivare l'audio, cambiare dispositivo e così via.</span><span class="sxs-lookup"><span data-stu-id="76dd7-211">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="76dd7-212">Per la condivisione dei programmi è ora possibile selezionare più programmi da condividere se si desidera utilizzare più di un programma.</span><span class="sxs-lookup"><span data-stu-id="76dd7-212">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="76dd7-213">È ora possibile caricare presentazioni che contengono clip video. È sufficiente caricare il file di PowerPoint e posizionare il mouse sulla diapositiva per visualizzare i controlli video, come i controlli di riproduzione e pausa, nonché i controlli audio.</span><span class="sxs-lookup"><span data-stu-id="76dd7-213">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="76dd7-214">Durante una riunione è possibile unire un'altra conversazione aperta scegliendo **Unisci la chiamata a** nel menu **Altre opzioni** (**…**).</span><span class="sxs-lookup"><span data-stu-id="76dd7-214">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="76dd7-215">Per visualizzare i nomi dei partecipanti, è possibile passare il mouse sul pulsante **Mostra partecipanti** oppure fare clic su **Mostra elenco partecipanti** per ancorare il pannello nella riunione.</span><span class="sxs-lookup"><span data-stu-id="76dd7-215">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="76dd7-216">A seconda del tipo di riunione, è possibile scegliere tra varie visualizzazioni diverse per contenuto e partecipanti.</span><span class="sxs-lookup"><span data-stu-id="76dd7-216">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="76dd7-p122">Le registrazioni delle riunioni vengono salvate automaticamente in un formato riproducibile in Windows Media Player (MP4). È possibile condividere facilmente il file con chiunque oppure utilizzare la funzionalità **Pubblica** in Gestione registrazioni per pubblicare la registrazione in una posizione condivisa.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="76dd7-p123">OneNote rende possibili nuovi scenari di collaborazione in una riunione. Durante una riunione è possibile aggiungere note con OneNote da utilizzare personalmente durante la riunione oppure utilizzare blocchi appunti condivisi per modificarli insieme agli altri partecipanti in tempo reale. Tutti i membri del team possono accedere alle note condivise per fornire il loro contributo, scambiarsi idee o utilizzare le pagine del blocco appunti come lavagna virtuale. Le persone e il contenuto condivisi nella riunione vengono aggiunti automaticamente alle note.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="76dd7-p124">È possibile passare da un tipo di contenuto all'altro tramite **Condividi contenuto e conduci attività di riunione** nella parte inferiore della sala riunioni. È inoltre possibile utilizzare il menu **Gestisci contenuto presentabile** per scegliere il contenuto da condividere.</span><span class="sxs-lookup"><span data-stu-id="76dd7-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76dd7-225">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76dd7-225">See Also</span></span>


[<span data-ttu-id="76dd7-226">Pianificazione per i client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76dd7-226">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

