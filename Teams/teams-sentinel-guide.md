---
title: Azure Sentinel e Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Consigli e suggerimenti per la sicurezza per amministratori IT sull'uso di Sentinel per monitorare e cercare possibili minacce in Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712768"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="755b5-103">Azure Sentinel e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="755b5-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="755b5-104">Azure Sentinel ha ora un connettore integrato.</span><span class="sxs-lookup"><span data-stu-id="755b5-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="755b5-105">Per altre informazioni, vedere [Collegare i log di Office 365 ad Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="755b5-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="755b5-106">Questa è la route consigliata per raccogliere questi log e sostituisce i metodi di raccolta descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="755b5-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="755b5-107">Teams riveste un ruolo centrale nella comunicazione e nella condivisione di dati nel cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="755b5-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="755b5-108">Poiché Teams è in contatto con così tante tecnologie nel cloud, può trarre beneficio dall'analisi automatica e manuale,</span><span class="sxs-lookup"><span data-stu-id="755b5-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="755b5-109">non solo per quanto riguarda *la ricerca nei log*, ma anche per il *monitoraggio in tempo reale delle riunioni*.</span><span class="sxs-lookup"><span data-stu-id="755b5-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="755b5-110">Azure Sentinel offre agli amministratori queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="755b5-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="755b5-111">Per un ripasso su Azure Sentinel,</span><span class="sxs-lookup"><span data-stu-id="755b5-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="755b5-112">vedere [questo articolo](/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="755b5-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="755b5-113">Sentinel e i log attività di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="755b5-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="755b5-114">Questo articolo è incentrato sulla raccolta dei log attività di Teams in Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="755b5-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="755b5-115">Sentinel consente agli amministratori di eseguire attività di gestione della sicurezza in un’unica posizione.</span><span class="sxs-lookup"><span data-stu-id="755b5-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="755b5-116">Ciò include la gestione di:</span><span class="sxs-lookup"><span data-stu-id="755b5-116">This includes managing:</span></span>

- <span data-ttu-id="755b5-117">dispositivi di terze parti</span><span class="sxs-lookup"><span data-stu-id="755b5-117">Third-party devices</span></span>
- <span data-ttu-id="755b5-118">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="755b5-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="755b5-119">Carichi di lavoro di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="755b5-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="755b5-120">Le cartelle di lavoro e i runbook di Sentinel possono rendere il monitoraggio della sicurezza *sistematico*.</span><span class="sxs-lookup"><span data-stu-id="755b5-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="755b5-121">Un buon primo passo in questo processo è la raccolta dei log necessari per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="755b5-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="755b5-122">È possibile visualizzare più abbonamenti a Microsoft 365 nella stessa istanza di Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="755b5-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="755b5-123">Questo consentirà il [monitoraggio in tempo reale](/azure/sentinel/livestream) e la ricerca di minacce nei file di log cronologici.</span><span class="sxs-lookup"><span data-stu-id="755b5-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="755b5-124">Gli amministratori potranno svolgere le ricerche usando [query tra risorse](/azure/azure-monitor/log-query/cross-workspace-query), ovvero all'interno di un unico gruppo di risorse, tra gruppi di risorse o in un altro abbonamento.</span><span class="sxs-lookup"><span data-stu-id="755b5-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="755b5-125">Passaggio 1: raccogliere log di Teams: abilitare i log di controllo in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="755b5-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="755b5-126">Poiché Teams registra le attività tramite Microsoft 365, i log di controllo non vengono raccolti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="755b5-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="755b5-127">Attivare questa funzionalità seguendo [questi passaggi](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="755b5-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="755b5-128">I dati di Teams vengono raccolti nel log di controllo di Microsoft 365 in *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="755b5-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="755b5-129">Passaggio 2: collegare i log di Office 365 ad Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="755b5-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="755b5-130">Azure sentinel fornisce un connettore incorporato per i log di Office 365, che consente di inserire i dati di Teams in Azure Sentinel e altri dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="755b5-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="755b5-131">In Azure Sentinel, abilitare il connettore di dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="755b5-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="755b5-132">Per altre informazioni, vedere la [Documentazione di Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="755b5-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="755b5-133">Query KQL utili per la ricerca</span><span class="sxs-lookup"><span data-stu-id="755b5-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="755b5-134">Usare queste query per acquisire familiarità con i dati e l'ambiente di Teams.</span><span class="sxs-lookup"><span data-stu-id="755b5-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="755b5-135">Conoscere l'aspetto e il comportamento che l'ambiente dovrebbe avere è un buon primo passo per riconoscere le attività sospette.</span><span class="sxs-lookup"><span data-stu-id="755b5-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="755b5-136">Fatto questo, ci si può dedicare alla ricerca delle minacce.</span><span class="sxs-lookup"><span data-stu-id="755b5-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="755b5-137">Query per utenti esterni federati</span><span class="sxs-lookup"><span data-stu-id="755b5-137">Federated external users query</span></span>

<span data-ttu-id="755b5-138">Questa query consente di ottenere l'elenco dei siti di Teams con utenti esterni federati.</span><span class="sxs-lookup"><span data-stu-id="755b5-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="755b5-139">Questi utenti avranno un suffisso del nome di dominio e/o UPN che non è di proprietà dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="755b5-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="755b5-140">In questa query di esempio l'organizzazione è proprietaria di contoso.com.</span><span class="sxs-lookup"><span data-stu-id="755b5-140">In this example query, the organization owns contoso.com.</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> <span data-ttu-id="755b5-141">Per altre informazioni sui tipi di accesso esterno e guest in Teams, vedere [Comunicare con utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md), o la sezione [Tipi di partecipanti](teams-security-guide.md#participant-types) nella Guida alla sicurezza di Teams.</span><span class="sxs-lookup"><span data-stu-id="755b5-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="755b5-142">Chi si è unito di recente/chi ha cambiato ruolo</span><span class="sxs-lookup"><span data-stu-id="755b5-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="755b5-143">Eseguire una query su uno specifico utente per controllare se è stato aggiunto a un canale di Teams negli ultimi 7 giorni o entro una settimana:</span><span class="sxs-lookup"><span data-stu-id="755b5-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="755b5-144">Controllare se il ruolo di un utente in un team è stato cambiato negli ultimi sette giorni:</span><span class="sxs-lookup"><span data-stu-id="755b5-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="755b5-145">Utenti esterni di organizzazioni sconosciute o nuove</span><span class="sxs-lookup"><span data-stu-id="755b5-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="755b5-146">In Teams è possibile aggiungere utenti esterni ai propri canali o al proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="755b5-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="755b5-147">Spesso le organizzazioni hanno un numero limitato di partnership strategiche e aggiungono utenti da queste società partner.</span><span class="sxs-lookup"><span data-stu-id="755b5-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="755b5-148">Questa query KQL esamina gli utenti esterni aggiunti ai team che provengono da organizzazioni mai viste o aggiunte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="755b5-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="755b5-149">Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="755b5-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="755b5-150">Aggiunta e successiva rimozione di utenti esterni</span><span class="sxs-lookup"><span data-stu-id="755b5-150">External users who were added and then removed</span></span>

<span data-ttu-id="755b5-151">Gli utenti malintenzionati con qualche livello di accesso esistente possono aggiungere un nuovo account esterno a Teams per accedere ed esfiltrare dati.</span><span class="sxs-lookup"><span data-stu-id="755b5-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="755b5-152">Possono anche rimuovere rapidamente l'utente per nascondere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="755b5-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="755b5-153">Questa query cerca account esterni aggiunti a Teams e rimossi rapidamente, per identificare comportamenti sospetti.</span><span class="sxs-lookup"><span data-stu-id="755b5-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="755b5-154">Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="755b5-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="755b5-155">Aggiunta di nuovi bot o applicazioni</span><span class="sxs-lookup"><span data-stu-id="755b5-155">New bot or application added</span></span>

<span data-ttu-id="755b5-156">Teams può includere app o bot in un team per estendere il set di caratteristiche (incluse le app e i bot personalizzati).</span><span class="sxs-lookup"><span data-stu-id="755b5-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="755b5-157">In alcuni casi, un'app o un bot può essere usato per *persistenza* in Teams senza bisogno di un account utente e può accedere ai file e ad altri dati.</span><span class="sxs-lookup"><span data-stu-id="755b5-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="755b5-158">Questa query cerca nuove app o bot in Teams.</span><span class="sxs-lookup"><span data-stu-id="755b5-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="755b5-159">Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span><span class="sxs-lookup"><span data-stu-id="755b5-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="755b5-160">Account utente proprietari di un numero elevato di team</span><span class="sxs-lookup"><span data-stu-id="755b5-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="755b5-161">Gli utenti malintenzionati che provano a elevare i propri privilegi possono assegnare a se stessi privilegi proprietario di un numero elevato di team diversi,</span><span class="sxs-lookup"><span data-stu-id="755b5-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="755b5-162">mentre *In genere*, gli utenti creano e possiedono un numero limitato di team su argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="755b5-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="755b5-163">Questa query KQL cerca i comportamenti sospetti.</span><span class="sxs-lookup"><span data-stu-id="755b5-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="755b5-164">Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span><span class="sxs-lookup"><span data-stu-id="755b5-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="755b5-165">Numerose eliminazioni di team da parte di un singolo utente</span><span class="sxs-lookup"><span data-stu-id="755b5-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="755b5-166">Gli utenti malintenzionati possono causare interruzioni e mettere in pericolo progetti e dati eliminando più team.</span><span class="sxs-lookup"><span data-stu-id="755b5-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="755b5-167">Poiché i team vengano generalmente eliminati dai singoli proprietari, l'eliminazione centrale di molti team può essere un segnale di problemi.</span><span class="sxs-lookup"><span data-stu-id="755b5-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="755b5-168">Questa query KQL cerca singoli utenti che eliminano più team.</span><span class="sxs-lookup"><span data-stu-id="755b5-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="755b5-169">Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span><span class="sxs-lookup"><span data-stu-id="755b5-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="755b5-170">Espansione delle opportunità di ricerca delle minacce</span><span class="sxs-lookup"><span data-stu-id="755b5-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="755b5-171">Combinando le query di risorse come Azure Active Directory (Azure AD) o altri carichi di lavoro di Office 365 possono essere usati con le query di Teams.</span><span class="sxs-lookup"><span data-stu-id="755b5-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="755b5-172">Per esempio, combinare il rilevamento degli schemi sospetti nei log di accesso (SigninLogs) di Azure AD e usare tali output durante la ricerca dei proprietari del team.</span><span class="sxs-lookup"><span data-stu-id="755b5-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

```Kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

<span data-ttu-id="755b5-173">Inoltre, è possibile rendere i rilevamenti in SigninLogs specifici per Teams, aggiungendo un filtro per i soli accessi basati su Teams usando:</span><span class="sxs-lookup"><span data-stu-id="755b5-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="755b5-174">Per spiegare meglio l'uso di *in cui AppDisplayName include Teams*, la query KQL seguente illustra un accesso riuscito da un indirizzo IP con un errore da un indirizzo IP diverso, ma con ambito *limitato* agli accessi di Teams:</span><span class="sxs-lookup"><span data-stu-id="755b5-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="755b5-175">Informazioni e aggiornamenti importanti</span><span class="sxs-lookup"><span data-stu-id="755b5-175">Important information and updates</span></span>

<span data-ttu-id="755b5-176">**Grazie per la collaborazione sui contenuti a Pete Bryan, Nicholas DiCola e Matthew Lowe.**</span><span class="sxs-lookup"><span data-stu-id="755b5-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="755b5-177">Pete Bryan e i suoi collaboratori continueranno a sviluppare query di rilevamento e ricerca per Teams.</span><span class="sxs-lookup"><span data-stu-id="755b5-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="755b5-178">Consultare questo repository [ Github](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="755b5-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="755b5-179">Controllare la disponibilità di aggiornamenti per il [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e l'[app per la logica](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="755b5-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="755b5-180">Si può anche entrare a far parte della [community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki).</span><span class="sxs-lookup"><span data-stu-id="755b5-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="755b5-181">Microsoft sta cercando attivamente feedback su questo articolo, quindi usare l’opzione per il feedback riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="755b5-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="755b5-182">Grazie a tutti e buona caccia alle minacce.</span><span class="sxs-lookup"><span data-stu-id="755b5-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="755b5-183">Registrazione dell'applicazione in Azure AD</span><span class="sxs-lookup"><span data-stu-id="755b5-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="755b5-184">Abilitare o disabilitare la ricerca nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="755b5-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="755b5-185">Che cos'è Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="755b5-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
