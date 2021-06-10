---
title: Configurare la funzionalità Chiamami per gli utenti
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare la funzionalità Chiamami in Teams in modo che gli utenti possano partecipare alla parte audio telefonicamente quando usano il computer per l'audio potrebbe non essere possibile.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623134"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="df9d2-103">Configurare la funzionalità Chiamami per gli utenti</span><span class="sxs-lookup"><span data-stu-id="df9d2-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="df9d2-104">In Microsoft Teams, la **funzionalità Chiamami** offre agli utenti un modo per partecipare alla parte audio di una riunione telefonicamente.</span><span class="sxs-lookup"><span data-stu-id="df9d2-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="df9d2-105">Questo è utile negli scenari in cui l'uso di un computer per l'audio potrebbe non essere possibile.</span><span class="sxs-lookup"><span data-stu-id="df9d2-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="df9d2-106">Gli utenti ottengono la parte audio della riunione tramite il cellulare o la linea di terra e la parte di contenuto della riunione, ad esempio quando un altro partecipante alla riunione condivide lo schermo o riproduce un video tramite il &mdash; &mdash; computer.</span><span class="sxs-lookup"><span data-stu-id="df9d2-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="df9d2-107">Nei periodi in cui il volume di riunioni è elevato (come abbiamo sperimentato durante l'epidemia di COVID-19), si consiglia agli utenti di partecipare alle riunioni facendo clic sul pulsante <strong>Partecipa alla riunione di Teams</strong> anziché chiamare utilizzando i numeri di conferenza PSTN o utilizzando <strong>Chiamami a</strong>.</span><span class="sxs-lookup"><span data-stu-id="df9d2-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="df9d2-108">In questo modo la qualità dell’audio è migliore durante i periodi in cui il numero elevato delle riunioni causa una congestione della rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="df9d2-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="df9d2-109">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="df9d2-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="df9d2-110">Partecipare a una riunione usando il telefono per l'audio</span><span class="sxs-lookup"><span data-stu-id="df9d2-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="df9d2-111">Fare **clic su** Partecipa per partecipare a una riunione, quindi Telefono **audio** nella schermata Scegli le opzioni video e **audio** e fare clic su Partecipa **ora**.</span><span class="sxs-lookup"><span data-stu-id="df9d2-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="df9d2-112">Da qui, gli utenti possono avere la chiamata alla riunione e partecipare o accedere manualmente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="df9d2-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Schermata dell'opzione Telefono audio](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="df9d2-114">**Consentire al Teams di una riunione**</span><span class="sxs-lookup"><span data-stu-id="df9d2-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="df9d2-115">Nella schermata **Usa telefono per l'audio,** l'utente immette il numero di telefono e quindi fa clic **su Chiama.**</span><span class="sxs-lookup"><span data-stu-id="df9d2-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="df9d2-116">La riunione chiama l'utente e lo partecipa alla riunione.</span><span class="sxs-lookup"><span data-stu-id="df9d2-116">The meeting calls the user and joins them to the meeting.</span></span>

![Schermata dell'opzione Chiamami nella schermata Usa telefono per l'audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="df9d2-118">**Effettuare l'accesso manualmente**</span><span class="sxs-lookup"><span data-stu-id="df9d2-118">**Dial in manually**</span></span>

<span data-ttu-id="df9d2-119">Un altro modo per partecipare è accedere direttamente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="df9d2-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="df9d2-120">Nella schermata Usa telefono per  **l'audio** fare clic su Accesso esterno manualmente per ottenere un elenco di numeri di telefono da usare per accedere alla riunione.</span><span class="sxs-lookup"><span data-stu-id="df9d2-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Schermata dell'opzione Accesso manuale](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="df9d2-122">Ricevere una chiamata quando si verifica un problema con l'audio durante una riunione</span><span class="sxs-lookup"><span data-stu-id="df9d2-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="df9d2-123">Se un utente verifica problemi audio quando usa il computer durante una riunione, può passare facilmente all'uso del telefono per l'audio.</span><span class="sxs-lookup"><span data-stu-id="df9d2-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="df9d2-124">Teams rileva quando si verifica un problema audio o dispositivo e reindirizza l'utente all'uso del telefono visualizzando l'opzione **Chiamami indietro.**</span><span class="sxs-lookup"><span data-stu-id="df9d2-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="df9d2-125">Ecco un esempio del messaggio  e dell'opzione Richiamami che viene visualizzata quando Teams non rileva un microfono.</span><span class="sxs-lookup"><span data-stu-id="df9d2-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Schermata dell'opzione Richiama](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="df9d2-127">L'utente fa clic **su Chiamami indietro**, che visualizza lo **schermo Usa telefono per l'audio.**</span><span class="sxs-lookup"><span data-stu-id="df9d2-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="df9d2-128">Da qui, possono immettere il proprio numero di telefono e fare Teams chiamata alla riunione e partecipare alla riunione o effettuare l'accesso manualmente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="df9d2-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="df9d2-129">Configurare la funzionalità Chiama</span><span class="sxs-lookup"><span data-stu-id="df9d2-129">Set up the Call me feature</span></span>

<span data-ttu-id="df9d2-130">Per abilitare la funzionalità Chiamami per gli utenti dell'organizzazione, è necessario configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="df9d2-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="df9d2-131">L'audioconferenza è abilitata per gli utenti dell'organizzazione che pianificano riunioni (organizzatori delle riunioni).</span><span class="sxs-lookup"><span data-stu-id="df9d2-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="df9d2-132">Per altre informazioni, vedere Configurare le audioconferenze [per](set-up-audio-conferencing-in-teams.md) Teams [e Gestire le impostazioni di audioconferenza](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)per un utente in Teams .</span><span class="sxs-lookup"><span data-stu-id="df9d2-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="df9d2-133">L'organizzatore della riunione può effettuare chiamate in uscita dalle riunioni.</span><span class="sxs-lookup"><span data-stu-id="df9d2-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="df9d2-134">Per altre informazioni, vedere [Gestire le impostazioni di audioconferenza per un utente in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="df9d2-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="df9d2-135">Se l'organizzatore della riunione non ha abilitato la chiamata in uscita dalle riunioni, l'opzione **audio Telefono** nella schermata Scegli le opzioni video e **audio** non è disponibile per nessuno e gli altri utenti non possono ricevere una chiamata per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="df9d2-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="df9d2-136">Per gli utenti con accesso esterno abilitato, dopo aver partecipato alla riunione, possono partecipare ad altri componendo il proprio numero **dall'icona Mostra partecipanti.**</span><span class="sxs-lookup"><span data-stu-id="df9d2-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
