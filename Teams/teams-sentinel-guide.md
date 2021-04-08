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
ms.openlocfilehash: 1075a2c345bd866266b175a4b62432e9f819b330
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598525"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="3f429-103">Azure Sentinel e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f429-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f429-104">Azure Sentinel ha ora un connettore integrato.</span><span class="sxs-lookup"><span data-stu-id="3f429-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="3f429-105">Per altre informazioni, vedere [Collegare i log di Office 365 ad Azure Sentinel](/azure/sentinel/connect-office-365).</span><span class="sxs-lookup"><span data-stu-id="3f429-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="3f429-106">Questa è la route consigliata per raccogliere questi log e sostituisce i metodi di raccolta descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="3f429-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="3f429-107">Teams riveste un ruolo centrale sia nella comunicazione che nella condivisione di dati nel cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f429-107">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="3f429-108">Poiché il servizio Teams è in contatto con così tante tecnologie sottostanti nel cloud, può trarre beneficio dall'analisi automatica e manuale, non solo per quanto riguarda la *ricerca nei log*, ma anche per il *monitoraggio in tempo reale delle riunioni*.</span><span class="sxs-lookup"><span data-stu-id="3f429-108">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="3f429-109">Azure Sentinel offre agli amministratori queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="3f429-109">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="3f429-110">Per un ripasso su Azure Sentinel,</span><span class="sxs-lookup"><span data-stu-id="3f429-110">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="3f429-111">vedere [questo articolo](/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="3f429-111">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="3f429-112">Sentinel e i log attività di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f429-112">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="3f429-113">Questo articolo è incentrato sulla raccolta dei log attività di Teams in Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="3f429-113">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="3f429-114">Oltre a consentire agli amministratori di gestire la sicurezza in un'unica interfaccia, inclusi dispositivi di terze parti selezionati, Microsoft Threat Protection e altri carichi di lavoro di Microsoft 365, le cartelle di lavoro e i runbook di Sentinel consentono di rendere il monitoraggio della sicurezza sistematico.</span><span class="sxs-lookup"><span data-stu-id="3f429-114">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="3f429-115">Un buon primo passo in questo processo è la raccolta dei log necessari per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="3f429-115">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="3f429-116">È possibile visualizzare più abbonamenti a Microsoft 365 nella stessa istanza di Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="3f429-116">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="3f429-117">Questo consentirà il [monitoraggio in tempo reale](/azure/sentinel/livestream) e la ricerca di minacce nei file di log cronologici.</span><span class="sxs-lookup"><span data-stu-id="3f429-117">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="3f429-118">Gli amministratori potranno svolgere le ricerche usando [query tra risorse](/azure/azure-monitor/log-query/cross-workspace-query), ovvero all'interno di un unico gruppo di risorse, tra gruppi di risorse o in un altro abbonamento.</span><span class="sxs-lookup"><span data-stu-id="3f429-118">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="3f429-119">Passaggio 1: Raccogliere i log di Teams</span><span class="sxs-lookup"><span data-stu-id="3f429-119">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="3f429-120">Questa sezione include tre parti:</span><span class="sxs-lookup"><span data-stu-id="3f429-120">This section has three parts:</span></span>

1. <span data-ttu-id="3f429-121">Abilitazione dei log di controllo in **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="3f429-121">Enabling Audit Logs in **Microsoft 365**.</span></span>
2. <span data-ttu-id="3f429-122">Registrazione di un'app in **Microsoft Azure** per consentire l'autenticazione e l'autorizzazione per la raccolta di log.</span><span class="sxs-lookup"><span data-stu-id="3f429-122">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="3f429-123">Registrazione della sottoscrizione per l'API che consentirà la raccolta di log con l'API Microsoft 365 tramite **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3f429-123">Registering the API subscription that will allow log collection via Microsoft 365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="3f429-124">Abilitare i log di controllo in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f429-124">Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="3f429-125">Poiché Teams registra le attività tramite Microsoft 365, i log di controllo non vengono raccolti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3f429-125">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="3f429-126">Attivare questa funzionalità seguendo [questi passaggi](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span><span class="sxs-lookup"><span data-stu-id="3f429-126">Turn on this feature via [these steps](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span></span> <span data-ttu-id="3f429-127">I dati di Teams vengono raccolti nel log di controllo di Microsoft 365 in *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="3f429-127">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="3f429-128">Registrare un'app in Microsoft Azure per la raccolta di log</span><span class="sxs-lookup"><span data-stu-id="3f429-128">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="3f429-129">Prima di iniziare, è necessario prendere nota dell'**ID applicazione/ID client** e dell'**ID tenant** per usarli più avanti.</span><span class="sxs-lookup"><span data-stu-id="3f429-129">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="3f429-130">Registrarli mentre si esegue la procedura di registrazione dell'app riportata sotto.</span><span class="sxs-lookup"><span data-stu-id="3f429-130">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="3f429-131">Verranno visualizzati entrambi gli ID.</span><span class="sxs-lookup"><span data-stu-id="3f429-131">You will see both IDs.</span></span>
>- <span data-ttu-id="3f429-132">Dopo la creazione dell'app, fare clic su Registrazione app sulla barra laterale di avvio veloce > individuare il nome visualizzato della nuova app > copiare l'ID applicazione (client).</span><span class="sxs-lookup"><span data-stu-id="3f429-132">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="3f429-133">Fare clic su Panoramica sulla barra laterale di avvio veloce > copiare l'ID della directory (tenant).</span><span class="sxs-lookup"><span data-stu-id="3f429-133">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="3f429-134">Autenticare e autorizzare un'app di Azure Active Directory (Azure AD) per la raccolta di dati di log dall'API.</span><span class="sxs-lookup"><span data-stu-id="3f429-134">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="3f429-135">Passare al pannello *Azure AD* nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="3f429-135">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="3f429-136">Fare clic su *Registrazioni app* sulla barra laterale di avvio veloce.</span><span class="sxs-lookup"><span data-stu-id="3f429-136">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="3f429-137">Selezionare *Nuova registrazione*.</span><span class="sxs-lookup"><span data-stu-id="3f429-137">Select *New registration*.</span></span>
4. <span data-ttu-id="3f429-138">Assegnare un nome all'app per la raccolta di log di Teams e fare clic su *Registra*.</span><span class="sxs-lookup"><span data-stu-id="3f429-138">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="3f429-139">Seguire questo percorso: *Autorizzazioni API* > *Aggiungi un'autorizzazione* > *API di gestione di Office 365* > *Autorizzazioni applicazione*.</span><span class="sxs-lookup"><span data-stu-id="3f429-139">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="3f429-140">Espandere Feed attività e selezionare *ActivityFeed.Read*.</span><span class="sxs-lookup"><span data-stu-id="3f429-140">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="3f429-141">Scegliere *Fornisci il consenso amministratore*.</span><span class="sxs-lookup"><span data-stu-id="3f429-141">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="3f429-142">Quando viene richiesto di confermare, fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="3f429-142">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="3f429-143">Fare clic su *Certificati e segreti* nella barra laterale > pulsante *Nuovo segreto client*.</span><span class="sxs-lookup"><span data-stu-id="3f429-143">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="3f429-144">Nella finestra Nuovo segreto client immettere una descrizione per il nuovo segreto client, assicurarsi di scegliere "Mai" per la scadenza e quindi fare clic su *Aggiungi*.</span><span class="sxs-lookup"><span data-stu-id="3f429-144">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f429-145">È **fondamentale** copiare il nuovo segreto client in una voce di gestione password associata al nome dell'app appena creata.</span><span class="sxs-lookup"><span data-stu-id="3f429-145">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="3f429-146">Non sarà possibile visualizzare di nuovo il segreto dopo aver chiuso il pannello di Azure (*pannello* è il termine usato in Azure per indicare una finestra).</span><span class="sxs-lookup"><span data-stu-id="3f429-146">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="3f429-147">Registrare l'API con PowerShell per raccogliere i log di Teams</span><span class="sxs-lookup"><span data-stu-id="3f429-147">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="3f429-148">Il passaggio finale della configurazione consiste nel raccogliere e registrare la sottoscrizione dell'API in modo che sia possibile raccogliere i dati di log.</span><span class="sxs-lookup"><span data-stu-id="3f429-148">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="3f429-149">Questa operazione viene eseguita tramite chiamate REST di PowerShell all'API Microsoft 365 Management Activity.</span><span class="sxs-lookup"><span data-stu-id="3f429-149">This is done via PowerShell REST calls to the Microsoft 365 Management Activity API.</span></span>

<span data-ttu-id="3f429-150">Prepararsi a inserire l'**ID applicazione (client)**, il nuovo **segreto client**, il **dominio URL per Microsoft 365** e l'**ID directory (tenant)** nel cmdlet di PowerShell di seguito.</span><span class="sxs-lookup"><span data-stu-id="3f429-150">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="3f429-151">Passaggio 2: Distribuire un playbook di Sentinel per inserire i log di Teams</span><span class="sxs-lookup"><span data-stu-id="3f429-151">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="3f429-152">I playbook di Azure Sentinel, anche detti app per la logica, consentiranno ad Azure di inserire i dati di Teams raccolti.</span><span class="sxs-lookup"><span data-stu-id="3f429-152">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="3f429-153">L'app per la logica interroga Office 365 per trovare i dati di controllo che scrive nell'area di lavoro di Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="3f429-153">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="3f429-154">Usare [questo](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) modello ARM per distribuire il playbook di Sentinel.</span><span class="sxs-lookup"><span data-stu-id="3f429-154">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="3f429-155">Aspetti da ricordare:</span><span class="sxs-lookup"><span data-stu-id="3f429-155">Things to remember:</span></span>

1. <span data-ttu-id="3f429-156">Sarà necessario esaminare il modello ARM e sostituire alcuni valori con valori appropriati per l'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="3f429-156">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="3f429-157">Tra l'inserimento dei log e la visualizzazione dei risultati in Azure Sentinel trascorrerà del tempo.</span><span class="sxs-lookup"><span data-stu-id="3f429-157">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="3f429-158">Attendere 5 o 10 minuti, tenendo presente che se non ci sono dati relativi agli ultimi 5 minuti verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="3f429-158">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="3f429-159">Controllare i log di controllo tenendo presente che, poiché le informazioni di Teams si trovano tra gli eventi Audit.General, che contengono altro oltre ai log di Teams, nei sistemi in uso i risultati dovrebbero essere visualizzati entro 5 o 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="3f429-159">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="3f429-160">Se si usa un ambiente di testo, accertarsi di usare Teams per generare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="3f429-160">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![Immagine che mostra le classi dell'app per la logica.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="3f429-162">Spiegazione delle azioni nella figura:</span><span class="sxs-lookup"><span data-stu-id="3f429-162">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="3f429-163">• Ricorrenza è il trigger dell'app per la logica che indica che il flusso di lavoro deve essere eseguito ogni ora.</span><span class="sxs-lookup"><span data-stu-id="3f429-163">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="3f429-164">• L'azione Ora corrente è molto semplice e ottiene semplicemente l'orario attuale.</span><span class="sxs-lookup"><span data-stu-id="3f429-164">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="3f429-165">• Inizializza variabile crea una variabile denominata NextPage e la imposta su 1.</span><span class="sxs-lookup"><span data-stu-id="3f429-165">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="3f429-166">Verrà usata in seguito per gestire la paginazione dall'API Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f429-166">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="3f429-167">• Inizializza variabile 2 crea una variabile vuota denominata StartTime.</span><span class="sxs-lookup"><span data-stu-id="3f429-167">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="3f429-168">• Esegui la query ed elenca i risultati è un'azione di Monitoraggio di Azure che eseguirà una query sull'area di lavoro per l'ultimo log di Office 365 immesso dall'app per la logica.</span><span class="sxs-lookup"><span data-stu-id="3f429-168">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="3f429-169">• Condizione 4 serve per verificare se l'azione Esegui la query ed elenca i risultati ha restituito i dati.</span><span class="sxs-lookup"><span data-stu-id="3f429-169">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="3f429-170">Questa operazione viene eseguita per controllare se è la prima volta che si usa l'app per la logica.</span><span class="sxs-lookup"><span data-stu-id="3f429-170">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="3f429-171">Se non vengono restituiti dati, la variabile StartTime viene impostata su Adesso - 24 ore.</span><span class="sxs-lookup"><span data-stu-id="3f429-171">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="3f429-172">Se vengono restituiti dati, StartTime è impostato sul valore TimeGenerated dell'ultimo record.</span><span class="sxs-lookup"><span data-stu-id="3f429-172">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="3f429-173">Questa operazione viene eseguita in modo che la query possa recuperare dati dall'ultima voce fino ad ora nel polling dell'API Office 365, o nelle ultime 24 ore se si tratta della prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3f429-173">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="3f429-174">• Inizializza variabile 3 crea una variabile vuota denominata AvailableUri.</span><span class="sxs-lookup"><span data-stu-id="3f429-174">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="3f429-175">Si tratta di una stringa con l'URL generato usando StartTime e CurrentTime rispettivamente come ora di inizio e ora di fine.</span><span class="sxs-lookup"><span data-stu-id="3f429-175">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="3f429-176">• La condizione Until è un ciclo che consente all'app per la logica di continuare a eseguire il polling dell'API per vedere se sono presenti altri dati (paginazione).</span><span class="sxs-lookup"><span data-stu-id="3f429-176">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="3f429-177">Finché la variabile NextPage è 1, il ciclo continuerà.</span><span class="sxs-lookup"><span data-stu-id="3f429-177">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="3f429-178">In seguito questa variabile verrà aggiornata se non ci sono altre pagine da recuperare.</span><span class="sxs-lookup"><span data-stu-id="3f429-178">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="3f429-179">• All'interno del ciclo Until, il primo passaggio HTTP effettua la connessione ad AvailableURI.</span><span class="sxs-lookup"><span data-stu-id="3f429-179">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="3f429-180">Questo URI restituisce un elenco del contenuto disponibile e l'URI di ogni contenuto.</span><span class="sxs-lookup"><span data-stu-id="3f429-180">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="3f429-181">Per saperne di più, vedere questo articolo: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="3f429-181">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="3f429-182">• Viene poi eseguito un controllo per verificare che vengano restituiti dati.</span><span class="sxs-lookup"><span data-stu-id="3f429-182">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="3f429-183">La condizione controlla se la lunghezza del corpo è 0.</span><span class="sxs-lookup"><span data-stu-id="3f429-183">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="3f429-184">In caso affermativo, non sono disponibili dati da scrivere in Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="3f429-184">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="3f429-185">Se il valore è maggiore di 0, sono presenti dati da elaborare.</span><span class="sxs-lookup"><span data-stu-id="3f429-185">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="3f429-186">• Se vengono rilevati dati, sarà necessario elaborarli.</span><span class="sxs-lookup"><span data-stu-id="3f429-186">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="3f429-187">Analizza JSON definisce uno schema dei dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="3f429-187">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="3f429-188">Questo consente alle app per la logica di usare i dati analizzati come contenuto dinamico nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="3f429-188">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="3f429-189">• Poiché l'elenco di dati disponibili restituito è una matrice, viene usata un'azione For Each per scorrere l'elenco di contenuto disponibile.</span><span class="sxs-lookup"><span data-stu-id="3f429-189">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="3f429-190">• A questo punto viene recuperato il contenuto.</span><span class="sxs-lookup"><span data-stu-id="3f429-190">• Next is grabbing the content.</span></span>  <span data-ttu-id="3f429-191">HTTP viene usato nuovamente per ottenere contentUri, una proprietà dinamica creata da Analizza JSON, che è l'URL dei dati da recuperare.</span><span class="sxs-lookup"><span data-stu-id="3f429-191">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="3f429-192">• Analizza JSON consente anche di analizzare i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="3f429-192">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="3f429-193">È possibile trovare contenuto di esempio all'URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="3f429-193">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="3f429-194">• Anche i dati restituiti sono una matrice.</span><span class="sxs-lookup"><span data-stu-id="3f429-194">• The data returned is also an array.</span></span> <span data-ttu-id="3f429-195">Anche in questo caso si può quindi usare un ciclo For Each.</span><span class="sxs-lookup"><span data-stu-id="3f429-195">A For Each loop can be used here as well.</span></span> <span data-ttu-id="3f429-196">In questo ciclo, il flusso di lavoro acquisisce l'elemento di dati corrente e usa l'azione Invia dati per scrivere i dati in Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="3f429-196">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="3f429-197">• Poiché potrebbero esserci più pagine di contenuto disponibile, una condizione controlla se NextPageUri non è NULL.</span><span class="sxs-lookup"><span data-stu-id="3f429-197">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="3f429-198">Se è NULL, o vuoto, NextPage viene impostato su 0, terminando così il ciclo Until.</span><span class="sxs-lookup"><span data-stu-id="3f429-198">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="3f429-199">Se contiene un URL, la variabile AvaibleUri viene aggiornata all'URL.</span><span class="sxs-lookup"><span data-stu-id="3f429-199">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="3f429-200">In questo modo, la successiva esecuzione del ciclo Until userà un URL disponibile successivo e non l'URL iniziale.</span><span class="sxs-lookup"><span data-stu-id="3f429-200">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="3f429-201">È possibile scegliere di usare una *funzione di Azure* per inserire questi log e, in tal caso, le informazioni su come distribuirla sono disponibili [qui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)o [qui](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), in base alle preferenze.</span><span class="sxs-lookup"><span data-stu-id="3f429-201">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="3f429-202">Con il connettore in esecuzione, indipendentemente dall'opzione scelta, dovrebbe essere visualizzata una tabella personalizzata denominata O365API_CL nell'area di lavoro di Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="3f429-202">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="3f429-203">Questa tabella ospiterà i log di Teams.</span><span class="sxs-lookup"><span data-stu-id="3f429-203">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="3f429-204">Passaggio 3: Usare Sentinel per monitorare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f429-204">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="3f429-205">L'identità è un vettore di attacco importante da monitorare in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f429-205">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="3f429-206">Poiché Azure Active Directory (Azure AD) è alla base della directory di Microsoft 365, incluso Teams, la raccolta e la ricerca di minacce relative all'autenticazione nei log di Azure AD saranno utili per individuare comportamenti sospetti relativi all'identità.</span><span class="sxs-lookup"><span data-stu-id="3f429-206">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="3f429-207">È possibile usare il connettore integrato per eseguire il pull dei dati di Azure Active Directory in Azure Sentinel e usare queste query di [rilevamento](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) e [ricerca](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) per individuare i problemi.</span><span class="sxs-lookup"><span data-stu-id="3f429-207">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="3f429-208">Per quanto riguarda gli attacchi specifici di Microsoft Teams, le minacce ai dati, ad esempio, Azure Sentinel offre anche il modo di monitorarli e cercarli.</span><span class="sxs-lookup"><span data-stu-id="3f429-208">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="3f429-209">Creare un parser per i dati</span><span class="sxs-lookup"><span data-stu-id="3f429-209">Create a parser for your data</span></span>

<span data-ttu-id="3f429-210">La prima cosa da fare per interpretare l'ampio set di dati raccolti consiste nel darvi un senso mediante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="3f429-210">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="3f429-211">Questa operazione si può eseguire con una funzione in linguaggio di query Kusto (KQL) che semplifica l'uso dei dati.</span><span class="sxs-lookup"><span data-stu-id="3f429-211">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="3f429-212">Le funzioni KQL sono query KQL salvate come tipo di dati "function".</span><span class="sxs-lookup"><span data-stu-id="3f429-212">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="3f429-213">Le funzioni KQL hanno un alias che può essere immesso nella casella della query in Sentinel per ripetere velocemente l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="3f429-213">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="3f429-214">Per altre informazioni sulle funzioni KQL e su come creare una funzione parser, leggere [questo articolo della Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="3f429-214">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="3f429-215">Il parser seguente è un esempio personalizzabile il cui scopo è selezionare un subset dei campi dell'API di gestione di Office 365 pertinenti per *Teams*.</span><span class="sxs-lookup"><span data-stu-id="3f429-215">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="3f429-216">Esiste anche un parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) suggerito, ma quello che segue può essere modificato in base a esigenze e preferenze diverse.</span><span class="sxs-lookup"><span data-stu-id="3f429-216">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

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
 <span data-ttu-id="3f429-217">Salvare il parser come funzione KQL, con l'alias TeamsData.</span><span class="sxs-lookup"><span data-stu-id="3f429-217">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="3f429-218">Verrà usato per le query successive.</span><span class="sxs-lookup"><span data-stu-id="3f429-218">It will be used for the queries to follow.</span></span> <span data-ttu-id="3f429-219">I dettagli sulla configurazione e sull'uso di una funzione KQL come parser sono disponibili in questo[ articolo della Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="3f429-219">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="3f429-220">Query KQL utili per la ricerca</span><span class="sxs-lookup"><span data-stu-id="3f429-220">Helpful hunting KQL queries</span></span>

<span data-ttu-id="3f429-221">Usare queste query per acquisire familiarità con i dati e l'ambiente di Teams.</span><span class="sxs-lookup"><span data-stu-id="3f429-221">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="3f429-222">Conoscere l'aspetto e il comportamento che l'ambiente dovrebbe avere è un buon primo passo per riconoscere le attività sospette.</span><span class="sxs-lookup"><span data-stu-id="3f429-222">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="3f429-223">Fatto questo, ci si può dedicare alla ricerca delle minacce.</span><span class="sxs-lookup"><span data-stu-id="3f429-223">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="3f429-224">Query per utenti esterni federati</span><span class="sxs-lookup"><span data-stu-id="3f429-224">Federated external users query</span></span>

<span data-ttu-id="3f429-225">Questa query consente di ottenere l'elenco dei siti di Teams con utenti esterni federati.</span><span class="sxs-lookup"><span data-stu-id="3f429-225">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="3f429-226">Questi utenti avranno un suffisso del nome di dominio o UPN che *non è* di proprietà dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f429-226">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="3f429-227">In questa query di esempio l'organizzazione è proprietaria di contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3f429-227">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="3f429-228">Per altre informazioni sui tipi di accesso esterno e guest in Teams, vedere [questo articolo](./communicate-with-users-from-other-organizations.md)o la sezione *Tipi di partecipante* nella [Guida alla sicurezza di Teams](./teams-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="3f429-228">To learn more about External and Guest access types in Teams see [this article](./communicate-with-users-from-other-organizations.md), or the *Participant Types* section in the [Teams Security Guide](./teams-security-guide.md).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="3f429-229">Chi si è unito di recente/chi ha cambiato ruolo</span><span class="sxs-lookup"><span data-stu-id="3f429-229">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="3f429-230">Eseguire una query su uno specifico utente per controllare se è stato aggiunto a un canale di Teams negli ultimi 7:</span><span class="sxs-lookup"><span data-stu-id="3f429-230">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="3f429-231">Controllare se il ruolo di un utente in un team è stato cambiato negli ultimi 7 giorni:</span><span class="sxs-lookup"><span data-stu-id="3f429-231">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="3f429-232">Utenti esterni di organizzazioni sconosciute o nuove</span><span class="sxs-lookup"><span data-stu-id="3f429-232">External users from unknown or new organizations</span></span>

<span data-ttu-id="3f429-233">In Teams è possibile aggiungere utenti esterni ai propri canali o al proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="3f429-233">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="3f429-234">Spesso le organizzazioni hanno un numero limitato di partnership strategiche e aggiungono utenti da queste società partner.</span><span class="sxs-lookup"><span data-stu-id="3f429-234">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="3f429-235">Questa query KQL esamina gli utenti esterni aggiunti ai team che provengono da organizzazioni mai viste o aggiunte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3f429-235">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

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

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="3f429-236">Aggiunta e successiva rimozione di utenti esterni</span><span class="sxs-lookup"><span data-stu-id="3f429-236">External users who were added and then removed</span></span>

<span data-ttu-id="3f429-237">Gli utenti malintenzionati con qualche livello di accesso esistente possono aggiungere un nuovo account esterno a Teams per accedere ed esfiltrare dati.</span><span class="sxs-lookup"><span data-stu-id="3f429-237">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="3f429-238">Possono anche rimuovere rapidamente l'utente per nascondere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3f429-238">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="3f429-239">Questa query cerca account esterni aggiunti a Teams e rimossi rapidamente, per identificare comportamenti sospetti.</span><span class="sxs-lookup"><span data-stu-id="3f429-239">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

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

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="3f429-240">Aggiunta di nuovi bot o applicazioni</span><span class="sxs-lookup"><span data-stu-id="3f429-240">New bot or application added</span></span>

<span data-ttu-id="3f429-241">Teams offre la possibilità di includere app o bot in un team per estendere il set di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3f429-241">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="3f429-242">Questo include app e bot personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3f429-242">This includes custom apps and bots.</span></span> <span data-ttu-id="3f429-243">In alcuni casi, un'app o un bot potrebbe essere usato per stabilire la persistenza in Teams senza bisogno di un account utente, oltre che per accedere ai file e ad altri dati.</span><span class="sxs-lookup"><span data-stu-id="3f429-243">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="3f429-244">Questa query cerca nuove app o bot in Teams.</span><span class="sxs-lookup"><span data-stu-id="3f429-244">This query hunts for apps or bots that are new to Teams.</span></span>

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="3f429-245">Account utente proprietari di un numero elevato di team</span><span class="sxs-lookup"><span data-stu-id="3f429-245">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="3f429-246">Gli utenti malintenzionati che provano a elevare i propri privilegi possono assegnare a se stessi privilegi proprietario di un numero elevato di team diversi, mentre in genere gli utenti creano e possiedono un numero limitato di team su argomenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3f429-246">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="3f429-247">Questa query KQL cerca i comportamenti sospetti.</span><span class="sxs-lookup"><span data-stu-id="3f429-247">This KQL query looks for suspicious behavior.</span></span>

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

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="3f429-248">Numerose eliminazioni di team da parte di un singolo utente</span><span class="sxs-lookup"><span data-stu-id="3f429-248">Many Team deletions by a single user</span></span>

<span data-ttu-id="3f429-249">Gli utenti malintenzionati possono causare interruzioni e mettere in pericolo progetti e dati eliminando più team.</span><span class="sxs-lookup"><span data-stu-id="3f429-249">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="3f429-250">Poiché i team vengano generalmente eliminati dai singoli proprietari, l'eliminazione centrale di molti team può essere un segnale di problemi.</span><span class="sxs-lookup"><span data-stu-id="3f429-250">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="3f429-251">Questa query KQL cerca singoli utenti che eliminano più team.</span><span class="sxs-lookup"><span data-stu-id="3f429-251">This KQL looks for single users who delete multiple teams.</span></span>

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

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="3f429-252">Espansione delle opportunità di ricerca delle minacce</span><span class="sxs-lookup"><span data-stu-id="3f429-252">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="3f429-253">È possibile espandere la ricerca combinando le query di risorse come Azure Active Directory (Azure AD) o altri carichi di lavoro di Office 365 con le query di Teams.</span><span class="sxs-lookup"><span data-stu-id="3f429-253">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="3f429-254">Ad esempio, si può combinare il rilevamento degli schemi sospetti nei log di accesso (SigninLogs) di Azure AD e usare tali informazioni durante la ricerca dei proprietari di team.</span><span class="sxs-lookup"><span data-stu-id="3f429-254">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

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

<span data-ttu-id="3f429-255">Inoltre, è possibile rendere i rilevamenti in SigninLogs specifici per Teams, aggiungendo un filtro per i soli accessi basati su Teams usando:</span><span class="sxs-lookup"><span data-stu-id="3f429-255">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="3f429-256">Per spiegare meglio l'uso di `where AppDisplayName starts with "Microsoft Teams"`, la query KQL seguente illustra un accesso riuscito da un indirizzo IP con un errore da un indirizzo IP diverso, ma con ambito limitato agli accessi di Teams:</span><span class="sxs-lookup"><span data-stu-id="3f429-256">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="3f429-257">Informazioni e aggiornamenti importanti</span><span class="sxs-lookup"><span data-stu-id="3f429-257">Important information and updates</span></span>

<span data-ttu-id="3f429-258">**Grazie per la collaborazione sui contenuti a Pete Bryan, Nicholas DiCola e Matthew Lowe.**</span><span class="sxs-lookup"><span data-stu-id="3f429-258">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="3f429-259">Pete Bryan e i suoi collaboratori continueranno a sviluppare query di rilevamento e ricerca per Teams, consultare questo repository [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) per gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="3f429-259">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="3f429-260">Controllare la disponibilità di aggiornamenti per il [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) e l'[app per la logica](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3f429-260">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="3f429-261">Si può anche entrare a far parte della [community di Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) e collaborare.</span><span class="sxs-lookup"><span data-stu-id="3f429-261">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="3f429-262">Grazie!</span><span class="sxs-lookup"><span data-stu-id="3f429-262">Thank you!</span></span> <span data-ttu-id="3f429-263">Buona caccia alle minacce.</span><span class="sxs-lookup"><span data-stu-id="3f429-263">Happy hunting.</span></span>

[<span data-ttu-id="3f429-264">Registrazione dell'applicazione in Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f429-264">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="3f429-265">Abilitare o disabilitare la ricerca nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="3f429-265">Turn audit log search on or off</span></span>](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0)

[<span data-ttu-id="3f429-266">Che cos'è Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="3f429-266">What is Azure Sentinel</span></span>](/azure/sentinel/overview)
