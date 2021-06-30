---
title: Archiviare o eliminare un team in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: In questo articolo verrà indicato come archiviare o eliminare definitivamente un team in Microsoft Teams.
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
ms.openlocfilehash: 88c5bf29717efaa75f166e515006cfdb39461448
ms.sourcegitcommit: 0c942d9e25f9a51bb9bd22b40c5926e1d6d3892d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53186925"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="f1053-103">Archiviare o eliminare un team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f1053-103">Archive or delete a team in Microsoft Teams</span></span>

<span data-ttu-id="f1053-104">Nel corso del tempo, un team creato in Microsoft Teams potrebbe non essere più usato o potrebbe essere necessario archiviare o eliminare un team alla fine di un progetto.</span><span class="sxs-lookup"><span data-stu-id="f1053-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="f1053-105">Se si è un amministratore di Microsoft Teams, seguire i passaggi di questo articolo per archiviare o eliminare un team non più necessario.</span><span class="sxs-lookup"><span data-stu-id="f1053-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="f1053-106">Quando avviene l'archiviazione di un team, cessano tutte le attività relative a quel team.</span><span class="sxs-lookup"><span data-stu-id="f1053-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="f1053-107">L'archiviazione di un team comprende anche i canali privati nel team e le raccolte siti associate.</span><span class="sxs-lookup"><span data-stu-id="f1053-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="f1053-108">Tuttavia, è comunque possibile aggiungere o rimuovere membri e aggiornare i ruoli, nonché visualizzare tutte le attività del team in canali, chat e file standard e privati.</span><span class="sxs-lookup"><span data-stu-id="f1053-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="f1053-109">Con l'eliminazione di un team, vengono eliminate anche le attività del team in canali, chat e file standard e privati (e nelle raccolte siti associate).</span><span class="sxs-lookup"><span data-stu-id="f1053-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1053-110">I team archiviati possono essere riattivati, ma non è possibile ripristinare direttamente un team eliminato.</span><span class="sxs-lookup"><span data-stu-id="f1053-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="f1053-111">Considerare la possibilità di archiviare prima il team e di posticipare l'eliminazione finché non si è certi di non aver più bisogno del team.</span><span class="sxs-lookup"><span data-stu-id="f1053-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="f1053-112">Archiviare un team</span><span class="sxs-lookup"><span data-stu-id="f1053-112">Archive a team</span></span>

<span data-ttu-id="f1053-113">Seguire questi passaggi per archiviare un team.</span><span class="sxs-lookup"><span data-stu-id="f1053-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="f1053-114">Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="f1053-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="f1053-115">Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](./using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f1053-115">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="f1053-116">Nell'interfaccia di amministrazione, selezionare **Teams**.</span><span class="sxs-lookup"><span data-stu-id="f1053-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="f1053-117">Selezionare un team facendo clic sul nome del team.</span><span class="sxs-lookup"><span data-stu-id="f1053-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="f1053-118">Selezionare **Archivia**.</span><span class="sxs-lookup"><span data-stu-id="f1053-118">Select **Archive**.</span></span> <span data-ttu-id="f1053-119">Verrà visualizzato il messaggio seguente.</span><span class="sxs-lookup"><span data-stu-id="f1053-119">The following message will appear.</span></span>

    ![Screenshot del messaggio di archiviazione di Teams](media/teams-archive-message.png)

4. <span data-ttu-id="f1053-121">Per evitare che gli utenti modifichino i contenuti nel sito di SharePoint e nella scheda Wiki associati al team, selezionare **Rendere il sito di SharePoint di sola lettura per i membri del team**.</span><span class="sxs-lookup"><span data-stu-id="f1053-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="f1053-122">(I proprietari di Teams potranno ancora modificare questi contenuti.)</span><span class="sxs-lookup"><span data-stu-id="f1053-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="f1053-123">Selezionare **Archivia** per archiviare il team.</span><span class="sxs-lookup"><span data-stu-id="f1053-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="f1053-124">Lo stato del team diventerà **Archiviato**.</span><span class="sxs-lookup"><span data-stu-id="f1053-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="f1053-125">Attivare un team archiviato</span><span class="sxs-lookup"><span data-stu-id="f1053-125">Make an archived team active</span></span>

<span data-ttu-id="f1053-126">Seguire questi passaggi per attivare nuovamente un team archiviato.</span><span class="sxs-lookup"><span data-stu-id="f1053-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="f1053-127">Nell'interfaccia di amministrazione, selezionare **Teams**.</span><span class="sxs-lookup"><span data-stu-id="f1053-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="f1053-128">Selezionare un team facendo clic sul nome del team.</span><span class="sxs-lookup"><span data-stu-id="f1053-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="f1053-129">Selezionare **Annulla archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="f1053-129">Select **Unarchive**.</span></span> <span data-ttu-id="f1053-130">Lo stato del team diventerà **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="f1053-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="f1053-131">Eliminare un team</span><span class="sxs-lookup"><span data-stu-id="f1053-131">Delete a team</span></span>

<span data-ttu-id="f1053-132">Se il team non è più necessario, è possibile eseguire l’eliminazione al posto dell’archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f1053-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="f1053-133">Seguire questi passaggi per eliminare il team.</span><span class="sxs-lookup"><span data-stu-id="f1053-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="f1053-134">Nell'interfaccia di amministrazione, selezionare **Teams**.</span><span class="sxs-lookup"><span data-stu-id="f1053-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="f1053-135">Selezionare un team facendo clic sul nome del team.</span><span class="sxs-lookup"><span data-stu-id="f1053-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="f1053-136">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f1053-136">Select **Delete**.</span></span> <span data-ttu-id="f1053-137">Verrà visualizzato un messaggio di conferma.</span><span class="sxs-lookup"><span data-stu-id="f1053-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="f1053-138">Selezionare **Elimina** per eliminare definitivamente il team.</span><span class="sxs-lookup"><span data-stu-id="f1053-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="f1053-139">Ripristinare un team eliminato</span><span class="sxs-lookup"><span data-stu-id="f1053-139">Restore a deleted team</span></span>

<span data-ttu-id="f1053-140">Seguire questi passaggi per ripristinare un team eliminato ripristinando il gruppo di Microsoft 365 associato al team.</span><span class="sxs-lookup"><span data-stu-id="f1053-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="f1053-141">Il ripristino del gruppo di Microsoft 365 per un team ripristina anche i contenuti del team, incluse schede, canali standard e privati e raccolte siti associate.</span><span class="sxs-lookup"><span data-stu-id="f1053-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="f1053-142">Per impostazione predefinita, un gruppo di Microsoft 365 viene mantenuto per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f1053-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="f1053-143">Questo periodo di 30 giorni è definito di "eliminazione temporanea", perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="f1053-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="f1053-144">Per ulteriori informazioni, vedere [Ripristinare un gruppo eliminato](/microsoft-365/admin/create-groups/restore-deleted-group).</span><span class="sxs-lookup"><span data-stu-id="f1053-144">To learn more, see [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="f1053-145">Installare l’anteprima del modulo di Azure AD</span><span class="sxs-lookup"><span data-stu-id="f1053-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="f1053-146">Aprire Windows PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="f1053-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="f1053-147">Se è presente l’installazione di una versione precedente del modulo di Azure AD o di una sua anteprima, disinstallarlo eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1053-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="f1053-148">Installare la versione più recente dell’anteprima del modulo di Azure AD eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1053-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="f1053-149">Ripristinare il gruppo di Microsoft 365 eliminato</span><span class="sxs-lookup"><span data-stu-id="f1053-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="f1053-150">Connettersi ad Azure AD eseguendo le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="f1053-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="f1053-151">Quando viene richiesto, accedere con l'account e la password di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f1053-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="f1053-152">Eseguire questo comando per visualizzare un elenco dei gruppi di Microsoft 365 eliminati temporaneamente che sono ancora compresi nel periodo di conservazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f1053-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="f1053-153">Utilizzare il parametro **-All $True** se sono presenti molti gruppi.</span><span class="sxs-lookup"><span data-stu-id="f1053-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="f1053-154">Individuare il gruppo che si vuole ripristinare e quindi prendere nota dell'ID.</span><span class="sxs-lookup"><span data-stu-id="f1053-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="f1053-155">Eseguire le operazioni seguenti, in cui [Id] è l'ID del gruppo, per ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="f1053-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="f1053-156">Eseguire le operazioni seguenti, in cui [Id] è l'ID del gruppo, per verificare che il gruppo sia stato ripristinato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f1053-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="f1053-157">Il completamento del processo di ripristino può richiedere fino a 24 ore, dopodiché il team e i contenuti associati al team, incluse le schede e i canali, verranno visualizzati in Teams.</span><span class="sxs-lookup"><span data-stu-id="f1053-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f1053-158">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1053-158">Related topics</span></span>

- [<span data-ttu-id="f1053-159">Archiviare o ripristinare un team</span><span class="sxs-lookup"><span data-stu-id="f1053-159">Archive or restore a team</span></span>](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 
