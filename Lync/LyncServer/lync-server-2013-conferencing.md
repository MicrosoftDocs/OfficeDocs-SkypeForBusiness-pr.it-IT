---
title: 'Lync Server 2013: Servizi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f368a375a73eddc78b858c0d85a1bc21a1bd04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="f786b-102">Servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f786b-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f786b-103">_**Argomento Ultima modifica:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="f786b-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="f786b-104">Con le conferenze unificate in Lync Server 2013, gli utenti possono collaborare, condividere informazioni e coordinare i loro sforzi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f786b-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="f786b-105">Tutti gli utenti possono usare l'intera gamma di collaborazioni spontanee, riunioni pianificate e strumenti per riunioni.</span><span class="sxs-lookup"><span data-stu-id="f786b-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="f786b-106">Le funzionalità di conferenza vocale e video possono essere usate da qualsiasi posizione con una connessione Internet e gli utenti non possono partecipare a conferenze audio tramite la chiamata con un telefono PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="f786b-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="f786b-107">Gli strumenti di riunione integrati in Outlook consentono agli organizzatori di pianificare una riunione o iniziare una conferenza estemporanea con un solo clic e renderlo altrettanto facile per i partecipanti partecipare.</span><span class="sxs-lookup"><span data-stu-id="f786b-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="f786b-108">Un client Web estende le funzionalità di conferenza avanzate ai partecipanti che non hanno eseguito la versione desktop di Lync.</span><span class="sxs-lookup"><span data-stu-id="f786b-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="f786b-109">Conferenze audio e video</span><span class="sxs-lookup"><span data-stu-id="f786b-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="f786b-110">Lync Server offre un'esperienza utente familiare per gli utenti dei servizi di Bridge audio tradizionali, inclusi i servizi di accesso esterno PSTN con i comandi di controllo delle chiamate a tocco tonale.</span><span class="sxs-lookup"><span data-stu-id="f786b-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="f786b-111">Allo stesso tempo, incorpora potenti funzionalità di pianificazione, partecipazione e gestione disponibili solo con una piattaforma di comunicazioni unificata integrata.</span><span class="sxs-lookup"><span data-stu-id="f786b-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="f786b-112">Con un solo clic, gli utenti possono pianificare una riunione da Outlook.</span><span class="sxs-lookup"><span data-stu-id="f786b-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="f786b-113">I dettagli, ad esempio l'ora della riunione, la posizione e i partecipanti, seguono il modello familiare di Outlook.</span><span class="sxs-lookup"><span data-stu-id="f786b-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="f786b-114">Inoltre, le informazioni specifiche per le conferenze telefoniche, ad esempio il numero di accesso esterno, gli ID riunione e i promemoria PIN (Personal Identification Number), vengono popolati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f786b-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="f786b-115">Per assicurarti che solo le persone autorizzate partecipino a una chiamata, Lync Server offre più livelli di autenticazione per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f786b-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="f786b-116">Gli utenti che partecipano tramite Lync sono già autenticati da servizi di dominio Active Directory e non devono immettere un PIN, un codice di passaggio o un ID riunione.</span><span class="sxs-lookup"><span data-stu-id="f786b-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="f786b-117">Lync semplifica l'esperienza degli utenti di videoconferenza incorporando video nel client unificato, in modo che la programmazione di una riunione con video o l'escalation del video sia spontanea e semplice.</span><span class="sxs-lookup"><span data-stu-id="f786b-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="f786b-118">Lync Server semplifica l'aggiunta di video a una chiamata telefonica standard con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="f786b-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="f786b-119">Quando sono presenti più partecipanti a una videochiamata o a una conferenza, ogni utente può visualizzare il video da un massimo di cinque utenti contemporaneamente o un relatore può scegliere una sola origine video per essere visualizzata esclusivamente da tutti.</span><span class="sxs-lookup"><span data-stu-id="f786b-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="f786b-120">Video ad alta definizione (risoluzione 1270 x 720; proporzioni 16:9) e video VGA (risoluzione 640 x 480; proporzioni 4:3) sono supportati per le chiamate peer-to-peer tra gli utenti che eseguono Lync in computer di fascia alta.</span><span class="sxs-lookup"><span data-stu-id="f786b-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="f786b-121">La risoluzione visualizzata da ogni partecipante in una singola conversazione può essere diversa, a seconda delle funzionalità video del rispettivo hardware di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="f786b-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="f786b-122">Gli amministratori IT possono impostare criteri per limitare o disabilitare il video ad alta definizione o VGA nei client, a seconda della funzionalità del computer, della larghezza di banda della rete e della presenza di una fotocamera in grado di fornire la risoluzione necessaria.</span><span class="sxs-lookup"><span data-stu-id="f786b-122">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution.</span></span> <span data-ttu-id="f786b-123">Questi criteri vengono applicati tramite il provisioning in banda.</span><span class="sxs-lookup"><span data-stu-id="f786b-123">These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="f786b-124">Conferenza Web</span><span class="sxs-lookup"><span data-stu-id="f786b-124">Web conferencing</span></span>

<span data-ttu-id="f786b-125">Lync Server integra funzionalità di condivisione dei servizi di conferenza, ad esempio desktop, applicazioni, allegati, lavagne, sondaggi e PowerPoint, in Lync semplificato.</span><span class="sxs-lookup"><span data-stu-id="f786b-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="f786b-126">In combinazione con le conferenze audio o video, il risultato è una sessione altamente immersiva e collaborativa semplice da semplificare.</span><span class="sxs-lookup"><span data-stu-id="f786b-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="f786b-127">Per migliorare l'esperienza complessiva degli utenti che presentano o visualizzano presentazioni di PowerPoint, Lync Server 2013 impiega Office Web Apps per gestire le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f786b-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="f786b-128">Gli utenti possono condividere un'immagine o copiare e incollare testo usando una lavagna nella riunione Lync.</span><span class="sxs-lookup"><span data-stu-id="f786b-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="f786b-129">I relatori possono eseguire sondaggi nella riunione Lync per sollecitare il feedback dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f786b-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="f786b-130">La condivisione desktop consente ai relatori di trasmettere in tempo reale qualsiasi elemento visivo, applicazioni, pagine Web, documenti, software o parte dei propri desktop ai partecipanti remoti, direttamente da Lync.</span><span class="sxs-lookup"><span data-stu-id="f786b-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="f786b-131">I membri del gruppo di destinatari possono seguire i movimenti del mouse e l'input da tastiera.</span><span class="sxs-lookup"><span data-stu-id="f786b-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="f786b-132">I relatori possono scegliere di condividere l'intero schermo o solo una parte.</span><span class="sxs-lookup"><span data-stu-id="f786b-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="f786b-133">Condividendo i loro desktop, i relatori possono interagire con i loro destinatari in demo di prodotti o software interattivi da qualsiasi posizione.</span><span class="sxs-lookup"><span data-stu-id="f786b-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="f786b-134">La condivisione delle applicazioni consente ai relatori di condividere il controllo del software sui propri desktop senza perdere di vista il feedback dei partecipanti o le domande di testo.</span><span class="sxs-lookup"><span data-stu-id="f786b-134">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions.</span></span> <span data-ttu-id="f786b-135">I relatori possono anche delegare il controllo dell'applicazione ai partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f786b-135">Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="f786b-136">Servizi di conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="f786b-136">Dial-in Conferencing</span></span>

<span data-ttu-id="f786b-137">Per gli utenti che non usano un computer personale, sono disponibili diversi metodi per partecipare a una conferenza telefonica Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f786b-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="f786b-138">Un utente PSTN può chiamare un numero di accesso, accedere al Bridge della riunione e quindi immettere l'ID riunione.</span><span class="sxs-lookup"><span data-stu-id="f786b-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="f786b-139">Per riunioni più sicure, l'utente può anche essere obbligato a immettere il proprio PIN per l'autenticazione in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f786b-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="f786b-140">Lync Server supporta anche i dispositivi Lync Phone Edition, che sono dispositivi IP autonomi forniti da Microsoft partner.</span><span class="sxs-lookup"><span data-stu-id="f786b-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

