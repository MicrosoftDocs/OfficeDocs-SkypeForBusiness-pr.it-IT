---
title: Iniziare a usare team per organizzazioni sanitarie
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Iniziare a usare team per organizzazioni sanitarie
ms.openlocfilehash: e8c41249da52ce9a5e19471954de6d71db3df1b3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569233"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="270fd-103">Iniziare a usare team per organizzazioni sanitarie</span><span class="sxs-lookup"><span data-stu-id="270fd-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="270fd-104">Microsoft teams offre una serie di funzionalità utili per ospedali e altre organizzazioni sanitarie.</span><span class="sxs-lookup"><span data-stu-id="270fd-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="270fd-105">Le caratteristiche dei team sono in fase di sviluppo per aiutare gli ospedali:</span><span class="sxs-lookup"><span data-stu-id="270fd-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="270fd-106">Coordinamento e collaborazione per l'assistenza</span><span class="sxs-lookup"><span data-stu-id="270fd-106">Care Coordination and collaboration</span></span>
- <span data-ttu-id="270fd-107">Messaggistica sicura</span><span class="sxs-lookup"><span data-stu-id="270fd-107">Secure Messaging</span></span>
- <span data-ttu-id="270fd-108">Telemedicina</span><span class="sxs-lookup"><span data-stu-id="270fd-108">Telehealth</span></span>
- <span data-ttu-id="270fd-109">Integrazione di EHR (Electronic Healthcare record)</span><span class="sxs-lookup"><span data-stu-id="270fd-109">Electronic Healthcare Record (EHR) integration</span></span> 
- <span data-ttu-id="270fd-110">Integrazione di i FIRSTLINE Worker System</span><span class="sxs-lookup"><span data-stu-id="270fd-110">Firstline Worker system integration</span></span> 

<span data-ttu-id="270fd-111">Il contenuto di questa sezione si basa sulle funzionalità fondamentali dei team, ad esempio riunioni, chiamate e messaggistica, e presuppone che siano già stati distribuiti team nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="270fd-111">The content in this section builds on the foundational capabilities of Teams, such as meetings, calling, and messaging, and assumes that you've already deployed Teams in your organization.</span></span> <span data-ttu-id="270fd-112">Se non sono stati ancora distribuiti team, iniziare a leggere [come implementare Microsoft teams](../../How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="270fd-112">If you haven't yet rolled out Teams, start by reading [How to roll out Microsoft Teams](../../How-to-roll-out-teams.md).</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="270fd-113">Coordinamento delle cure-app Microsoft teams patients</span><span class="sxs-lookup"><span data-stu-id="270fd-113">Care Coordination - Microsoft Teams Patients app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="270fd-114">Microsoft Teams ha ora una soluzione di coordinamento delle cure specifiche per le organizzazioni sanitarie per aiutarli a fornire la migliore assistenza per i pazienti.</span><span class="sxs-lookup"><span data-stu-id="270fd-114">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them provide the best patient care.</span></span> <span data-ttu-id="270fd-115">Il punto cruciale della soluzione di coordinamento delle cure, l'app Microsoft teams patients, è un'app per la scheda First party che si integra con i sistemi di EHR (Electronic Health Record) che usano un'interfaccia[FHIR](https://www.hl7.org/fhir/)(Fast Healthcare Resources) per fornire preziose funzionalità informazioni mediche in Microsoft Teams nel contesto per consentire la collaborazione e la comunicazione clinica.</span><span class="sxs-lookup"><span data-stu-id="270fd-115">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams in context to enable clinical collaboration and communication.</span></span>  

<span data-ttu-id="270fd-116">La soluzione di coordinamento delle cure può interfacciarsi con fornitori di software indipendenti leader (ISV) che possono connettere l'app patients ai sistemi EHR usando standard di dati sanitari esistenti come HL7v2 e FHIR.</span><span class="sxs-lookup"><span data-stu-id="270fd-116">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="270fd-117">Partner Microsoft con i seguenti leader del settore per stabilire l'integrazione elettronica dei record sanitari con i team:</span><span class="sxs-lookup"><span data-stu-id="270fd-117">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="270fd-118">Datica (tramite l'offerta [CMI](https://datica.com/compliant-managed-integration/) )</span><span class="sxs-lookup"><span data-stu-id="270fd-118">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="270fd-119">Infor Cloverleaf (tramite il [Bridge infor FHIR](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="270fd-119">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="270fd-120">Redox (tramite il [Server R ^ FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="270fd-120">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="270fd-121">Dapasoft (tramite [corolar in FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="270fd-121">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="270fd-122">Un partner di integrazione e interoperabilità di EHR che prova ad implementare Microsoft teams per un'organizzazione di provider di servizi sanitari deve garantire all'app patients una connessione sicura e autenticata con i sistemi di EHR dell'organizzazione del provider di servizi sanitari.</span><span class="sxs-lookup"><span data-stu-id="270fd-122">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="270fd-123">In questo modo, il flusso unidirezionale (di sola lettura) dei record paziente rilevanti viene attivato nell'app patients.</span><span class="sxs-lookup"><span data-stu-id="270fd-123">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="270fd-124">L'app patients comprende il formato FHIR, in modo che il partner sia anche responsabile della trasformazione dei dati aggregati da vari altri formati come HL7v2 e così via in FHIR DSTU2 o STU3.</span><span class="sxs-lookup"><span data-stu-id="270fd-124">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![Illustrazione che evidenzia il coordinamento e la collaborazione all'assistenza](../../media/ehr-1.png)

<br>

<span data-ttu-id="270fd-126">L'app patients si integra con i sistemi Electronic Health Records (EHR) e consente ai provider di assistenza di comunicare informazioni sulle cure dei pazienti in tempo reale all'interno della piattaforma sicura di teams.</span><span class="sxs-lookup"><span data-stu-id="270fd-126">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams’ secure platform.</span></span> <span data-ttu-id="270fd-127">L'app pazienti è il primo investimento importante nell'area di coordinamento delle cure che mira ad affrontare le sfide seguenti:</span><span class="sxs-lookup"><span data-stu-id="270fd-127">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="270fd-128">Scarsa efficienza nelle consegne e comunicazioni critiche attraverso l'esperienza del paziente</span><span class="sxs-lookup"><span data-stu-id="270fd-128">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="270fd-129">Informazioni silos che creano oneri amministrativi</span><span class="sxs-lookup"><span data-stu-id="270fd-129">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="270fd-130">Insoddisfazione tra i clinici con strumenti di collaborazione complessi e frammentati</span><span class="sxs-lookup"><span data-stu-id="270fd-130">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="270fd-131">Coordinamento delle cure in-persona inefficiente che può bruciare troppo tempo clinico molto costoso</span><span class="sxs-lookup"><span data-stu-id="270fd-131">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="270fd-132">Microsoft teams consente a medici, clinici, infermieri e altri membri del personale di collaborare in modo efficiente:</span><span class="sxs-lookup"><span data-stu-id="270fd-132">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="270fd-133">Partecipare a un singolo team virtualizzato che lavora e collabora ai documenti di Office</span><span class="sxs-lookup"><span data-stu-id="270fd-133">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="270fd-134">Avere conversazioni persistenti su pazienti diversi che richiedono attenzione</span><span class="sxs-lookup"><span data-stu-id="270fd-134">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="270fd-135">Usare i canali con le schede per strutturare il proprio lavoro, con ulteriori informazioni sulle schede a cui possono aggiungere le origini dati</span><span class="sxs-lookup"><span data-stu-id="270fd-135">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="270fd-136">Uso delle riunioni di canale con la potenza dei team audio, video, condivisione dello schermo, registrazione e funzionalità di trascrizione per gestire le riunioni quotidiane</span><span class="sxs-lookup"><span data-stu-id="270fd-136">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="270fd-137">Usando l'app pazienti per curare un elenco di pazienti ad alto rischio che devono essere controllati e i loro dettagli più recenti dal sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="270fd-137">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="270fd-138">L'app patients stessa aggiunge le caratteristiche seguenti a Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="270fd-138">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="270fd-139">Possibilità di creare più elenchi di pazienti all'interno di un singolo canale.</span><span class="sxs-lookup"><span data-stu-id="270fd-139">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="270fd-140">Possibilità di visualizzare e ordinare le informazioni visualizzate sui pazienti tramite colonne configurabili.</span><span class="sxs-lookup"><span data-stu-id="270fd-140">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="270fd-141">Possibilità di eseguire il provisioning automatico dell'app tramite un modello di team.</span><span class="sxs-lookup"><span data-stu-id="270fd-141">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="270fd-142">Disponibile nell'app teams per iOS e Android per i primi operatori sanitari per dispositivi mobili, oltre a Microsoft teams Web e desktop client.</span><span class="sxs-lookup"><span data-stu-id="270fd-142">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="270fd-143">Supporto per le versioni di FHIR DSTU2 e STU3 tramite l'analisi dell'istruzione di conformità.</span><span class="sxs-lookup"><span data-stu-id="270fd-143">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="270fd-144">Registri di controllo per tutte le azioni di visualizzazione e ricerca nell'interfaccia utente per salvaguardare le linee guida di PHI per HIPAA.</span><span class="sxs-lookup"><span data-stu-id="270fd-144">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="270fd-145">L'app pazienti si basa sulla piattaforma di estensibilità teams e sfrutta il framework delle schede per visualizzare il contenuto del paziente avanzato all'interno di un canale.</span><span class="sxs-lookup"><span data-stu-id="270fd-145">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="270fd-146">Per altre informazioni sulle app di altri team e sulla piattaforma stessa, vedere [app per Microsoft teams](/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="270fd-146">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="270fd-147">L'app patients è in anteprima privata e l'interfaccia FHIR è in versione beta.</span><span class="sxs-lookup"><span data-stu-id="270fd-147">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="270fd-148">Le versioni rilasciate non dovrebbero essere compatibili con la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="270fd-148">Released versions are not expected to be backward compatible.</span></span>

![Screenshot dell'app pazienti su dispositivi desktop e mobili](../../media/ehr-2.png)

<span data-ttu-id="270fd-150">Vedere [integrazione di record sanitari elettronici in Microsoft teams](patients-app.md) per dettagli sull'implementazione.</span><span class="sxs-lookup"><span data-stu-id="270fd-150">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="templates"></a><span data-ttu-id="270fd-151">Modelli</span><span class="sxs-lookup"><span data-stu-id="270fd-151">Templates</span></span>

<span data-ttu-id="270fd-152">I nuovi modelli per la creazione di team sono stati sviluppati per applicarsi a un ambiente ospedaliero e più presto sono attesi.</span><span class="sxs-lookup"><span data-stu-id="270fd-152">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="270fd-153">In questo modo è più semplice creare team che gli operatori sanitari usano per coordinare le cure per i pazienti in diversi reparti o corsi.</span><span class="sxs-lookup"><span data-stu-id="270fd-153">This makes it easier to create Teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="270fd-154">Vedere [Introduzione ai modelli di team per le organizzazioni sanitarie](healthcare-templates.md).</span><span class="sxs-lookup"><span data-stu-id="270fd-154">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="270fd-155">I team possono essere avviati per i reparti interni, ad esempio cardiologia o per i corsi di assistenza, e altri modelli sono in sviluppo.</span><span class="sxs-lookup"><span data-stu-id="270fd-155">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="270fd-156">Messaggistica sicura</span><span class="sxs-lookup"><span data-stu-id="270fd-156">Secure Messaging</span></span>

<span data-ttu-id="270fd-157">La messaggistica sicura supporta la collaborazione all'interno di team di assistenza, incluse diverse nuove caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="270fd-157">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="270fd-158">Un mittente del messaggio può impostare una priorità speciale per il messaggio, in modo che il destinatario venga notificato ripetutamente fino a quando non legge il messaggio.</span><span class="sxs-lookup"><span data-stu-id="270fd-158">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="270fd-159">Un mittente del messaggio può richiedere una conferma di lettura, in modo che venga notificato quando un messaggio inviato è stato letto dal destinatario del messaggio.</span><span class="sxs-lookup"><span data-stu-id="270fd-159">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>


<span data-ttu-id="270fd-160">Insieme, queste funzionalità permettono una maggiore attenzione ai messaggi urgenti e alla fiducia che il messaggio è stato ricevuto e letto.</span><span class="sxs-lookup"><span data-stu-id="270fd-160">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="270fd-161">I nuovi team di assistenza che usano queste funzionalità possono essere creati per ogni singolo paziente.</span><span class="sxs-lookup"><span data-stu-id="270fd-161">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="270fd-162">Queste caratteristiche sono basate su criteri e possono essere assegnate a singoli o a Team interi.</span><span class="sxs-lookup"><span data-stu-id="270fd-162">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="270fd-163">Per ulteriori informazioni, vedere [Introduzione ai criteri di messaggistica sicura per le organizzazioni sanitarie](messaging-policies-hc.md) .</span><span class="sxs-lookup"><span data-stu-id="270fd-163">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

<span data-ttu-id="270fd-164">Anche correlato alla messaggistica sicura è la possibilità di avere altri tenant federati da organizzazioni sanitarie, consentendo una comunicazione intertenant più ricca.</span><span class="sxs-lookup"><span data-stu-id="270fd-164">Also related to secure messaging is the ability to have other tenants federated by Healthcare organizations, allowing richer inter-tenant communication.</span></span> <span data-ttu-id="270fd-165">vedere [gestire l'accesso esterno (Federazione) in Microsoft teams](../../manage-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="270fd-165">(see [Manage external access (federation) in Microsoft Teams](../../manage-external-access.md)).</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="270fd-166">Integrazione di i FIRSTLINE Worker</span><span class="sxs-lookup"><span data-stu-id="270fd-166">Firstline Worker integration</span></span>

<span data-ttu-id="270fd-167">Microsoft teams si integra con I FIRSTLINE Worker, che può essere usato per coordinare le caratteristiche di personale di spostamento e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="270fd-167">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span>

 <span data-ttu-id="270fd-168">Vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="270fd-168">See the following articles:</span></span>

- [<span data-ttu-id="270fd-169">Spostare i team di Microsoft StaffHub in turni in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="270fd-169">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [<span data-ttu-id="270fd-170">Gestire l'app turni per l'organizzazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="270fd-170">Manage the Shifts app for your organization in Microsoft Teams</span></span>](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
