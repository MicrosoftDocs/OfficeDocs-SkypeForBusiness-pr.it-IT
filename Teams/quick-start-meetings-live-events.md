---
title: Guida introduttiva per l'amministratore - Riunioni ed eventi live in Microsoft Teams
ms.reviewer: ''
description: Introduzione rapida alle riunioni e agli eventi live in Microsoft Teams.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec86d9f57afca71624263d1cbd6ca212b8093dd
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157975"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="4ad76-103">Guida introduttiva per l'amministratore - Riunioni ed eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ad76-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="4ad76-104">Ci sono due modi per incontrarsi in Microsoft Teams: riunioni ed eventi live.</span><span class="sxs-lookup"><span data-stu-id="4ad76-104">There are 2 ways to meet in Microsoft Teams - meetings and live events.</span></span> <span data-ttu-id="4ad76-105">Questo articolo illustra come implementare e configurare rapidamente riunioni ed eventi live per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ad76-105">Use this article to quickly roll out and configure meetings and live events for your organization.</span></span> 

 - <span data-ttu-id="4ad76-106">Le **riunioni** in Teams includono audio, video e condivisione dello schermo con un massimo di 250 persone.</span><span class="sxs-lookup"><span data-stu-id="4ad76-106">**Meetings** in Teams include audio, video, and screen sharing for up to 250 people.</span></span> <span data-ttu-id="4ad76-107">Sono uno dei modi principali per collaborare in Teams.</span><span class="sxs-lookup"><span data-stu-id="4ad76-107">They're one of the key ways to collaborate in Teams.</span></span> <span data-ttu-id="4ad76-108">Inoltre, non è necessario essere membri di un'organizzazione (né avere un account Teams) per partecipare a una riunione di Teams: nell'invito sono incluse tutte le istruzioni per collegarsi.</span><span class="sxs-lookup"><span data-stu-id="4ad76-108">And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span> 

 - <span data-ttu-id="4ad76-109">Gli **eventi live** sono un'estensione delle riunioni di Teams. Permettono di pianificare e produrre eventi da trasmettere a un vasto pubblico online, fino a 10.000 persone.</span><span class="sxs-lookup"><span data-stu-id="4ad76-109">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people.</span></span> <span data-ttu-id="4ad76-110">Per una riunione con più di 250 persone, usare un evento live.</span><span class="sxs-lookup"><span data-stu-id="4ad76-110">If you need a meeting for more than 250 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="4ad76-111">Ottenere le licenze per le riunioni e gli eventi live</span><span class="sxs-lookup"><span data-stu-id="4ad76-111">Get licenses for meetings and live events</span></span>

<span data-ttu-id="4ad76-112">Chiunque può partecipare gratuitamente a una riunione o a un evento live di Teams. Non è necessaria una licenza.</span><span class="sxs-lookup"><span data-stu-id="4ad76-112">Anyone can attend a Teams meeting or live event for free - no license is required.</span></span> <span data-ttu-id="4ad76-113">Per partecipare a una riunione o a un evento live di Teams, è sufficiente fare clic sul pulsante **Partecipa** in Teams o nell'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="4ad76-113">Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation.</span></span> <span data-ttu-id="4ad76-114">L'audio della riunione è incluso in una riunione di Teams, ma se si vuole consentire agli utenti di accedere a una riunione tramite telefono, è necessario specificare un numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="4ad76-114">Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span> 

<span data-ttu-id="4ad76-115">Le persone che intendono organizzare, pianificare o condurre riunioni o eventi live devono disporre di una delle licenze di Microsoft 365 o Office 365 elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4ad76-115">For the people who will organize, schedule, and host meetings or live events, they'll need one of the Microsoft 365 or Office 365 licenses listed in the table below.</span></span> <span data-ttu-id="4ad76-116">Se si usa già Teams, è probabile che si abbia la licenza necessaria per organizzare e condurre riunioni ed eventi live.</span><span class="sxs-lookup"><span data-stu-id="4ad76-116">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span> 

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="Tabella con le licenze necessarie per le riunioni o gli eventi live di Teams":::

> <span data-ttu-id="4ad76-118"><sup>1</sup> Gli organizzatori delle riunioni devono avere una [licenza per il componente aggiuntivo Audioconferenza](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per inviare un invito che include una conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="4ad76-118"><sup>1</sup>  Meeting organizers need to have an [Audio Conferencing add-on license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) to send an invite that includes dial-in conferencing.</span></span>
>
> <span data-ttu-id="4ad76-119"><sup>2</sup> Per una riunione con chiamata in uscita a un numero [**Chiamami al numero**, ](set-up-the-call-me-feature-for-your-users.md) gli organizzatori devono avere una licenza di E5 o una [licenza per il componente aggiuntivo Audioconferenza](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4ad76-119"><sup>2</sup>  Meeting dial out to a [**Call me at** number](set-up-the-call-me-feature-for-your-users.md) requires organizers to have an E5 or [Audio Conference add-in license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> <span data-ttu-id="4ad76-120">Può essere necessario anche un [dial plan](what-are-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="4ad76-120">A [dial plan](what-are-dial-plans.md) may also be needed.</span></span> 


<span data-ttu-id="4ad76-121">Per altre informazioni sulle licenze, vedere [Gestione delle licenze di Office 365 per Teams](Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4ad76-121">To learn more about licensing, read [Office 365 licensing for Teams](Office-365-licensing.md).</span></span> 

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="4ad76-122">Assicurarsi che la rete sia pronta</span><span class="sxs-lookup"><span data-stu-id="4ad76-122">Make sure your network's ready</span></span>

<span data-ttu-id="4ad76-123">Se la rete è già stata preparata durante la distribuzione di Microsoft 365 o Office 365, è probabile che sia tutto pronto.</span><span class="sxs-lookup"><span data-stu-id="4ad76-123">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set.</span></span> <span data-ttu-id="4ad76-124">In ogni caso, e soprattutto se si sta implementando rapidamente Teams come primo carico di lavoro di Office 365 per supportare i **lavoratori remoti**, vedere [Preparare la rete dell'organizzazione per Teams](prepare-network.md) per assicurarsi che sia tutto pronto.</span><span class="sxs-lookup"><span data-stu-id="4ad76-124">In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="4ad76-125">Riunioni e conferenze</span><span class="sxs-lookup"><span data-stu-id="4ad76-125">Meetings and conferencing</span></span>

- <span data-ttu-id="4ad76-126">L'amministratore deve configurare le [impostazioni della riunione](meeting-settings-in-teams.md) per tutti.</span><span class="sxs-lookup"><span data-stu-id="4ad76-126">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone.</span></span> <span data-ttu-id="4ad76-127">Quindi userà i [criteri riunione](meeting-policies-in-teams.md) per controllare quali funzionalità delle riunioni sono o non sono disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ad76-127">Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span> 

- <span data-ttu-id="4ad76-128">Se gli utenti non hanno familiarità con le riunioni di Teams, condividere il training [Gestire riunioni](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4).</span><span class="sxs-lookup"><span data-stu-id="4ad76-128">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them.</span></span> <span data-ttu-id="4ad76-129">Seguire il corso online con docente su come [organizzare riunioni efficaci con Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span><span class="sxs-lookup"><span data-stu-id="4ad76-129">Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="4ad76-130">Per informazioni sulla gestione delle opzioni per una riunione, vedere [Modificare le impostazioni dei partecipanti per una riunione Teams](https://support.microsoft.com/office/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span><span class="sxs-lookup"><span data-stu-id="4ad76-130">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/office/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="4ad76-131">Non dimenticare la [gestione dei dispositivi degli utenti](device-management.md), quali telefoni, auricolari e videocamere.</span><span class="sxs-lookup"><span data-stu-id="4ad76-131">Don't forget about [managing your users' devices](device-management.md) - phones, headsets, cameras.</span></span> <span data-ttu-id="4ad76-132">Per informazioni più recenti e aggiornate sui dispositivi certificati per Teams, passare a [Dispositivi Teams](https://office.com/teamsdevices).</span><span class="sxs-lookup"><span data-stu-id="4ad76-132">To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="4ad76-133">Eventi live</span><span class="sxs-lookup"><span data-stu-id="4ad76-133">Live events</span></span>

- <span data-ttu-id="4ad76-134">Analogamente alle riunioni, l'amministratore [configura gli eventi live](teams-live-events/configure-teams-live-events.md) per tutti.</span><span class="sxs-lookup"><span data-stu-id="4ad76-134">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone.</span></span> <span data-ttu-id="4ad76-135">Quindi configura (e assegna) [criteri dell'evento live](teams-live-events/set-up-for-teams-live-events.md) per controllare ciò che gli utenti possono e non possono fare.</span><span class="sxs-lookup"><span data-stu-id="4ad76-135">Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="4ad76-136">Per assicurarsi che i produttori e gli organizzatori degli eventi live siano formati, consigliare la lettura di [Introduzione agli eventi live](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span><span class="sxs-lookup"><span data-stu-id="4ad76-136">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="4ad76-137">Se non si ha familiarità con gli eventi live, vedere [Che cosa sono gli eventi live di Teams?](teams-live-events/what-are-teams-live-events.md) e [Pianificare gli eventi live di Teams](teams-live-events/plan-for-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="4ad76-137">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4ad76-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4ad76-138">Related topics</span></span>

[<span data-ttu-id="4ad76-139">Riunioni e conferenze in Teams</span><span class="sxs-lookup"><span data-stu-id="4ad76-139">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="4ad76-140">Audioconferenza in Teams</span><span class="sxs-lookup"><span data-stu-id="4ad76-140">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="4ad76-141">Eventi live in Teams</span><span class="sxs-lookup"><span data-stu-id="4ad76-141">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="4ad76-142">Limiti e specifiche per Teams</span><span class="sxs-lookup"><span data-stu-id="4ad76-142">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)