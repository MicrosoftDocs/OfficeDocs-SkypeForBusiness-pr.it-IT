---
title: Gestire i tag in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
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
description: Informazioni su come gestire i tag usati nell'organizzazione in Microsoft teams.
ms.openlocfilehash: b19613268384831aaaa2608fc183b62fdc1b0445
ms.sourcegitcommit: 0979fae58ecd713f8317ed99caae015b5cc2c8e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "44877937"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="5f37e-103">Gestire i tag in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f37e-103">Manage tags in Microsoft Teams</span></span>

<span data-ttu-id="5f37e-104">I tag in Microsoft teams consentono agli utenti di comunicare con un sottoinsieme di persone in un team.</span><span class="sxs-lookup"><span data-stu-id="5f37e-104">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="5f37e-105">I tag possono essere aggiunti a uno o più membri del team per connettersi facilmente con il sottoinsieme giusto di persone.</span><span class="sxs-lookup"><span data-stu-id="5f37e-105">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="5f37e-106">I proprietari e i membri del team (se la funzionalità è abilitata) possono aggiungere uno o più tag a una persona.</span><span class="sxs-lookup"><span data-stu-id="5f37e-106">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="5f37e-107">I tag possono quindi essere usati in @mentions da chiunque nel team in un post di canale o per avviare una conversazione con solo gli utenti a cui è stato assegnato il tag.</span><span class="sxs-lookup"><span data-stu-id="5f37e-107">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="5f37e-108">I tag non sono ancora supportati nei canali privati.</span><span class="sxs-lookup"><span data-stu-id="5f37e-108">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="5f37e-109">I tag non sono ancora disponibili nelle organizzazioni US Government community Cloud (GCC), GCC High o Department of Defense (DoD).</span><span class="sxs-lookup"><span data-stu-id="5f37e-109">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="5f37e-110">Come funzionano i tag</span><span class="sxs-lookup"><span data-stu-id="5f37e-110">How tags work</span></span>

<span data-ttu-id="5f37e-111">Un tag può essere aggiunto a una persona in un team specifico.</span><span class="sxs-lookup"><span data-stu-id="5f37e-111">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="5f37e-112">Dopo l'aggiunta di un tag, può essere usato in @mentions in una chat o in qualsiasi canale standard del team.</span><span class="sxs-lookup"><span data-stu-id="5f37e-112">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="5f37e-113">Ecco alcuni esempi di come i tag possono essere usati in teams:</span><span class="sxs-lookup"><span data-stu-id="5f37e-113">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="5f37e-114">Un responsabile dello Store vuole pubblicare un annuncio su un canale e inviare una notifica a tutti i cassieri.</span><span class="sxs-lookup"><span data-stu-id="5f37e-114">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="5f37e-115">Un Product Manager di gruppo vuole Message tutti i responsabili di prodotto in un canale.</span><span class="sxs-lookup"><span data-stu-id="5f37e-115">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="5f37e-116">Un amministratore dell'ospedale vuole inviare un messaggio a tutti i radiologi di un canale.</span><span class="sxs-lookup"><span data-stu-id="5f37e-116">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="5f37e-117">Un responsabile marketing vuole avviare una chat di gruppo con tutte le finestre di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5f37e-117">A marketing manager wants to start a group chat with all designers.</span></span>

<span data-ttu-id="5f37e-118">Quando un tag viene @mentioned in una conversazione di canale, i membri del team associati al tag riceveranno una notifica, come qualsiasi altra @mention.</span><span class="sxs-lookup"><span data-stu-id="5f37e-118">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

<span data-ttu-id="5f37e-119">Per altre informazioni, vedere [usare i contrassegni in teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="5f37e-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="5f37e-120">Gestire i tag per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5f37e-120">Manage tags for your organization</span></span>

<span data-ttu-id="5f37e-121">Come amministratore, puoi controllare chi può aggiungere tag e come vengono usati i tag in tutta l'organizzazione nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="5f37e-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Screenshot delle impostazioni di tagging nell'interfaccia di amministrazione di Microsoft Teams](media/manage-tags-admin-settings.png)

<span data-ttu-id="5f37e-123">Un team può avere fino a 100 tag, fino a 100 i membri del team possono essere assegnati a un tag e può essere assegnato un massimo di 25 tag a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="5f37e-123">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-tags"></a><span data-ttu-id="5f37e-124">Impostare gli utenti che possono aggiungere tag</span><span class="sxs-lookup"><span data-stu-id="5f37e-124">Set who can add tags</span></span>

<span data-ttu-id="5f37e-125">Per impostazione predefinita, i proprietari del team possono aggiungere tag.</span><span class="sxs-lookup"><span data-stu-id="5f37e-125">By default, team owners can add tags.</span></span> <span data-ttu-id="5f37e-126">Puoi modificare questa impostazione per consentire ai proprietari del team e ai membri del team di aggiungere tag oppure disattivare i tag per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f37e-126">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="5f37e-127">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su impostazioni **di Team impostazioni a livello di organizzazione**  >  **Teams settings**.</span><span class="sxs-lookup"><span data-stu-id="5f37e-127">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="5f37e-128">In **contrassegno**, accanto a **contrassegno è abilitato per**Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f37e-128">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="5f37e-129">**Proprietari e membri del team**: consentire ai proprietari e ai membri del team di aggiungere tag.</span><span class="sxs-lookup"><span data-stu-id="5f37e-129">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="5f37e-130">**Proprietari del team**: consentire ai proprietari del team di aggiungere tag.</span><span class="sxs-lookup"><span data-stu-id="5f37e-130">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="5f37e-131">**Disabilitato**: disattivare i contrassegni.</span><span class="sxs-lookup"><span data-stu-id="5f37e-131">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="5f37e-132">Configurare le impostazioni di tag</span><span class="sxs-lookup"><span data-stu-id="5f37e-132">Configure tags settings</span></span>

<span data-ttu-id="5f37e-133">Puoi configurare le impostazioni dei tag seguenti per controllare il modo in cui i tag vengono usati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f37e-133">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="5f37e-134">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su impostazioni **di Team impostazioni a livello di organizzazione**  >  **Teams settings**.</span><span class="sxs-lookup"><span data-stu-id="5f37e-134">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="5f37e-135">In **tagging**impostare le operazioni seguenti in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f37e-135">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="5f37e-136">Il **proprietario del team può eseguire l'override di chi può applicare i tag**: quando questo è attivato, i proprietari del team possono consentire o impedire ai membri di aggiungere tag nelle impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="5f37e-136">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="5f37e-137">**I membri possono aggiungere tag aggiuntivi**: se si consente ai membri del team di aggiungere tag, attivare questa opzione per consentire ai membri del team di aggiungere tag diversi dai tag predefiniti consigliati impostati.</span><span class="sxs-lookup"><span data-stu-id="5f37e-137">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="5f37e-138">Se questa opzione è disattivata, i membri del team possono usare solo i tag predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5f37e-138">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="5f37e-139">**Tag predefiniti suggeriti**: usare questa opzione per aggiungere un set di tag predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5f37e-139">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="5f37e-140">È possibile aggiungere fino a 25 tag e ogni tag può contenere un massimo di 25 caratteri.</span><span class="sxs-lookup"><span data-stu-id="5f37e-140">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="5f37e-141">I proprietari e i membri del team (se la funzionalità è abilitata) possono usare questi suggerimenti, aggiungerli o creare un nuovo set di tag.</span><span class="sxs-lookup"><span data-stu-id="5f37e-141">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="5f37e-142">Gestire le impostazioni dei tag per un team</span><span class="sxs-lookup"><span data-stu-id="5f37e-142">Manage tags settings for a team</span></span>

<span data-ttu-id="5f37e-143">Se è stato attivato il **proprietario del team può eseguire l'override di chi può applicare** l'impostazione di tag nell'interfaccia di amministrazione di Microsoft teams, i proprietari del team possono impostare se i membri possono aggiungere tag a livello di team.</span><span class="sxs-lookup"><span data-stu-id="5f37e-143">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="5f37e-144">A questo scopo, nella scheda **Impostazioni** di un team passa a **tag**e quindi scegli chi può aggiungere i tag.</span><span class="sxs-lookup"><span data-stu-id="5f37e-144">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Screenshot dell'impostazione di tag a livello di Team](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="5f37e-146">Usare i tag</span><span class="sxs-lookup"><span data-stu-id="5f37e-146">Use tags</span></span>

### <a name="add-tags"></a><span data-ttu-id="5f37e-147">Aggiungere tag</span><span class="sxs-lookup"><span data-stu-id="5f37e-147">Add tags</span></span>

<span data-ttu-id="5f37e-148">Per creare e assegnare tag, selezionare **Teams** sul lato sinistro dell'app e quindi trovare il team nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5f37e-148">To create and assign tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="5f37e-149">Selezionare **altre opzioni**, quindi scegliere **Gestisci Tag**.</span><span class="sxs-lookup"><span data-stu-id="5f37e-149">Select **More options**, and then choose **Manage tags**.</span></span>

<span data-ttu-id="5f37e-150">In questo caso, è possibile creare i tag e assegnarli agli utenti del team.</span><span class="sxs-lookup"><span data-stu-id="5f37e-150">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="5f37e-151">Screenshot che illustra come applicare i tag nel client Teams</span><span class="sxs-lookup"><span data-stu-id="5f37e-151">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

### <a name="delete-tags"></a><span data-ttu-id="5f37e-152">Eliminare i tag</span><span class="sxs-lookup"><span data-stu-id="5f37e-152">Delete tags</span></span>

<span data-ttu-id="5f37e-153">Rimuovi tutti i membri del team associati al tag e il tag verrà eliminato.</span><span class="sxs-lookup"><span data-stu-id="5f37e-153">Remove all team members associated with the tag and the tag will be deleted.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5f37e-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5f37e-154">Related topics</span></span>

[<span data-ttu-id="5f37e-155">Uso di tag in teams</span><span class="sxs-lookup"><span data-stu-id="5f37e-155">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)
