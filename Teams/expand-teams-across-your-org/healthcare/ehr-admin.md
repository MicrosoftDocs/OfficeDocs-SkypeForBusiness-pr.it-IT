---
title: Team per le visite virtuali
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
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usare Microsoft teams per configurare il sistema di visite virtuali
ms.openlocfilehash: 4c8511939532a448d5229865618aa308494c7a42
ms.sourcegitcommit: 4bf85d91befb56566130731198518c103a53ebc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50101334"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="f5bfb-103">Visite virtuali con teams-integrazione in EHR</span><span class="sxs-lookup"><span data-stu-id="f5bfb-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="f5bfb-104">Microsoft teams Electronic Health record (EHR) Connector rende più facile per i medici avviare una visita virtuale o una consultazione con un altro provider in teams direttamente dal sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="f5bfb-105">Basato sul cloud Microsoft 365, Microsoft teams consente la collaborazione e la comunicazione semplici e sicure con strumenti di chat, video, Voice e Healthcare in un singolo hub che supporta la conformità con HIPAA, la certificazione HITECH e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="f5bfb-106">La piattaforma di comunicazione e collaborazione dei team rende più facile per i clinici tagliare il groviglio di sistemi frammentati in modo che possano trascorrere il tempo fornendo le migliori cure possibili.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="f5bfb-107">Microsoft teams Electronic Health record (EHR) Connector può:</span><span class="sxs-lookup"><span data-stu-id="f5bfb-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="f5bfb-108">Avviare le visite virtuali di team sia da provider che da portatori di pazienti.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="f5bfb-109">Riscrivi i metadati di EHR sugli eventi Connetti e Disconnetti per abilitare il controllo automatico e la conservazione dei record.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="f5bfb-110">Integrare i flussi di lavoro clinici e del paziente esistenti, consentendo loro di usare Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="f5bfb-111">Guarda il video su come gestire le visite virtuali dal portale di EHR.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="f5bfb-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f5bfb-112">Before you begin</span></span>

<span data-ttu-id="f5bfb-113">Per poter integrare il connettore EHR, è necessario assicurarsi di avere i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5bfb-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="f5bfb-114">Accesso da usare all'app Microsoft teams nell' [app Orchard Marketplace di Epic](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="f5bfb-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="f5bfb-115">Abbonamento attivo a Microsoft Cloud per l'assistenza sanitaria o all'abbonamento a Microsoft teams EHR Connector standalone offer (applicato solo durante i test di produzione).</span><span class="sxs-lookup"><span data-stu-id="f5bfb-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="f5bfb-116">Gli utenti devono avere una licenza Microsoft 365 o Office 365 appropriata che include le riunioni di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="f5bfb-117">Microsoft Teams deve essere adottato e usato all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="f5bfb-118">Le organizzazioni devono avere con versione epica il 2018 novembre o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="f5bfb-119">I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="f5bfb-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="f5bfb-120">Saranno inoltre necessarie informazioni dalle persone seguenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="f5bfb-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="f5bfb-121">Amministratore di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5bfb-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="f5bfb-122">Analista di clienti epici</span><span class="sxs-lookup"><span data-stu-id="f5bfb-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="f5bfb-123">Richiedi il tuo specialista tecnico epico per specificare la Guida all'integrazione di telehealth di Epic-Microsoft teams disponibile nell'Epic Marketplace.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="f5bfb-124">Configurazione del connettore</span><span class="sxs-lookup"><span data-stu-id="f5bfb-124">Connector setup</span></span>

<span data-ttu-id="f5bfb-125">La configurazione del connettore richiede che:</span><span class="sxs-lookup"><span data-stu-id="f5bfb-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="f5bfb-126">Avviare il portale di configurazione di EHR Connector</span><span class="sxs-lookup"><span data-stu-id="f5bfb-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="f5bfb-127">Informazioni sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="f5bfb-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="f5bfb-128">Approvare o visualizzare la configurazione</span><span class="sxs-lookup"><span data-stu-id="f5bfb-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="f5bfb-129">Rivedere e completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="f5bfb-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="f5bfb-130">Avviare il portale di configurazione di EHR Connector</span><span class="sxs-lookup"><span data-stu-id="f5bfb-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="f5bfb-131">La configurazione dell'organizzazione sanitaria per avviare le visite virtuali con Microsoft teams inizia con l'avvio del portale di configurazione di EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="f5bfb-132">Si configura una singola o più organizzazioni per testare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="f5bfb-133">Configurare l'URL di test e produzione nel portale di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="f5bfb-134">Testare l'integrazione dall'ambiente di test epico prima di passare alla produzione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="f5bfb-135">URL di configurazione del connettore EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f5bfb-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="f5bfb-136">L'amministratore di Microsoft 365 e l'analista di clienti epici dell'organizzazione devono completare i passaggi di informazioni e integrazione nel portale di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="f5bfb-137">Per i passaggi di configurazione epici, contattare la risorsa specialistica tecnica epica assegnata all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="f5bfb-138">Informazioni sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="f5bfb-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="f5bfb-139">Questo passaggio deve essere completato dall'amministratore di **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="f5bfb-140">L'amministratore di Microsoft 365 deve avviare il portale di configurazione del connettore ed eseguire l'accesso con le credenziali Microsoft per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="f5bfb-141">Per completare questo passaggio, l'amministratore di Microsoft 365 deve ricevere un URL di base per l'interoperabilità rapida (FHIR) valido presso il proprio specialista tecnico epico e il nome utente dell'analista di clienti epici che approverà la configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="f5bfb-142">L'amministratore di Microsoft 365 deve avviare la pagina di configurazione del connettore ed eseguire l'accesso con le credenziali Microsoft per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="f5bfb-143">L'URL di base di FHIR è un indirizzo statico corrispondente all'endpoint dell'API FHIR del server.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="f5bfb-144">Un URL di esempio è `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` .</span><span class="sxs-lookup"><span data-stu-id="f5bfb-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="f5bfb-145">Il nome dell'approvatore della configurazione è il nome dell'analista di clienti Epic che sarà responsabile dell'approvazione della configurazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="f5bfb-146">L'analista di clienti epici è una persona dell'organizzazione con accesso SignIn a Epic.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-146">The Epic customer analyst is a person in your organization with signin access to Epic.</span></span>

  ![Il nome dell'approvatore della configurazione viene selezionato da un elenco nel connettore EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="f5bfb-148">Approvare o visualizzare la configurazione</span><span class="sxs-lookup"><span data-stu-id="f5bfb-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="f5bfb-149">L'analista di clienti epici per l'organizzazione sanitaria che è stato aggiunto come approvatore deve ora usare lo stesso URL del connettore EHR del passaggio precedente per accedere con le credenziali di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="f5bfb-150">Dopo aver eseguito correttamente la convalida, l'approvatore verrà invitato a eseguire l'accesso usando le proprie credenziali epiche per convalidare l'organizzazione epica.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="f5bfb-151">L'amministratore di Microsoft 365 e l'analista di clienti epici dell'organizzazione possono essere la stessa persona.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="f5bfb-152">In questo caso, Aggiungi il tuo nome utente come responsabile approvazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="f5bfb-153">È comunque necessario accedere a Epic per convalidare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="f5bfb-154">L'accesso Epic viene usato solo per convalidare l'URL di base di FHIR.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="f5bfb-155">Microsoft non archivia le credenziali o accede ai dati di EHR con questo accesso.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Verificare e approvare la configurazione delle credenziali.](../../media/approve-view-configuration.png)

<span data-ttu-id="f5bfb-157">Dopo un accesso epico di successo, l'analista del cliente Epic **deve** approvare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="f5bfb-158">Se la configurazione non è corretta, l'amministratore di Microsoft 365 avrà la possibilità di modificare le configurazioni originali accedendo di nuovo al portale di Microsoft EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Verificare che il connettore EHR sia configurato e che sia possibile modificare la configurazione.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="f5bfb-160">Rivedere e completare la configurazione</span><span class="sxs-lookup"><span data-stu-id="f5bfb-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="f5bfb-161">Quando le informazioni di configurazione sono approvate dall'amministratore Epic, verranno presentati i record di integrazione per l'avvio del paziente e del provider.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="f5bfb-162">Questi record sono necessari per completare la configurazione della visita virtuale in Epic.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="f5bfb-163">Per altre informazioni, vedere la Guida all'integrazione di telehealth di Epic-Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="f5bfb-164">In qualsiasi momento Microsoft 365 o Epic Customer Analyst può accedere al portale di configurazione per visualizzare i record di integrazione e modificare la configurazione dell'organizzazione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Vengono visualizzate le informazioni sull'integrazione.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="f5bfb-166">Il processo di approvazione deve essere completato dall'analista di clienti epici per ogni URL di FHIR configurato dall'amministratore Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Le informazioni di configurazione sono approvate.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="f5bfb-168">Avviare visite virtuali di Teams</span><span class="sxs-lookup"><span data-stu-id="f5bfb-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="f5bfb-169">Dopo aver completato i passaggi del connettore EHR e la configurazione Epic, l'organizzazione è pronta per supportare le visite video con Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="f5bfb-170">Prerequisiti per la visita virtuale</span><span class="sxs-lookup"><span data-stu-id="f5bfb-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="f5bfb-171">I sistemi devono soddisfare tutti i [prerequisiti del software e del browser](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="f5bfb-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="f5bfb-172">L'organizzazione sanitaria deve aver completato la configurazione tra l'organizzazione Epic e l'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="f5bfb-173">Esperienza del provider</span><span class="sxs-lookup"><span data-stu-id="f5bfb-173">Provider experience</span></span>

<span data-ttu-id="f5bfb-174">I provider di servizi sanitari dell'organizzazione possono partecipare anche alle visite virtuali con Microsoft teams dalle loro applicazioni di provider epiche (iperspazio, Haiku, canto).</span><span class="sxs-lookup"><span data-stu-id="f5bfb-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="f5bfb-175">Il pulsante **inizia visita virtuale** è incorporato nel flusso del provider.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="f5bfb-176">Caratteristiche principali dell'esperienza del provider:</span><span class="sxs-lookup"><span data-stu-id="f5bfb-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="f5bfb-177">I provider possono partecipare a visite virtuali usando i browser supportati o l'applicazione Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="f5bfb-178">I provider devono eseguire l'accesso una tantum con il proprio account Microsoft 365 quando si partecipa a una visita virtuale per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="f5bfb-179">Dopo l'accesso una tantum, il provider verrà portato direttamente all'appuntamento virtuale in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="f5bfb-180">Il provider deve essere connesso a Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="f5bfb-181">Il provider può vedere gli aggiornamenti in tempo reale dei partecipanti connettersi e disconnettersi per un appuntamento specifico.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="f5bfb-182">Il provider può vedere quando il paziente è connesso a una visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Esperienza di provider di una visita virtuale con il paziente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="f5bfb-184">Esperienza paziente</span><span class="sxs-lookup"><span data-stu-id="f5bfb-184">Patient experience</span></span>

<span data-ttu-id="f5bfb-185">Il connettore supporta i pazienti che partecipano a visite virtuali tramite il grafico Web e il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="f5bfb-186">Al momento dell'appuntamento, i pazienti possono iniziare una visita virtuale dal grafico con il pulsante **inizia visita virtuale** .</span><span class="sxs-lookup"><span data-stu-id="f5bfb-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="f5bfb-187">Caratteristiche principali dell'esperienza paziente:</span><span class="sxs-lookup"><span data-stu-id="f5bfb-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="f5bfb-188">I pazienti possono partecipare a visite virtuali da Web browser moderni su desktop e dispositivi mobili senza installazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="f5bfb-189">I pazienti possono partecipare a visite virtuali con un solo clic e non è necessario alcun altro account o accesso.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="f5bfb-190">I pazienti non sono tenuti a creare un account Microsoft o a eseguire l'accesso per avviare una visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="f5bfb-191">I pazienti verranno collocati in una sala d'attesa fino a quando il provider di servizi sanitari non si unisce all'appuntamento e li ammette alla visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="f5bfb-192">Il test del video e del microfono è disponibile nella sala di attesa prima di partecipare alla visita virtuale.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Esperienza paziente della visita virtuale](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="f5bfb-194">Epic, grafico, Haiku e canto sono marchi registrati di Epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="f5bfb-195">Privacy e posizione dei dati</span><span class="sxs-lookup"><span data-stu-id="f5bfb-195">Privacy and location of data</span></span>

<span data-ttu-id="f5bfb-196">L'integrazione dei team nei sistemi EHR ottimizza la quantità di dati che vengono usati e archiviati durante l'integrazione e i flussi di visite virtuali.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="f5bfb-197">La soluzione segue i principi e le linee guida generali per la privacy e la gestione dei dati di teams descritti in privacy teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="f5bfb-198">Il connettore Microsoft teams EHR non archivia né trasferisce i dati personali identificabili o i record sanitari di pazienti o fornitori di servizi sanitari dal sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="f5bfb-199">Gli unici dati archiviati dal connettore EHR sono l'ID univoco dell'utente di EHR, usato durante la configurazione della riunione di teams.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="f5bfb-200">L'ID univoco dell'utente di EHR è archiviato in una delle tre aree geografiche descritte in [cui sono archiviati i dati del cliente Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span><span class="sxs-lookup"><span data-stu-id="f5bfb-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="f5bfb-201">Tutte le chat, le registrazioni e altri dati immessi in teams dai partecipanti alla riunione vengono archiviati in base ai criteri di archiviazione esistenti.</span><span class="sxs-lookup"><span data-stu-id="f5bfb-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="f5bfb-202">Per ulteriori informazioni sulla posizione dei dati in Microsoft teams, visitare le [posizioni dei dati in teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f5bfb-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
