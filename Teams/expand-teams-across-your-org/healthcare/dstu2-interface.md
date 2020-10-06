---
title: Interfaccia DSTU2 dell'app pazienti e integrazione di EHR
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informazioni sulla specifica dell'interfaccia DSTU2 in teams, inclusa la configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2fa5575d6d7a4cbdffec6c3396004c38e743720a
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361456"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="1d89e-103">Specifica dell'interfaccia DSTU2</span><span class="sxs-lookup"><span data-stu-id="1d89e-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d89e-104">**Efficace il 15 ottobre 2020, l'app pazienti sarà deprecata e gli utenti non potranno più installarli dall'app store teams. Ti invitiamo a iniziare a usare l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams Today.**</span><span class="sxs-lookup"><span data-stu-id="1d89e-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="1d89e-105">I dati dell'app patients sono archiviati nella cassetta postale del gruppo del gruppo Office 365 che appoggia il team.</span><span class="sxs-lookup"><span data-stu-id="1d89e-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="1d89e-106">Quando l'app patients viene ritirata, tutti i dati associati verranno mantenuti in questo gruppo, ma non sarà più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1d89e-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="1d89e-107">Gli utenti correnti possono ricreare gli elenchi usando l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="1d89e-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="1d89e-108">L' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) è preinstallata per tutti gli utenti di teams ed è disponibile come scheda in ogni team e canale.</span><span class="sxs-lookup"><span data-stu-id="1d89e-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="1d89e-109">Con gli elenchi, i team di assistenza possono creare elenchi di pazienti usando il modello di pazienti incorporati, da zero o importando dati in Excel.</span><span class="sxs-lookup"><span data-stu-id="1d89e-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="1d89e-110">Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="1d89e-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="1d89e-111">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="1d89e-112">Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="1d89e-113">Paziente</span><span class="sxs-lookup"><span data-stu-id="1d89e-113">Patient</span></span>](#patient)
- [<span data-ttu-id="1d89e-114">Osservazione</span><span class="sxs-lookup"><span data-stu-id="1d89e-114">Observation</span></span>](#observation)
- [<span data-ttu-id="1d89e-115">Condizione</span><span class="sxs-lookup"><span data-stu-id="1d89e-115">Condition</span></span>](#condition)
- [<span data-ttu-id="1d89e-116">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="1d89e-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="1d89e-117">Intolleranza alle allergie</span><span class="sxs-lookup"><span data-stu-id="1d89e-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="1d89e-118">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="1d89e-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="1d89e-119">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="1d89e-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="1d89e-120">Posizione</span><span class="sxs-lookup"><span data-stu-id="1d89e-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="1d89e-121">La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto.</span><span class="sxs-lookup"><span data-stu-id="1d89e-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="1d89e-122">Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.</span><span class="sxs-lookup"><span data-stu-id="1d89e-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="1d89e-123">Le query dell'app Microsoft teams patients per più di una risorsa pubblicano un bundle (BATCH) di richieste per l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="1d89e-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="1d89e-124">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="1d89e-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="1d89e-125">Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="1d89e-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="1d89e-126">Tutte le risorse FHIR seguenti devono essere accessibili tramite riferimento diretto alle risorse.</span><span class="sxs-lookup"><span data-stu-id="1d89e-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="1d89e-127">Set di campi obbligatori minimi di conformità</span><span class="sxs-lookup"><span data-stu-id="1d89e-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="1d89e-128">Il server FHIR deve implementare l'istruzione di conformità per avere un riepilogo effettivo delle proprie funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1d89e-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="1d89e-129">Prevediamo i parametri seguenti in un server di FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="1d89e-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="1d89e-130">RESTO</span><span class="sxs-lookup"><span data-stu-id="1d89e-130">REST</span></span>
   1. <span data-ttu-id="1d89e-131">Modalità</span><span class="sxs-lookup"><span data-stu-id="1d89e-131">Mode</span></span>
   2. <span data-ttu-id="1d89e-132">Interazione</span><span class="sxs-lookup"><span data-stu-id="1d89e-132">Interaction</span></span>
   3. <span data-ttu-id="1d89e-133">Risorsa: digitare</span><span class="sxs-lookup"><span data-stu-id="1d89e-133">Resource: Type</span></span>
   4. <span data-ttu-id="1d89e-134">Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="1d89e-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="1d89e-135">FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot mentre sosteniamo più versioni).</span><span class="sxs-lookup"><span data-stu-id="1d89e-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="1d89e-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="1d89e-137">Paziente</span><span class="sxs-lookup"><span data-stu-id="1d89e-137">Patient</span></span>

<span data-ttu-id="1d89e-138">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi del [profilo del paziente Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="1d89e-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="1d89e-139">Name. Family</span><span class="sxs-lookup"><span data-stu-id="1d89e-139">Name.Family</span></span>
2. <span data-ttu-id="1d89e-140">Name. given</span><span class="sxs-lookup"><span data-stu-id="1d89e-140">Name.Given</span></span>
3. <span data-ttu-id="1d89e-141">Genere</span><span class="sxs-lookup"><span data-stu-id="1d89e-141">Gender</span></span>
4. <span data-ttu-id="1d89e-142">Nascita</span><span class="sxs-lookup"><span data-stu-id="1d89e-142">BirthDate</span></span>
5. <span data-ttu-id="1d89e-143">MRN (identificatore)</span><span class="sxs-lookup"><span data-stu-id="1d89e-143">MRN (Identifier)</span></span>

<span data-ttu-id="1d89e-144">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="1d89e-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="1d89e-145">Name.Use</span></span>
2. <span data-ttu-id="1d89e-146">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="1d89e-146">Name.Prefix</span></span>
3. <span data-ttu-id="1d89e-147">CareProvider (questo riferimento sulla risorsa paziente deve includere i campi visualizzati nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="1d89e-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="1d89e-148">Richiesta: ottenere <Fhir-server>/patient/<ID paziente></span><span class="sxs-lookup"><span data-stu-id="1d89e-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="1d89e-149">Response: {"resourceType": "patient", "ID": "<patient-ID>",.</span><span class="sxs-lookup"><span data-stu-id="1d89e-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="1d89e-150">.</span><span class="sxs-lookup"><span data-stu-id="1d89e-150">.</span></span>
      <span data-ttu-id="1d89e-151">.</span><span class="sxs-lookup"><span data-stu-id="1d89e-151">.</span></span>
      <span data-ttu-id="1d89e-152">"nome": [{"use": "Official", "prefix": ["Mr"], "Family": ["Chau"], "given": ["Hugh"]}], "Identifier": [{"use": "ufficiale", "tipo": {"codifica": [{"System": " https://hl7.org/fhir/v2/0203 " "," codice ":" Mr "}]}," valore ":" 1234567 "}]," sesso ":" maschio "," DataNascita ":" 1957-06-05 "," careProvider ": [{" display ":" Jane Doe "}],}</span><span class="sxs-lookup"><span data-stu-id="1d89e-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="1d89e-153">Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="1d89e-154">ID</span><span class="sxs-lookup"><span data-stu-id="1d89e-154">id</span></span>
2. <span data-ttu-id="1d89e-155">Family: Contains = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore).</span><span class="sxs-lookup"><span data-stu-id="1d89e-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="1d89e-156">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="1d89e-156">given=\<substring></span></span>
4. <span data-ttu-id="1d89e-157">nome =\<substring></span><span class="sxs-lookup"><span data-stu-id="1d89e-157">name=\<substring></span></span>
5. <span data-ttu-id="1d89e-158">nascita = (corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="1d89e-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="1d89e-159">\_conteggio (numero massimo di risultati che devono essere restituiti)</span><span class="sxs-lookup"><span data-stu-id="1d89e-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="1d89e-160">La risposta deve contenere il numero totale di record restituiti come risultato della ricerca e il \_ conteggio verrà usato da PatientsApp per limitare la quantità di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="1d89e-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="1d89e-161">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="1d89e-161">identifier=\<mrn></span></span>

<span data-ttu-id="1d89e-162">L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="1d89e-163">ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.</span><span class="sxs-lookup"><span data-stu-id="1d89e-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="1d89e-164">MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe.</span><span class="sxs-lookup"><span data-stu-id="1d89e-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="1d89e-165">Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR</span><span class="sxs-lookup"><span data-stu-id="1d89e-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="1d89e-166">Nome</span><span class="sxs-lookup"><span data-stu-id="1d89e-166">Name</span></span>
- <span data-ttu-id="1d89e-167">Nascita</span><span class="sxs-lookup"><span data-stu-id="1d89e-167">Birthdate</span></span>

<span data-ttu-id="1d89e-168">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d89e-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="1d89e-169">Request: POST <Fhir-server>/patient/_search request body: given = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="1d89e-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="1d89e-170">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>",.</span><span class="sxs-lookup"><span data-stu-id="1d89e-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="1d89e-171">.</span><span class="sxs-lookup"><span data-stu-id="1d89e-171">.</span></span>
      <span data-ttu-id="1d89e-172">.</span><span class="sxs-lookup"><span data-stu-id="1d89e-172">.</span></span>
      <span data-ttu-id="1d89e-173">"voce": [{"risorsa": {"resourceType": "paziente", "ID": "<ID paziente>", "nome": [{"testo": "Hugh Chau", "famiglia": ["Chau"], "given": ["Hugh"]}], "gender": "maschio", "database": "1957-06-05"}, "ricerca": {"modalità": "corrispondenza"}}]</span><span class="sxs-lookup"><span data-stu-id="1d89e-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="1d89e-174">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="1d89e-175">Osservazione</span><span class="sxs-lookup"><span data-stu-id="1d89e-175">Observation</span></span>

<span data-ttu-id="1d89e-176">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut Vital Signs:</span><span class="sxs-lookup"><span data-stu-id="1d89e-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="1d89e-177">Effettivo (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="1d89e-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="1d89e-178">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="1d89e-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="1d89e-179">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="1d89e-179">ValueQuantity.Value</span></span>

<span data-ttu-id="1d89e-180">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="1d89e-181">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="1d89e-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="1d89e-182">ValueQuantity. unit</span><span class="sxs-lookup"><span data-stu-id="1d89e-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="1d89e-183">Se si usano le osservazioni dei componenti, la stessa logica viene applicata per ogni osservazione del componente.</span><span class="sxs-lookup"><span data-stu-id="1d89e-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="1d89e-184">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1d89e-185">paziente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="1d89e-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="1d89e-186">Ordina: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="1d89e-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="1d89e-187">L'obiettivo è quello di riuscire a recuperare gli ultimi segni vitali per un paziente, [VitalSigns. DSTU....] (osservazione?).</span><span class="sxs-lookup"><span data-stu-id="1d89e-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="1d89e-188">Richiesta: ottenere <Fhir-server>/Observation? patient =<patient-ID>&_sort:d ESC = data&Category = Vital-Signs</span><span class="sxs-lookup"><span data-stu-id="1d89e-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="1d89e-189">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "digitare": "searchset", "Total": 20, "entry": [{"risorsa": {"resourceType": "osservazione", "ID": "<Resource-ID>", "Category": {"coding": [{code ":" Vital-Signs "}],}," code ": {" coding ": [{" System ":" http://loinc.org "," code ":" 39156-5 "," display ":" BMI "}],}," effectiveDateTime ":" 2009-12-01 "," valueQuantity ": {" valore ": 34,4," unità ":" kg/m2 "," sistema ":" http://unitsofmeasure.org "," codice ":" kg/m2 "}},},.</span><span class="sxs-lookup"><span data-stu-id="1d89e-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="1d89e-190">.</span><span class="sxs-lookup"><span data-stu-id="1d89e-190">.</span></span>
        <span data-ttu-id="1d89e-191">.</span><span class="sxs-lookup"><span data-stu-id="1d89e-191">.</span></span>
      <span data-ttu-id="1d89e-192">] }</span><span class="sxs-lookup"><span data-stu-id="1d89e-192">] }</span></span>

* * *

<span data-ttu-id="1d89e-193">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="1d89e-194">Condizione</span><span class="sxs-lookup"><span data-stu-id="1d89e-194">Condition</span></span>

<span data-ttu-id="1d89e-195">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="1d89e-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="1d89e-196">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="1d89e-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="1d89e-197">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="1d89e-198">Data registrata</span><span class="sxs-lookup"><span data-stu-id="1d89e-198">Date Recorded</span></span>
2. <span data-ttu-id="1d89e-199">Gravità</span><span class="sxs-lookup"><span data-stu-id="1d89e-199">Severity</span></span>

<span data-ttu-id="1d89e-200">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1d89e-201">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d89e-201">patient=\<patient id></span></span>
2. <span data-ttu-id="1d89e-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="1d89e-202">_count=\<max results></span></span>

<span data-ttu-id="1d89e-203">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="1d89e-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1d89e-204">Richiesta: ottenere <Fhir-server>/Condition? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="1d89e-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="1d89e-205">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"Resource", "resourceType", "Condition", "ID", "<Resource-ID>", "code": {"coding": [{"System": " http://snomed.info/sct ", "code": "386033004", "display": "neuropatia (danni nervosi)"}]}, "dateRecorded": "2018-09-17", "Severity": {"coding": [{"System": " http://snomed.info/sct ", "code": "24484000", "display": "grave"}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="1d89e-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="1d89e-206">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="1d89e-207">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="1d89e-207">Encounter</span></span>

<span data-ttu-id="1d89e-208">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo degli incontri di base degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="1d89e-209">Stato</span><span class="sxs-lookup"><span data-stu-id="1d89e-209">Status</span></span>
2. <span data-ttu-id="1d89e-210">Digitare [0]. Codifica [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="1d89e-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="1d89e-211">Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="1d89e-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="1d89e-212">Periodo. inizio</span><span class="sxs-lookup"><span data-stu-id="1d89e-212">Period.Start</span></span>
2. <span data-ttu-id="1d89e-213">Posizione [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="1d89e-213">Location[0].Location.Display</span></span>

<span data-ttu-id="1d89e-214">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1d89e-215">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d89e-215">patient=\<patient id></span></span>
2. <span data-ttu-id="1d89e-216">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="1d89e-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="1d89e-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="1d89e-217">_count=\<max results></span></span>

<span data-ttu-id="1d89e-218">L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="1d89e-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="1d89e-219">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="1d89e-219">Each encounter references a location resource.</span></span> <span data-ttu-id="1d89e-220">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="1d89e-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="1d89e-221">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d89e-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="1d89e-222">Richiesta: ottenere <Fhir-server>/Encounter? patient =<ID paziente>&_sort:d ESC = data&_count = 1</span><span class="sxs-lookup"><span data-stu-id="1d89e-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="1d89e-223">Risposta: {"resourceType": "bundle", "Type": "searchset", "Total": 1, "entry": [{"" Resource ": {" resourceType ":" Encounter "," ID ":" <Resource-ID> "," identificatore ": [{" use ":" Official "," value ":" <id> "}]," stato ":" arrivato "," tipo ": [{" codifica ": [{" visualizzazione ":" appuntamento "}],}]," paziente ": {" riferimento ":" paziente/<paziente-id> "}," punto ": {" Start ":" 09/17/2018 1:00:00 PM "}," location ": [{" location ": {" display ":" Clinic-ENT "},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="1d89e-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="1d89e-224">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="1d89e-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="1d89e-225">AllergyIntolerance</span></span>

<span data-ttu-id="1d89e-226">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="1d89e-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="1d89e-227">Code. Text</span><span class="sxs-lookup"><span data-stu-id="1d89e-227">Code.Text</span></span>
2. <span data-ttu-id="1d89e-228">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="1d89e-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="1d89e-229">Stato</span><span class="sxs-lookup"><span data-stu-id="1d89e-229">Status</span></span>

<span data-ttu-id="1d89e-230">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="1d89e-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="1d89e-231">RecordedDate</span></span>
2. <span data-ttu-id="1d89e-232">Nota. testo</span><span class="sxs-lookup"><span data-stu-id="1d89e-232">Note.Text</span></span>
3. <span data-ttu-id="1d89e-233">Reazione [..]. Sostanza. testo</span><span class="sxs-lookup"><span data-stu-id="1d89e-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="1d89e-234">Reazione [..]. Manifestazione [..]. Testo</span><span class="sxs-lookup"><span data-stu-id="1d89e-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="1d89e-235">Text. div</span><span class="sxs-lookup"><span data-stu-id="1d89e-235">Text.Div</span></span>

<span data-ttu-id="1d89e-236">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1d89e-237">Paziente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="1d89e-237">Patient =  \<patient id></span></span>

<span data-ttu-id="1d89e-238">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="1d89e-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1d89e-239">Richiesta: ottenere <Fhir-server>/AllergyIntolerance? patient =<ID paziente></span><span class="sxs-lookup"><span data-stu-id="1d89e-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="1d89e-240">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "recordedDate": "2018-09-17T07:00:00.000 Z", "sostanza": {"testo": "anacardi Nuts"}, "stato": "confermato", "reazione": [{"sostanza": {"testo": "Estratto prodotto iniettabile di anacardio dado allergenico"}, "manifestazione": [{"testo": "reazione anafilattica"}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="1d89e-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="1d89e-241">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="1d89e-242">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="1d89e-242">Medication Order</span></span>

<span data-ttu-id="1d89e-243">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="1d89e-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="1d89e-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="1d89e-244">DateWritten</span></span>
2. <span data-ttu-id="1d89e-245">Prescriber. display</span><span class="sxs-lookup"><span data-stu-id="1d89e-245">Prescriber.Display</span></span>
3. <span data-ttu-id="1d89e-246">Medicine. display (se di riferimento)</span><span class="sxs-lookup"><span data-stu-id="1d89e-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="1d89e-247">Medicine. Text (se Concept)</span><span class="sxs-lookup"><span data-stu-id="1d89e-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="1d89e-248">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="1d89e-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="1d89e-249">DateEnded</span></span>
2. <span data-ttu-id="1d89e-250">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="1d89e-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="1d89e-251">Text. div</span><span class="sxs-lookup"><span data-stu-id="1d89e-251">Text.Div</span></span>

<span data-ttu-id="1d89e-252">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1d89e-253">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d89e-253">patient=\<patient id></span></span>
2. <span data-ttu-id="1d89e-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="1d89e-254">_count=\<max results></span></span>

<span data-ttu-id="1d89e-255">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="1d89e-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1d89e-256">Richiesta: ottenere <Fhir-server>/MedicationOrder? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="1d89e-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="1d89e-257">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medicationCodeableConcept": {"Text": "Lisinopril 20 MG Oral Tablet"}, "Prescriber": {"display": "Jane Doe"}, "dosageInstruction": [{"testo": "1 Daily"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="1d89e-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="1d89e-258">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="1d89e-259">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="1d89e-259">Coverage</span></span>

<span data-ttu-id="1d89e-260">Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="1d89e-261">Pagante</span><span class="sxs-lookup"><span data-stu-id="1d89e-261">Payor</span></span>

<span data-ttu-id="1d89e-262">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d89e-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1d89e-263">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="1d89e-263">patient=\<patient id></span></span>

<span data-ttu-id="1d89e-264">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="1d89e-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1d89e-265">Richiesta: ottenere <Fhir-server>/coverage? patient =<ID paziente></span><span class="sxs-lookup"><span data-stu-id="1d89e-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="1d89e-266">Response: {"resourceType": "bundle", "digitare": "searchset", "Total": 1, "entry": [{"risorsa": {"resourceType": "coverage", "ID": "<Resource-ID>", "piano": "nessuna assicurazione primaria", "sottoscrittore": {"riferimento": "paziente/<-ID>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="1d89e-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="1d89e-267">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="1d89e-268">Posizione</span><span class="sxs-lookup"><span data-stu-id="1d89e-268">Location</span></span>

<span data-ttu-id="1d89e-269">Questa risorsa viene usata solo come riferimento nella risorsa [Encounter](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="1d89e-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="1d89e-270">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="1d89e-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
