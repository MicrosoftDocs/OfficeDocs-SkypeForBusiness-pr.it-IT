---
title: Guida introduttiva per l'amministratore - Riunioni ed eventi live in Microsoft Teams
ms.reviewer: ''
description: Guida introduttiva per amministratori su come ottenere le licenze, distribuire e configurare riunioni online ed eventi live in Microsoft Teams.
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03611f2d166883ce960e272e2f3b11300cd20c54
ms.sourcegitcommit: 616b6d0d5be2b333519b79ab59a4117036ba647e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363581"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="3680e-103">Guida introduttiva per l'amministratore - Riunioni ed eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3680e-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="3680e-p101">Esistono due modi per incontrarsi in Microsoft Teams: riunioni ed eventi live. Questo articolo illustra come implementare e configurare rapidamente riunioni ed eventi live per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3680e-p101">There are 2 ways to meet in Microsoft Teams - meetings and live events. Use this article to quickly roll out and configure meetings and live events for your organization.</span></span>

> [!Note]
> <span data-ttu-id="3680e-106">Per informazioni dettagliate sulla configurazione rapida delle riunioni e degli eventi di Teams su diverse piattaforme, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="3680e-106">For details about quickly configuring Teams meetings and events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

 - <span data-ttu-id="3680e-p102">Le **riunioni** in Teams includono audio, video e condivisione dello schermo per un massimo di 1000 persone. Sono uno dei modi principali per collaborare in Teams. Inoltre, non è necessario essere membri di un'organizzazione (né avere un account Teams) per partecipare a una riunione di Teams: nell'invito sono incluse tutte le istruzioni per collegarsi.</span><span class="sxs-lookup"><span data-stu-id="3680e-p102">**Meetings** in Teams include audio, video, and screen sharing for up to 1000 people. They're one of the key ways to collaborate in Teams. And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span>

 - <span data-ttu-id="3680e-p103">Gli **eventi live** sono un'estensione delle riunioni di Teams. Permettono di pianificare e produrre eventi da trasmettere a un vasto pubblico online, fino a 10.000 persone. Per una riunione con più di 1000 persone, usare un evento live.</span><span class="sxs-lookup"><span data-stu-id="3680e-p103">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people. If you need a meeting for more than 1000 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="3680e-112">Ottenere licenze per riunioni ed eventi live</span><span class="sxs-lookup"><span data-stu-id="3680e-112">Get licenses for meetings and live events</span></span>

<span data-ttu-id="3680e-p104">Chiunque può partecipare gratuitamente a una riunione o a un evento live pubblico di Teams. Non è necessaria una licenza. Per partecipare a una riunione o a un evento live di Teams, è sufficiente fare clic sul pulsante **Partecipa** in Teams o nell'invito alla riunione. L'audio della riunione è incluso in una riunione di Teams, ma se vuoi consentire agli utenti di accedere a una riunione tramite telefono, si dovrà specificare un numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3680e-p104">Anyone can attend a Teams meeting or public live event for free - no license is required. Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation. Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span>

<span data-ttu-id="3680e-116">Le persone che intendono organizzare, pianificare o condurre riunioni o eventi live devono disporre di uno dei piani di licenza indicati nella [descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="3680e-116">For the people who will organize, schedule, and host meetings or live events, they'll need one of the licensing plans described in the [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span> 

<span data-ttu-id="3680e-117">Se usi già Teams, è probabile che tu abbia la licenza necessaria per organizzare e condurre riunioni ed eventi live.</span><span class="sxs-lookup"><span data-stu-id="3680e-117">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span>

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="3680e-118">Assicurarsi che la rete sia pronta</span><span class="sxs-lookup"><span data-stu-id="3680e-118">Make sure your network's ready</span></span>

<span data-ttu-id="3680e-p105">Se la rete è già stata preparata durante la distribuzione di Microsoft 365 o Office 365, è probabile che sia tutto pronto. In ogni caso, e soprattutto se si implementando rapidamente Teams come primo carico di lavoro di Office 365 per supportare i **lavoratori remoti**, vedere [Preparare la rete dell'organizzazione per Teams](prepare-network.md) per assicurarti che sia tutto pronto.</span><span class="sxs-lookup"><span data-stu-id="3680e-p105">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set. In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="3680e-121">Riunioni e conferenze</span><span class="sxs-lookup"><span data-stu-id="3680e-121">Meetings and conferencing</span></span>

- <span data-ttu-id="3680e-p106">L'amministratore deve configurare le [impostazioni della riunione](meeting-settings-in-teams.md) per tutti. Quindi userà i [criteri riunione](meeting-policies-in-teams.md) per controllare quali funzionalità delle riunioni sono o non sono disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3680e-p106">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone. Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span>

- <span data-ttu-id="3680e-124">Per informazioni su come gestire la registrazione di una riunione, leggere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).</span><span class="sxs-lookup"><span data-stu-id="3680e-124">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="3680e-p107">Se gli utenti non hanno familiarità con le riunioni di Teams, condividi il training [Gestire riunioni](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4). Consultare il corso online con istruttore [Condurre riunioni efficaci con Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span><span class="sxs-lookup"><span data-stu-id="3680e-p107">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them. Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="3680e-127">Per informazioni sulla gestione delle opzioni per una riunione, vedi [Modificare le impostazioni dei partecipanti per una riunione Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span><span class="sxs-lookup"><span data-stu-id="3680e-127">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="3680e-p108">Non dimenticare la [gestione dei dispositivi degli utenti](./devices/device-management.md), quali telefoni, auricolari e videocamere. Per ottenere le informazioni più recenti e aggiornate sui dispositivi certificati Teams, vedere [Dispositivi di Teams](https://office.com/teamsdevices).</span><span class="sxs-lookup"><span data-stu-id="3680e-p108">Don't forget about [managing your users' devices](./devices/device-management.md) - phones, headsets, cameras. To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="3680e-130">Eventi live</span><span class="sxs-lookup"><span data-stu-id="3680e-130">Live events</span></span>

- <span data-ttu-id="3680e-p109">Analogamente alle riunioni, l'amministratore [configura gli eventi live](teams-live-events/configure-teams-live-events.md) per tutti. Quindi configurare (e assegnare) i [criteri evento live](teams-live-events/set-up-for-teams-live-events.md) per controllare ciò che gli utenti possono fare o meno.</span><span class="sxs-lookup"><span data-stu-id="3680e-p109">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone. Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="3680e-133">Per assicurarti che i produttori e gli organizzatori degli eventi live siano formati, consigliare la lettura di [Introduzione agli eventi live](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span><span class="sxs-lookup"><span data-stu-id="3680e-133">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="3680e-134">Se non si ha familiarità con gli eventi live, vedere [Che cosa sono gli eventi live di Teams?](teams-live-events/what-are-teams-live-events.md) e [Pianificare gli eventi live di Teams](teams-live-events/plan-for-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="3680e-134">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3680e-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3680e-135">Related topics</span></span>

[<span data-ttu-id="3680e-136">Riunioni e conferenze in Teams</span><span class="sxs-lookup"><span data-stu-id="3680e-136">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="3680e-137">Audioconferenza in Teams</span><span class="sxs-lookup"><span data-stu-id="3680e-137">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="3680e-138">Eventi live in Teams</span><span class="sxs-lookup"><span data-stu-id="3680e-138">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="3680e-139">Limiti e specifiche per Teams</span><span class="sxs-lookup"><span data-stu-id="3680e-139">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="3680e-140">Community tecnica Microsoft: eventi live in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3680e-140">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)
