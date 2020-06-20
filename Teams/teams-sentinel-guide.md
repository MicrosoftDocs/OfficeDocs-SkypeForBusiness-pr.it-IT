---
title: Azure Sentinel e Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: serdars
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
ms.openlocfilehash: a59609404e51287be02dafc961561bd03e9efb9b
ms.sourcegitcommit: 8b172e9a0d0626c9a88998600d4b17c6c8cdadd2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761484"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel e Microsoft Teams

Teams riveste un ruolo centrale sia nella comunicazione che nella condivisione di dati nel cloud di Microsoft 365. Poiché il servizio Teams è in contatto con così tante tecnologie sottostanti nel cloud, può trarre beneficio dall'analisi automatica e manuale, non solo per quanto riguarda la *ricerca nei log*, ma anche per il *monitoraggio in tempo reale delle riunioni*. Azure Sentinel offre agli amministratori queste soluzioni.

> [!NOTE]
> Per un ripasso su Azure Sentinel, vedere [questo articolo](https://docs.microsoft.com/azure/sentinel/overview).

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel e i log attività di Microsoft Teams

Questo articolo è incentrato sulla raccolta dei log attività di Teams in Azure Sentinel. Oltre a consentire agli amministratori di gestire la sicurezza in un'unica interfaccia, inclusi dispositivi di terze parti selezionati, Microsoft Threat Protection e altri carichi di lavoro di Microsoft 365, le cartelle di lavoro e i runbook di Sentinel consentono di rendere il monitoraggio della sicurezza sistematico. Un buon primo passo in questo processo è la raccolta dei log necessari per l'analisi.

> [!NOTE]
> È possibile visualizzare più abbonamenti a Microsoft 365 nella stessa istanza di Azure Sentinel. Questo consentirà il [monitoraggio in tempo reale](https://docs.microsoft.com/azure/sentinel/livestream) e la ricerca di minacce nei file di log cronologici. Gli amministratori potranno svolgere le ricerche usando [query tra risorse](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), ovvero all'interno di un unico gruppo di risorse, tra gruppi di risorse o in un altro abbonamento.

## <a name="step-1-collect-teams-logs"></a>Passaggio 1: Raccogliere i log di Teams

Questa sezione include tre parti:

1. Abilitazione dei log di controllo in **Microsoft 365**.
2. Registrazione di un'app in **Microsoft Azure** per consentire l'autenticazione e l'autorizzazione per la raccolta di log.
3. Registrazione della sottoscrizione per l'API che consentirà la raccolta di log con l'API Microsoft 365 tramite **PowerShell**.

### <a name="enable-audit-logs-in-m365"></a>Abilitare i log di controllo in Microsoft 365

Poiché Teams registra le attività tramite Microsoft 365, i log di controllo non vengono raccolti per impostazione predefinita. Attivare questa funzionalità seguendo [questi passaggi](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0). I dati di Teams vengono raccolti nel log di controllo di Microsoft 365 in *Audit.General*.

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>Registrare un'app in Microsoft Azure per la raccolta di log

> [!TIP]
> Prima di iniziare, è necessario prendere nota dell'**ID applicazione/ID client**e dell'**ID tenant ** per usarli più avanti. Registrarli mentre si esegue la procedura di registrazione dell'app riportata sotto. Verranno visualizzati entrambi gli ID.
>- Dopo la creazione dell'app, fare clic su Registrazione app sulla barra laterale di avvio veloce > individuare il nome visualizzato della nuova app > copiare l'ID applicazione (client).
>- Fare clic su Panoramica sulla barra laterale di avvio veloce > copiare l'ID della directory (tenant).

Autenticare e autorizzare un'app di Azure Active Directory (Azure AD) per la raccolta di dati di log dall'API.

1. Passare al pannello *Azure AD* nel portale di Azure.
2. Fare clic su *Registrazioni app* sulla barra laterale di avvio veloce.
3. Selezionare *Nuova registrazione*.
4. Assegnare un nome all'app per la raccolta di log di Teams e fare clic su *Registra*.
5. Seguire questo percorso: *Autorizzazioni API* > *Aggiungi un'autorizzazione* > *API di gestione di Office 365 * > *Autorizzazioni applicazione*.
6. Espandere Feed attività e selezionare *ActivityFeed.Read*.
7. Scegliere *Fornisci il consenso amministratore*. Quando viene richiesto di confermare, fare clic su Sì.
8. Fare clic su *Certificati e segreti* nella barra laterale > pulsante *Nuovo segreto client*.
9. Nella finestra Nuovo segreto client immettere una descrizione per il nuovo segreto client, assicurarsi di scegliere "Mai" per la scadenza e quindi fare clic su *Aggiungi*.

> [!IMPORTANT]
> È **fondamentale** copiare il nuovo segreto client in una voce di gestione password associata al nome dell'app appena creata. Non sarà possibile visualizzare di nuovo il segreto dopo aver chiuso il pannello di Azure (*pannello* è il termine usato in Azure per indicare una finestra).

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>Registrare l'API con PowerShell per raccogliere i log di Teams

Il passaggio finale della configurazione consiste nel raccogliere e registrare la sottoscrizione dell'API in modo che sia possibile raccogliere i dati di log. Questa operazione viene eseguita tramite chiamate REST di PowerShell all'API Office 365 Management Activity.

Prepararsi a inserire l'**ID applicazione (client)**, il nuovo **segreto client**, il **dominio URL per Microsoft 365** e l'**ID directory (tenant)** nel cmdlet di PowerShell di seguito.

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>Passaggio 2: Distribuire un playbook di Sentinel per inserire i log di Teams

I playbook di Azure Sentinel, anche detti app per la logica, consentiranno ad Azure di inserire i dati di Teams raccolti. L'app per la logica interroga Office 365 per trovare i dati di controllo che scrive nell'area di lavoro di Azure Sentinel.

Usare [questo](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) modello ARM per distribuire il playbook di Sentinel.

Aspetti da ricordare:

1. Sarà necessario esaminare il modello ARM e sostituire alcuni valori con valori appropriati per l'ambiente in uso.
2. Tra l'inserimento dei log e la visualizzazione dei risultati in Azure Sentinel trascorrerà del tempo.

   Attendere 5 o 10 minuti, tenendo presente che se non ci sono dati relativi agli ultimi 5 minuti verrà visualizzato un messaggio di errore. Controllare i log di controllo tenendo presente che, poiché le informazioni di Teams si trovano tra gli eventi Audit.General, che contengono altro oltre ai log di Teams, nei sistemi in uso i risultati dovrebbero essere visualizzati entro 5 o 10 minuti. Se si usa un ambiente di testo, accertarsi di usare Teams per generare la registrazione.

![Immagine che mostra le classi dell'app per la logica.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> Spiegazione delle azioni nella figura: 
  </summary>

  • Ricorrenza è il trigger dell'app per la logica che indica che il flusso di lavoro deve essere eseguito ogni ora.
  <p>
• L'azione Ora corrente è molto semplice e ottiene semplicemente l'orario attuale.
  <p>
• Inizializza variabile crea una variabile denominata NextPage e la imposta su 1. Verrà usata in seguito per gestire la paginazione dall'API Office 365.
  <p>
• Inizializza variabile 2 crea una variabile vuota denominata StartTime.
  <p>
• Esegui la query ed elenca i risultati è un'azione di Monitoraggio di Azure che eseguirà una query sull'area di lavoro per l'ultimo log di Office 365 immesso dall'app per la logica.
  <p>
• Condizione 4 serve per verificare se l'azione Esegui la query ed elenca i risultati ha restituito i dati. Questa operazione viene eseguita per controllare se è la prima volta che si usa l'app per la logica. Se non vengono restituiti dati, la variabile StartTime viene impostata su Adesso - 24 ore. Se vengono restituiti dati, StartTime è impostato sul valore TimeGenerated dell'ultimo record. Questa operazione viene eseguita in modo che la query possa recuperare dati dall'ultima voce fino ad ora nel polling dell'API Office 365, o nelle ultime 24 ore se si tratta della prima esecuzione.
  <p>
• Inizializza variabile 3 crea una variabile vuota denominata AvailableUri. Si tratta di una stringa con l'URL generato usando StartTime e CurrentTime rispettivamente come ora di inizio e ora di fine.
  <p>
• La condizione Until è un ciclo che consente all'app per la logica di continuare a eseguire il polling dell'API per vedere se sono presenti altri dati (paginazione). Finché la variabile NextPage è 1, il ciclo continuerà. In seguito questa variabile verrà aggiornata se non ci sono altre pagine da recuperare.
  <p>
• All'interno del ciclo Until, il primo passaggio HTTP effettua la connessione ad AvailableURI. Questo URI restituisce un elenco del contenuto disponibile e l'URI di ogni contenuto. Per saperne di più, vedere questo articolo: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Viene poi eseguito un controllo per verificare che vengano restituiti dati. La condizione controlla se la lunghezza del corpo è 0. In caso affermativo, non sono disponibili dati da scrivere in Log Analytics. Se il valore è maggiore di 0, sono presenti dati da elaborare.
  <p>
• Se vengono rilevati dati, sarà necessario elaborarli. Analizza JSON definisce uno schema dei dati restituiti. Questo consente alle app per la logica di usare i dati analizzati come contenuto dinamico nei passaggi successivi.
  <p>
• Poiché l'elenco di dati disponibili restituito è una matrice, viene usata un'azione For Each per scorrere l'elenco di contenuto disponibile.
  <p>
• A questo punto viene recuperato il contenuto.  HTTP viene usato nuovamente per ottenere contentUri, una proprietà dinamica creata da Analizza JSON, che è l'URL dei dati da recuperare.
  <p>
• Analizza JSON consente anche di analizzare i dati restituiti. È possibile trovare contenuto di esempio all'URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Anche i dati restituiti sono una matrice. Anche in questo caso si può quindi usare un ciclo For Each. In questo ciclo, il flusso di lavoro acquisisce l'elemento di dati corrente e usa l'azione Invia dati per scrivere i dati in Log Analytics.
  <p>
• Poiché potrebbero esserci più pagine di contenuto disponibile, una condizione controlla se NextPageUri non è NULL. Se è NULL, o vuoto, NextPage viene impostato su 0, terminando così il ciclo Until. Se contiene un URL, la variabile AvaibleUri viene aggiornata all'URL. In questo modo, la successiva esecuzione del ciclo Until userà un URL disponibile successivo e non l'URL iniziale.

  </details>

> [!TIP]
> È possibile scegliere di usare una *funzione di Azure* per inserire questi log e, in tal caso, le informazioni su come distribuirla sono disponibili [qui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)o [qui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), in base alle preferenze.

Con il connettore in esecuzione, indipendentemente dall'opzione scelta, dovrebbe essere visualizzata una tabella personalizzata denominata O365API_CL nell'area di lavoro di Azure Sentinel. Questa tabella ospiterà i log di Teams.

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>Passaggio 3: Usare Sentinel per monitorare Microsoft Teams

L'identità è un vettore di attacco importante da monitorare in Microsoft Teams. Azure Active Directory (Azure AD) è alla base della directory di Microsoft 365, incluso Teams, la raccolta e la ricerca di minacce relative all'autenticazione nei log di Azure AD sarà utile per individuare comportamenti sospetti relativi all'identità. È possibile usare il connettore integrato per eseguire il pull dei dati di Azure Active Directory in Azure Sentinel e usare queste query di [rilevamento](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) e [ricerca](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) per individuare i problemi.

Per quanto riguarda gli attacchi specifici di Microsoft Teams, le minacce ai dati, ad esempio, Azure Sentinel offre anche il modo di monitorarli e cercarli.

### <a name="create-a-parser-for-your-data"></a>Creare un parser per i dati

La prima cosa da fare per interpretare l'ampio set di dati raccolti consiste nel darvi un senso mediante l'analisi. Questa operazione si può eseguire con una funzione in linguaggio di query Kusto (KQL) che semplifica l'uso dei dati.

> [!NOTE]
> Le funzioni KQL sono query KQL salvate come tipo di dati "function". Le funzioni KQL hanno un alias che può essere immesso nella casella della query in Sentinel per ripetere velocemente l'esecuzione della query. Per altre informazioni sulle funzioni KQL e su come creare una funzione parser, leggere [questo articolo della Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).
 
 Il parser seguente è un esempio personalizzabile il cui scopo è selezionare un subset dei campi dell'API di gestione di Office 365 pertinenti per *Teams*. Esiste anche un parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) suggerito, ma quello che segue può essere modificato in base a esigenze e preferenze diverse.

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 Salvare il parser come funzione KQL, con l'alias TeamsData. Verrà usato per le query successive. I dettagli sulla configurazione e sull'uso di una funzione KQL come parser sono disponibili in questo[ articolo della Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).

## <a name="helfpul-hunting-kql-queries"></a>Query KQL utili per la ricerca

Usare queste query per acquisire familiarità con i dati e l'ambiente di Teams. Conoscere l'aspetto e il comportamento che l'ambiente dovrebbe avere è un buon primo passo per riconoscere le attività sospette. Fatto questo, ci si può dedicare alla ricerca delle minacce.

#### <a name="federated-external-users-query"></a>Query per utenti esterni federati

Questa query consente di ottenere l'elenco dei siti di Teams con utenti esterni federati. Questi utenti avranno un suffisso del nome di dominio o UPN che *non è* di proprietà dell'organizzazione. In questa query di esempio l'organizzazione è proprietaria di contoso.com.

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> Per altre informazioni sui tipi di accesso esterno e guest in Teams, vedere [questo articolo](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)o la sezione*Tipi di partecipante* nella [Guida alla sicurezza di Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide).

#### <a name="who-recently-joined--whose-role-changed"></a>Chi si è unito di recente/chi ha cambiato ruolo

Eseguire una query su uno specifico utente per controllare se è stato aggiunto a un canale di Teams negli ultimi 7:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

Controllare se il ruolo di un utente in un team è stato cambiato negli ultimi 7 giorni:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>Utenti esterni di organizzazioni sconosciute o nuove

In Teams è possibile aggiungere utenti esterni ai propri canali o al proprio ambiente. Spesso le organizzazioni hanno un numero limitato di partnership strategiche e aggiungono utenti da queste società partner. Questa query KQL esamina gli utenti esterni aggiunti ai team che provengono da organizzazioni mai viste o aggiunte in precedenza.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a>Aggiunta e successiva rimozione di utenti esterni

Gli utenti malintenzionati con qualche livello di accesso esistente possono aggiungere un nuovo account esterno a Teams per accedere ed esfiltrare dati. Possono anche rimuovere rapidamente l'utente per nascondere l'accesso. Questa query cerca account esterni aggiunti a Teams e rimossi rapidamente, per identificare comportamenti sospetti.

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a>Aggiunta di nuovi bot o applicazioni

Teams offre la possibilità di includere app o bot in un team per estendere il set di funzionalità. Questo include app e bot personalizzati. In alcuni casi, un'app o un bot potrebbe essere usato per stabilire la persistenza in Teams senza bisogno di un account utente, oltre che per accedere ai file e ad altri dati. Questa query cerca nuove app o bot in Teams.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Account utente proprietari di un numero elevato di team

Gli utenti malintenzionati che provano a elevare i propri privilegi possono assegnare a se stessi privilegi proprietario di un numero elevato di team diversi, mentre in genere gli utenti creano e possiedono un numero limitato di team su argomenti specifici. Questa query KQL cerca i comportamenti sospetti.

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a>Numerose eliminazioni di team da parte di un singolo utente

Gli utenti malintenzionati possono causare interruzioni e mettere in pericolo progetti e dati eliminando più team. Poiché i team vengano generalmente eliminati dai singoli proprietari, l'eliminazione centrale di molti team può essere un segnale di problemi. Questa query KQL cerca singoli utenti che eliminano più team.

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a>Espansione delle opportunità di ricerca delle minacce

È possibile espandere la ricerca combinando le query di risorse come Azure Active Directory (Azure AD) o altri carichi di lavoro di Office 365 con le query di Teams. Ad esempio, si può combinare il rilevamento degli schemi sospetti nei log di accesso (SigninLogs) di Azure AD e usare tali informazioni durante la ricerca dei proprietari di team.

```kusto
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
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

Inoltre, è possibile rendere i rilevamenti in SigninLogs specifici per Teams, aggiungendo un filtro per i soli accessi basati su Teams usando:

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

Per spiegare meglio l'uso di `where AppDisplayName starts with "Microsoft Teams"`, la query KQL seguente illustra un accesso riuscito da un indirizzo IP con un errore da un indirizzo IP diverso, ma con ambito limitato agli accessi di Teams:

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
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

**Grazie per la collaborazione sui contenuti a Pete Bryan, Nicholas DiCola e Matthew Lowe.** Pete Bryan e i suoi collaboratori continueranno a sviluppare query di rilevamento e ricerca per Teams, consultare questo repository [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) per gli aggiornamenti.  Controllare la disponibilità di aggiornamenti per il [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e l'[app per la logica](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usati in questo articolo. Si può anche entrare a far parte della [community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) e collaborare. Grazie! Buona caccia alle minacce.

[Registrazione dell'applicazione in Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[Abilitare o disabilitare la ricerca nel log di controllo](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[Che cos'è Azure Sentinel?](https://docs.microsoft.com/azure/sentinel/overview)