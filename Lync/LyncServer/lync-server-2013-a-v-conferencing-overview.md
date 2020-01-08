---
title: Panoramica di Lync Server 2013 A/V Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="4c7a2-102">Panoramica delle conferenze A/V in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c7a2-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c7a2-103">_**Argomento Ultima modifica:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="4c7a2-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="4c7a2-104">A/V Conferencing consente le comunicazioni audio e video in tempo reale tra gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="4c7a2-105">Quando si distribuiscono i servizi di conferenza, è possibile scegliere di abilitare e usare servizi di conferenza Web e conferenze A/V o solo servizi di conferenza Web.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="4c7a2-106">Per pianificare i servizi di conferenza A/V, è necessario comprendere la larghezza di banda della rete necessaria per il tipo di supporto per i servizi di conferenza richiesto dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="4c7a2-107">Questo potrebbe includere l'audio, il video e il video panoramico.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="4c7a2-108">Prima di abilitare gli utenti per le conferenze A/V, assicurati che la rete possa gestire il carico risultante.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="4c7a2-109">Senza una sufficiente larghezza di banda della rete, l'esperienza utente potrebbe essere gravemente degradata.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="4c7a2-110">Puoi usare il controllo di ammissione chiamata (CAC) per gestire la larghezza di banda della rete usata da servizi di conferenza A/V.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="4c7a2-111">Questa operazione è importante per le reti con restrizioni, ad esempio i collegamenti a larghezza di banda limitati tra siti centrali e succursali.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="4c7a2-112">Per informazioni dettagliate, vedere [Panoramica del controllo di ammissione alle chiamate in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="4c7a2-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="4c7a2-113">Per informazioni dettagliate sui requisiti di larghezza di banda multimediali, vedere [requisiti di larghezza di banda della rete per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="4c7a2-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="4c7a2-114">Se si distribuiscono i servizi di audioconferenza nella rete, gli utenti avranno bisogno di dispositivi audio come auricolari per partecipare a una conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="4c7a2-115">Se si distribuiscono videoconferenze, è necessario distribuire dispositivi video, ad esempio webcam per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="4c7a2-116">Ti consigliamo di usare i dispositivi Unified Communications (UC) certificati da Microsoft per tutti i tipi di dispositivi, per garantire un'esperienza utente ottimale.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="4c7a2-117">Per informazioni dettagliate sui dispositivi certificati UC, vedere "telefoni e dispositivi per Lync" all' [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="4c7a2-118">Per i dispositivi audio o video, la distribuzione di dispositivi e la formazione degli utenti sono passaggi importanti da considerare e pianificare.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="4c7a2-119">Le sezioni seguenti descrivono le funzionalità per le conferenze audio e video, incluse le informazioni sulla gestione della larghezza di banda e la selezione dei client appropriati.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="4c7a2-120">Funzionalità di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="4c7a2-120">Audio Conferencing Features</span></span>

<span data-ttu-id="4c7a2-121">Lync Server 2013 offre diverse funzionalità che possono essere usate per configurare l'esperienza di audioconferenza per l'utente, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c7a2-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="4c7a2-122">**Disattivazione del pubblico**   il relatore può usare questa impostazione per disattivare l'audio di tutti i partecipanti alla conferenza e inserire la conferenza in uno stato in cui non è possibile riattivare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="4c7a2-123">**Annunci di entrata/uscita per conferenze**   se sono stati abilitati i servizi di conferenza telefonica con accesso esterno, i relatori possono usare questa impostazione per attivare o disattivare gli annunci di entrata e uscita per ridurre al minimo le distrazioni mentre è in corso una conferenza.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="4c7a2-124">**L'aggiunta di un utente tramite la chiamata di**   relatori e partecipanti a cui è stata assegnata l'autorizzazione può aggiungere numeri PSTN alle conferenze e effettuare la chiamata in uscita per i numeri.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="4c7a2-125">Funzionalità di conferenza video</span><span class="sxs-lookup"><span data-stu-id="4c7a2-125">Video Conferencing Features</span></span>

<span data-ttu-id="4c7a2-126">Lync Server 2013 offre diverse funzionalità che è possibile usare per configurare l'esperienza di videoconferenza per l'utente, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c7a2-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="4c7a2-127">**Visualizzazione raccolta in**   videoconferenze con più di due persone, gli utenti vedranno automaticamente tutti i partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="4c7a2-128">Se la conferenza include più di cinque partecipanti, il video dei partecipanti più attivi viene visualizzato nella riga superiore e viene visualizzata solo la foto per gli altri partecipanti.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="4c7a2-129">Il video a più parti è attivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="4c7a2-130">Per informazioni dettagliate sulla configurazione o disattivazione di un video con più parti, vedere [configurazione della larghezza di banda video in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="4c7a2-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="4c7a2-131">**Video panoramico**   se un dispositivo di videoconferenza RoundTable è installato nella sala conferenze, questa caratteristica offre una visualizzazione completa di 360 gradi della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="4c7a2-132">La striscia video panoramica è disponibile solo con i dispositivi RoundTable.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="4c7a2-133">**Relatore solo**   i presentatori della modalità video possono configurare la riunione in modo che venga visualizzato solo il video del relatore.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="4c7a2-134">In questo modo si evitano le distrazioni nelle riunioni di grandi dimensioni quando sono disponibili più flussi video e si bloccano in origini diverse.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="4c7a2-135">Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="4c7a2-136">\*\*\*\*   Gli utenti di video HD possono provare risoluzioni fino a 1080p HD in chiamate in due parti e conferenze multiparte.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="4c7a2-137">\*\*\*\*   I relatori dei riflettori video possono configurare la riunione in modo che solo il video di un partecipante selezionato che è un'origine video sia visibile dagli altri partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="4c7a2-138">Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable per il video panoramico.</span><span class="sxs-lookup"><span data-stu-id="4c7a2-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

