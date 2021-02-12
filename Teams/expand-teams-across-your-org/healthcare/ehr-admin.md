---
title: Teams per le visite virtuali
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
ms.openlocfilehash: 2d2be135668bcc45f0054e987a23845e3245c38e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125779"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="ac56a-103">Visite virtuali con Teams - Integrazione in EHR</span><span class="sxs-lookup"><span data-stu-id="ac56a-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="ac56a-104">Microsoft Teams Electronic Health Record (EHR) Connector consente ai medici di avviare facilmente una visita o una consulenza virtuale con un altro provider di Teams direttamente dal sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="ac56a-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="ac56a-105">Basato sul cloud Microsoft 365, Microsoft Teams consente una collaborazione e comunicazione semplici e sicure con strumenti di chat, video, voce e assistenza sanitaria in un unico hub che supporta la conformità con HIPAA, certificazione HITECH e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="ac56a-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="ac56a-106">La piattaforma di comunicazione e collaborazione di Teams consente ai medici di tagliare il disordine di sistemi frammentati in modo che possano dedicare tempo alle cure migliori possibili.</span><span class="sxs-lookup"><span data-stu-id="ac56a-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="ac56a-107">Microsoft Teams Electronic Health Record (EHR) Connector può:</span><span class="sxs-lookup"><span data-stu-id="ac56a-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="ac56a-108">Avvia le visite virtuali di Teams dai portali del provider e dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="ac56a-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="ac56a-109">Scrivere di nuovo nei metadati EHR per connettersi e disconnettere gli eventi per abilitare il controllo automatico e il mantenimento dei record.</span><span class="sxs-lookup"><span data-stu-id="ac56a-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="ac56a-110">È possibile integrare i flussi di lavoro esistenti di un medico o di pazienti, consentendo loro di usare Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="ac56a-111">Guardare il video su come gestire le visite virtuali dal portale EHR.</span><span class="sxs-lookup"><span data-stu-id="ac56a-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="ac56a-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ac56a-112">Before you begin</span></span>

<span data-ttu-id="ac56a-113">Per poter integrare il connettore EHR, è necessario verificare di avere i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac56a-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="ac56a-114">Accesso all'app Microsoft Teams in [App Orchard marketplace di Amazon.](https://apporchard.epic.com/Gallery?id=6153)</span><span class="sxs-lookup"><span data-stu-id="ac56a-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="ac56a-115">Abbonamento attivo a Microsoft Cloud per il settore sanitario o abbonamento all'offerta autonoma microsoft Teams EHR Connector (applicata solo durante i test di produzione).</span><span class="sxs-lookup"><span data-stu-id="ac56a-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="ac56a-116">Gli utenti devono avere una licenza appropriata di Microsoft 365 o Office 365 che includa le riunioni di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="ac56a-117">Microsoft Teams deve essere adottato e usato all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="ac56a-118">Le organizzazioni devono avere con la versione Beta di novembre 2018 o successiva.</span><span class="sxs-lookup"><span data-stu-id="ac56a-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="ac56a-119">I sistemi devono soddisfare tutti [i prerequisiti software e del browser.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="ac56a-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="ac56a-120">Sono necessarie anche le informazioni dei seguenti utenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="ac56a-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="ac56a-121">Amministratore di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac56a-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="ac56a-122">Analista cliente esalta</span><span class="sxs-lookup"><span data-stu-id="ac56a-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="ac56a-123">Richiedi al tuo esperto tecnico Disabilita di fornire la Epic-Microsoft di integrazione telehealth di Teams disponibile in Marketplace di Amazon.</span><span class="sxs-lookup"><span data-stu-id="ac56a-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="ac56a-124">Configurazione del connettore</span><span class="sxs-lookup"><span data-stu-id="ac56a-124">Connector setup</span></span>

<span data-ttu-id="ac56a-125">Per la configurazione del connettore è necessario:</span><span class="sxs-lookup"><span data-stu-id="ac56a-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="ac56a-126">Avviare il portale di configurazione del connettore EHR</span><span class="sxs-lookup"><span data-stu-id="ac56a-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="ac56a-127">Informazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="ac56a-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="ac56a-128">Approvazione o visualizzazione della configurazione</span><span class="sxs-lookup"><span data-stu-id="ac56a-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="ac56a-129">Rivedere e completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="ac56a-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="ac56a-130">Avviare il portale di configurazione del connettore EHR</span><span class="sxs-lookup"><span data-stu-id="ac56a-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="ac56a-131">La configurazione dell'organizzazione sanitaria per l'avvio di visite virtuali con Microsoft Teams avvia il portale di configurazione del connettore EHR.</span><span class="sxs-lookup"><span data-stu-id="ac56a-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="ac56a-132">Configurare una o più organizzazioni per testare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="ac56a-133">Configurare l'URL di test e produzione nel portale di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="ac56a-134">Prima di passare alla produzione, testare l'integrazione dell'ambiente di test di Innova.</span><span class="sxs-lookup"><span data-stu-id="ac56a-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="ac56a-135">URL di configurazione del connettore EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ac56a-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="ac56a-136">L'amministratore di Microsoft 365 e l'analista cliente Più questo dell'organizzazione devono completare i passaggi per l'integrazione e le informazioni nel portale di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="ac56a-137">Per i passaggi di configurazione dell'organizzazione, contattare la risorsa tecnica Diarotte assegnata all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="ac56a-138">Informazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="ac56a-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="ac56a-139">Questo passaggio deve essere completato **dall'amministratore di Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="ac56a-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="ac56a-140">Per avviare il processo di configurazione, l'amministratore di Microsoft 365 deve avviare il portale di configurazione del connettore e accedere con le credenziali Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac56a-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="ac56a-141">Per completare questo passaggio, l'amministratore di Microsoft 365 deve ricevere un URL di base Fast Health Interoperability Resources (FHIR) valido dal tecnico Specializzato e il nome utente dell'analista del cliente Fast Health Interoperability Resources che approva la configurazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="ac56a-142">Per avviare il processo di configurazione, l'amministratore di Microsoft 365 deve avviare la pagina di configurazione del connettore e accedere con le credenziali Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac56a-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="ac56a-143">L'URL di base FHIR è un indirizzo statico corrispondente all'endpoint dell'API FHIR del server.</span><span class="sxs-lookup"><span data-stu-id="ac56a-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="ac56a-144">Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` .</span><span class="sxs-lookup"><span data-stu-id="ac56a-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="ac56a-145">Nome responsabile approvazione configurazione è il nome dell'analista cliente Innovatore che sarà responsabile dell'approvazione della configurazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="ac56a-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="ac56a-146">L'analista cliente Più importante è una persona dell'organizzazione con accesso ad Avaro.</span><span class="sxs-lookup"><span data-stu-id="ac56a-146">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![Il nome del responsabile dell'approvazione della configurazione viene selezionato da un elenco nel connettore EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="ac56a-148">Approvazione o visualizzazione della configurazione</span><span class="sxs-lookup"><span data-stu-id="ac56a-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="ac56a-149">L'analista cliente Disalvata per l'organizzazione sanitaria che è stata aggiunta come responsabile approvazione ora deve usare lo stesso URL del connettore EHR del passaggio precedente per accedere con le credenziali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac56a-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="ac56a-150">Dopo la convalida, al responsabile approvazione verrà chiesto di eseguire l'accesso con le loro credenziali frequenti per convalidare l'organizzazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ac56a-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="ac56a-151">L'amministratore di Microsoft 365 e l'analista cliente Più di questo tipo nell'organizzazione possono essere la stessa persona.</span><span class="sxs-lookup"><span data-stu-id="ac56a-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="ac56a-152">In questo caso, aggiungere il proprio nome utente come responsabile approvazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="ac56a-153">Per convalidare l'accesso, dovrai comunque accedere ad Haiti.</span><span class="sxs-lookup"><span data-stu-id="ac56a-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="ac56a-154">L'accesso Dir 3 viene usato solo per convalidare l'URL di base FHIR.</span><span class="sxs-lookup"><span data-stu-id="ac56a-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="ac56a-155">Microsoft non archivia le credenziali né accede ai dati EHR con questo accesso.</span><span class="sxs-lookup"><span data-stu-id="ac56a-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Verificare e approvare la configurazione delle credenziali.](../../media/approve-view-configuration.png)

<span data-ttu-id="ac56a-157">Dopo aver completato l'accesso, l'analista cliente Innova **deve** approvare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="ac56a-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="ac56a-158">Se la configurazione non è corretta, l'amministratore di Microsoft 365 avrà la possibilità di modificare le configurazioni originali accedendo di nuovo al portale dei connettori Microsoft EHR.</span><span class="sxs-lookup"><span data-stu-id="ac56a-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Verificare che il connettore EHR sia configurato e che l'opzione per modificare la configurazione sia configurata.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="ac56a-160">Rivedere e completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="ac56a-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="ac56a-161">Quando le informazioni di configurazione vengono approvate dall'amministratore programmaTaro, verranno visualizzati i record di integrazione per il lancio di pazienti e provider.</span><span class="sxs-lookup"><span data-stu-id="ac56a-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="ac56a-162">Questi record sono necessari per completare la configurazione della visita virtuale in Ho.</span><span class="sxs-lookup"><span data-stu-id="ac56a-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="ac56a-163">Per altre informazioni, Epic-Microsoft guida all'integrazione teleintegra di Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="ac56a-164">In qualsiasi momento, l'analista cliente Microsoft 365 o Riesci può accedere al portale di configurazione per visualizzare i record di integrazione e modificare la configurazione dell'organizzazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ac56a-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Vengono visualizzate le informazioni di integrazione.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="ac56a-166">Prima di completare il processo di approvazione da parte dell'analista clienteConfigure per ogni URL FHIR configurato dall'amministratore Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac56a-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Le informazioni di configurazione sono approvate.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="ac56a-168">Avviare le visite virtuali di Teams</span><span class="sxs-lookup"><span data-stu-id="ac56a-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="ac56a-169">Dopo aver completato la procedura per il connettore EHR e la configurazione di questo tipo, l'organizzazione è pronta a supportare le video visite con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="ac56a-170">Prerequisiti per la visita virtuale</span><span class="sxs-lookup"><span data-stu-id="ac56a-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="ac56a-171">I sistemi devono soddisfare tutti [i prerequisiti software e del browser.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="ac56a-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="ac56a-172">È necessario che l'organizzazione sanitaria abbia completato la configurazione tra l'organizzazione Invasa e l'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac56a-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="ac56a-173">Esperienza del provider</span><span class="sxs-lookup"><span data-stu-id="ac56a-173">Provider experience</span></span>

<span data-ttu-id="ac56a-174">Gli operatori sanitari dell'organizzazione possono partecipare alle visite virtuali con Microsoft Teams dalle applicazioni provider Di Questo tipo (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="ac56a-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="ac56a-175">Il **pulsante Avvia visita** virtuale è incorporato nel flusso del provider.</span><span class="sxs-lookup"><span data-stu-id="ac56a-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="ac56a-176">Caratteristiche principali dell'esperienza del provider:</span><span class="sxs-lookup"><span data-stu-id="ac56a-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="ac56a-177">I provider possono partecipare a visite virtuali usando i browser supportati o l'applicazione Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="ac56a-178">I provider devono eseguire l'accesso una sola volta con il proprio account Microsoft 365 quando si partecipa a una visita virtuale per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="ac56a-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="ac56a-179">Dopo l'accesso una sola volta, il provider verrà portato direttamente all'appuntamento virtuale in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="ac56a-180">(Il provider deve essere connesso a Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="ac56a-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="ac56a-181">Il provider può vedere gli aggiornamenti in tempo reale dei partecipanti che si connettono e si disconnettino per un determinato appuntamento.</span><span class="sxs-lookup"><span data-stu-id="ac56a-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="ac56a-182">Il provider può vedere quando il paziente è connesso a una visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="ac56a-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Esperienza del provider per una visita virtuale con un paziente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="ac56a-184">Esperienza dei pazienti</span><span class="sxs-lookup"><span data-stu-id="ac56a-184">Patient experience</span></span>

<span data-ttu-id="ac56a-185">Il connettore supporta i pazienti che partecipano a visite virtuali tramite il Web e il dispositivo mobile MyChart.</span><span class="sxs-lookup"><span data-stu-id="ac56a-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="ac56a-186">Al momento dell'appuntamento, i pazienti possono iniziare una visita virtuale da MyChart usando il pulsante **Inizia visita** virtuale.</span><span class="sxs-lookup"><span data-stu-id="ac56a-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="ac56a-187">Caratteristiche principali dell'esperienza del paziente:</span><span class="sxs-lookup"><span data-stu-id="ac56a-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="ac56a-188">I pazienti possono partecipare a visite virtuali da Web browser moderni su desktop e dispositivi mobili senza installazione di app.</span><span class="sxs-lookup"><span data-stu-id="ac56a-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="ac56a-189">I pazienti possono partecipare a visite virtuali con un solo clic e non è necessario alcun altro account o accesso.</span><span class="sxs-lookup"><span data-stu-id="ac56a-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="ac56a-190">I pazienti non sono tenuti a creare un account Microsoft o ad accedere per avviare una visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="ac56a-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="ac56a-191">I pazienti saranno messi in sala d'attesa finché il provider sanitario non si unisce all'appuntamento e li ammettere alla visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="ac56a-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="ac56a-192">I test del video e del microfono sono disponibili nella sala di attesa prima di partecipare alla visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="ac56a-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Esperienza dei pazienti per la visita virtuale](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="ac56a-194">MyChart, Haiku e Canto sono marchi di Corporation, Corporation, MyChart e Canto.</span><span class="sxs-lookup"><span data-stu-id="ac56a-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="ac56a-195">Privacy e posizione dei dati</span><span class="sxs-lookup"><span data-stu-id="ac56a-195">Privacy and location of data</span></span>

<span data-ttu-id="ac56a-196">L'integrazione di Teams nei sistemi EHR ottimizza la quantità di dati usati e archiviati durante l'integrazione e i flussi delle visite virtuali.</span><span class="sxs-lookup"><span data-stu-id="ac56a-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="ac56a-197">La soluzione segue i principi generali sulla privacy e la gestione dei dati di Teams e le linee guida sulla privacy di Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="ac56a-198">Il connettore Microsoft Teams EHR non archivia né trasferisce dati personali identificabili o cartelle sanitarie di pazienti o fornitori di assistenza sanitaria dal sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="ac56a-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="ac56a-199">Gli unici dati archiviati dal connettore EHR sono l'ID univoco dell'utente EHR, usato durante la configurazione della riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="ac56a-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="ac56a-200">L'ID univoco dell'utente EHR viene archiviato in una delle tre aree geografiche descritte in Dove vengono archiviati i dati dei clienti [di Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)</span><span class="sxs-lookup"><span data-stu-id="ac56a-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="ac56a-201">Tutte le chat, le registrazioni e altri dati immessi in Teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="ac56a-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="ac56a-202">Per ulteriori informazioni sulla posizione dei dati in Microsoft Teams, visita [Posizioni dei dati in Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)</span><span class="sxs-lookup"><span data-stu-id="ac56a-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
