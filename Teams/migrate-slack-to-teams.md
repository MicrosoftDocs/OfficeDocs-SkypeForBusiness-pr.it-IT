---
title: Effettuare la migrazione da Slack a Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- NOCSH
description: Indicazioni complete per effettuare la migrazione da Slack a Microsoft Teams.
ms.openlocfilehash: 15ef6203fa2cf27d081865e3966198f033b1bd80
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845213"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a><span data-ttu-id="c637b-103">Effettuare la migrazione da Slack a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c637b-103">Migrate from Slack to Microsoft Teams</span></span>

<span data-ttu-id="c637b-104">Questo articolo illustra il passaggio da Slack a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-104">This article walks you through the journey of moving to Microsoft Teams from Slack.</span></span>

<span data-ttu-id="c637b-105">Quando si pianifica il passaggio dell'organizzazione da Slack a Teams, è importante stabilire cosa è necessario eventualmente mantenere.</span><span class="sxs-lookup"><span data-stu-id="c637b-105">When planning your organization’s move to Teams from Slack, it's important to decide what you need to keep (if anything).</span></span> <span data-ttu-id="c637b-106">Verranno innanzitutto descritti i tipi di dati che possono essere migrati, quindi verrà illustrato come valutare le esigenze, pianificare il passaggio e infine eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="c637b-106">We'll start off by describing what types of data can be migrated and then walk you through how to assess your needs, plan your move, and then make the move.</span></span>

<span data-ttu-id="c637b-107">Il diagramma di seguito riportato mostra l'architettura di Slack a un livello elevato.</span><span class="sxs-lookup"><span data-stu-id="c637b-107">The diagram below shows the Slack architecture at a high level.</span></span>

![Immagine che mostra l'architettura di Slack a un livello elevato](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a><span data-ttu-id="c637b-109">Pianificare la migrazione da Slack</span><span class="sxs-lookup"><span data-stu-id="c637b-109">Plan your migration from Slack</span></span>
### <a name="what-you-can-and-cant-migrate"></a><span data-ttu-id="c637b-110">Cosa è possibile e cosa non è possibile migrare</span><span class="sxs-lookup"><span data-stu-id="c637b-110">What you can and can’t migrate</span></span>
<span data-ttu-id="c637b-111">Il piano di servizio di Slack determina cosa è possibile e cosa non è possibile migrare.</span><span class="sxs-lookup"><span data-stu-id="c637b-111">Your Slack service plan will determine what you can and can’t migrate.</span></span> <span data-ttu-id="c637b-112">Ad esempio, alcuni piani di servizio di Slack consentono di esportare solo la cronologia e i file dei canali pubblici, altri necessitano di una richiesta di DocuSign per includere canali privati e messaggi diretti.</span><span class="sxs-lookup"><span data-stu-id="c637b-112">For example, some Slack service plans only let you export public channels history and files, other require a DocuSign request to include Private Channels and Direct Messages.</span></span> 

<span data-ttu-id="c637b-113">Per stabilire il livello di servizio dell'area di lavoro di Slack, accedere a Slack e prendere nota del tipo di piano riportato nella pagina **Informazioni sull'area di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="c637b-113">To determine your Slack Workspace service level, log into Slack and note your plan type on the **About this Workspace** page.</span></span>

<span data-ttu-id="c637b-114">Per altre informazioni sulle opzioni di esportazione di Slack, visitare il sito Web di Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="c637b-114">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

<span data-ttu-id="c637b-115">Il diagramma che segue offre una panoramica generale della migrazione di Slack illustrata in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c637b-115">The diagram below gives you a high-level look at the Slack migration landscape that we’ll cover in this article.</span></span> 

![Diagramma che mostra una panoramica dell'esportazione di Slack.](media/migrate-slack-to-teams-image2.png)

<span data-ttu-id="c637b-117">Al termine di questa sezione, il lettore sarà in grado di comprendere i seguenti concetti:</span><span class="sxs-lookup"><span data-stu-id="c637b-117">When you're done with this section, you should understand:</span></span>
- <span data-ttu-id="c637b-118">Il livello di servizio delle aree di lavoro di Slack</span><span class="sxs-lookup"><span data-stu-id="c637b-118">The service level of your Slack Workspaces</span></span>
- <span data-ttu-id="c637b-119">Cosa può e cosa non può essere esportato</span><span class="sxs-lookup"><span data-stu-id="c637b-119">What can and can't be exported</span></span>
- <span data-ttu-id="c637b-120">Approcci comuni all'esportazione</span><span class="sxs-lookup"><span data-stu-id="c637b-120">Common approaches to exporting</span></span>

### <a name="assess-your-slack-workspaces"></a><span data-ttu-id="c637b-121">Valutare le aree di lavoro di Slack</span><span class="sxs-lookup"><span data-stu-id="c637b-121">Assess your Slack workspaces</span></span>
<span data-ttu-id="c637b-122">Per poter pianificare il piano di migrazione dell'organizzazione, è necessario raccogliere alcune informazioni sulle aree di lavoro di Slack.</span><span class="sxs-lookup"><span data-stu-id="c637b-122">Before you can plan your organization’s migration plan, you need to pull together some information about your Slack workspaces.</span></span> <span data-ttu-id="c637b-123">Comprendere come vengono utilizzate le aree di lavoro di Slack consente di determinare l'ambito della migrazione.</span><span class="sxs-lookup"><span data-stu-id="c637b-123">Understanding how your Slack workspaces are being used helps you determine the scope of your migration.</span></span> <span data-ttu-id="c637b-124">Ad esempio, quante aree di lavoro verranno spostate?</span><span class="sxs-lookup"><span data-stu-id="c637b-124">For example, how many workspaces are being moved?</span></span> <span data-ttu-id="c637b-125">Le aree di lavoro vengono utilizzate da un reparto specifico, da molti reparti o da un'intera organizzazione?</span><span class="sxs-lookup"><span data-stu-id="c637b-125">Are they used by a specific department, many, or in use by an entire organization?</span></span>

<span data-ttu-id="c637b-126">Se si è membri delle aree di lavoro di Slack che si desidera migrare, è possibile analizzarne l'uso andando su *<your Slack workspace>.slack.com/stats*. Esaminare le schede Canali e Membri per cercare i modelli di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c637b-126">If you’re a member of the Slack Workspaces you want to migrate, you can analyze the usage yourself by going to *<your Slack workspace>.slack.com/stats*. Review the Channels and Members tabs to look for usage patterns.</span></span> <span data-ttu-id="c637b-127">Stabilire quali aree di lavoro si desidera migrare e quali si desidera lasciare.</span><span class="sxs-lookup"><span data-stu-id="c637b-127">Decide which workspaces you want to migrate (and which ones you want to leave behind).</span></span> 

> [!NOTE]
> <span data-ttu-id="c637b-128">Solo gli amministratori o i proprietari dispongono dell'accesso alla pagina stats.</span><span class="sxs-lookup"><span data-stu-id="c637b-128">If you don’t have access to the stats page, you’re not an admin or owner.</span></span> 

### <a name="export-channels"></a><span data-ttu-id="c637b-129">Esportare canali</span><span class="sxs-lookup"><span data-stu-id="c637b-129">Export Channels</span></span>

<span data-ttu-id="c637b-130">Gli utenti di Slack entrano in un canale che fa parte di un'area di lavoro di Slack, mentre gli utenti di Teams entrano in un team che rappresenta una raccolta di canali.</span><span class="sxs-lookup"><span data-stu-id="c637b-130">In Slack, users join a channel which is part of a Slack Workspace, whereas in Teams users join a team which is a collection of channels.</span></span> <span data-ttu-id="c637b-131">Si consiglia di utilizzare l'analisi di Slack per calcolare l'attività che avviene in ogni canale e stabilire quali canali spostare.</span><span class="sxs-lookup"><span data-stu-id="c637b-131">We recommend that you use Slack analytics to see how much activity happens in each channel to help you decide which channels to move.</span></span> <span data-ttu-id="c637b-132">L'elenco risultante potrà essere utilizzato per comprendere come raggruppare i canali di Slack in team di Teams, nonché per stabilire i membri di ciascun team.</span><span class="sxs-lookup"><span data-stu-id="c637b-132">You’ll use the resulting list to figure out how to group your Slack channels into teams in Teams as well as who should be members of each team.</span></span>

<span data-ttu-id="c637b-133">Se si dispone di un piano di servizio di Slack a pagamento (qualsiasi piano diverso da Free), è possibile utilizzare l'analisi di Slack (<your Slack workspace>.slack.com/admin/stats#channels) per verificare quanto un canale è attivo, quando è stato utilizzato l'ultima volta e quante persone ne sono membri.</span><span class="sxs-lookup"><span data-stu-id="c637b-133">If you have a paid Slack service plan (anything other than Free), you can use Slack’s analytics (<your Slack workspace>.slack.com/admin/stats#channels) to see how active a channel is, when it was last used, and how many people are members.</span></span> <span data-ttu-id="c637b-134">In questo modo è possibile stabilire se migrare il canale o meno.</span><span class="sxs-lookup"><span data-stu-id="c637b-134">This can help you decide whether to migrate the channel.</span></span> <span data-ttu-id="c637b-135">Per impostazione predefinita, il contenuto pubblico di un canale (messaggi e file) può essere esportato.</span><span class="sxs-lookup"><span data-stu-id="c637b-135">By default, public channels content (messages and files) can be exported.</span></span> <span data-ttu-id="c637b-136">In base al piano di servizio di Slack e a seconda che siano stati richiesti o meno, canali privati e messaggi diretti di Slack possono essere esportati.</span><span class="sxs-lookup"><span data-stu-id="c637b-136">Depending on your Slack service plan and whether you’ve requested Private Channels and Direct Messages from Slack, those can be exported.</span></span>

<span data-ttu-id="c637b-137">Per altre informazioni sulle opzioni di esportazione di Slack, visitare il sito Web di Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="c637b-137">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c637b-138">Controllare i requisiti di privacy e conformità dell'organizzazione per quanto riguarda i dati del canale.</span><span class="sxs-lookup"><span data-stu-id="c637b-138">Check your organization’s privacy and compliance requirements around channel data.</span></span> <span data-ttu-id="c637b-139">L'organizzazione potrebbe avere requisiti di conformità relativi alla gestione, all'archiviazione e all'elaborazione di tali dati, oltre a dover rispettare il ciclo di vita dei contenuti identificabili dell'utente finale (EUII).</span><span class="sxs-lookup"><span data-stu-id="c637b-139">Your organization may have compliance requirements around the handling, storage, and processing of this data, in addition to complying with the lifecycle of end-user identifiable content (EUII).</span></span>

### <a name="export-direct-messages"></a><span data-ttu-id="c637b-140">Esportare messaggi diretti</span><span class="sxs-lookup"><span data-stu-id="c637b-140">Export Direct Messages</span></span>
<span data-ttu-id="c637b-141">I messaggi diretti corrispondono alle chat di Teams, vale a dire conversazioni uno-a-uno o uno-a-molti che non avvengono sul canale.</span><span class="sxs-lookup"><span data-stu-id="c637b-141">Direct Messages are the same as chats in Teams, which are 1:1 or 1-to-many non-channel conversations.</span></span> <span data-ttu-id="c637b-142">La capacità di esportazione dipende dal piano di servizio di Slack e dal fatto che sia stato richiesto o meno che i messaggi diretti fossero inclusi nell'esportazione di Slack.</span><span class="sxs-lookup"><span data-stu-id="c637b-142">Export-ability depends on your Slack service plan and if you’ve requested Direct Messages to be included in your Slack Export.</span></span> <span data-ttu-id="c637b-143">Teams non supporta attualmente l'importazione di messaggi diretti.</span><span class="sxs-lookup"><span data-stu-id="c637b-143">Teams doesn’t support importing Direct messages currently.</span></span> <span data-ttu-id="c637b-144">Rivolgersi a un partner Microsoft per conoscere le soluzioni di terze parti che possono essere esaminate per visualizzare il contenuto dei messaggi diretti in Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-144">Consult a Microsoft partner to learn about third-party solutions you can explore that bring Direct Messages content into Teams.</span></span>

<span data-ttu-id="c637b-145">Per esportare i messaggi diretti, controllare strumenti come Esporta nell'App Store di Slack.</span><span class="sxs-lookup"><span data-stu-id="c637b-145">For exporting Direct Messages, check out tools, such as Export, in the Slack App Store.</span></span>

### <a name="apps-and-custom-integrations"></a><span data-ttu-id="c637b-146">App e integrazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c637b-146">Apps and custom integrations</span></span>

<span data-ttu-id="c637b-147">Le app in Slack sono come le app in Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-147">Apps in Slack are like apps in Teams.</span></span> <span data-ttu-id="c637b-148">Una volta ottenuto un elenco di app e delle relative configurazioni nell'area di lavoro, è possibile verificare nell'App Store di Teams se sono disponibili per Teams\*.</span><span class="sxs-lookup"><span data-stu-id="c637b-148">Once you have a list of apps and their configurations in the Workspace, you can search in the Teams App store to see if they’re available for Teams\*.</span></span> 

<span data-ttu-id="c637b-149">Accedere a <your Slack workspace>.slack.com/apps/manage per ottenere un elenco di app e integrazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="c637b-149">Go to <your Slack workspace>.slack.com/apps/manage to get a list of Apps and Custom Integrations.</span></span> <span data-ttu-id="c637b-150">In questa pagina viene riportato anche il numero di configurazioni utilizzate da ciascuna app.</span><span class="sxs-lookup"><span data-stu-id="c637b-150">This page also shows you the number of configurations where each app is in use.</span></span> <span data-ttu-id="c637b-151">Le integrazioni personalizzate variano in base alla capacità di migrazione.</span><span class="sxs-lookup"><span data-stu-id="c637b-151">Custom Integrations vary in their “migrate-ability.”</span></span> <span data-ttu-id="c637b-152">Se si tratta di un hook Web, in genere è possibile inviarlo a un connettore di Office 365 per spostare il flusso di lavoro in Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-152">If it’s a Web Hook, you can usually send it to an Office 365 Connector to shift the workflow into Teams.</span></span> <span data-ttu-id="c637b-153">Valutare bot e altre app caso per caso, per pianificarne il passaggio a Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-153">Assess bots and other apps on a case-by-case basis to plan for moving them to Teams.</span></span>

<span data-ttu-id="c637b-154">\*Se l'amministratore ha limitato l'utilizzo delle app, è possibile che l'elenco completo delle app disponibili non sia visibile.</span><span class="sxs-lookup"><span data-stu-id="c637b-154">\* If your administrator has restricted apps usage, you may not be looking at the full list of available apps.</span></span>

### <a name="users"></a><span data-ttu-id="c637b-155">Utenti</span><span class="sxs-lookup"><span data-stu-id="c637b-155">Users</span></span>
<span data-ttu-id="c637b-156">Gli schemi di identità utilizzati in Slack potrebbero non essere direttamente corrispondenti a Office 365.</span><span class="sxs-lookup"><span data-stu-id="c637b-156">The identity schemes you used in Slack might not map directly to Office 365.</span></span> <span data-ttu-id="c637b-157">Ad esempio, gli indirizzi e-mail degli utenti di Slack potrebbero non essere associati agli account aziendali o dell'istituto di istruzione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c637b-157">For example, the email addresses of your Slack users may not map to Office 365 work or school accounts.</span></span> <span data-ttu-id="c637b-158">Per iniziare a pianificare l'implementazione di Teams, è consigliabile creare una mappa di ID utente.</span><span class="sxs-lookup"><span data-stu-id="c637b-158">You should create a user-ID map before you start planning your Teams rollout.</span></span>

<span data-ttu-id="c637b-159">Se si dispone di un piano di servizio di Slack a pagamento, è possibile passare a *<your Slack workspace>.slack.com/admin/stats#members* per ottenere informazioni dettagliate sui membri, come l'indirizzo e-mail e il tipo di account per ogni utente, ad esempio guest singolo o multicanale.</span><span class="sxs-lookup"><span data-stu-id="c637b-159">If you’re on a paid Slack service plan, you can go to *<your Slack workspace>.slack.com/admin/stats#members* to get member details such as email address and account type for each user (for example, single vs. multi-channel guest).</span></span>

<span data-ttu-id="c637b-160">Di seguito viene riportato uno script che è possibile utilizzare per confrontare gli indirizzi e-mail di un'esportazione di Slack con Azure AD per risolvere l'ambiguità del nome.</span><span class="sxs-lookup"><span data-stu-id="c637b-160">Here’s a script you can use to compare email addresses from a Slack export against Azure AD to help solve for name ambiguity.</span></span> <span data-ttu-id="c637b-161">Lo script indica anche se l'utente è abilitato per Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-161">It’ll also report if the user is enabled for Teams.</span></span> <span data-ttu-id="c637b-162">Se è necessaria assistenza con PowerShell, consultare [Introduzione ad Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="c637b-162">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

<span data-ttu-id="c637b-163">Al termine di questa sezione, il lettore avrà acquisito i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="c637b-163">When you’re done with this section, you should have:</span></span>
- <span data-ttu-id="c637b-164">Un elenco di canali per ciascuna area di lavoro con statistiche di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c637b-164">A list of Channels per Workspace with usage statistics.</span></span>
- <span data-ttu-id="c637b-165">Un elenco di app di Slack con configurazioni per ciascun canale.</span><span class="sxs-lookup"><span data-stu-id="c637b-165">A list of Slack Apps with configurations per channel.</span></span>
- <span data-ttu-id="c637b-166">Avrà stabilito quale tipo di cronologia dei messaggi di Slack esportare (se disponibile).</span><span class="sxs-lookup"><span data-stu-id="c637b-166">Determined what type of Slack message history you want to export (if any).</span></span>
- <span data-ttu-id="c637b-167">Un elenco di utenti i cui account Slack sono associati agli account aziendali o dell'istituto di formazione Microsoft e le licenze Teams di cui dispongono.</span><span class="sxs-lookup"><span data-stu-id="c637b-167">A list of users whose Slack accounts map to Microsoft work or school accounts and which Teams license they have.</span></span>

## <a name="plan-your-teams-deployment"></a><span data-ttu-id="c637b-168">Pianificare la distribuzione di Teams</span><span class="sxs-lookup"><span data-stu-id="c637b-168">Plan your Teams deployment</span></span>
<span data-ttu-id="c637b-169">Gli elementi necessari di Slack sono stati esportati tralasciando tutto ciò di cui non si ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="c637b-169">You’ve exported what you need from Slack (and left behind anything you don’t need).</span></span> <span data-ttu-id="c637b-170">Ora è il momento di pianificare come distribuire Teams e importare i dati di Slack.</span><span class="sxs-lookup"><span data-stu-id="c637b-170">Now it’s time to plan how you’ll roll out Teams and import your Slack data.</span></span> <span data-ttu-id="c637b-171">Si tratta di una grande opportunità per valutare gli elementi che hanno funzionato per il team in base all'utilizzo e includere tali elementi nel piano di distribuzione di Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-171">This is a great opportunity to assess what's worked well for the team based on usage and include those elements in your Teams deployment plan.</span></span> <span data-ttu-id="c637b-172">Al termine di questa sezione, sarà disponibile un progetto per gli utenti, i canali e le app di Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-172">At the end of this section, you’ll have a blueprint for your Teams users, channels, and apps.</span></span> 

<span data-ttu-id="c637b-173">Il diagramma di seguito riportato fornisce una panoramica di livello elevato delle questioni che verranno affrontate durante la distribuzione di Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-173">The diagram below gives you a high-level outline of the things you’ll address in your Teams deployment.</span></span>

:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="Panoramica di livello elevato della pianificazione di una distribuzione di Teams da Slack.":::

### <a name="team-and-channel-structure"></a><span data-ttu-id="c637b-175">Struttura del team e del canale</span><span class="sxs-lookup"><span data-stu-id="c637b-175">Team and channel structure</span></span>

<span data-ttu-id="c637b-176">Un'area di lavoro di Slack potrebbe rappresentare un singolo team, più team o un'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c637b-176">A Slack Workspace may represent a single team, multiple teams or an entire organization.</span></span> <span data-ttu-id="c637b-177">È importante comprendere l'ambito delle aree di lavoro nel momento in cui si determina la struttura.</span><span class="sxs-lookup"><span data-stu-id="c637b-177">It’s important to understand the scope of the Workspaces as you determine the structure.</span></span> <span data-ttu-id="c637b-178">La relazione più stretta con un team di Teams in Slack è l'area di lavoro, che contiene una raccolta di canali.</span><span class="sxs-lookup"><span data-stu-id="c637b-178">The closest relationship to a Teams team in Slack is the Workspace, which contains a collection of channels.</span></span> <span data-ttu-id="c637b-179">Il diagramma di seguito riportato mostra 3 diverse associazioni tra Slack e Teams e una guida per la scelta dell'associazione giusta per ogni area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c637b-179">The diagram below demonstrates 3 different Slack-to-Teams mappings, and guidance for picking the right one for each Workspace.</span></span>


|<span data-ttu-id="c637b-180">Associazione tra Slack e Teams</span><span class="sxs-lookup"><span data-stu-id="c637b-180">Slack-to-Teams mapping</span></span> |  |
|---------|---------|
|<span data-ttu-id="c637b-181">1 area di lavoro di Slack :arrow_right: 1 team</span><span class="sxs-lookup"><span data-stu-id="c637b-181">1 Slack Workspace :arrow_right: 1 team</span></span>   | <span data-ttu-id="c637b-182">Per aree di lavoro di Slack più piccole che richiedono un numero inferiore a 200 canali</span><span class="sxs-lookup"><span data-stu-id="c637b-182">For smaller Slack workspaces that need fewer than 200 channels</span></span><br><span data-ttu-id="c637b-183">Includere un buffer per la crescita e la pianificazione del canale privato</span><span class="sxs-lookup"><span data-stu-id="c637b-183">Include a buffer for growth and private channel planning</span></span>  |
|<span data-ttu-id="c637b-184">1 area di lavoro di Slack :arrow_right: più team</span><span class="sxs-lookup"><span data-stu-id="c637b-184">1 Slack Workspace :arrow_right: multiple teams</span></span>     | <span data-ttu-id="c637b-185">Utilizzare i dati di analisi dell'area di lavoro di Slack per creare raggruppamenti logici di canali, che diventano la base dei team</span><span class="sxs-lookup"><span data-stu-id="c637b-185">Use your Slack Workspace analytics data to create logical channel groupings, which become the basis of your teams</span></span>        |
|<span data-ttu-id="c637b-186">Più di 2 aree di lavoro di Slack :arrow_right: più team</span><span class="sxs-lookup"><span data-stu-id="c637b-186">2+ Slack Workspaces :arrow_right: multiple teams</span></span>     | <span data-ttu-id="c637b-187">Utilizzare i dati di analisi dell'area di lavoro di Slack per creare raggruppamenti logici di team e canali, che diventano la base dei team</span><span class="sxs-lookup"><span data-stu-id="c637b-187">Use your Slack Workspace analytics data to create logical team and channel groupings, which become the basis of your teams</span></span>        |

<span data-ttu-id="c637b-188">Le soluzioni di terze parti includono statistiche di utilizzo che consentono di valutare l'attività del canale e il numero di post.</span><span class="sxs-lookup"><span data-stu-id="c637b-188">Third-party solutions have usage statistics to help you assess how active the channel is and how many posts there are.</span></span> <span data-ttu-id="c637b-189">In genere, i canali usati di frequente verranno inclusi nella pianificazione del team.</span><span class="sxs-lookup"><span data-stu-id="c637b-189">Typically, channels that are frequently used would be candidates to include in your team planning.</span></span>

> [!TIP]
> <span data-ttu-id="c637b-190">Mantenere solo gli elementi necessari nell'approccio per determinare quali canali ricreare in Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-190">Retain only what is required in your approach to determine which channels to recreate in Teams.</span></span> <span data-ttu-id="c637b-191">Per ulteriori informazioni, consultare [Panoramica su team e canali](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c637b-191">To learn more, read [Overview of teams and channels](teams-channels-overview.md).</span></span> 

#### <a name="team-planning"></a><span data-ttu-id="c637b-192">Pianificazione di team</span><span class="sxs-lookup"><span data-stu-id="c637b-192">Team Planning</span></span>
<span data-ttu-id="c637b-193">Utilizzando l'inventario dei canali compilato nella sezione Pianificazione illustrata in precedenza, collaborare con i proprietari e gli amministratori di Slack per individuare i canali che devono diventare team e i canali che devono diventare canali di un team.</span><span class="sxs-lookup"><span data-stu-id="c637b-193">Using the Channel inventory you compiled in the Planning section above, work with your Slack owners and admins to figure out which channels should become teams and which ones should become channels in a team.</span></span> <span data-ttu-id="c637b-194">Utilizzare Excel o PowerBI per semplificare l'analisi; entrambe le applicazioni forniscono ulteriori informazioni su quali canali mantenere.</span><span class="sxs-lookup"><span data-stu-id="c637b-194">Use either Excel or PowerBI to help with this analysis - both can provide additional insights to help drive these discussions on which channels to retain.</span></span>

> [!TIP]
> <span data-ttu-id="c637b-195">Teams ha attualmente un limite di 200 canali per ciascun team.</span><span class="sxs-lookup"><span data-stu-id="c637b-195">Teams currently has a 200-channel limit per team.</span></span> <span data-ttu-id="c637b-196">Se l'elenco di canali si avvicina a quel limite, è consigliabile suddividere i canali in due team diversi.</span><span class="sxs-lookup"><span data-stu-id="c637b-196">If your list of channels is getting close to that limit, you should figure out a way to split them into two separate teams.</span></span>

### <a name="channel-history"></a><span data-ttu-id="c637b-197">Cronologia dei canali</span><span class="sxs-lookup"><span data-stu-id="c637b-197">Channel History</span></span>

<span data-ttu-id="c637b-198">Per mantenere la cronologia dei canali pubblici e privati, è possibile utilizzare sia soluzioni gratuite su GitHub che soluzioni a pagamento, a seconda delle esigenze dell'organizzazione. </span><span class="sxs-lookup"><span data-stu-id="c637b-198">There are both free solutions on GitHub and paid solutions you can use, depending on your organization’s requirements to retain Channel History of Public and Private channels.</span></span> <span data-ttu-id="c637b-199">Queste informazioni potrebbero essere riportate anche in Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-199">Additionally, this could be scripted into Teams.</span></span>

<span data-ttu-id="c637b-200">Una volta configurata la nuova struttura di team e canali in Teams, è possibile copiare i file esportati nelle librerie di documenti appropriate nei canali di Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-200">Once you’ve set up your new team and channel structure in Teams, you can copy the exported files into the appropriate document libraries in your Teams channels.</span></span>

<span data-ttu-id="c637b-201">Per automatizzare l'importazione dei contenuti, è possibile prendere in considerazione diversi approcci.</span><span class="sxs-lookup"><span data-stu-id="c637b-201">To automate the importing of your content, there are several approaches you can consider.</span></span> <span data-ttu-id="c637b-202">Sono disponibili soluzioni gratuite su GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) o [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) e soluzioni partner.</span><span class="sxs-lookup"><span data-stu-id="c637b-202">There are  free solutions on GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) or [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) and partner solutions.</span></span> <span data-ttu-id="c637b-203">Scegliere una soluzione in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c637b-203">Choose a solution based on your organization’s needs.</span></span> 

### <a name="channel-files"></a><span data-ttu-id="c637b-204">File di canale</span><span class="sxs-lookup"><span data-stu-id="c637b-204">Channel Files</span></span>

<span data-ttu-id="c637b-205">La maggior parte delle soluzioni esportano i file.</span><span class="sxs-lookup"><span data-stu-id="c637b-205">Most solutions will export files.</span></span> <span data-ttu-id="c637b-206">Tuttavia, sono in genere fornite nella cronologia dei canali come link che richiedono una chiave API per essere recuperati in modo programmatico.</span><span class="sxs-lookup"><span data-stu-id="c637b-206">However, they’re typically provided as links in the Channel History that require an API key to programmatically retrieve.</span></span>

<span data-ttu-id="c637b-207">Per quanto riguarda i file archiviati in Slack, dopo aver configurato i team e i canali in Teams, è possibile copiare tali file da Slack nel canale Teams di destinazione in modo programmatico.</span><span class="sxs-lookup"><span data-stu-id="c637b-207">For files stored in Slack, once you’ve set up your teams and channels in Teams, you can programmatically copy them from Slack into the target Teams channel.</span></span>

<span data-ttu-id="c637b-208">Nello script che segue vengono recuperati file da Slack.</span><span class="sxs-lookup"><span data-stu-id="c637b-208">The following script retrieves files from Slack.</span></span> <span data-ttu-id="c637b-209">Viene cercata nel computer l'esportazione di Slack specificata, viene creata una cartella in ogni canale di destinazione e vengono scaricati tutti i file nella posizione desiderata.</span><span class="sxs-lookup"><span data-stu-id="c637b-209">It searches the specified Slack export on your computer, creates a folder in each target channel, and downloads all of the files to that location.</span></span> <span data-ttu-id="c637b-210">Esistono soluzioni di terze parti in grado di estrarre i dati.</span><span class="sxs-lookup"><span data-stu-id="c637b-210">Third-party solutions exist that can extract data.</span></span> <span data-ttu-id="c637b-211">Se è necessaria assistenza con PowerShell, consultare [Introduzione ad Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="c637b-211">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a><span data-ttu-id="c637b-212">App e integrazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c637b-212">Apps and Custom Integrations</span></span>
<span data-ttu-id="c637b-213">Esaminare l'elenco delle app e delle integrazioni personalizzate di Slack con le relative configurazioni e stabilire quali spostare in Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-213">Review your list of Slack apps and custom integrations (with configurations) and decide which ones you want to move to Teams.</span></span> <span data-ttu-id="c637b-214">Controllare il Marketplace di Teams per verificare se è disponibile un'app.</span><span class="sxs-lookup"><span data-stu-id="c637b-214">Check the Teams Marketplace to see if an app is available.</span></span> <span data-ttu-id="c637b-215">In caso contrario, è probabile che esistano delle alternative.</span><span class="sxs-lookup"><span data-stu-id="c637b-215">If not, there are likely alternatives.</span></span> 

<span data-ttu-id="c637b-216">Per individuare le app da aggiungere a Teams, è importante sapere come viene utilizzata l'app.</span><span class="sxs-lookup"><span data-stu-id="c637b-216">To figure out which apps to add to Teams, it’s important to understand how the app is being used.</span></span> <span data-ttu-id="c637b-217">Ponendo la domanda "quale funzionalità fornisce l'app a questo canale?", si potrà conoscere il risultato dell'utilizzo dell'app.</span><span class="sxs-lookup"><span data-stu-id="c637b-217">By asking the question "what functionality is the app providing to this channel?", you'll learn about the outcome the app is delivering.</span></span> 

<span data-ttu-id="c637b-218">In molti casi, le app ricevono dati in base agli eventi da un servizio esterno, ad esempio un sistema di monitoraggio, e inseriscono un messaggio in Slack.</span><span class="sxs-lookup"><span data-stu-id="c637b-218">In many cases, apps primarily receive event-driven data from an external service (for example, monitoring system) and push a message into Slack.</span></span> <span data-ttu-id="c637b-219">È possibile ottenere lo stesso risultato utilizzando un connettore di Microsoft 365, che consente di inviare messaggi in Teams in base agli eventi.</span><span class="sxs-lookup"><span data-stu-id="c637b-219">You can achieve the same outcome by using a Microsoft 365 Connector that can push messages into Teams based on events.</span></span>

<span data-ttu-id="c637b-220">Di seguito sono riportati alcuni esempi di soluzioni di Slack in cui è stato utilizzato un connettore di Office 365 in Teams per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="c637b-220">Below are examples of Slack solutions where an Office 365 Connector was used in Teams for integration.</span></span>
- <span data-ttu-id="c637b-221">Ansible</span><span class="sxs-lookup"><span data-stu-id="c637b-221">Ansible</span></span>
  - <span data-ttu-id="c637b-222">È possibile inviare avvisi a Teams tramite il [webhook di Ansible](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span><span class="sxs-lookup"><span data-stu-id="c637b-222">Alerts can be sent to Teams via [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span></span>
- <span data-ttu-id="c637b-223">New Relic</span><span class="sxs-lookup"><span data-stu-id="c637b-223">New Relic</span></span>
  - <span data-ttu-id="c637b-224">Verificare questa soluzione utente per [l'invio di nuovi avvisi Relic a Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span><span class="sxs-lookup"><span data-stu-id="c637b-224">Check out this user solution for [sending New Relic alerts to Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span></span>
- <span data-ttu-id="c637b-225">Nagios</span><span class="sxs-lookup"><span data-stu-id="c637b-225">Nagios</span></span>
  - <span data-ttu-id="c637b-226">Oggi gli avvisi possono essere integrati tramite connettori.</span><span class="sxs-lookup"><span data-stu-id="c637b-226">Alerts can be integrated today via Connectors.</span></span> <span data-ttu-id="c637b-227">https://github.com/isaac-galvan/nagios-teams-notify</span><span class="sxs-lookup"><span data-stu-id="c637b-227">https://github.com/isaac-galvan/nagios-teams-notify</span></span>
- <span data-ttu-id="c637b-228">ZenDesk</span><span class="sxs-lookup"><span data-stu-id="c637b-228">ZenDesk</span></span>
  - <span data-ttu-id="c637b-229">L'app è disponibile in Teams Store</span><span class="sxs-lookup"><span data-stu-id="c637b-229">App exists in Teams Store</span></span>
- <span data-ttu-id="c637b-230">Jenkins</span><span class="sxs-lookup"><span data-stu-id="c637b-230">Jenkins</span></span>
  - <span data-ttu-id="c637b-231">È possibile inviare avvisi a Teams utilizzando [Connettore di Office 365 di Jenkins](https://plugins.jenkins.io/Office-365-Connector)</span><span class="sxs-lookup"><span data-stu-id="c637b-231">Alerts can be sent to Teams using [Jenkins’s Office 365 Connector](https://plugins.jenkins.io/Office-365-Connector)</span></span>


### <a name="user-readiness-and-adoption-plan"></a><span data-ttu-id="c637b-232">Piano di disponibilità e adozione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c637b-232">User readiness and adoption plan</span></span>
<span data-ttu-id="c637b-233">L'elemento essenziale per l'esito positivo della distribuzione del software dipende da quanto gli utenti sono pronti al cambiamento.</span><span class="sxs-lookup"><span data-stu-id="c637b-233">The cornerstone of any successful software deployment hinges on how prepared users are for the change.</span></span> <span data-ttu-id="c637b-234">Gli utenti dell'organizzazione che utilizzano Slack potranno comprendere facilmente i concetti relativi a Teams, ma una formazione è comunque necessaria per facilitare la transizione.</span><span class="sxs-lookup"><span data-stu-id="c637b-234">Users in your organization using Slack will easily understand Teams concepts, but training is still needed to help them make a smooth transition.</span></span> <span data-ttu-id="c637b-235">Per un set completo di risorse di adozione di Teams, passare [all'hub di adozione di Teams](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c637b-235">For a comprehensive set of Teams adoption resources, go to the [Teams adoption hub](adopt-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="c637b-236">Ad esempio, entrambi i prodotti dispongono di canali, ma vengono usati in modo diverso in ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="c637b-236">For example, both products feature channels, but they’re used differently in each product.</span></span> <span data-ttu-id="c637b-237">Spesso un canale di Stack viene usato, ad esempio, come una chat in Teams per le conversazioni transazionali a breve termine.</span><span class="sxs-lookup"><span data-stu-id="c637b-237">For example, often a Channel in Slack is used like a chat in Teams for short-term, transactional conversations.</span></span> <span data-ttu-id="c637b-238">Altre importanti differenze sono relative alle conversazioni in thread e non in thread e alle impostazioni di notifica dell'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="c637b-238">Other notable differences are around threaded/non-threaded conversations and tuning notification settings.</span></span>

<span data-ttu-id="c637b-239">Controllare la libreria completa di [formazione per gli utenti finali di Teams.](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="c637b-239">Check out our rich library of [End-user Teams training](enduser-training.md).</span></span> 

## <a name="move-to-teams"></a><span data-ttu-id="c637b-240">Passare a Teams</span><span class="sxs-lookup"><span data-stu-id="c637b-240">Move to Teams</span></span> 
<span data-ttu-id="c637b-241">Una volta definito il piano di transizione, è possibile iniziare a creare team e canali in Teams.</span><span class="sxs-lookup"><span data-stu-id="c637b-241">Now that your transition plan is defined, you can begin creating your teams and channels in Teams.</span></span> 

<span data-ttu-id="c637b-242">Dopo aver creato team e canali, iniziare a copiare i file dai canali di Slack in Teams e a configurare le app.</span><span class="sxs-lookup"><span data-stu-id="c637b-242">Once you’ve created your teams & channels, begin copying files from Slack channels into Teams and configuring your apps.</span></span> <span data-ttu-id="c637b-243">Se si utilizza una soluzione per conservare la cronologia, è possibile configurarla ora.</span><span class="sxs-lookup"><span data-stu-id="c637b-243">If you’re using a solution to retain history, that can be configured now as well.</span></span> <span data-ttu-id="c637b-244">Quindi, si è pronti a concedere licenze agli utenti (se non hanno già una licenza) e ad aggiungerli ai team appropriati.</span><span class="sxs-lookup"><span data-stu-id="c637b-244">Then you’re ready to start licensing users (if they aren’t licensed already) and adding them to the appropriate teams.</span></span> <span data-ttu-id="c637b-245">Per ridurre la necessità di ulteriori esportazioni e copie di file, è consigliabile rimuovere l'accesso di Slack in una data concordata che coincide con l'aggiunta di ciascun utente al team.</span><span class="sxs-lookup"><span data-stu-id="c637b-245">To reduce the need for additional exports and file copies, consider removing Slack access at an agreed-upon date that coincides with each user’s addition to the team.</span></span> <span data-ttu-id="c637b-246">In questo modo si evita di dover riesportare e importare le modifiche delta in file e cronologia.</span><span class="sxs-lookup"><span data-stu-id="c637b-246">This avoids needing to re-export and import delta changes on files and history.</span></span>

<span data-ttu-id="c637b-247">Seguire i passaggi descritti nel diagramma seguente per distribuire Teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c637b-247">Follow the steps in the diagram below to roll out Teams in your organization.</span></span> <span data-ttu-id="c637b-248">Per altre informazioni, consultare [Come distribuire Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c637b-248">For more information, check out [How to roll out Teams](How-to-roll-out-teams.md).</span></span>


:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="Diagramma che elenca le fasi del passaggio da Slack a Teams.":::
