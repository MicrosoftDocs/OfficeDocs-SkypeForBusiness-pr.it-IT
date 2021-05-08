---
title: Gestire i team nell'Microsoft Teams di amministrazione
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Informazioni su come visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione nell'Microsoft Teams di amministrazione.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237542"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="97248-103">Gestire i team nell'Microsoft Teams di amministrazione</span><span class="sxs-lookup"><span data-stu-id="97248-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="97248-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="97248-104">Overview</span></span>

<span data-ttu-id="97248-105">Questo articolo fornisce una panoramica degli strumenti di gestione per Teams nell'interfaccia Microsoft Teams amministrazione.</span><span class="sxs-lookup"><span data-stu-id="97248-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="97248-106">L'amministratore potrebbe dover visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione oppure potrebbe essere necessario eseguire azioni di correzione, ad esempio l'assegnazione di proprietari per i team senza proprietario.</span><span class="sxs-lookup"><span data-stu-id="97248-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="97248-107">È possibile gestire i team usati nell'organizzazione tramite il modulo Microsoft Teams PowerShell e l'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="97248-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="97248-108">È possibile accedere all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="97248-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="97248-109">Per le funzionalità di amministrazione complete che usano questi due set di strumenti, è consigliabile assicurarsi di avere uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="97248-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="97248-110">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="97248-110">Global Administrator</span></span>
- <span data-ttu-id="97248-111">Teams Amministratore</span><span class="sxs-lookup"><span data-stu-id="97248-111">Teams Administrator</span></span>

<span data-ttu-id="97248-112">Per altre informazioni sui ruoli di amministratore in Teams, vedere Usare i ruoli di amministratore di Microsoft Teams per gestire [Teams](using-admin-roles.md)e altre informazioni su come usare i cmdlet di PowerShell per la gestione dei team nella guida di riferimento ai cmdlet di [Microsoft Teams.](/powershell/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="97248-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="97248-113">Teams griglia panoramica</span><span class="sxs-lookup"><span data-stu-id="97248-113">Teams overview grid</span></span>

<span data-ttu-id="97248-114">Gli strumenti di gestione per i team **si** Teams nodo Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="97248-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="97248-115">Nell'interfaccia di amministrazione selezionare **Teams**  >  **Gestire i team.)** Ogni team è supportato da un gruppo Microsoft 365 e questo nodo offre una visualizzazione dei gruppi abilitati Microsoft Teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="97248-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Screenshot della griglia Teams panoramica](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="97248-117">La griglia visualizza le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="97248-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="97248-118">**Nome del team**</span><span class="sxs-lookup"><span data-stu-id="97248-118">**Team name**</span></span>
- <span data-ttu-id="97248-119">**Canali:** conteggio di tutti i canali del team, incluso il canale generale predefinito.</span><span class="sxs-lookup"><span data-stu-id="97248-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="97248-120">**Membri del** team: numero totale di utenti, inclusi proprietari, guest e membri del tenant.</span><span class="sxs-lookup"><span data-stu-id="97248-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="97248-121">**Proprietari:** numero di proprietari per questo team.</span><span class="sxs-lookup"><span data-stu-id="97248-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="97248-122">**Guest:** numero di Azure Active Directory utenti guest B2B che sono membri di questo team.</span><span class="sxs-lookup"><span data-stu-id="97248-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="97248-123">**Privacy:** visibilità/AccessType del gruppo di Microsoft 365 di backup.</span><span class="sxs-lookup"><span data-stu-id="97248-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="97248-124">**Stato:** lo stato Archiviato o Attivo per questo team.</span><span class="sxs-lookup"><span data-stu-id="97248-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="97248-125">Altre informazioni sui team di archiviazione in [Archiviare o ripristinare un team.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="97248-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="97248-126">**Descrizione:** descrizione del gruppo di Microsoft 365 di backup.</span><span class="sxs-lookup"><span data-stu-id="97248-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="97248-127">**Classificazione:** classificazione (se usata nell'organizzazione) assegnata al gruppo di Microsoft 365 di backup.</span><span class="sxs-lookup"><span data-stu-id="97248-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="97248-128">Per altre informazioni sulle classificazioni, vedere [Creare classificazioni per Office gruppi nell'organizzazione.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="97248-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="97248-129">**GROUPID:** l'ID Gruppo univoco del gruppo Microsoft 365 di backup.</span><span class="sxs-lookup"><span data-stu-id="97248-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="97248-130">Se tutte queste proprietà non sono visualizzate nella griglia, fare clic **sull'icona Modifica** colonne.</span><span class="sxs-lookup"><span data-stu-id="97248-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="97248-131">Nel riquadro **Modifica colonne** è possibile usare gli interruttori per attivare o disattivare le colonne nella griglia.</span><span class="sxs-lookup"><span data-stu-id="97248-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="97248-132">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="97248-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="97248-133">Aggiungi</span><span class="sxs-lookup"><span data-stu-id="97248-133">Add</span></span>

<span data-ttu-id="97248-134">Per aggiungere un nuovo team, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="97248-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="97248-135">Nel riquadro **Aggiungi un nuovo team** assegnare un nome e una descrizione al team, specificare se si vuole impostarlo come team privato o pubblico e impostare la classificazione.</span><span class="sxs-lookup"><span data-stu-id="97248-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="97248-136">I team appena creati possono essere gestiti immediatamente nell'interfaccia di amministrazione di Teams, a differenza dell'esperienza di altri client come Outlook.</span><span class="sxs-lookup"><span data-stu-id="97248-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="97248-137">Modifica</span><span class="sxs-lookup"><span data-stu-id="97248-137">Edit</span></span>

<span data-ttu-id="97248-138">Per modificare le impostazioni specifiche del gruppo e del team, selezionare il team facendo clic a sinistra del nome del team e quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="97248-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="97248-139">Archivia</span><span class="sxs-lookup"><span data-stu-id="97248-139">Archive</span></span>

<span data-ttu-id="97248-140">È possibile archiviare un team.</span><span class="sxs-lookup"><span data-stu-id="97248-140">You can archive a team.</span></span> <span data-ttu-id="97248-141">L'archiviazione di un team consente al team di entrare in modalità di sola lettura all'interno Teams.</span><span class="sxs-lookup"><span data-stu-id="97248-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="97248-142">Gli amministratori possono archiviare e annullare l'archiviazione dei team per conto dell'organizzazione nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="97248-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="97248-143">Elimina</span><span class="sxs-lookup"><span data-stu-id="97248-143">Delete</span></span>

<span data-ttu-id="97248-144">L'eliminazione di un team è un'eliminazione soffice del team e del gruppo Microsoft 365 gruppo.</span><span class="sxs-lookup"><span data-stu-id="97248-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="97248-145">Per ripristinare un team eliminato per errore, seguire le istruzioni in [Ripristinare un gruppo eliminato.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="97248-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="97248-146">Ricerca</span><span class="sxs-lookup"><span data-stu-id="97248-146">Search</span></span>

<span data-ttu-id="97248-147">La ricerca attualmente supporta la stringa "Inizia con" ed esegue la ricerca nel **campo Nome** team.</span><span class="sxs-lookup"><span data-stu-id="97248-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="97248-148">Profilo del team</span><span class="sxs-lookup"><span data-stu-id="97248-148">Team profile</span></span>

<span data-ttu-id="97248-149">È possibile passare alla pagina del profilo del team di qualsiasi team dalla griglia di panoramica dei team principali facendo clic sul nome del team.</span><span class="sxs-lookup"><span data-stu-id="97248-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="97248-150">La pagina del profilo del team mostra i membri, i proprietari e gli utenti guest che appartengono al team (e il relativo gruppo di Microsoft 365 di supporto), nonché i canali e le impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="97248-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="97248-151">Dalla pagina del profilo del team è possibile:</span><span class="sxs-lookup"><span data-stu-id="97248-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="97248-152">Aggiungere o rimuovere membri e proprietari.</span><span class="sxs-lookup"><span data-stu-id="97248-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="97248-153">Aggiungere o rimuovere canali (si noti che non è possibile rimuovere il canale Generale).</span><span class="sxs-lookup"><span data-stu-id="97248-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="97248-154">Modificare le impostazioni del team e del gruppo.</span><span class="sxs-lookup"><span data-stu-id="97248-154">Change team and group settings.</span></span>
 
![Screenshot di un profilo del team di esempio](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="97248-156">Apportare modifiche ai team</span><span class="sxs-lookup"><span data-stu-id="97248-156">Making changes to teams</span></span>

<span data-ttu-id="97248-157">Nella pagina del profilo del team è possibile modificare gli elementi seguenti di un team:</span><span class="sxs-lookup"><span data-stu-id="97248-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="97248-158">**Membri:** aggiungere o rimuovere membri e alzare o abbassare di livello i proprietari.</span><span class="sxs-lookup"><span data-stu-id="97248-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="97248-159">**Canali:** aggiungere nuovi canali e modificare o rimuovere i canali esistenti.</span><span class="sxs-lookup"><span data-stu-id="97248-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="97248-160">Tenere presente che non è possibile eliminare il canale generale predefinito.</span><span class="sxs-lookup"><span data-stu-id="97248-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="97248-161">**Nome del team**</span><span class="sxs-lookup"><span data-stu-id="97248-161">**Team name**</span></span>
- <span data-ttu-id="97248-162">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="97248-162">**Description**</span></span>
- <span data-ttu-id="97248-163">**Privacy:** specificare se il team è pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="97248-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="97248-164">**Classificazione:** questa opzione è supportata dalle Microsoft 365 di gruppo.</span><span class="sxs-lookup"><span data-stu-id="97248-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="97248-165">Scegliere **Riservato,** **Altamente riservato** o **Generale.**</span><span class="sxs-lookup"><span data-stu-id="97248-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="97248-166">**Impostazioni conversazioni:** consente di specificare se i membri possono modificare ed eliminare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="97248-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="97248-167">**Impostazioni canali:** consente di specificare se i membri possono creare nuovi canali e modificare quelli esistenti e aggiungere, modificare e rimuovere schede, connettori e app.</span><span class="sxs-lookup"><span data-stu-id="97248-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="97248-168">Le modifiche apportate a un team vengono registrate.</span><span class="sxs-lookup"><span data-stu-id="97248-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="97248-169">Se si modificano le impostazioni del gruppo (modificando il nome, la descrizione, la foto, la privacy, la classificazione o i membri del team), le modifiche vengono attribuite tramite la pipeline di controllo.</span><span class="sxs-lookup"><span data-stu-id="97248-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="97248-170">Se si eseguono azioni Teams impostazioni specifiche, le modifiche vengono rilevate e attribuite all'utente nel canale Generale del team.</span><span class="sxs-lookup"><span data-stu-id="97248-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="97248-171">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="97248-171">Troubleshooting</span></span>

<span data-ttu-id="97248-172">**Problema: Teams nella griglia panoramica del team**</span><span class="sxs-lookup"><span data-stu-id="97248-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="97248-173">Alcuni dei team non sono presenti nell'elenco dei team nella griglia Teams panoramica.</span><span class="sxs-lookup"><span data-stu-id="97248-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="97248-174">**Causa:** questo problema si verifica quando il team è stato profilato in modo non corretto (o non ancora) dal sistema, causando la perdita di una proprietà per il riconoscimento.</span><span class="sxs-lookup"><span data-stu-id="97248-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="97248-175">**Soluzione: impostare manualmente la proprietà sul valore corretto tramite MS Graph**</span><span class="sxs-lookup"><span data-stu-id="97248-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="97248-176">Sostituire **{groupid}** nella query per l'effettivo GroupId in questione, che è possibile ottenere tramite powershell di Exchange Online, con il cmdlet **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)",** come attributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="97248-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="97248-177">Accedere [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="97248-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="97248-178">Accedere a Graph Explorer nel menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="97248-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="97248-179">Modificare la riga della query in: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} .</span><span class="sxs-lookup"><span data-stu-id="97248-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="97248-180">Aggiungere il valore seguente nel corpo della richiesta: {"resourceProvisioningOptions": ["Team"]}.</span><span class="sxs-lookup"><span data-stu-id="97248-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="97248-181">Eseguire la query in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="97248-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="97248-182">Verificare che il team venga visualizzato correttamente nell'interfaccia Microsoft Teams di amministrazione - Panoramica del team.</span><span class="sxs-lookup"><span data-stu-id="97248-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="97248-183">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="97248-183">Learn more</span></span>

- [<span data-ttu-id="97248-184">Teams cmdlet</span><span class="sxs-lookup"><span data-stu-id="97248-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="97248-185">Usare Teams di amministratore per gestire i Teams</span><span class="sxs-lookup"><span data-stu-id="97248-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="97248-186">Pianificare la gestione del ciclo di vita in Teams</span><span class="sxs-lookup"><span data-stu-id="97248-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)