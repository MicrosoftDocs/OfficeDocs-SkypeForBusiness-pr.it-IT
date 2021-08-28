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
ms.localizationpriority: high
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
ms.openlocfilehash: 745500dd0ac30d717e37ec9287618342554b26c9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627028"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel e Microsoft Teams

> [!IMPORTANT]
> Azure Sentinel ha ora un connettore integrato. Per altre informazioni, vedere [Collegare i log di Office 365 ad Azure Sentinel](/azure/sentinel/connect-office-365). Questa è la route consigliata per raccogliere questi log e sostituisce i metodi di raccolta descritti di seguito.

Teams riveste un ruolo centrale nella comunicazione e nella condivisione di dati nel cloud di Microsoft 365. Poiché Teams è in contatto con così tante tecnologie nel cloud, può trarre beneficio dall'analisi automatica e manuale, non solo per quanto riguarda *la ricerca nei log*, ma anche per il *monitoraggio in tempo reale delle riunioni*. Azure Sentinel offre agli amministratori queste soluzioni.

> [!NOTE]
> Per un ripasso su Azure Sentinel, vedere [questo articolo](/azure/sentinel/overview).

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel e i log attività di Microsoft Teams

Questo articolo è incentrato sulla raccolta dei log attività di Teams in Azure Sentinel.

Sentinel consente agli amministratori di gestire la sicurezza in un'unica posizione. Ciò include la gestione di:

- dispositivi di terze parti
- Microsoft Threat Protection
- Carichi di lavoro di Microsoft 365

Le cartelle di lavoro e i runbook di Sentinel possono rendere il monitoraggio della sicurezza *sistematico*. Un buon primo passo in questo processo è la raccolta dei log necessari per l'analisi.

> [!NOTE]
> È possibile visualizzare più abbonamenti a Microsoft 365 nella stessa istanza di Azure Sentinel. Questo consentirà il [monitoraggio in tempo reale](/azure/sentinel/livestream) e la ricerca di minacce nei file di log cronologici. Gli amministratori potranno svolgere le ricerche usando [query tra risorse](/azure/azure-monitor/log-query/cross-workspace-query), ovvero all'interno di un unico gruppo di risorse, tra gruppi di risorse o in un altro abbonamento.

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>Passaggio 1: raccogliere log di Teams: abilitare i log di controllo in Microsoft 365

Poiché Teams registra le attività tramite Microsoft 365, i log di controllo non vengono raccolti per impostazione predefinita. Attivare questa funzionalità seguendo [questi passaggi](/microsoft-365/compliance/turn-audit-log-search-on-or-off). I dati di Teams vengono raccolti nel log di controllo di Microsoft 365 in *Audit.General*.

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>Passaggio 2: collegare i log di Office 365 ad Azure Sentinel

Azure sentinel fornisce un connettore incorporato per i log di Office 365, che consente di inserire i dati di Teams in Azure Sentinel e altri dati di Office 365.
 
In Azure Sentinel, abilitare il connettore di dati di Office 365. Per altre informazioni, vedere la [Documentazione di Azure Sentinel](/azure/sentinel/connect-office-365).

## <a name="helpful-hunting-kql-queries"></a>Query KQL utili per la ricerca

Usare queste query per acquisire familiarità con i dati e l'ambiente di Teams. Conoscere l'aspetto e il comportamento che l'ambiente dovrebbe avere è un buon primo passo per riconoscere le attività sospette. Fatto questo, ci si può dedicare alla ricerca delle minacce.

### <a name="federated-external-users-query"></a>Query per utenti esterni federati

Questa query consente di ottenere l'elenco dei siti di Teams con utenti esterni federati. Questi utenti avranno un suffisso del nome di dominio e/o UPN che non è di proprietà dell'organizzazione.

In questa query di esempio l'organizzazione è proprietaria di contoso.com.

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
> Per altre informazioni sui tipi di accesso esterno e guest in Teams, vedere [Comunicare con utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md), o la sezione [Tipi di partecipanti](teams-security-guide.md#participant-types) nella Guida alla sicurezza di Teams.

### <a name="who-recently-joined--whose-role-changed"></a>Chi si è unito di recente/chi ha cambiato ruolo

Eseguire una query su uno specifico utente per controllare se è stato aggiunto a un canale di Teams negli ultimi 7 giorni o entro una settimana:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

Controllare se il ruolo di un utente in un team è stato cambiato negli ultimi sette giorni:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>Utenti esterni di organizzazioni sconosciute o nuove

In Teams è possibile aggiungere utenti esterni ai propri canali o al proprio ambiente. Spesso le organizzazioni hanno un numero limitato di partnership strategiche e aggiungono utenti da queste società partner. Questa query KQL esamina gli utenti esterni aggiunti ai team che provengono da organizzazioni mai viste o aggiunte in precedenza.

Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).

### <a name="external-users-who-were-added-and-then-removed"></a>Aggiunta e successiva rimozione di utenti esterni

Gli utenti malintenzionati con qualche livello di accesso esistente possono aggiungere un nuovo account esterno a Teams per accedere ed esfiltrare dati. Possono anche rimuovere rapidamente l'utente per nascondere l'accesso. Questa query cerca account esterni aggiunti a Teams e rimossi rapidamente, per identificare comportamenti sospetti.

Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).

### <a name="new-bot-or-application-added"></a>Aggiunta di nuovi bot o applicazioni

Teams può includere app o bot in un team per estendere il set di caratteristiche (incluse le app e i bot personalizzati). In alcuni casi, un'app o un bot può essere usato per *persistenza* in Teams senza bisogno di un account utente e può accedere ai file e ad altri dati. Questa query cerca nuove app o bot in Teams.

Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Account utente proprietari di un numero elevato di team

Gli utenti malintenzionati che provano a elevare i propri privilegi possono assegnare a se stessi privilegi proprietario di un numero elevato di team diversi, mentre *In genere*, gli utenti creano e possiedono un numero limitato di team su argomenti specifici. Questa query KQL cerca i comportamenti sospetti.

Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).

### <a name="many-team-deletions-by-a-single-user"></a>Numerose eliminazioni di team da parte di un singolo utente

Gli utenti malintenzionati possono causare interruzioni e mettere in pericolo progetti e dati eliminando più team. Poiché i team vengano generalmente eliminati dai singoli proprietari, l'eliminazione centrale di molti team può essere un segnale di problemi. Questa query KQL cerca singoli utenti che eliminano più team.

Per altre informazioni, vedere la query [nel github della community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).

### <a name="expanding-your-threat-hunting-opportunities"></a>Espansione delle opportunità di ricerca delle minacce

Combinando le query di risorse come Azure Active Directory (Azure AD) o altri carichi di lavoro di Office 365 possono essere usati con le query di Teams. Per esempio, combinare il rilevamento degli schemi sospetti nei log di accesso (SigninLogs) di Azure AD e usare tali output durante la ricerca dei proprietari del team.

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

Inoltre, è possibile rendere i rilevamenti in SigninLogs specifici per Teams, aggiungendo un filtro per i soli accessi basati su Teams usando:

```Kusto
| where AppDisplayName has 'Teams'
```

Per spiegare meglio l'uso di *in cui AppDisplayName include Teams*, la query KQL seguente illustra un accesso riuscito da un indirizzo IP con un errore da un indirizzo IP diverso, ma con ambito *limitato* agli accessi di Teams:

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

## <a name="important-information-and-updates"></a>Informazioni e aggiornamenti importanti

**Grazie per la collaborazione sui contenuti a Pete Bryan, Nicholas DiCola e Matthew Lowe.** Pete Bryan e i suoi collaboratori continueranno a sviluppare query di rilevamento e ricerca per Teams.

Consultare questo repository [ Github](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) per gli aggiornamenti.

Controllare la disponibilità di aggiornamenti per il [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e l'[app per la logica](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usati in questo articolo.

Si può anche entrare a far parte della [community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki). Microsoft sta cercando attivamente feedback su questo articolo, quindi usare l’opzione per il feedback riportata di seguito. Grazie a tutti e buona caccia alle minacce.

[Registrazione dell'applicazione in Azure AD](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[Abilitare o disabilitare la ricerca nel log di controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[Che cos'è Azure Sentinel?](/azure/sentinel/overview)
