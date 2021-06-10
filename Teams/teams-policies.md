---
title: Gestire i criteri dei team in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Informazioni su come usare e gestire i criteri dei team nell'organizzazione per controllare le attività che gli utenti possono eseguire nei team e nei canali.
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094206"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="6e2df-103">Gestire i criteri dei team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e2df-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="6e2df-104">Gli amministratori possono usare i criteri di teams in Microsoft Teams per controllare le attività che gli utenti dell'organizzazione possono eseguire nei team e nei canali.</span><span class="sxs-lookup"><span data-stu-id="6e2df-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="6e2df-105">Ad esempio, è possibile impostare se gli utenti sono autorizzati a creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="6e2df-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="6e2df-106">Per gestire i criteri dei team, è **possibile accedere Teams** Teams criteri  >  **nell'Microsoft Teams** di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6e2df-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6e2df-107">È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6e2df-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="6e2df-108">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6e2df-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="6e2df-109">È possibile modificare i criteri globali o creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6e2df-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="6e2df-110">Dopo aver modificato i criteri globali o aver assegnato un criterio, l'applicazione delle modifiche può richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="6e2df-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="6e2df-111">Creare criteri di team personalizzati</span><span class="sxs-lookup"><span data-stu-id="6e2df-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="6e2df-112">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare **a** Teams  >  **Teams criteri.**</span><span class="sxs-lookup"><span data-stu-id="6e2df-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="6e2df-113">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6e2df-113">Click **Add**.</span></span>
3. <span data-ttu-id="6e2df-114">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="6e2df-114">Enter a name and description for the policy.</span></span>

    ![Screenshot delle impostazioni dei criteri dei team](media/teams-policies.png)
4. <span data-ttu-id="6e2df-116">Attivare o disattivare Crea <a name="createchannels"></a> canali **privati,** a seconda che si voglia consentire agli utenti di creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="6e2df-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="6e2df-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6e2df-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="6e2df-118">Modificare un criterio di Teams</span><span class="sxs-lookup"><span data-stu-id="6e2df-118">Edit a teams policy</span></span>

<span data-ttu-id="6e2df-119">È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6e2df-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="6e2df-120">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare **a** Teams  >  **Teams criteri.**</span><span class="sxs-lookup"><span data-stu-id="6e2df-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="6e2df-121">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6e2df-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6e2df-122">Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="6e2df-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="6e2df-123">Assegnare criteri di team personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="6e2df-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="6e2df-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6e2df-124">Related topics</span></span>

[<span data-ttu-id="6e2df-125">Canali privati in Teams</span><span class="sxs-lookup"><span data-stu-id="6e2df-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="6e2df-126">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="6e2df-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="6e2df-127">New-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="6e2df-127">New-CsTeamsChannelsPolicy</span></span>](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)