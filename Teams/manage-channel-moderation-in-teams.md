---
title: Configurare e gestire la moderazione dei canali
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come configurare canali per la moderazione in Microsoft Teams, inclusa la procedura per aggiungere membri del team come moderatori di canale.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9598723d1a88826d1efa5fb487d02fc93aa5d4e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822896"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="9de44-103">Configurare e gestire la moderazione dei canali in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9de44-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="9de44-104">In Microsoft Teams, i proprietari dei team possono attivare la moderazione per un canale standard per controllare chi può avviare nuovi post e rispondere ai post in quel canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="9de44-105">I proprietari del team possono anche aggiungere membri del team come moderatori.</span><span class="sxs-lookup"><span data-stu-id="9de44-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="9de44-106">Un proprietario del team potrebbe non avere le competenze in materia a livello di canale per supportare al meglio la moderazione dei canali.</span><span class="sxs-lookup"><span data-stu-id="9de44-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="9de44-107">Consentendo a specifici membri del team di moderare un canale, la responsabilità di gestire i contenuti e il contesto all'interno di un canale è condivisa tra i proprietari del team e i moderatori di canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="9de44-108">Ad esempio, un proprietario del team può aggiungere proprietari aziendali o proprietari di contenuti come moderatori, il che consente di controllare la condivisione delle informazioni in quel canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="9de44-109">La moderazione dei canali è disponibile per i canali standard.</span><span class="sxs-lookup"><span data-stu-id="9de44-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="9de44-110">Non è disponibile per il canale Generale o per i canali privati.</span><span class="sxs-lookup"><span data-stu-id="9de44-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="9de44-111">Cosa può fare un moderatore di canale?</span><span class="sxs-lookup"><span data-stu-id="9de44-111">What can a channel moderator do?</span></span>

<span data-ttu-id="9de44-112">I moderatori dei canali possono:</span><span class="sxs-lookup"><span data-stu-id="9de44-112">Channel moderators can:</span></span>

- <span data-ttu-id="9de44-113">Avvia nuovi post nel canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-113">Start new posts in the channel.</span></span> <span data-ttu-id="9de44-114">Quando la moderazione è attivata per un canale, solo i moderatori possono iniziare nuovi post in quel canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="9de44-115">Aggiungere e rimuovere membri del team come moderatori di un canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="9de44-116">Tenere presente che, per impostazione predefinita, i proprietari dei team sono moderatori di canale e non possono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="9de44-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="9de44-117">Controlla se i membri del team possono rispondere ai messaggi del canale esistenti e se bot e connettori possono inviare messaggi del canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="9de44-118">Scenari</span><span class="sxs-lookup"><span data-stu-id="9de44-118">Scenarios</span></span>

<span data-ttu-id="9de44-119">Ecco alcuni esempi di come l'organizzazione può usare la moderazione dei canali in Teams.</span><span class="sxs-lookup"><span data-stu-id="9de44-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="9de44-120">Usare un canale come canale di annuncio</span><span class="sxs-lookup"><span data-stu-id="9de44-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="9de44-121">Il team Marketing usa un canale specifico per condividere gli annunci di progetto e i risultati finali principali.</span><span class="sxs-lookup"><span data-stu-id="9de44-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="9de44-122">A volte i membri del team pubblicano contenuti nel canale che appartengono in modo più appropriato ad altri canali.</span><span class="sxs-lookup"><span data-stu-id="9de44-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="9de44-123">Il proprietario del team vuole limitare la condivisione di informazioni nel canale solo agli annunci, in modo che i membri del team possano usare quel canale per essere sempre al corrente delle cose importanti.</span><span class="sxs-lookup"><span data-stu-id="9de44-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="9de44-124">In questo scenario, il proprietario del team aggiunge i lead di marketing come moderatori in modo che possano pubblicare annunci nel canale e disattivare la possibilità per i membri del team di rispondere ai messaggi in quel canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="9de44-125">Usare un canale per le discussioni di classe in Teams for Education</span><span class="sxs-lookup"><span data-stu-id="9de44-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="9de44-126">In Teams for Education, un insegnante di scienze vuole usare un canale per coinvolgere gli studenti in discussioni mirate su specifici argomenti della classe.</span><span class="sxs-lookup"><span data-stu-id="9de44-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="9de44-127">In questo scenario, l'insegnante consente agli assistenti didattici di moderare il canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="9de44-128">Gli assistenti didattici potranno quindi creare nuovi post per avviare e avviare discussioni con gli studenti.</span><span class="sxs-lookup"><span data-stu-id="9de44-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="9de44-129">Gestire la moderazione dei canali</span><span class="sxs-lookup"><span data-stu-id="9de44-129">Manage channel moderation</span></span>

<span data-ttu-id="9de44-130">In Teams, vai al canale, fai clic **su Altre opzioni...**  >  **Gestisci canale.**</span><span class="sxs-lookup"><span data-stu-id="9de44-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="9de44-131">Da qui puoi attivare e disattivare la moderazione, aggiungere membri del team come moderatori e impostare le preferenze.</span><span class="sxs-lookup"><span data-stu-id="9de44-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="9de44-132">La moderazione dei canali è un'impostazione per canale.</span><span class="sxs-lookup"><span data-stu-id="9de44-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="9de44-133">Non esiste un'impostazione a livello di tenant per la moderazione dei canali.</span><span class="sxs-lookup"><span data-stu-id="9de44-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="9de44-134">Per richiedere a Microsoft di aggiungere un'impostazione di moderazione del canale a livello di tenant, richiederla in [Teams UserVoice.](https://microsoftteams.uservoice.com/)</span><span class="sxs-lookup"><span data-stu-id="9de44-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences.png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="9de44-136">Attivare o disattivare la moderazione per un canale</span><span class="sxs-lookup"><span data-stu-id="9de44-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="9de44-137">Per impostazione predefinita, la moderazione è disattivata, il che significa che le consuete impostazioni del canale si applicano ai proprietari del team e ai membri del team.</span><span class="sxs-lookup"><span data-stu-id="9de44-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="9de44-138">Ad esempio, è possibile limitare i nuovi post solo ai membri del team o consentire a tutti, compresi gli utenti guest, di creare nuovi post.</span><span class="sxs-lookup"><span data-stu-id="9de44-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="9de44-139">Per attivare la moderazione per un canale, in **Moderazione canale** fare clic su **Attiva.**</span><span class="sxs-lookup"><span data-stu-id="9de44-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="9de44-140">Quando la moderazione dei canali è attivata, solo i moderatori possono iniziare nuovi post.</span><span class="sxs-lookup"><span data-stu-id="9de44-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="9de44-141">Aggiungere o rimuovere moderatori di canale</span><span class="sxs-lookup"><span data-stu-id="9de44-141">Add or remove channel moderators</span></span>

<span data-ttu-id="9de44-142">In **Chi sono i moderatori?** fai clic su **Gestisci,** quindi aggiungi o rimuovi i membri del team come moderatori.</span><span class="sxs-lookup"><span data-stu-id="9de44-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="9de44-143">I proprietari e i moderatori del team possono aggiungere e rimuovere altri moderatori.</span><span class="sxs-lookup"><span data-stu-id="9de44-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="9de44-144">Impostare le autorizzazioni per i membri del team</span><span class="sxs-lookup"><span data-stu-id="9de44-144">Set team member permissions</span></span>

<span data-ttu-id="9de44-145">In **Autorizzazioni per i membri** del team selezionare le caselle di controllo accanto alle attività da consentire.</span><span class="sxs-lookup"><span data-stu-id="9de44-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9de44-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9de44-146">Related topics</span></span>

- [<span data-ttu-id="9de44-147">Panoramica su team e canali in Teams</span><span class="sxs-lookup"><span data-stu-id="9de44-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
