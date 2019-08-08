---
title: Configurare e gestire la moderazione del canale in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come configurare i canali per la moderazione in Microsoft teams, incluso come aggiungere membri del team come moderatori del canale.
ms.openlocfilehash: 93fb0a6d8a88979d14031792ccf96a8861629b1d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244976"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="20d2e-103">Configurare e gestire la moderazione del canale in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20d2e-103">Set up and manage channel moderation in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="20d2e-104">In Microsoft teams i proprietari del team possono attivare la moderazione per un canale per controllare chi può avviare nuovi post e rispondere ai post del canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-104">In Microsoft Teams, team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="20d2e-105">I proprietari del team possono anche aggiungere membri del team come moderatori.</span><span class="sxs-lookup"><span data-stu-id="20d2e-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="20d2e-106">Un proprietario del team potrebbe non avere l'esperienza in materia a livello di canale per il supporto ottimale della moderazione del canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="20d2e-107">Consentendo ai membri del team specifici di moderare un canale, la responsabilità di gestire il contenuto e il contesto all'interno di un canale viene condivisa tra i proprietari del team e i moderatori del canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="20d2e-108">Ad esempio, un proprietario del team può aggiungere proprietari di aziende o proprietari di contenuti come moderatori, che consente loro di controllare la condivisione delle informazioni in quel canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="20d2e-109">Cosa può fare un moderatore del canale?</span><span class="sxs-lookup"><span data-stu-id="20d2e-109">What can a channel moderator do?</span></span>

<span data-ttu-id="20d2e-110">I moderatori del canale possono:</span><span class="sxs-lookup"><span data-stu-id="20d2e-110">Channel moderators can:</span></span>

- <span data-ttu-id="20d2e-111">Avviare nuovi post nel canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-111">Start new posts in the channel.</span></span> <span data-ttu-id="20d2e-112">Quando la moderazione è attivata per un canale, solo i moderatori possono avviare nuovi post nel canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-112">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="20d2e-113">Aggiungere e rimuovere membri del team come moderatori a un canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-113">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="20d2e-114">Tieni presente che per impostazione predefinita, i proprietari del team sono moderatori del canale e non possono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="20d2e-114">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="20d2e-115">Controlla se i membri del team possono rispondere ai messaggi del canale esistenti e se i bot e i connettori possono inviare messaggi di canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-115">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="20d2e-116">Scenari</span><span class="sxs-lookup"><span data-stu-id="20d2e-116">Scenarios</span></span>

<span data-ttu-id="20d2e-117">Ecco alcuni esempi di come l'organizzazione può usare la moderazione dei canali in teams.</span><span class="sxs-lookup"><span data-stu-id="20d2e-117">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="20d2e-118">Usare un canale come canale di annuncio</span><span class="sxs-lookup"><span data-stu-id="20d2e-118">Use a channel as an announcement channel</span></span>

<span data-ttu-id="20d2e-119">Il team di marketing usa un canale specifico per condividere gli annunci e i risultati finali del progetto chiave.</span><span class="sxs-lookup"><span data-stu-id="20d2e-119">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="20d2e-120">Talvolta i membri del team pubblicano contenuti nel canale che appartengono più opportunamente ad altri canali.</span><span class="sxs-lookup"><span data-stu-id="20d2e-120">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="20d2e-121">Il proprietario del team vuole limitare la condivisione di informazioni nel canale solo agli annunci in modo che i membri del team possano usarlo per mantenere il livello di importanza.</span><span class="sxs-lookup"><span data-stu-id="20d2e-121">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="20d2e-122">In questo scenario, il proprietario del team aggiunge i lead di marketing come moderatori in modo che possano pubblicare annunci nel canale e disattivare la possibilità per i membri del team di rispondere ai messaggi presenti nel canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-122">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="20d2e-123">Usare un canale per le discussioni di classe in teams for Education</span><span class="sxs-lookup"><span data-stu-id="20d2e-123">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="20d2e-124">In teams for Education un insegnante di Scienze vuole usare un canale per coinvolgere gli studenti in discussioni mirate su specifici argomenti in classe.</span><span class="sxs-lookup"><span data-stu-id="20d2e-124">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="20d2e-125">In questo scenario, l'insegnante consente agli assistenti didattici di moderare il canale.</span><span class="sxs-lookup"><span data-stu-id="20d2e-125">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="20d2e-126">Gli assistenti didattici possono quindi creare nuovi post per avviare e guidare le discussioni con gli studenti.</span><span class="sxs-lookup"><span data-stu-id="20d2e-126">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="20d2e-127">Gestire la moderazione del canale</span><span class="sxs-lookup"><span data-stu-id="20d2e-127">Manage channel moderation</span></span>

<span data-ttu-id="20d2e-128">In teams, vai al canale, fai clic su **altre opzioni...**  >  **Gestisci canale**.</span><span class="sxs-lookup"><span data-stu-id="20d2e-128">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="20d2e-129">Da qui è possibile attivare e disattivare la moderazione, aggiungere membri del team come moderatori e impostare le preferenze.</span><span class="sxs-lookup"><span data-stu-id="20d2e-129">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

![Manage-Channel-Moderation-in-teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="20d2e-131">Attivare o disattivare la moderazione per un canale</span><span class="sxs-lookup"><span data-stu-id="20d2e-131">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="20d2e-132">Per impostazione predefinita, la moderazione è disattivata ed è possibile limitare i nuovi post solo ai membri del team o consentire a tutti, inclusi gli ospiti, di avviare nuovi post.</span><span class="sxs-lookup"><span data-stu-id="20d2e-132">By default, moderation is off and you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="20d2e-133">Per attivare la moderazione per un canale, fare clic **su attiva**in **moderazione canale**.</span><span class="sxs-lookup"><span data-stu-id="20d2e-133">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="20d2e-134">Quando la moderazione del canale è attiva, solo i moderatori possono avviare nuovi post.</span><span class="sxs-lookup"><span data-stu-id="20d2e-134">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="20d2e-135">Aggiungere o rimuovere i moderatori del canale</span><span class="sxs-lookup"><span data-stu-id="20d2e-135">Add or remove channel moderators</span></span>

<span data-ttu-id="20d2e-136">In **chi sono i moderatori?**, fare \*\*\*\* clic su Gestisci e quindi aggiungere o rimuovere membri del team come moderatori.</span><span class="sxs-lookup"><span data-stu-id="20d2e-136">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="20d2e-137">I proprietari e i moderatori del team possono aggiungere e rimuovere altri moderatori.</span><span class="sxs-lookup"><span data-stu-id="20d2e-137">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="20d2e-138">Impostare le autorizzazioni per i membri del team</span><span class="sxs-lookup"><span data-stu-id="20d2e-138">Set team member permissions</span></span>

<span data-ttu-id="20d2e-139">In **autorizzazioni membro del team**selezionare le caselle di controllo accanto alle attività che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="20d2e-139">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="20d2e-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="20d2e-140">Related topics</span></span>

- [<span data-ttu-id="20d2e-141">Panoramica di team e canali in teams</span><span class="sxs-lookup"><span data-stu-id="20d2e-141">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)