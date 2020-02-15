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
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034509"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="1f37a-103">Gestire i tag in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f37a-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1f37a-104">Questa funzionalità non è ancora visualizzata nell'interfaccia di amministrazione di Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="1f37a-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="1f37a-105">Attualmente viene implementato e potrebbe non essere ancora disponibile nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f37a-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="1f37a-106">Per rimanere in primo piano sulle caratteristiche future per i team, consulta la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span><span class="sxs-lookup"><span data-stu-id="1f37a-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="1f37a-107">I tag in Microsoft teams consentono agli utenti di comunicare con un sottoinsieme di persone in un team.</span><span class="sxs-lookup"><span data-stu-id="1f37a-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="1f37a-108">I tag possono essere aggiunti a uno o più membri del team per connettersi facilmente con il sottoinsieme giusto di persone.</span><span class="sxs-lookup"><span data-stu-id="1f37a-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="1f37a-109">I proprietari e i membri del team (se la funzionalità è abilitata) possono aggiungere uno o più tag a una persona.</span><span class="sxs-lookup"><span data-stu-id="1f37a-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="1f37a-110">I tag possono quindi essere usati in @mentions da chiunque nel team in un post del canale per comunicare solo con gli utenti a cui è stato assegnato il tag.</span><span class="sxs-lookup"><span data-stu-id="1f37a-110">The tags can then be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="1f37a-111">I tag non sono ancora supportati nei canali privati.</span><span class="sxs-lookup"><span data-stu-id="1f37a-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="1f37a-112">Come funzionano i tag</span><span class="sxs-lookup"><span data-stu-id="1f37a-112">How tags work</span></span>

<span data-ttu-id="1f37a-113">Un tag può essere aggiunto a una persona in un team specifico.</span><span class="sxs-lookup"><span data-stu-id="1f37a-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="1f37a-114">Dopo l'aggiunta di un tag, può essere usato in @mentions in qualsiasi canale standard del team.</span><span class="sxs-lookup"><span data-stu-id="1f37a-114">After a tag is added, it can be used in @mentions in any standard channel of the team.</span></span> <span data-ttu-id="1f37a-115">Ecco alcuni esempi di come i tag possono essere usati in teams:</span><span class="sxs-lookup"><span data-stu-id="1f37a-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="1f37a-116">Un responsabile dello Store vuole pubblicare un annuncio su un canale e inviare una notifica a tutti i cassieri.</span><span class="sxs-lookup"><span data-stu-id="1f37a-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="1f37a-117">Un Product Manager di gruppo vuole Message tutti i responsabili di prodotto in un canale.</span><span class="sxs-lookup"><span data-stu-id="1f37a-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="1f37a-118">Un amministratore dell'ospedale vuole inviare un messaggio a tutti i radiologi di un canale.</span><span class="sxs-lookup"><span data-stu-id="1f37a-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>

<span data-ttu-id="1f37a-119">Per altre informazioni, vedere [usare i contrassegni in teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="1f37a-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="1f37a-120">Gestire i tag per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1f37a-120">Manage tags for your organization</span></span>

<span data-ttu-id="1f37a-121">Come amministratore, puoi controllare chi può aggiungere tag e come vengono usati i tag in tutta l'organizzazione nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="1f37a-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Screenshot delle impostazioni di tagging nell'interfaccia di amministrazione di Microsoft Teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="1f37a-123">Impostare gli utenti che possono aggiungere tag</span><span class="sxs-lookup"><span data-stu-id="1f37a-123">Set who can add tags</span></span>

<span data-ttu-id="1f37a-124">Per impostazione predefinita, i proprietari del team possono aggiungere tag.</span><span class="sxs-lookup"><span data-stu-id="1f37a-124">By default, team owners can add tags.</span></span> <span data-ttu-id="1f37a-125">Puoi modificare questa impostazione per consentire ai proprietari del team e ai membri del team di aggiungere tag oppure disattivare i tag per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f37a-125">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="1f37a-126">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su**impostazioni di Team** **Impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f37a-126">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="1f37a-127">In **contrassegno**, accanto a **contrassegno è abilitato per**Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f37a-127">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="1f37a-128">**Proprietari e membri del team**: consentire ai proprietari e ai membri del team di aggiungere tag.</span><span class="sxs-lookup"><span data-stu-id="1f37a-128">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="1f37a-129">**Proprietari del team**: consentire ai proprietari del team di aggiungere tag.</span><span class="sxs-lookup"><span data-stu-id="1f37a-129">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="1f37a-130">**Disabilitato**: disattivare i contrassegni.</span><span class="sxs-lookup"><span data-stu-id="1f37a-130">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="1f37a-131">Configurare le impostazioni di tag</span><span class="sxs-lookup"><span data-stu-id="1f37a-131">Configure tags settings</span></span>

<span data-ttu-id="1f37a-132">Puoi configurare le impostazioni dei tag seguenti per controllare il modo in cui i tag vengono usati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f37a-132">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="1f37a-133">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su**impostazioni di Team** **Impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f37a-133">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="1f37a-134">In **tagging**impostare le operazioni seguenti in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f37a-134">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="1f37a-135">Il **proprietario del team può eseguire l'override di chi può applicare i tag**: quando questo è attivato, i proprietari del team possono consentire o impedire ai membri di aggiungere tag nelle impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="1f37a-135">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="1f37a-136">**I membri possono aggiungere tag aggiuntivi**: se si consente ai membri del team di aggiungere tag, attivare questa opzione per consentire ai membri del team di aggiungere tag diversi dai tag predefiniti consigliati impostati.</span><span class="sxs-lookup"><span data-stu-id="1f37a-136">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="1f37a-137">Se questa opzione è disattivata, i membri del team possono usare solo i tag predefiniti.</span><span class="sxs-lookup"><span data-stu-id="1f37a-137">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="1f37a-138">**Tag predefiniti suggeriti**: usare questa opzione per aggiungere un set di tag predefiniti.</span><span class="sxs-lookup"><span data-stu-id="1f37a-138">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="1f37a-139">È possibile aggiungere fino a 25 tag e ogni tag può contenere un massimo di 25 caratteri.</span><span class="sxs-lookup"><span data-stu-id="1f37a-139">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="1f37a-140">I proprietari e i membri del team (se la funzionalità è abilitata) possono usare questi suggerimenti, aggiungerli o creare un nuovo set di tag.</span><span class="sxs-lookup"><span data-stu-id="1f37a-140">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="1f37a-141">Gestire le impostazioni dei tag per un team</span><span class="sxs-lookup"><span data-stu-id="1f37a-141">Manage tags settings for a team</span></span>

<span data-ttu-id="1f37a-142">Se è stato attivato il **proprietario del team può eseguire l'override di chi può applicare** l'impostazione di tag nell'interfaccia di amministrazione di Microsoft teams, i proprietari del team possono impostare se i membri possono aggiungere tag a livello di team.</span><span class="sxs-lookup"><span data-stu-id="1f37a-142">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="1f37a-143">A questo scopo, nella scheda **Impostazioni** di un team passa a **tag**e quindi scegli chi può aggiungere i tag.</span><span class="sxs-lookup"><span data-stu-id="1f37a-143">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Screenshot dell'impostazione di tag a livello di Team](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="1f37a-145">Aggiungere tag in teams</span><span class="sxs-lookup"><span data-stu-id="1f37a-145">Add tags in Teams</span></span>

<span data-ttu-id="1f37a-146">In teams la scheda **membri** della pagina Manage team per un team include una colonna **Tags** .</span><span class="sxs-lookup"><span data-stu-id="1f37a-146">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="1f37a-147">I proprietari e i membri del team (se la funzionalità è abilitata) possono fare clic su **Gestisci Tag** accanto a un membro per visualizzare l'elenco dei tag suggeriti per il membro e aggiungere i tag all'elenco.</span><span class="sxs-lookup"><span data-stu-id="1f37a-147">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="1f37a-148">Screenshot che illustra come applicare i tag nel client Teams</span><span class="sxs-lookup"><span data-stu-id="1f37a-148">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
