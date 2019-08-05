---
title: Gestire l'individuazione di team privati in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
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
description: Informazioni su come controllare se i team privati possono essere scoperti dagli utenti di Microsoft teams tramite suggerimenti nella raccolta team e nei risultati della ricerca.
ms.openlocfilehash: 0c75d0e08290b12cf658b2a84eef609e2d15dc86
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "36184729"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="86323-103">Gestire l'individuazione di team privati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86323-103">Manage discovery of private teams in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="86323-104">Gli amministratori e i proprietari del team possono controllare se i team privati possono essere scoperti dagli utenti di Microsoft teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="86323-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="86323-105">Quando un team privato è individuabile, viene visualizzato nei risultati della ricerca ed è incluso nei suggerimenti della raccolta team insieme ai team pubblici in teams.</span><span class="sxs-lookup"><span data-stu-id="86323-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="86323-106">In questo modo è facile per gli utenti cercare e trovare i team privati a cui vogliono partecipare.</span><span class="sxs-lookup"><span data-stu-id="86323-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="86323-107">Gli utenti possono richiedere di partecipare a un team privato e un proprietario del team può quindi approvare o rifiutare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="86323-107">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="86323-108">Panoramica di Team pubblici, team privati e individuazione in teams</span><span class="sxs-lookup"><span data-stu-id="86323-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="86323-109">La maggior parte delle organizzazioni ha i seguenti tipi di Team: team pubblici, team privati individuabili e team privati non individuabili.</span><span class="sxs-lookup"><span data-stu-id="86323-109">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Screenshot della raccolta team](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="86323-111">Team pubblici</span><span class="sxs-lookup"><span data-stu-id="86323-111">Public teams</span></span>

<span data-ttu-id="86323-112">I team pubblici sono disponibili per tutti gli utenti dell'organizzazione a cui partecipare.</span><span class="sxs-lookup"><span data-stu-id="86323-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="86323-113">I team pubblici sono visibili a tutti i membri della raccolta teams e gli utenti possono partecipare a un team pubblico senza dover ottenere l'approvazione del proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="86323-113">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="86323-114">Gli esempi di Team pubblici includono un team per discutere notizie tecnologiche, un team per ottenere feedback per i tuoi prodotti e un team per consentire alle persone di carpooling di lavorare.</span><span class="sxs-lookup"><span data-stu-id="86323-114">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="86323-115">Team privati individuabili</span><span class="sxs-lookup"><span data-stu-id="86323-115">Discoverable private teams</span></span>

<span data-ttu-id="86323-116">I team privati individuabili possono essere Uniti solo quando il proprietario del team aggiunge gli utenti.</span><span class="sxs-lookup"><span data-stu-id="86323-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="86323-117">Quando rendi un team privato individuabile, il team è incluso nell'elenco dei team suggeriti e dei risultati della ricerca nella raccolta teams.</span><span class="sxs-lookup"><span data-stu-id="86323-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="86323-118">USA teams privati individuabili per progetti e gruppi dell'organizzazione che tutti siano a conoscenza e dove sia necessario controllare l'accesso alle conversazioni e ai file del team.</span><span class="sxs-lookup"><span data-stu-id="86323-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="86323-119">Gli esempi includono un team per il reparto HR, un team per tutti i responsabili dell'organizzazione e un team per un Manager e i relativi report diretti.</span><span class="sxs-lookup"><span data-stu-id="86323-119">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="86323-120">Team privati non individuabili</span><span class="sxs-lookup"><span data-stu-id="86323-120">Non-discoverable private teams</span></span>

<span data-ttu-id="86323-121">I team privati non individuabili possono essere Uniti solo quando il proprietario del team aggiunge gli utenti.</span><span class="sxs-lookup"><span data-stu-id="86323-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="86323-122">Quando rendi un team privato non individuabile, è nascosto dall'elenco dei team suggeriti e rimosso dai risultati della ricerca nella raccolta teams.</span><span class="sxs-lookup"><span data-stu-id="86323-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="86323-123">USA team non individuabili per collaborare a argomenti sensibili e altamente riservati.</span><span class="sxs-lookup"><span data-stu-id="86323-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="86323-124">Gli esempi includono un team per discutere di un'acquisizione imminente e di un team per discutere un cambiamento nella direzione strategica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="86323-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="86323-125">Impostare se i nuovi team privati sono individuabili</span><span class="sxs-lookup"><span data-stu-id="86323-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="86323-126">Quando un proprietario del team crea un team privato, può scegliere di renderlo individuabile configurando l'impostazione di individuazione del team.</span><span class="sxs-lookup"><span data-stu-id="86323-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="86323-127">Per impostazione predefinita, i nuovi team privati sono ricercabili e individuabili.</span><span class="sxs-lookup"><span data-stu-id="86323-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="86323-128">Se il proprietario del team non vuole che il team privato venga visualizzato nei risultati della ricerca e nei suggerimenti, il proprietario può disattivare l'impostazione selezionando **Modifica impostazione** accanto a **questo team è possibile eseguire la ricerca e**l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="86323-128">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Schermata dell'impostazione individuazione per i nuovi team privati](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="86323-130">Impostare se i team privati esistenti sono individuabili</span><span class="sxs-lookup"><span data-stu-id="86323-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="86323-131">I proprietari del team possono impostare l'impostazione di individuazione per un team privato esistente direttamente nelle impostazioni del team e gli amministratori possono farlo usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86323-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="86323-132">Nelle impostazioni del team</span><span class="sxs-lookup"><span data-stu-id="86323-132">In team settings</span></span>

<span data-ttu-id="86323-133">In teams, vai al team privato, fai clic su **altre opzioni** > **Gestisci team**.</span><span class="sxs-lookup"><span data-stu-id="86323-133">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="86323-134">Nella scheda **Impostazioni** espandere **individuazione team**e quindi deselezionare o selezionare la casella di controllo **attiva individuabilità** .</span><span class="sxs-lookup"><span data-stu-id="86323-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Schermata dell'impostazione individuazione per i team privati esistenti](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="86323-136">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="86323-136">Using PowerShell</span></span>

<span data-ttu-id="86323-137">Utilizzare il cmdlet **[set-team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** per disattivare o attivare l'impostazione di individuazione per un team privato esistente.</span><span class="sxs-lookup"><span data-stu-id="86323-137">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="86323-138">Ecco un esempio di come rendere individuabile un team:</span><span class="sxs-lookup"><span data-stu-id="86323-138">Here's an example of how to make a team discoverable:</span></span>
```
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
<span data-ttu-id="86323-139">Puoi usare questo cmdlet in uno script per impostare l'impostazione di individuazione dei team privati esistenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="86323-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="86323-140">Impostare se gli utenti possono trovare team privati</span><span class="sxs-lookup"><span data-stu-id="86323-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="86323-141">Come amministratore, puoi anche controllare gli utenti dell'organizzazione che possono scoprire team privati nei risultati della ricerca e nei suggerimenti in teams.</span><span class="sxs-lookup"><span data-stu-id="86323-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="86323-142">Creare un criterio usando il cmdlet **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** e quindi assegnare i criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="86323-142">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="86323-143">Imposta il parametro **AllowPrivateTeamDiscovery** su **true** per consentire agli utenti a cui viene assegnato il criterio di visualizzare team privati individuabili nei risultati della ricerca e nei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="86323-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="86323-144">L'impostazione del parametro **AllowPrivateTeamDiscovery** su **false** consente di rimuovere tutti i team privati individuabili dai risultati della ricerca e dai suggerimenti per gli utenti a cui è stato assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="86323-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="86323-145">Per impostazione predefinita, **AllowPrivateTeamDiscovery** è impostato su **true** per tutti gli utenti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="86323-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="86323-146">In questo esempio creiamo un criterio denominato VendorPolicy che impedisce agli utenti di individuare eventuali team privati resi individuabili e quindi assegniamo i criteri a un utente denominato vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="86323-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="86323-147">I team privati non individuabili non vengono mai visualizzati nei risultati della ricerca e nei suggerimenti, indipendentemente dall'impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="86323-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="86323-148">Ad esempio, se disattivi l'impostazione di individuazione per un team privato, gli utenti non riescono a individuare il team, anche se il parametro **AllowPrivateTeamDiscovery** è impostato su **true** nell'impostazione dei criteri per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="86323-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="86323-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="86323-149">Related topics</span></span>
- [<span data-ttu-id="86323-150">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="86323-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
