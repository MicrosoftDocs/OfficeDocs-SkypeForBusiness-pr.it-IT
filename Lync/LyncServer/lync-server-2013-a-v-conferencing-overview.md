---
title: Panoramica di Lync Server 2013 A/V Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d77d39cfa1483db9251d038f876f8e91428ae23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="04068-102">Panoramica di A/V Conferencing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04068-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04068-103">_**Ultimo argomento modificato:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="04068-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="04068-104">A/V Conferencing consente di abilitare le comunicazioni audio e video in tempo reale tra gli utenti.</span><span class="sxs-lookup"><span data-stu-id="04068-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="04068-105">Quando si distribuisce il servizio di conferenza, è possibile scegliere di abilitare e utilizzare sia le conferenze Web che le conferenze audio/video oppure solo le conferenze Web.</span><span class="sxs-lookup"><span data-stu-id="04068-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="04068-106">Per la pianificazione delle conferenze audio/video è necessario conoscere i requisiti di larghezza di banda di rete dei vari tipi di supporti per le conferenze richiesti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="04068-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="04068-107">Questo potrebbe includere audio, video e video panoramici.</span><span class="sxs-lookup"><span data-stu-id="04068-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="04068-108">Prima di abilitare gli utenti per il servizio A/V Conferencing, verificare che la rete sia in grado di gestire il carico risultante.</span><span class="sxs-lookup"><span data-stu-id="04068-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="04068-109">Senza larghezza di banda di rete sufficiente, l'esperienza utente può essere gravemente degradata.</span><span class="sxs-lookup"><span data-stu-id="04068-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="04068-110">È possibile utilizzare il controllo di ammissione di chiamata per gestire la larghezza di banda di rete utilizzata da A/V Conferencing.</span><span class="sxs-lookup"><span data-stu-id="04068-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="04068-111">Questo è importante per le reti limitate, ad esempio collegamenti a larghezza di banda limitate tra i siti centrali e di succursale.</span><span class="sxs-lookup"><span data-stu-id="04068-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="04068-112">Per ulteriori informazioni, vedere [Panoramica del controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="04068-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="04068-113">Per informazioni dettagliate sui requisiti di larghezza di banda multimediale, vedere [requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="04068-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="04068-114">Se si distribuiscono audioconferenza in rete, gli utenti avranno bisogno di dispositivi audio come gli auricolari per partecipare a una conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="04068-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="04068-115">Se si distribuiscono video Conferencing, è necessario distribuire dispositivi video, ad esempio webcams per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="04068-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="04068-116">È consigliabile utilizzare i dispositivi Unified Communications (UC) certificati da Microsoft per tutti i tipi di dispositivi, per garantire un'esperienza utente ottimale.</span><span class="sxs-lookup"><span data-stu-id="04068-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="04068-117">Per informazioni dettagliate sui dispositivi certificati per le comunicazioni unificate, vedere "telefoni e dispositivi [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861)per Lync" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="04068-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="04068-118">Per i dispositivi audio o video, la distribuzione dei dispositivi e la formazione degli utenti sono passaggi importanti da considerare e pianificare.</span><span class="sxs-lookup"><span data-stu-id="04068-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="04068-119">Nelle sezioni seguenti vengono descritte le funzionalità per le conferenze audio e video, incluse le informazioni sulla gestione della larghezza di banda e la selezione dei client adatti.</span><span class="sxs-lookup"><span data-stu-id="04068-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="04068-120">Funzionalità di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="04068-120">Audio Conferencing Features</span></span>

<span data-ttu-id="04068-121">Lync Server 2013 offre diverse funzionalità che è possibile utilizzare per configurare l'esperienza di audioconferenza per l'utente, incluse le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04068-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="04068-122">**Disattivazione**   del gruppo il relatore può utilizzare questa impostazione per disattivare l'audio di tutti i partecipanti alla conferenza e inserire la conferenza in uno stato in cui non è possibile riattivare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="04068-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="04068-123">**Annunci di entrata/uscita**   per le conferenze se sono state abilitate le conferenze telefoniche con accesso esterno, i relatori possono utilizzare questa impostazione per attivare o disattivare gli annunci di entrata e uscita per ridurre al minimo le distrazioni mentre è in corso una conferenza.</span><span class="sxs-lookup"><span data-stu-id="04068-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="04068-124">**L'aggiunta di un utente tramite la composizione di**   relatori e partecipanti a cui è stata assegnata l'autorizzazione, può aggiungere numeri PSTN alle conferenze e fare in modo che la conferenza venga disattivata in questi numeri.</span><span class="sxs-lookup"><span data-stu-id="04068-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="04068-125">Funzionalità di conferenza video</span><span class="sxs-lookup"><span data-stu-id="04068-125">Video Conferencing Features</span></span>

<span data-ttu-id="04068-126">Lync Server 2013 offre diverse funzionalità che è possibile utilizzare per configurare l'esperienza di videoconferenza per l'utente, incluse le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04068-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="04068-127">**Visualizzazione raccolta nelle**   conferenze video con più di due persone, gli utenti visualizzano automaticamente tutti i partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="04068-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="04068-128">Se la conferenza ha più di cinque partecipanti, il video dei partecipanti più attivi viene visualizzato nella riga superiore e viene visualizzata solo la foto per gli altri partecipanti.</span><span class="sxs-lookup"><span data-stu-id="04068-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="04068-129">Il video a più parti è attivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="04068-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="04068-130">Per informazioni dettagliate sulla configurazione o la disattivazione del video in più parti, vedere [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="04068-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="04068-131">**Video panoramico**   se un dispositivo per conferenze video RoundTable è installato nella sala conferenze, questa funzionalità fornisce una visualizzazione completa di 360 gradi della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="04068-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="04068-132">La striscia panoramica video è disponibile solo con i dispositivi RoundTable.</span><span class="sxs-lookup"><span data-stu-id="04068-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="04068-133">**Relatore solo**   i presentatori della modalità video possono configurare la riunione in modo che venga visualizzato solo il video del relatore.</span><span class="sxs-lookup"><span data-stu-id="04068-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="04068-134">In questo modo si evitano le distrazioni nelle riunioni di grandi dimensioni quando sono disponibili più flussi video e si bloccano su origini diverse.</span><span class="sxs-lookup"><span data-stu-id="04068-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="04068-135">Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable.</span><span class="sxs-lookup"><span data-stu-id="04068-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="04068-136">\*\*\*\*   Gli utenti di video HD possono sperimentare risoluzioni fino a 1080p HD in chiamate a due parti e conferenze con più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="04068-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="04068-137">\*\*\*\*   I relatori video Spotlight possono configurare la riunione in modo che solo il video di un partecipante selezionato che sia un'origine video venga visualizzato dagli altri partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="04068-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="04068-138">Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable per il video panoramico.</span><span class="sxs-lookup"><span data-stu-id="04068-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

