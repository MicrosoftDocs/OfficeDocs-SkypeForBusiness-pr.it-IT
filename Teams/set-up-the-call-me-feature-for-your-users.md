---
title: Configurare la funzionalità Chiamami per gli utenti
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare la funzionalità Chiamami in teams in modo che gli utenti possano accedere alla parte audio per telefono quando l'uso del computer per l'audio potrebbe non essere possibile.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2343ce76e404ce2462cdbfc443130058112dcc4
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140859"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="43e4e-103">Configurare la funzionalità Chiamami per gli utenti</span><span class="sxs-lookup"><span data-stu-id="43e4e-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="43e4e-104">In Microsoft teams, la funzionalità **chiamami** offre agli utenti un modo per partecipare alla parte audio di una riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="43e4e-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="43e4e-105">Questa operazione è utile in scenari in cui l'uso di un computer per l'audio potrebbe non essere possibile.</span><span class="sxs-lookup"><span data-stu-id="43e4e-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="43e4e-106">Gli utenti ottengono la parte audio della riunione tramite il telefono cellulare o la linea di terra e la parte di contenuto&mdash;della riunione, quando un altro partecipante alla riunione condivide lo schermo&mdash;o riproduce un video nel computer.</span><span class="sxs-lookup"><span data-stu-id="43e4e-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43e4e-107">Nel corso dell'epidemia di COVID-19, si consiglia agli utenti di partecipare alle riunioni facendo clic sul pulsante **Partecipa alla riunione di Teams** anziché chiamare utilizzando i numeri della conferenza PSTN o utilizzando **Chiamami a**</strong>.</span><span class="sxs-lookup"><span data-stu-id="43e4e-107">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="43e4e-108">Ciò è principalmente dovuto alla congestione delle infrastrutture telefoniche dei paesi colpiti da COVID-19.</span><span class="sxs-lookup"><span data-stu-id="43e4e-108">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="43e4e-109">Evitando le chiamate PSTN, la qualità audio sarà probabilmente migliore.</span><span class="sxs-lookup"><span data-stu-id="43e4e-109">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="43e4e-110">Esperienza utente</span><span class="sxs-lookup"><span data-stu-id="43e4e-110">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="43e4e-111">Partecipare a una riunione tramite telefono per l'audio</span><span class="sxs-lookup"><span data-stu-id="43e4e-111">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="43e4e-112">Fare clic su **partecipa** per partecipare a una riunione e quindi fare clic su **audio telefono** nella schermata **Scegli impostazioni audio e video** .</span><span class="sxs-lookup"><span data-stu-id="43e4e-112">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="43e4e-113">Da qui gli utenti possono avere la chiamata di riunione e unirli o connettersi manualmente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e4e-113">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Screenshot dell'opzione audio telefono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="43e4e-115">**Consentire la chiamata alla riunione Teams**</span><span class="sxs-lookup"><span data-stu-id="43e4e-115">**Let the Teams meeting call**</span></span>

<span data-ttu-id="43e4e-116">Nella schermata **Usa telefono per l'audio** l'utente immette il proprio numero di telefono e quindi fa clic su **chiamami**.</span><span class="sxs-lookup"><span data-stu-id="43e4e-116">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="43e4e-117">La riunione chiama l'utente e li unisce alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e4e-117">The meeting calls the user and joins them to the meeting.</span></span>

![Screenshot dell'opzione chiamami nella schermata Usa telefono per l'audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="43e4e-119">**Componi manualmente**</span><span class="sxs-lookup"><span data-stu-id="43e4e-119">**Dial in manually**</span></span>

<span data-ttu-id="43e4e-120">Un altro modo per partecipare consiste nel connettersi direttamente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e4e-120">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="43e4e-121">Nella schermata **Usa telefono per audio** fare clic su **Componi manualmente** per ottenere un elenco di numeri di telefono da usare per connettersi alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e4e-121">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Screenshot dell'opzione Componi manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="43e4e-123">Ottenere una chiamata quando si verifica un problema con l'audio durante una riunione</span><span class="sxs-lookup"><span data-stu-id="43e4e-123">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="43e4e-124">Se un utente avverte problemi di audio quando si usa il proprio computer durante una riunione, l'utente può facilmente passare a usare il telefono per l'audio.</span><span class="sxs-lookup"><span data-stu-id="43e4e-124">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="43e4e-125">Teams rileva quando si verifica un problema di audio o dispositivo e reindirizza l'utente a usare il telefono visualizzando l'opzione **chiamami** .</span><span class="sxs-lookup"><span data-stu-id="43e4e-125">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="43e4e-126">Ecco un esempio del messaggio e l'opzione **chiamami di nuovo** visualizzata quando i team non rilevano un microfono.</span><span class="sxs-lookup"><span data-stu-id="43e4e-126">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Schermata dell'opzione chiamami di nuovo](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="43e4e-128">L'utente fa clic su **richiama me back**, che porta in alto il **telefono uso per** lo schermo audio.</span><span class="sxs-lookup"><span data-stu-id="43e4e-128">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="43e4e-129">Da qui è possibile immettere il proprio numero di telefono e convocare la riunione di teams per partecipare alla riunione o connettersi manualmente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e4e-129">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="43e4e-130">Configurare la caratteristica chiamami</span><span class="sxs-lookup"><span data-stu-id="43e4e-130">Set up the Call me feature</span></span>

<span data-ttu-id="43e4e-131">Per abilitare la funzionalità chiamami per gli utenti dell'organizzazione, è necessario configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43e4e-131">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="43e4e-132">I servizi di audioconferenza sono abilitati per gli utenti dell'organizzazione che pianificano riunioni (organizzatori di riunioni).</span><span class="sxs-lookup"><span data-stu-id="43e4e-132">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="43e4e-133">Per altre informazioni, vedere [configurare le conferenze audio per i team](set-up-audio-conferencing-in-teams.md) e [gestire le impostazioni di audioconferenza per un utente in teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="43e4e-133">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="43e4e-134">Gli utenti possono effettuare la chiamata fuori dalle riunioni.</span><span class="sxs-lookup"><span data-stu-id="43e4e-134">Users can dial out from meetings.</span></span> <span data-ttu-id="43e4e-135">Per altre informazioni, vedere [gestire le impostazioni di audioconferenza per un utente in teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="43e4e-135">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="43e4e-136">Se un utente non ha attivato la chiamata in uscita dalle riunioni, l'opzione **chiamami** non è disponibile e l'utente non riceverà una chiamata per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="43e4e-136">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="43e4e-137">L'utente vede invece un elenco di numeri di telefono nella schermata **Usa telefono per l'audio** che possono usare per effettuare la chiamata manualmente alla riunione sul telefono.</span><span class="sxs-lookup"><span data-stu-id="43e4e-137">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
