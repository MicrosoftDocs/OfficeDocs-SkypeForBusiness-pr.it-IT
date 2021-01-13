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
description: Informazioni su come usare e gestire i criteri per i team dell'organizzazione per controllare gli utenti che possono eseguire in team e canali.
ms.openlocfilehash: a05aaf65418e46f7b631bac6f7d88d8bbdf4c806
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802366"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="0deca-103">Gestire i criteri dei team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0deca-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="0deca-104">Come amministratore, puoi usare i criteri di teams in Microsoft teams per controllare gli utenti che possono eseguire in team e canali.</span><span class="sxs-lookup"><span data-stu-id="0deca-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="0deca-105">Ad esempio, puoi impostare se gli utenti possono creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="0deca-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="0deca-106">Per gestire i criteri dei team, è possibile **passare a** criteri teams teams nell'interfaccia di amministrazione di  >   Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0deca-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0deca-107">Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0deca-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="0deca-108">Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0deca-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="0deca-109">È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0deca-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="0deca-110">Dopo aver modificato il criterio globale o assegnato un criterio, è possibile che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="0deca-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="0deca-111">Creare un criterio teams personalizzato</span><span class="sxs-lookup"><span data-stu-id="0deca-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="0deca-112">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a**  >  **criteri** teams teams.</span><span class="sxs-lookup"><span data-stu-id="0deca-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="0deca-113">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0deca-113">Click **Add**.</span></span>
3. <span data-ttu-id="0deca-114">Immettere un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="0deca-114">Enter a name and description for the policy.</span></span>

    ![Screenshot delle impostazioni dei criteri di Teams](media/teams-policies.png)
4. <span data-ttu-id="0deca-116">Attivare o disattivare **crea canali privati**, <a name="createchannels"></a> a seconda che si voglia consentire agli utenti di creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="0deca-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="0deca-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0deca-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="0deca-118">Modificare un criterio Teams</span><span class="sxs-lookup"><span data-stu-id="0deca-118">Edit a teams policy</span></span>

<span data-ttu-id="0deca-119">È possibile modificare il criterio globale o i criteri personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="0deca-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="0deca-120">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **Vai a**  >  **criteri** teams teams.</span><span class="sxs-lookup"><span data-stu-id="0deca-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="0deca-121">Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="0deca-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0deca-122">Attivare o disattivare le impostazioni desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0deca-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="0deca-123">Assegnare un criterio team personalizzati agli utenti</span><span class="sxs-lookup"><span data-stu-id="0deca-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="0deca-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0deca-124">Related topics</span></span>

[<span data-ttu-id="0deca-125">Canali privati in teams</span><span class="sxs-lookup"><span data-stu-id="0deca-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="0deca-126">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="0deca-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="0deca-127">New-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="0deca-127">New-CsTeamsChannelsPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
