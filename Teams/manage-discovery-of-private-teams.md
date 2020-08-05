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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come controllare se i team privati possono essere scoperti dagli utenti di Microsoft teams tramite suggerimenti nella raccolta team e nei risultati della ricerca.
ms.openlocfilehash: e06a9511d8198a069c3dccfdbbbacf3d3f1b2c42
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46554696"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="dd9db-103">Gestire l'individuazione di team privati in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd9db-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd9db-104">In base al feedback dei clienti, stiamo disabilitando questa funzionalità, in vigore il 31 agosto 2020.</span><span class="sxs-lookup"><span data-stu-id="dd9db-104">Based on customer feedback, we're disabling this feature, effective August 31, 2020.</span></span> <span data-ttu-id="dd9db-105">Ciò significa che dopo il 31 agosto 2020 non sarà più possibile impostare team privati come individuabili e tutti i nuovi team privati esistenti non saranno più individuabili.</span><span class="sxs-lookup"><span data-stu-id="dd9db-105">This means that after August 31, 2020, you will no longer be able to set private teams to be discoverable and all existing and new private teams will no longer be discoverable.</span></span> <span data-ttu-id="dd9db-106">Per altre informazioni, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370).</span><span class="sxs-lookup"><span data-stu-id="dd9db-106">To learn more, see the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370).</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="dd9db-107">Gli amministratori e i proprietari del team possono controllare se i team privati possono essere scoperti dagli utenti di Microsoft teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd9db-107">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="dd9db-108">Quando un team privato è individuabile, viene visualizzato nei risultati della ricerca ed è incluso nei suggerimenti della raccolta team insieme ai team pubblici in teams.</span><span class="sxs-lookup"><span data-stu-id="dd9db-108">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="dd9db-109">In questo modo è facile per gli utenti cercare e trovare i team privati a cui vogliono partecipare.</span><span class="sxs-lookup"><span data-stu-id="dd9db-109">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="dd9db-110">Gli utenti possono richiedere di partecipare a un team privato e un proprietario del team può quindi approvare o rifiutare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="dd9db-110">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="dd9db-111">Panoramica di Team pubblici, team privati e individuazione in teams</span><span class="sxs-lookup"><span data-stu-id="dd9db-111">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="dd9db-112">La maggior parte delle organizzazioni ha i seguenti tipi di Team: team pubblici, team privati individuabili e team privati non individuabili.</span><span class="sxs-lookup"><span data-stu-id="dd9db-112">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Screenshot della raccolta team](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="dd9db-114">Team pubblici</span><span class="sxs-lookup"><span data-stu-id="dd9db-114">Public teams</span></span>

<span data-ttu-id="dd9db-115">I team pubblici sono disponibili per tutti gli utenti dell'organizzazione a cui partecipare.</span><span class="sxs-lookup"><span data-stu-id="dd9db-115">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="dd9db-116">I team pubblici sono visibili a tutti i membri della raccolta teams e gli utenti possono partecipare a un team pubblico senza dover ottenere l'approvazione del proprietario del team.</span><span class="sxs-lookup"><span data-stu-id="dd9db-116">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="dd9db-117">Gli esempi di Team pubblici includono un team per discutere notizie tecnologiche, un team per ottenere feedback per i tuoi prodotti e un team per consentire alle persone di carpooling di lavorare.</span><span class="sxs-lookup"><span data-stu-id="dd9db-117">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="dd9db-118">Team privati individuabili</span><span class="sxs-lookup"><span data-stu-id="dd9db-118">Discoverable private teams</span></span>

<span data-ttu-id="dd9db-119">I team privati individuabili possono essere Uniti solo quando il proprietario del team aggiunge gli utenti.</span><span class="sxs-lookup"><span data-stu-id="dd9db-119">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="dd9db-120">Quando rendi un team privato individuabile, il team è incluso nell'elenco dei team suggeriti e dei risultati della ricerca nella raccolta teams.</span><span class="sxs-lookup"><span data-stu-id="dd9db-120">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="dd9db-121">USA teams privati individuabili per progetti e gruppi dell'organizzazione che tutti siano a conoscenza e dove sia necessario controllare l'accesso alle conversazioni e ai file del team.</span><span class="sxs-lookup"><span data-stu-id="dd9db-121">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="dd9db-122">Gli esempi includono un team per il reparto HR, un team per tutti i responsabili dell'organizzazione e un team per un Manager e i relativi report diretti.</span><span class="sxs-lookup"><span data-stu-id="dd9db-122">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="dd9db-123">Team privati non individuabili</span><span class="sxs-lookup"><span data-stu-id="dd9db-123">Non-discoverable private teams</span></span>

<span data-ttu-id="dd9db-124">I team privati non individuabili possono essere Uniti solo quando il proprietario del team aggiunge gli utenti.</span><span class="sxs-lookup"><span data-stu-id="dd9db-124">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="dd9db-125">Quando rendi un team privato non individuabile, è nascosto dall'elenco dei team suggeriti e rimosso dai risultati della ricerca nella raccolta teams.</span><span class="sxs-lookup"><span data-stu-id="dd9db-125">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="dd9db-126">USA team non individuabili per collaborare a argomenti sensibili e altamente riservati.</span><span class="sxs-lookup"><span data-stu-id="dd9db-126">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="dd9db-127">Gli esempi includono un team per discutere di un'acquisizione imminente e di un team per discutere un cambiamento nella direzione strategica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd9db-127">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="dd9db-128">Impostare se i nuovi team privati sono individuabili</span><span class="sxs-lookup"><span data-stu-id="dd9db-128">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="dd9db-129">Quando un proprietario del team crea un team privato, può scegliere di renderlo individuabile configurando l'impostazione di individuazione del team.</span><span class="sxs-lookup"><span data-stu-id="dd9db-129">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="dd9db-130">Per impostazione predefinita, i nuovi team privati sono ricercabili e individuabili.</span><span class="sxs-lookup"><span data-stu-id="dd9db-130">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="dd9db-131">Se il proprietario del team non vuole che il team privato venga visualizzato nei risultati della ricerca e nei suggerimenti, il proprietario può disattivare l'impostazione selezionando **Modifica impostazione** accanto a **questo team è possibile eseguire la ricerca e**l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="dd9db-131">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Schermata dell'impostazione individuazione per i nuovi team privati](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="dd9db-133">Impostare se i team privati esistenti sono individuabili</span><span class="sxs-lookup"><span data-stu-id="dd9db-133">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="dd9db-134">I proprietari del team possono impostare l'impostazione di individuazione per un team privato esistente direttamente nelle impostazioni del team e gli amministratori possono farlo usando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd9db-134">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="dd9db-135">Nelle impostazioni del team</span><span class="sxs-lookup"><span data-stu-id="dd9db-135">In team settings</span></span>

<span data-ttu-id="dd9db-136">In teams, vai al team privato, fai clic su **altre opzioni**  >  **Gestisci team**.</span><span class="sxs-lookup"><span data-stu-id="dd9db-136">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="dd9db-137">Nella scheda **Impostazioni** espandere **individuazione team**e quindi deselezionare o selezionare la casella di controllo **attiva individuabilità** .</span><span class="sxs-lookup"><span data-stu-id="dd9db-137">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Schermata dell'impostazione individuazione per i team privati esistenti](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="dd9db-139">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd9db-139">Using PowerShell</span></span>

<span data-ttu-id="dd9db-140">Utilizzare il cmdlet **[set-team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** per disattivare o attivare l'impostazione di individuazione per un team privato esistente.</span><span class="sxs-lookup"><span data-stu-id="dd9db-140">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="dd9db-141">Ecco un esempio di come rendere individuabile un team:</span><span class="sxs-lookup"><span data-stu-id="dd9db-141">Here's an example of how to make a team discoverable:</span></span>
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
<span data-ttu-id="dd9db-142">Puoi usare questo cmdlet in uno script per impostare l'impostazione di individuazione dei team privati esistenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="dd9db-142">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="dd9db-143">Impostare se gli utenti possono trovare team privati</span><span class="sxs-lookup"><span data-stu-id="dd9db-143">Set whether users can discover private teams</span></span>

<span data-ttu-id="dd9db-144">Come amministratore, puoi anche controllare gli utenti dell'organizzazione che possono scoprire team privati nei risultati della ricerca e nei suggerimenti in teams.</span><span class="sxs-lookup"><span data-stu-id="dd9db-144">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="dd9db-145">Creare un criterio usando il cmdlet **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** e quindi assegnare i criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="dd9db-145">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="dd9db-146">Imposta il parametro **AllowPrivateTeamDiscovery** su **true** per consentire agli utenti a cui viene assegnato il criterio di visualizzare team privati individuabili nei risultati della ricerca e nei suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="dd9db-146">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="dd9db-147">L'impostazione del parametro **AllowPrivateTeamDiscovery** su **false** consente di rimuovere tutti i team privati individuabili dai risultati della ricerca e dai suggerimenti per gli utenti a cui è stato assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="dd9db-147">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="dd9db-148">Per impostazione predefinita, **AllowPrivateTeamDiscovery** è impostato su **true** per tutti gli utenti di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd9db-148">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="dd9db-149">In questo esempio creiamo un criterio denominato VendorPolicy che impedisce agli utenti di individuare eventuali team privati resi individuabili e quindi assegniamo i criteri a un utente denominato vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="dd9db-149">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="dd9db-150">I team privati non individuabili non vengono mai visualizzati nei risultati della ricerca e nei suggerimenti, indipendentemente dall'impostazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="dd9db-150">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="dd9db-151">Ad esempio, se disattivi l'impostazione di individuazione per un team privato, gli utenti non riescono a individuare il team, anche se il parametro **AllowPrivateTeamDiscovery** è impostato su **true** nell'impostazione dei criteri per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="dd9db-151">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dd9db-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dd9db-152">Related topics</span></span>
- [<span data-ttu-id="dd9db-153">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="dd9db-153">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
