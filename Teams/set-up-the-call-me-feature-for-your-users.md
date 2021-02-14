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
description: Informazioni su come impostare la funzionalità Chiama in Teams in modo che gli utenti possano accedere alla parte audio tramite telefono quando usano il computer per l'audio potrebbe non essere possibile.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821096"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="43e17-103">Configurare la funzionalità Chiamami per gli utenti</span><span class="sxs-lookup"><span data-stu-id="43e17-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="43e17-104">In Microsoft Teams, la **funzione Chiamami** offre agli utenti un modo per partecipare alla parte audio di una riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="43e17-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="43e17-105">Questo è utile negli scenari in cui potrebbe non essere possibile usare un computer per l'audio.</span><span class="sxs-lookup"><span data-stu-id="43e17-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="43e17-106">Gli utenti ottengono la parte audio della riunione tramite telefono cellulare o rete mobile e il contenuto della riunione, ad esempio quando un altro partecipante alla riunione condivide lo schermo o riproduce un video tramite il &mdash; &mdash; proprio computer.</span><span class="sxs-lookup"><span data-stu-id="43e17-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="43e17-107">Nei periodi in cui il volume di riunioni è elevato (come abbiamo sperimentato durante l'epidemia di COVID-19), si consiglia agli utenti di partecipare alle riunioni facendo clic sul pulsante <strong>Partecipa alla riunione di Teams</strong> anziché chiamare utilizzando i numeri di conferenza PSTN o utilizzando <strong>Chiamami a</strong>.</span><span class="sxs-lookup"><span data-stu-id="43e17-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="43e17-108">In questo modo la qualità dell’audio è migliore durante i periodi in cui il numero elevato delle riunioni causa una congestione della rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="43e17-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="43e17-109">Nel corso dell'epidemia di COVID-19, si consiglia agli utenti di partecipare alle riunioni facendo clic sul pulsante **Partecipa alla riunione di Teams** anziché chiamare utilizzando i numeri della conferenza PSTN o utilizzando **Chiamami a**</strong>.</span><span class="sxs-lookup"><span data-stu-id="43e17-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="43e17-110">Ciò è principalmente dovuto alla congestione delle infrastrutture telefoniche dei paesi colpiti da COVID-19.</span><span class="sxs-lookup"><span data-stu-id="43e17-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="43e17-111">Evitando le chiamate PSTN, la qualità audio sarà probabilmente migliore.</span><span class="sxs-lookup"><span data-stu-id="43e17-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="43e17-112">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="43e17-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="43e17-113">Partecipare a una riunione tramite telefono per l'audio</span><span class="sxs-lookup"><span data-stu-id="43e17-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="43e17-114">Fare **clic** su Partecipa per partecipare a una riunione e quindi su **Audio telefono** nella schermata per la scelta delle impostazioni audio e **video.**</span><span class="sxs-lookup"><span data-stu-id="43e17-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="43e17-115">Da qui, gli utenti possono effettuare la chiamata alla riunione e parteciparvi o accedere manualmente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e17-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Schermata dell'opzione Audio telefono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="43e17-117">**Consentire la chiamata alla riunione di Teams**</span><span class="sxs-lookup"><span data-stu-id="43e17-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="43e17-118">Nella schermata **Usa il telefono per l'audio,** l'utente immette il suo numero di telefono e quindi fa clic su **Chiama.**</span><span class="sxs-lookup"><span data-stu-id="43e17-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="43e17-119">La riunione chiama l'utente e lo partecipa alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e17-119">The meeting calls the user and joins them to the meeting.</span></span>

![Schermata dell'opzione Chiamami nella schermata Usa il telefono per l'audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="43e17-121">**Accesso manuale**</span><span class="sxs-lookup"><span data-stu-id="43e17-121">**Dial in manually**</span></span>

<span data-ttu-id="43e17-122">Un altro modo per partecipare è effettuare l'accesso diretto alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e17-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="43e17-123">Nella schermata Usa il telefono  **per l'audio,** fai clic su Accesso esterno manualmente per ottenere un elenco di numeri di telefono da utilizzare per accedere alla riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="43e17-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Schermata dell'opzione Accesso manuale con accesso manuale](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="43e17-125">Ricevere una chiamata in caso di problemi con l'audio durante una riunione</span><span class="sxs-lookup"><span data-stu-id="43e17-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="43e17-126">Se si verificano problemi audio durante l'uso del computer durante una riunione, l'utente può passare facilmente all'uso del telefono per l'audio.</span><span class="sxs-lookup"><span data-stu-id="43e17-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="43e17-127">Teams rileva quando si verifica un problema audio o del dispositivo e reindirizza l'utente all'uso del telefono visualizzando un'opzione **Richiamami.**</span><span class="sxs-lookup"><span data-stu-id="43e17-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="43e17-128">Ecco un esempio del messaggio  e dell'opzione Richiamami che viene visualizzata quando Teams non rileva un microfono.</span><span class="sxs-lookup"><span data-stu-id="43e17-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Schermata dell'opzione Richiama](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="43e17-130">L'utente fa **clic su Richiama,** per vedere lo schermo **Usa il telefono per l'audio.**</span><span class="sxs-lookup"><span data-stu-id="43e17-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="43e17-131">Da qui, possono immettere il proprio numero di telefono e avere la chiamata alla riunione di Teams e unirli alla riunione o accedere manualmente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e17-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="43e17-132">Impostare la funzionalità Chiama</span><span class="sxs-lookup"><span data-stu-id="43e17-132">Set up the Call me feature</span></span>

<span data-ttu-id="43e17-133">Per abilitare la funzionalità Chiamami per gli utenti dell'organizzazione, è necessario configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="43e17-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="43e17-134">L'audioconferenza è abilitata per gli utenti dell'organizzazione che pianificano riunioni (organizzatori di riunioni).</span><span class="sxs-lookup"><span data-stu-id="43e17-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="43e17-135">Per ulteriori informazioni, consulta [Configurare le audioconferenze per Teams](set-up-audio-conferencing-in-teams.md) e gestire le impostazioni di [audioconferenza per un utente in Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="43e17-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="43e17-136">Gli utenti possono effettuare chiamate in uscita dalle riunioni.</span><span class="sxs-lookup"><span data-stu-id="43e17-136">Users can dial out from meetings.</span></span> <span data-ttu-id="43e17-137">Per ulteriori informazioni, consulta [Gestire le impostazioni di audioconferenza per un utente in Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="43e17-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="43e17-138">Se un utente non ha la chiamata  in uscita dalle riunioni abilitata, l'opzione Chiama non è disponibile e l'utente non riceverà una chiamata per parteciparvi alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e17-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="43e17-139">L'utente vede invece un elenco di numeri di telefono nello schermo Usa il telefono per **l'audio,** che può usare per accedere manualmente alla riunione sul proprio telefono.</span><span class="sxs-lookup"><span data-stu-id="43e17-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
