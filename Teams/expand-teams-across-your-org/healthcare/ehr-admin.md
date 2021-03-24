---
title: Teams per Visite virtuali
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usare Microsoft Teams per configurare il sistema di visite virtuali
ms.openlocfilehash: 37b93533aeff6b519b1f5a65cf49211464b41388
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096280"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="e0e72-103">Visite virtuali con Teams - Integrazione in CCE</span><span class="sxs-lookup"><span data-stu-id="e0e72-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="e0e72-104">Il connettore CCE (cartella clinica elettronica) di Microsoft Teams consente al personale medico di avviare una visita o un consulto virtuale con un altro provider in Teams direttamente dal sistema CCE.</span><span class="sxs-lookup"><span data-stu-id="e0e72-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="e0e72-105">Basato sul cloud di Microsoft 365, Microsoft Teams semplifica e assicura la collaborazione e la comunicazione con strumenti di chat, video, voce e assistenza sanitaria in un unico hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="e0e72-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="e0e72-106">Con la piattaforma di comunicazione e collaborazione di Teams, il personale medico può facilmente superare la complessità e la confusione di sistemi frammentati per dedicare il proprio tempo a fornire la migliore assistenza possibile.</span><span class="sxs-lookup"><span data-stu-id="e0e72-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="e0e72-107">Il connettore CCE (cartella clinica elettronica) di Microsoft Teams permette di:</span><span class="sxs-lookup"><span data-stu-id="e0e72-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="e0e72-108">Avviare visite virtuali di Teams dai portali del provider e dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="e0e72-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="e0e72-109">Eseguire il writeback nei metadati CCE sugli eventi di connessione e disconnessione per abilitare l’auditing e l’archiviazione dei dati automatici.</span><span class="sxs-lookup"><span data-stu-id="e0e72-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="e0e72-110">Integrarsi nei flussi di lavoro esistenti di medici e pazienti consentendo loro di usare Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0e72-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="e0e72-111">Guardare il video su come gestire le visite virtuali dal portale CCE.</span><span class="sxs-lookup"><span data-stu-id="e0e72-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="e0e72-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e0e72-112">Before you begin</span></span>

<span data-ttu-id="e0e72-113">Prima di integrare il connettore CCE, è necessario verificare di avere i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0e72-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="e0e72-114">Accesso all'app Microsoft Teams nel [marketplace App Orchard di Epic](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="e0e72-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="e0e72-115">Abbonamento attivo a Microsoft Cloud per il Settore Sanitario o abbonamento all'offerta autonoma del connettore CCE di Microsoft Teams (applicato solo in fase di test di produzione).</span><span class="sxs-lookup"><span data-stu-id="e0e72-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="e0e72-116">Gli utenti devono avere una licenza Microsoft 365 o Office 365 appropriata che includa le riunioni di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0e72-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="e0e72-117">Microsoft Teams dovrà essere adottato e usato all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="e0e72-118">Le organizzazioni devono avere la versione Epic di novembre 2018 o successiva.</span><span class="sxs-lookup"><span data-stu-id="e0e72-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="e0e72-119">I sistemi devono soddisfare tutti i [prerequisiti per software e browser](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="e0e72-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="e0e72-120">All'interno dell'organizzazione saranno necessarie anche le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0e72-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="e0e72-121">Amministratore di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0e72-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="e0e72-122">Customer Analyst di Epic</span><span class="sxs-lookup"><span data-stu-id="e0e72-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="e0e72-123">Consulta la [Guida all'integrazione telesalana epica](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) di Microsoft Teams con il tuo esperto tecnico Epic.</span><span class="sxs-lookup"><span data-stu-id="e0e72-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="e0e72-124">Assicurarsi che tutti i prerequisiti siano stati completati.</span><span class="sxs-lookup"><span data-stu-id="e0e72-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="e0e72-125">Configurazione dei connettori</span><span class="sxs-lookup"><span data-stu-id="e0e72-125">Connector setup</span></span>

<span data-ttu-id="e0e72-126">Per la configurazione del connettore è necessario:</span><span class="sxs-lookup"><span data-stu-id="e0e72-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="e0e72-127">Avviare il portale di configurazione del connettore CCE</span><span class="sxs-lookup"><span data-stu-id="e0e72-127">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="e0e72-128">Informazioni sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="e0e72-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="e0e72-129">Approvare o visualizzare la configurazione</span><span class="sxs-lookup"><span data-stu-id="e0e72-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="e0e72-130">Rivedere e completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="e0e72-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="e0e72-131">Avviare il portale di configurazione del connettore CCE</span><span class="sxs-lookup"><span data-stu-id="e0e72-131">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="e0e72-132">Per configurare l'organizzazione del settore sanitario in modo da organizzare visite virtuali con Microsoft Teams, avviare il portale di configurazione del connettore CCE.</span><span class="sxs-lookup"><span data-stu-id="e0e72-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="e0e72-133">Configurare una o più organizzazioni per testare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="e0e72-134">Configurare l'URL di test e produzione nel portale di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="e0e72-135">Testare l'integrazione dall'ambiente di test di Epic prima di passare alla produzione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="e0e72-136">URL di configurazione del connettore CCE: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e0e72-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="e0e72-137">L'amministratore di Microsoft 365 e il Customer Analyst di Epic della propria organizzazione devono completare le informazioni e i passaggi di integrazione nel portale di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="e0e72-138">Per la procedura di configurazione di Epic, contattare l’esperto tecnico di Epic assegnato all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="e0e72-139">Informazioni sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="e0e72-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="e0e72-140">Questo passaggio deve essere completato dall'**amministratore di Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="e0e72-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="e0e72-141">Per avviare il processo di configurazione, l'amministratore di Microsoft 365 deve avviare il portale di configurazione del connettore e accedere con le credenziali Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0e72-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="e0e72-142">Per completare questo passaggio, l'amministratore di Microsoft 365 deve ricevere un valido URL di base FHIR (Fast Health Interoperability Resources) dal proprio esperto tecnico di Epic e il nome utente del Customer Analyst di Epic che approverà la configurazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="e0e72-143">Per avviare il processo di configurazione, l'amministratore di Microsoft 365 deve avviare la pagina di configurazione del connettore e accedere con le credenziali Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0e72-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="e0e72-144">L'URL di base FHIR è un indirizzo statico corrispondente all'endpoint dell'API FHIR del server.</span><span class="sxs-lookup"><span data-stu-id="e0e72-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="e0e72-145">Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span><span class="sxs-lookup"><span data-stu-id="e0e72-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="e0e72-146">Il nome del responsabile approvazione della configurazione è il nome del Customer Analyst di Epic che sarà incaricato di approvare la configurazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e0e72-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="e0e72-147">Il Customer Analyst di Epic è una persona all’interno dell'organizzazione con accesso autorizzato a Epic.</span><span class="sxs-lookup"><span data-stu-id="e0e72-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![Il nome del responsabile approvazione della configurazione viene selezionato da un elenco nel connettore CCE.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="e0e72-149">Approvare o visualizzare la configurazione</span><span class="sxs-lookup"><span data-stu-id="e0e72-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="e0e72-150">Il Customer Analyst di Epic per l'organizzazione del settore sanitario che è stato aggiunto come responsabile approvazione deve ora usare lo stesso URL del connettore CCE del passaggio precedente per accedere con le proprie credenziali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0e72-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="e0e72-151">Dopo aver completato la convalida, al responsabile approvazione verrà chiesto di accedere con le credenziali di Epic per convalidare l'organizzazione Epic.</span><span class="sxs-lookup"><span data-stu-id="e0e72-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="e0e72-152">L'amministratore di Microsoft 365 e il Customer Analyst di Epic nell'organizzazione possono essere la stessa persona.</span><span class="sxs-lookup"><span data-stu-id="e0e72-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="e0e72-153">In questo caso, aggiungere il proprio nome utente come responsabile approvazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="e0e72-154">Sarà comunque necessario accedere a Epic per convalidare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e0e72-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="e0e72-155">Le informazioni di accesso di Epic vengono usate solo per convalidare l'URL di base FHIR.</span><span class="sxs-lookup"><span data-stu-id="e0e72-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="e0e72-156">Con questo accesso, Microsoft non archivia le credenziali o accede ai dati CCE.</span><span class="sxs-lookup"><span data-stu-id="e0e72-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Verificare e approvare la configurazione delle credenziali.](../../media/approve-view-configuration.png)

<span data-ttu-id="e0e72-158">Dopo aver completato l'accesso a Epic, il Customer Analyst **deve** approvare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="e0e72-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="e0e72-159">Se la configurazione non è corretta, l'amministratore di Microsoft 365 avrà la possibilità di modificare le configurazioni originali accedendo di nuovo al portale del connettore CCE di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0e72-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Verificare che il connettore CCE sia configurato e l'opzione per modificare la configurazione.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="e0e72-161">Rivedere e completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="e0e72-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="e0e72-162">Quando l’amministratore di Epic avrà approvato le informazioni di configurazione, verranno visualizzati i record di integrazione per l’avvio di visite virtuali tra pazienti e provider.</span><span class="sxs-lookup"><span data-stu-id="e0e72-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="e0e72-163">Questi record sono necessari per completare la configurazione della visita virtuale in Epic.</span><span class="sxs-lookup"><span data-stu-id="e0e72-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="e0e72-164">Per altre informazioni, vedere la guida all'integrazione della telemedicina di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0e72-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="e0e72-165">In qualsiasi momento il Customer Analyst di Microsoft 365 o Epic potrà accedere al portale di configurazione per visualizzare i record di integrazione e modificare la configurazione dell'organizzazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e0e72-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Vengono visualizzate le informazioni di integrazione.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="e0e72-167">Il Customer Analyst di Epic dovrà completare il processo di approvazione per ogni URL FHIR configurato prima dall’amministratore Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0e72-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Le informazioni di configurazione vengono approvate.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="e0e72-169">Avviare visite virtuali di Teams</span><span class="sxs-lookup"><span data-stu-id="e0e72-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="e0e72-170">Dopo aver completato la procedura per il connettore CCE e la configurazione di Epic, l'organizzazione è pronta per supportare le video visite con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0e72-170">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="e0e72-171">Prerequisiti per la visita virtuale</span><span class="sxs-lookup"><span data-stu-id="e0e72-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="e0e72-172">I sistemi devono soddisfare tutti i [prerequisiti per software e browser](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="e0e72-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="e0e72-173">L'organizzazione del settore sanitario deve aver completato la configurazione tra l'organizzazione Epic e l'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0e72-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="e0e72-174">Esperienza del provider</span><span class="sxs-lookup"><span data-stu-id="e0e72-174">Provider experience</span></span>

<span data-ttu-id="e0e72-175">I provider di servizi sanitari dell'organizzazione possono partecipare alle visite virtuali con Microsoft Teams anche dalle applicazioni del provider Epic (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="e0e72-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="e0e72-176">Il pulsante **Begin virtual visit** (Avvia visita virtuale) è incorporato nel flusso del provider.</span><span class="sxs-lookup"><span data-stu-id="e0e72-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="e0e72-177">Caratteristiche principali dell'esperienza del provider:</span><span class="sxs-lookup"><span data-stu-id="e0e72-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="e0e72-178">I provider possono partecipare alle visite virtuali usando i browser supportati o l'applicazione Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0e72-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="e0e72-179">I provider devono eseguire l'accesso singolo con il proprio account Microsoft 365 quando partecipano a una visita virtuale per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="e0e72-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="e0e72-180">Dopo aver eseguito l'accesso singolo, il provider verrà trasferito direttamente all'appuntamento virtuale in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0e72-180">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="e0e72-181">(il provider deve aver eseguito l’accesso a Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="e0e72-181">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="e0e72-182">Il provider può vedere gli aggiornamenti in tempo reale dei partecipanti che si connettono e disconnettono per un appuntamento specifico.</span><span class="sxs-lookup"><span data-stu-id="e0e72-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="e0e72-183">Il provider può vedere quando il paziente è connesso a una visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="e0e72-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Esperienza del provider di una visita virtuale con un paziente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="e0e72-185">Esperienza del paziente</span><span class="sxs-lookup"><span data-stu-id="e0e72-185">Patient experience</span></span>

<span data-ttu-id="e0e72-186">Il connettore supporta la partecipazione di pazienti alle visite virtuali attraverso le versioni Web e per dispositivo mobile di MyChart.</span><span class="sxs-lookup"><span data-stu-id="e0e72-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="e0e72-187">All’ora dell'appuntamento, i pazienti possono iniziare una visita virtuale da MyChart usando il pulsante **Begin virtual visit** (Inizia visita virtuale).</span><span class="sxs-lookup"><span data-stu-id="e0e72-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="e0e72-188">Caratteristiche principali dell'esperienza del paziente:</span><span class="sxs-lookup"><span data-stu-id="e0e72-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="e0e72-189">I pazienti possono partecipare a visite virtuali da Web browser moderni su PC desktop e dispositivi mobili senza l'installazione di app.</span><span class="sxs-lookup"><span data-stu-id="e0e72-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="e0e72-190">I pazienti possono partecipare a visite virtuali con un solo clic e non è necessario alcun altro account o accesso.</span><span class="sxs-lookup"><span data-stu-id="e0e72-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="e0e72-191">I pazienti non sono tenuti a creare un account Microsoft o ad accedere con le credenziali per avviare una visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="e0e72-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="e0e72-192">I pazienti verranno inseriti in una sala di attesa finché il provider di servizi sanitari non parteciperà all'appuntamento e darà loro accesso alla visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="e0e72-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="e0e72-193">Il test del video e del microfono è disponibile nella sala di attesa prima di partecipare alla visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="e0e72-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Esperienza del paziente della visita virtuale](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="e0e72-195">Epic, MyChart, Haiku e Canto sono marchi registrati di Epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="e0e72-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="e0e72-196">Privacy e posizione dei dati</span><span class="sxs-lookup"><span data-stu-id="e0e72-196">Privacy and location of data</span></span>

<span data-ttu-id="e0e72-197">L'integrazione di Teams nei sistemi CCE ottimizza la quantità di dati usati e archiviati durante l'integrazione e i flussi di visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="e0e72-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="e0e72-198">La soluzione segue i principi generali della privacy e della gestione dei dati di Teams e le linee guida descritte nell’informativa sulla privacy di Teams.</span><span class="sxs-lookup"><span data-stu-id="e0e72-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="e0e72-199">Il connettore CCE di Microsoft Teams non archivia né trasferisce dati personali identificabili né cartelle sanitarie di pazienti o provider di servizi sanitari dal sistema CCE.</span><span class="sxs-lookup"><span data-stu-id="e0e72-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="e0e72-200">Gli unici dati archiviati dal connettore CCE sono l'ID univoco dell'utente CCE, che viene usato durante la configurazione della riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="e0e72-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="e0e72-201">L'ID univoco dell'utente CCE viene archiviato in una delle tre aree geografiche descritte in [Dove sono archiviati i dati dei clienti di Microsoft 365](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span><span class="sxs-lookup"><span data-stu-id="e0e72-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="e0e72-202">Tutti i dati di chat, registrazioni e altre fonti immessi in Teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="e0e72-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="e0e72-203">Per altre informazioni sulla posizione dei dati in Microsoft Teams, visitare [Posizione dei dati in Teams](../../location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e0e72-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>