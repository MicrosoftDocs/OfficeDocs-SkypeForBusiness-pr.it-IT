---
title: Lync Server 2013 Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecfca21d1cd7151cb48db8a165dbea00acdae560
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507823"
---
# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="fb38c-102">Servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb38c-102">Conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb38c-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="fb38c-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="fb38c-104">Con Unified Conferencing in Lync Server 2013, gli utenti possono collaborare, condividere informazioni e coordinare i propri sforzi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="fb38c-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="fb38c-105">Tutti gli utenti possono avvalersi dell'intera gamma di strumenti per la collaborazione spontanea, le riunioni pianificate e le riunioni.</span><span class="sxs-lookup"><span data-stu-id="fb38c-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="fb38c-106">Le funzionalità per conferenze audio e video possono essere utilizzate da qualsiasi posizione con una connessione Internet e gli utenti lontani da un computer possono partecipare a conferenze audio chiamando con un telefono PSTN (Public Switched Telephone Network) .</span><span class="sxs-lookup"><span data-stu-id="fb38c-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="fb38c-107">Gli strumenti per riunioni integrati in Outlook consentono agli organizzatori di pianificare una riunione o avviare una conferenza improvvisata con un solo clic e rendere altrettanto semplice per i partecipanti partecipare.</span><span class="sxs-lookup"><span data-stu-id="fb38c-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="fb38c-108">Un client Web estende le funzionalità di conferenza ricche ai partecipanti che non eseguono la versione desktop di Lync.</span><span class="sxs-lookup"><span data-stu-id="fb38c-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="fb38c-109">Conferenze audio e video</span><span class="sxs-lookup"><span data-stu-id="fb38c-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="fb38c-110">Lync Server fornisce un'esperienza utente che ha familiarità con gli utenti dei servizi di Bridge audio tradizionali, compresi i servizi di accesso esterno PSTN con i comandi di controllo delle chiamate Touch-Tone.</span><span class="sxs-lookup"><span data-stu-id="fb38c-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="fb38c-111">Sono allo stesso tempo incluse funzionalità avanzate per pianificazione, partecipazione e gestione disponibili solo con una piattaforma di comunicazioni unificate integrata.</span><span class="sxs-lookup"><span data-stu-id="fb38c-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="fb38c-112">Con un solo clic, gli utenti possono programmare una riunione da Outlook.</span><span class="sxs-lookup"><span data-stu-id="fb38c-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="fb38c-113">I dettagli, ad esempio la durata della riunione, la posizione e i partecipanti, seguono il modello di Outlook noto.</span><span class="sxs-lookup"><span data-stu-id="fb38c-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="fb38c-114">Inoltre, vengono inserite automaticamente informazioni specifiche per le chiamate di conferenza, ad esempio il numero di accesso esterno, gli ID riunione e i promemoria PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="fb38c-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="fb38c-115">Per garantire che solo le persone autorizzate partecipino a una chiamata, Lync Server fornisce più livelli di autenticazione per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="fb38c-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="fb38c-116">Gli utenti che si connettono utilizzando Lync sono già autenticati da servizi di dominio Active Directory e non devono immettere un PIN, un codice di passaggio o un ID riunione.</span><span class="sxs-lookup"><span data-stu-id="fb38c-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="fb38c-117">Lync semplifica l'esperienza utente per le conferenze video incorporando video nel client unificato, in modo che la pianificazione di una riunione con video o l'escalation del video sia spontanea e senza problemi.</span><span class="sxs-lookup"><span data-stu-id="fb38c-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="fb38c-118">Lync Server rende più semplice aggiungere video a una chiamata telefonica standard con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="fb38c-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="fb38c-119">Se alla chiamata video o a una conferenza partecipano più utenti, ogni utente può vedere il video di un massimo di cinque altri utenti contemporaneamente e un relatore può scegliere una sola origine video per essere l'unico a essere visibile per tutti i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="fb38c-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="fb38c-120">Video ad alta definizione (risoluzione 1270 x 720; proporzioni 16:9) e video VGA (risoluzione 640 x 480; proporzioni 4:3) sono supportati per le chiamate peer-to-peer tra gli utenti che eseguono Lync nei computer di fascia alta.</span><span class="sxs-lookup"><span data-stu-id="fb38c-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="fb38c-121">La risoluzione disponibile per ogni partecipante a una singola conversazione può essere diversa, a seconda delle capacità video del rispettivo hardware di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="fb38c-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="fb38c-p108">Gli amministratori IT possono impostare criteri per limitare o disabilitare il video ad alta definizione o VGA nei client, in base alle caratteristiche del computer, alla larghezza di banda della rete e alla presenza di videocamere in grado di offrire la risoluzione richiesta. Questi criteri vengono applicati tramite il provisioning di tipo in-band.</span><span class="sxs-lookup"><span data-stu-id="fb38c-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="fb38c-124">Conferenze Web</span><span class="sxs-lookup"><span data-stu-id="fb38c-124">Web conferencing</span></span>

<span data-ttu-id="fb38c-125">Lync Server integra funzionalità di condivisione delle conferenze quali desktop, applicazioni, allegati, lavagne, poll e PowerPoint nel Lync semplificato.</span><span class="sxs-lookup"><span data-stu-id="fb38c-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="fb38c-126">In combinazione con le funzionalità per conferenze audio o video, il risultato è una sessione di collaborazione molto coinvolgente e facile da coordinare.</span><span class="sxs-lookup"><span data-stu-id="fb38c-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="fb38c-127">Per migliorare l'esperienza complessiva degli utenti che presentano o visualizzano presentazioni di PowerPoint, Lync Server 2013 utilizza Office Web Apps per gestire le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="fb38c-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="fb38c-128">Gli utenti possono condividere un'immagine o copiare e incollare il testo utilizzando una lavagna nella riunione di Lync.</span><span class="sxs-lookup"><span data-stu-id="fb38c-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="fb38c-129">I relatori possono effettuare sondaggi nella riunione di Lync per richiedere commenti e suggerimenti da parte dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="fb38c-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="fb38c-130">La condivisione desktop consente ai relatori di trasmettere in tempo reale eventuali elementi visivi, applicazioni, pagine Web, documenti, software o parte dei desktop ai partecipanti remoti, direttamente da Lync.</span><span class="sxs-lookup"><span data-stu-id="fb38c-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="fb38c-131">I partecipanti possono seguire anche i movimenti del mouse e le immissioni da tastiera.</span><span class="sxs-lookup"><span data-stu-id="fb38c-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="fb38c-132">I relatori possono scegliere di condividere l'intero schermo o solo una parte.</span><span class="sxs-lookup"><span data-stu-id="fb38c-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="fb38c-133">Con la condivisione dei desktop, i relatori possono intrattenere il pubblico con dimostrazioni di prodotti o software interattive da qualsiasi luogo.</span><span class="sxs-lookup"><span data-stu-id="fb38c-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="fb38c-p112">Con la condivisione delle applicazioni i relatori possono condividere il controllo del software sul desktop senza perdere di vista i commenti e suggerimenti o le domande testuali dei partecipanti. I relatori hanno inoltre la possibilità di delegare il controllo dell'applicazione ai partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="fb38c-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="fb38c-136">Conferenza telefonica con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="fb38c-136">Dial-in Conferencing</span></span>

<span data-ttu-id="fb38c-137">Per gli utenti che non utilizzano un computer personale, sono disponibili diversi metodi per l'aggiunta di una conferenza telefonica di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb38c-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="fb38c-138">Un utente PSTN può comporre un numero di accesso, accedere al ponte della riunione e quindi immettere l'ID della riunione.</span><span class="sxs-lookup"><span data-stu-id="fb38c-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="fb38c-139">Per una maggiore sicurezza delle riunioni, è inoltre possibile che all'utente venga richiesto di immettere il PIN per l'autenticazione in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb38c-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="fb38c-140">Lync Server supporta anche i dispositivi Lync Phone Edition, che sono dispositivi IP di telefonia autonoma forniti da Microsoft Partners.</span><span class="sxs-lookup"><span data-stu-id="fb38c-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

