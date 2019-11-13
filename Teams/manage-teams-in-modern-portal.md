---
title: Gestire team nell'interfaccia di amministrazione di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Informazioni su come visualizzare o aggiornare i team nell'interfaccia di amministrazione di Microsoft teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7adfc2762d632f600f2982445f381139263894
ms.sourcegitcommit: ed7439d03e37c9c0184daf5215a68c5492932a83
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "38290936"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b1b43-103">Gestire team nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1b43-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="b1b43-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b1b43-104">Overview</span></span>

<span data-ttu-id="b1b43-105">Questo articolo offre una panoramica degli strumenti di gestione per i team nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="b1b43-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b1b43-106">Iniziare guardando questo breve video (3 minuti):</span><span class="sxs-lookup"><span data-stu-id="b1b43-106">Start by watching this short video (3 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

<span data-ttu-id="b1b43-107">Come amministratore, potrebbe essere necessario visualizzare o aggiornare i team configurati dall'organizzazione per la collaborazione oppure eseguire azioni correttive come l'assegnazione di proprietari per team non proprietari.</span><span class="sxs-lookup"><span data-stu-id="b1b43-107">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="b1b43-108">Puoi gestire i team usati nell'organizzazione tramite il modulo Microsoft teams PowerShell e l'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="b1b43-108">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="b1b43-109">Per le funzionalità di amministrazione complete che usano questi due set di strumenti, è necessario assicurarsi che sia stato assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1b43-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="b1b43-110">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="b1b43-110">Global Administrator</span></span>
- <span data-ttu-id="b1b43-111">Amministratore del servizio Teams</span><span class="sxs-lookup"><span data-stu-id="b1b43-111">Teams Service Administrator</span></span>

<span data-ttu-id="b1b43-112">Per altre informazioni sui ruoli di amministratore in teams, è possibile [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md)e altre informazioni su come usare i cmdlet di PowerShell per la gestione dei team nel [riferimento ai cmdlet di Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b1b43-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="b1b43-113">Griglia Panoramica Teams</span><span class="sxs-lookup"><span data-stu-id="b1b43-113">Teams overview grid</span></span>

<span data-ttu-id="b1b43-114">Gli strumenti di gestione per i team sono inclusi nel nodo **Teams** nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="b1b43-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b1b43-115">Nell'interfaccia di amministrazione selezionare **Teams** > **Manage teams**. Ogni team è supportato da un gruppo di Office 365 e questo nodo offre una visualizzazione dei gruppi che sono stati abilitati da Microsoft teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b1b43-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Screenshot della griglia di panoramica Teams](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="b1b43-117">La griglia Visualizza le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1b43-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="b1b43-118">**Nome del team**</span><span class="sxs-lookup"><span data-stu-id="b1b43-118">**Team name**</span></span>
- <span data-ttu-id="b1b43-119">**Channels** : numero di tutti i canali del team, incluso il canale generale predefinito.</span><span class="sxs-lookup"><span data-stu-id="b1b43-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="b1b43-120">**Membri del team** -numero totale di utenti, inclusi proprietari, Guest e membri del tenant.</span><span class="sxs-lookup"><span data-stu-id="b1b43-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="b1b43-121">**Proprietari** -numero di proprietari per il team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="b1b43-122">**Clienti** -numero di utenti guest di Azure Active Directory B2B che sono membri di questo team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="b1b43-123">**Privacy** -visibilità/AccessType del gruppo di Office 365 di supporto.</span><span class="sxs-lookup"><span data-stu-id="b1b43-123">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="b1b43-124">**Stato** : lo stato archiviato o attivo per il team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="b1b43-125">Leggi altre informazioni sull'archiviazione di teams in [Archive o su come ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="b1b43-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="b1b43-126">**Descrizione** : Descrizione del gruppo di Office 365 di supporto.</span><span class="sxs-lookup"><span data-stu-id="b1b43-126">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="b1b43-127">**Classificazione** : classificazione (se usata nell'organizzazione) assegnata al gruppo di Office 365 di supporto.</span><span class="sxs-lookup"><span data-stu-id="b1b43-127">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="b1b43-128">Leggi altre informazioni sulle classificazioni in [creare classificazioni per i gruppi di Office nell'organizzazione](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="b1b43-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="b1b43-129">**GroupID** : GroupID univoco del gruppo di Office 365 di supporto.</span><span class="sxs-lookup"><span data-stu-id="b1b43-129">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="b1b43-130">Se non sono visualizzate tutte queste proprietà nella griglia, fare clic sull'icona **modifica colonne** .</span><span class="sxs-lookup"><span data-stu-id="b1b43-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="b1b43-131">Nel riquadro **modifica colonne** è possibile usare gli interruttori per attivare o disattivare le colonne nella griglia.</span><span class="sxs-lookup"><span data-stu-id="b1b43-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="b1b43-132">Al termine, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="b1b43-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="b1b43-133">Aggiungere</span><span class="sxs-lookup"><span data-stu-id="b1b43-133">Add</span></span>

<span data-ttu-id="b1b43-134">Per aggiungere un nuovo team, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b1b43-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="b1b43-135">Nel riquadro **Aggiungi un nuovo team** assegna al team un nome e una descrizione, imposta se vuoi renderlo un team privato o pubblico e imposta la classificazione.</span><span class="sxs-lookup"><span data-stu-id="b1b43-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="b1b43-136">Modifica</span><span class="sxs-lookup"><span data-stu-id="b1b43-136">Edit</span></span>

<span data-ttu-id="b1b43-137">Per modificare le impostazioni specifiche per il gruppo e il team, selezionare il team facendo clic a sinistra del nome del team e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b1b43-137">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="b1b43-138">Archivio</span><span class="sxs-lookup"><span data-stu-id="b1b43-138">Archive</span></span>

<span data-ttu-id="b1b43-139">È possibile archiviare un team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-139">You can archive a team.</span></span> <span data-ttu-id="b1b43-140">L'archiviazione di un team inserisce il team in modalità di sola lettura all'interno di teams.</span><span class="sxs-lookup"><span data-stu-id="b1b43-140">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="b1b43-141">L'amministratore può archiviare e annullare l'archiviazione di team per conto della propria organizzazione nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="b1b43-141">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="b1b43-142">Eliminare</span><span class="sxs-lookup"><span data-stu-id="b1b43-142">Delete</span></span>

<span data-ttu-id="b1b43-143">L'eliminazione di un team è un'eliminazione morbida del team e del gruppo di Office 365 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b1b43-143">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="b1b43-144">Per ripristinare un team eliminato erroneamente, seguire le istruzioni in [ripristinare un gruppo di Office 365 eliminato](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="b1b43-144">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="b1b43-145">Ricerca</span><span class="sxs-lookup"><span data-stu-id="b1b43-145">Search</span></span>

<span data-ttu-id="b1b43-146">La ricerca attualmente supporta la stringa "inizia con" e cerca il campo **nome Team** .</span><span class="sxs-lookup"><span data-stu-id="b1b43-146">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="b1b43-147">Profilo del team</span><span class="sxs-lookup"><span data-stu-id="b1b43-147">Team profile</span></span>

<span data-ttu-id="b1b43-148">È possibile passare alla pagina del profilo del team di un team dalla griglia Panoramica di team principali facendo clic sul nome del team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-148">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="b1b43-149">La pagina del profilo del team Mostra i membri, i proprietari e gli ospiti che appartengono al team (e il relativo gruppo di supporto di Office 365), nonché i canali e le impostazioni del team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-149">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="b1b43-150">Nella pagina del profilo del team è possibile:</span><span class="sxs-lookup"><span data-stu-id="b1b43-150">From the team profile page, you can:</span></span>

- <span data-ttu-id="b1b43-151">Aggiungere o rimuovere membri e proprietari.</span><span class="sxs-lookup"><span data-stu-id="b1b43-151">Add or remove members and owners.</span></span>
- <span data-ttu-id="b1b43-152">Aggiungere o rimuovere canali (si noti che non è possibile rimuovere il canale generale).</span><span class="sxs-lookup"><span data-stu-id="b1b43-152">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="b1b43-153">Modificare le impostazioni del team e del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b1b43-153">Change team and group settings.</span></span>
 
![Screenshot di un profilo del team di esempio](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="b1b43-155">Apportare modifiche ai team</span><span class="sxs-lookup"><span data-stu-id="b1b43-155">Making changes to teams</span></span>

<span data-ttu-id="b1b43-156">Nella pagina del profilo del team è possibile modificare gli elementi seguenti di un team:</span><span class="sxs-lookup"><span data-stu-id="b1b43-156">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="b1b43-157">**Membri** : aggiungere o rimuovere membri e promuovere o abbassare di livello i proprietari.</span><span class="sxs-lookup"><span data-stu-id="b1b43-157">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="b1b43-158">**Canali** : aggiungere nuovi canali e modificare o rimuovere i canali esistenti.</span><span class="sxs-lookup"><span data-stu-id="b1b43-158">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="b1b43-159">Tenere presente che non è possibile eliminare il canale generale predefinito.</span><span class="sxs-lookup"><span data-stu-id="b1b43-159">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="b1b43-160">**Nome del team**</span><span class="sxs-lookup"><span data-stu-id="b1b43-160">**Team name**</span></span>
- <span data-ttu-id="b1b43-161">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b1b43-161">**Description**</span></span>
- <span data-ttu-id="b1b43-162">**Privacy** : specificare se il team è pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="b1b43-162">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="b1b43-163">**Classificazione** : è supportato dalle classificazioni dei gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1b43-163">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="b1b43-164">Scegliere **riservate**, **altamente riservate**o **generali**.</span><span class="sxs-lookup"><span data-stu-id="b1b43-164">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="b1b43-165">**Impostazioni conversazioni** -imposta se i membri possono modificare ed eliminare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="b1b43-165">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="b1b43-166">**Impostazioni canali** : imposta se i membri possono creare nuovi canali e modificare quelli esistenti e aggiungere, modificare e rimuovere schede, connettori e app.</span><span class="sxs-lookup"><span data-stu-id="b1b43-166">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="b1b43-167">Le modifiche apportate a un team vengono registrate.</span><span class="sxs-lookup"><span data-stu-id="b1b43-167">The changes that you make to a team are logged.</span></span> <span data-ttu-id="b1b43-168">Se si modificano le impostazioni di gruppo (modificando il nome, la descrizione, la foto, la privacy, la classificazione o i membri del team), le modifiche vengono attribuite all'utente tramite la pipeline di controllo.</span><span class="sxs-lookup"><span data-stu-id="b1b43-168">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="b1b43-169">Se si eseguono azioni per le impostazioni specifiche di un team, le modifiche vengono rilevate e attribuite all'utente nel canale generale del team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-169">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b1b43-170">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b1b43-170">Troubleshooting</span></span>

<span data-ttu-id="b1b43-171">**Problema: team mancanti nella griglia di panoramica del team**</span><span class="sxs-lookup"><span data-stu-id="b1b43-171">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="b1b43-172">Alcuni dei team sono mancanti nell'elenco dei team nella griglia Panoramica teams.</span><span class="sxs-lookup"><span data-stu-id="b1b43-172">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="b1b43-173">**Causa**: questo problema si verifica quando il team è stato in modo non corretto (o non ancora) profilato dal sistema, che può causare una proprietà mancante che venga riconosciuta.</span><span class="sxs-lookup"><span data-stu-id="b1b43-173">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="b1b43-174">**Risoluzione: impostare manualmente la proprietà sul valore corretto tramite MS Graph**</span><span class="sxs-lookup"><span data-stu-id="b1b43-174">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="b1b43-175">Sostituire **{GroupID}** nella query per l'effettivo GroupID in questione, che è possibile ottenere tramite la PowerShell di Exchange Online, con il cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , come attributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="b1b43-175">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="b1b43-176">[Esplora grafico](https://developer.microsoft.com/graph/graph-explorer)di Access.</span><span class="sxs-lookup"><span data-stu-id="b1b43-176">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="b1b43-177">Accedere a Esplora grafici nel menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="b1b43-177">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="b1b43-178">Modificare la riga della query in: PATCH > v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}>.</span><span class="sxs-lookup"><span data-stu-id="b1b43-178">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="b1b43-179">Aggiungere il valore seguente nel corpo della richiesta: {"resourceProvisioningOptions": ["team"]}.</span><span class="sxs-lookup"><span data-stu-id="b1b43-179">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="b1b43-180">Eseguire la query in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="b1b43-180">Run the query on the top-right.</span></span>

6. <span data-ttu-id="b1b43-181">Verificare che il team sia correttamente visualizzato nell'interfaccia di amministrazione di Microsoft teams-Panoramica del team.</span><span class="sxs-lookup"><span data-stu-id="b1b43-181">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="b1b43-182">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b1b43-182">Learn more</span></span>

- [<span data-ttu-id="b1b43-183">Informazioni di riferimento sui cmdlet Teams</span><span class="sxs-lookup"><span data-stu-id="b1b43-183">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="b1b43-184">Usare i ruoli di amministratore teams per gestire Teams</span><span class="sxs-lookup"><span data-stu-id="b1b43-184">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="b1b43-185">Pianificare la gestione del ciclo di vita in Teams</span><span class="sxs-lookup"><span data-stu-id="b1b43-185">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
