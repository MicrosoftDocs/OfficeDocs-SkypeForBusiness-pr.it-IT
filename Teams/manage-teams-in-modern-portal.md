---
title: Gestire team nell'interfaccia di amministrazione di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Informazioni su come visualizzare o aggiornare i team nell'interfaccia di amministrazione di Microsoft teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183859"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c05af-103">Gestire team nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c05af-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="c05af-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c05af-104">Overview</span></span>

<span data-ttu-id="c05af-105">In qualità di amministratore IT, potrebbe essere necessario visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione o può essere necessario eseguire azioni correttive come l'assegnazione di proprietari per team non proprietari.</span><span class="sxs-lookup"><span data-stu-id="c05af-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="c05af-106">Puoi gestire i team usati nell'organizzazione tramite il modulo Microsoft teams PowerShell e l'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c05af-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="c05af-107">Per le funzionalità di amministrazione complete che usano questi due set di strumenti, è necessario assicurarsi che sia stato assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c05af-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="c05af-108">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="c05af-108">Global Administrator</span></span>
- <span data-ttu-id="c05af-109">Amministratore del servizio Teams</span><span class="sxs-lookup"><span data-stu-id="c05af-109">Teams Service Administrator</span></span>

<span data-ttu-id="c05af-110">Per altre informazioni sui ruoli di amministratore in teams, è possibile [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md)e altre informazioni su come usare i cmdlet di PowerShell per la gestione dei team nel [riferimento ai cmdlet di Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c05af-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="c05af-111">Questo articolo offre una panoramica degli strumenti di gestione per i team nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c05af-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="c05af-112">Griglia Panoramica Teams</span><span class="sxs-lookup"><span data-stu-id="c05af-112">Teams overview grid</span></span>

<span data-ttu-id="c05af-113">Gli strumenti di gestione per i team \*\*\*\* sono inclusi nel nodo teams nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c05af-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c05af-114">Nell'interfaccia di amministrazione selezionare teams \*\*\*\* > **Manage teams**. Ogni team è supportato da un gruppo di Office 365 e questo nodo offre una visualizzazione dei gruppi che sono stati abilitati da Microsoft teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c05af-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Screenshot della griglia di panoramica Teams](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="c05af-116">La griglia Visualizza le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c05af-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="c05af-117">**Nome del team**</span><span class="sxs-lookup"><span data-stu-id="c05af-117">**Team name**</span></span>
- <span data-ttu-id="c05af-118">**Channels** : numero di tutti i canali del team, incluso il canale generale predefinito.</span><span class="sxs-lookup"><span data-stu-id="c05af-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="c05af-119">**Utenti** : numero totale di utenti, inclusi proprietari, Guest e membri del tenant.</span><span class="sxs-lookup"><span data-stu-id="c05af-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="c05af-120">**Proprietari** -numero di proprietari per il team.</span><span class="sxs-lookup"><span data-stu-id="c05af-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="c05af-121">**Clienti** -numero di utenti guest di Azure Active Directory B2B che sono membri di questo team.</span><span class="sxs-lookup"><span data-stu-id="c05af-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="c05af-122">**Privacy** -visibilità/AccessType del gruppo di Office 365 di supporto.</span><span class="sxs-lookup"><span data-stu-id="c05af-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="c05af-123">**Stato** : lo stato archiviato o attivo per il team.</span><span class="sxs-lookup"><span data-stu-id="c05af-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="c05af-124">Altre informazioni sull'archiviazione dei team nell' [archivio o sul ripristino di un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="c05af-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="c05af-125">**GroupID** -il GroupID univoco del gruppo di Office 365 di supporto</span><span class="sxs-lookup"><span data-stu-id="c05af-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="c05af-126">**Classificazione** : classificazione (se usata nell'organizzazione) assegnata al gruppo di Office 365 di supporto.</span><span class="sxs-lookup"><span data-stu-id="c05af-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="c05af-127">Leggi altre informazioni sulle classificazioni in [creare classificazioni per i gruppi di Office nell'organizzazione](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c05af-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="c05af-128">**Descrizione** : set di descrizioni per il gruppo di backup di Office 365</span><span class="sxs-lookup"><span data-stu-id="c05af-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="c05af-129">Ricerca</span><span class="sxs-lookup"><span data-stu-id="c05af-129">Search</span></span>

<span data-ttu-id="c05af-130">La ricerca attualmente supporta la stringa "inizia con" e cerca il campo **nome Team** .</span><span class="sxs-lookup"><span data-stu-id="c05af-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="c05af-131">Modifica</span><span class="sxs-lookup"><span data-stu-id="c05af-131">Edit</span></span>

<span data-ttu-id="c05af-132">È possibile modificare le impostazioni specifiche del gruppo e del team selezionando un team dalla griglia e quindi selezionando il pulsante **modifica** .</span><span class="sxs-lookup"><span data-stu-id="c05af-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Screenshot delle opzioni di modifica del team](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="c05af-134">Profilo del team</span><span class="sxs-lookup"><span data-stu-id="c05af-134">Team profile</span></span>

<span data-ttu-id="c05af-135">È possibile passare alla pagina del profilo del team di un team dalla griglia Panoramica di team principali facendo clic sul nome del team.</span><span class="sxs-lookup"><span data-stu-id="c05af-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="c05af-136">La pagina del profilo del team Mostra i membri, i proprietari e gli ospiti che appartengono al team (e il relativo gruppo di Office 365 di supporto), nonché i canali e le impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="c05af-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="c05af-137">Nella pagina del profilo del team è possibile:</span><span class="sxs-lookup"><span data-stu-id="c05af-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="c05af-138">Aggiungere o rimuovere membri e proprietari.</span><span class="sxs-lookup"><span data-stu-id="c05af-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="c05af-139">Aggiungere o rimuovere canali (si noti che non è possibile rimuovere il canale generale).</span><span class="sxs-lookup"><span data-stu-id="c05af-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="c05af-140">Aggiornare le impostazioni del team e del gruppo.</span><span class="sxs-lookup"><span data-stu-id="c05af-140">Update team and group settings.</span></span>
 
![Screenshot di un profilo del team di esempio](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="c05af-142">Apportare modifiche ai team</span><span class="sxs-lookup"><span data-stu-id="c05af-142">Making changes to teams</span></span>

<span data-ttu-id="c05af-143">È possibile modificare gli elementi seguenti di un team:</span><span class="sxs-lookup"><span data-stu-id="c05af-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="c05af-144">**Utenti del team** : è possibile aggiungere o rimuovere membri e promuovere o abbassare di livello i proprietari</span><span class="sxs-lookup"><span data-stu-id="c05af-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="c05af-145">**Canali** : è possibile aggiungere nuovi canali o rimuovere i canali esistenti.</span><span class="sxs-lookup"><span data-stu-id="c05af-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="c05af-146">Non è possibile eliminare il canale "generale" predefinito e, una volta creato, è possibile modificare solo il nome del canale e non la descrizione.</span><span class="sxs-lookup"><span data-stu-id="c05af-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="c05af-147">**Nome del team**</span><span class="sxs-lookup"><span data-stu-id="c05af-147">**Team name**</span></span>
- <span data-ttu-id="c05af-148">**Descrizione del team**</span><span class="sxs-lookup"><span data-stu-id="c05af-148">**Team description**</span></span>
- <span data-ttu-id="c05af-149">**Privacy del team** -pubblico o privato</span><span class="sxs-lookup"><span data-stu-id="c05af-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="c05af-150">**Classificazione del team** -supportato dalle classificazioni dei gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="c05af-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="c05af-151">**Impostazioni** per i membri del team: selezionare impostazioni membro del team</span><span class="sxs-lookup"><span data-stu-id="c05af-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="c05af-152">Altre modifiche supportate ai team</span><span class="sxs-lookup"><span data-stu-id="c05af-152">Other supported changes to teams</span></span>

- <span data-ttu-id="c05af-153">**Elimina** -l'eliminazione di un team è un'eliminazione morbida del team e del gruppo di Office 365 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c05af-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="c05af-154">Per ripristinare un team eliminato erroneamente, seguire le istruzioni riportate in [ripristinare un gruppo di Office 365 eliminato](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c05af-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="c05af-155">**Archivio** -archiviazione un team inserisce il team in modalità di sola lettura all'interno di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c05af-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="c05af-156">L'amministratore può archiviare e disarchiviare team per conto dell'organizzazione tramite il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c05af-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="c05af-157">Le modifiche apportate a un team vengono registrate.</span><span class="sxs-lookup"><span data-stu-id="c05af-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="c05af-158">Se si modificano le impostazioni di gruppo (modificando il nome, la descrizione, la foto, la privacy, la classificazione o i membri del team), queste modifiche verranno attribuite all'utente tramite la pipeline di controllo.</span><span class="sxs-lookup"><span data-stu-id="c05af-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="c05af-159">Se si eseguono azioni per le impostazioni specifiche di un team, le modifiche verranno rilevate e attribuite all'utente nel canale generale del team.</span><span class="sxs-lookup"><span data-stu-id="c05af-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c05af-160">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c05af-160">Troubleshooting</span></span>

<span data-ttu-id="c05af-161">**Problema: team mancanti nella griglia di panoramica del team**</span><span class="sxs-lookup"><span data-stu-id="c05af-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="c05af-162">Quando si immette l'interfaccia di amministrazione di Microsoft teams \*\*\*\* , sotto l'opzione teams alcuni dei team mancanti nell'elenco nella griglia Panoramica teams.</span><span class="sxs-lookup"><span data-stu-id="c05af-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="c05af-163">**Causa**: questo problema si verifica quando il team è stato in modo non corretto (o non ancora) profilato dal sistema, che può causare una proprietà mancante che venga riconosciuta.</span><span class="sxs-lookup"><span data-stu-id="c05af-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="c05af-164">**Risoluzione: impostare manualmente la proprietà sul valore corretto tramite MS Graph**</span><span class="sxs-lookup"><span data-stu-id="c05af-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="c05af-165">Sostituire **{GroupID}** nella query per l'effettivo GroupID in questione, che è possibile ottenere tramite la PowerShell di Exchange Online, con il cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , come attributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="c05af-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="c05af-166">[Esplora grafico](https://developer.microsoft.com/en-us/graph/graph-explorer) di Access</span><span class="sxs-lookup"><span data-stu-id="c05af-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="c05af-167">Accedere a Esplora grafici nel menu a sinistra</span><span class="sxs-lookup"><span data-stu-id="c05af-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="c05af-168">Cambiare la riga della query in: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="c05af-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="c05af-169">Aggiungere il valore seguente nel corpo della richiesta: {"resourceProvisioningOptions": ["team"]}</span><span class="sxs-lookup"><span data-stu-id="c05af-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="c05af-170">Eseguire la query in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="c05af-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="c05af-171">Verificare che il team sia correttamente visualizzato nell'interfaccia di amministrazione di Microsoft teams-Panoramica del team</span><span class="sxs-lookup"><span data-stu-id="c05af-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="c05af-172">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="c05af-172">Learn more</span></span>

[<span data-ttu-id="c05af-173">Informazioni di riferimento sui cmdlet di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c05af-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="c05af-174">Ruoli di amministratore in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c05af-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

