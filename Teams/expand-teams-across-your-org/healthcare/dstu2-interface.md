---
title: " Interfaccia DSTU2 dell'app pazienti e integrazione di EHR"
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Integrazione dell'app EHR di Microsoft teams patients
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "36182026"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="aed0d-103">Specifica dell'interfaccia DSTU2</span><span class="sxs-lookup"><span data-stu-id="aed0d-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="aed0d-104">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="aed0d-105">Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="aed0d-106">Paziente</span><span class="sxs-lookup"><span data-stu-id="aed0d-106">Patient</span></span>](#patient)
- [<span data-ttu-id="aed0d-107">Osservazione</span><span class="sxs-lookup"><span data-stu-id="aed0d-107">Observation</span></span>](#observation)
- [<span data-ttu-id="aed0d-108">Condizione</span><span class="sxs-lookup"><span data-stu-id="aed0d-108">Condition</span></span>](#condition)
- [<span data-ttu-id="aed0d-109">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="aed0d-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="aed0d-110">Intolleranza alle allergie</span><span class="sxs-lookup"><span data-stu-id="aed0d-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="aed0d-111">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="aed0d-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="aed0d-112">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="aed0d-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="aed0d-113">Posizione</span><span class="sxs-lookup"><span data-stu-id="aed0d-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="aed0d-114">La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto.</span><span class="sxs-lookup"><span data-stu-id="aed0d-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="aed0d-115">Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.</span><span class="sxs-lookup"><span data-stu-id="aed0d-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="aed0d-116">Le query dell'app Microsoft teams patients per più di una risorsa pubblicano un bundle (BATCH) di richieste per l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="aed0d-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="aed0d-117">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="aed0d-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="aed0d-118">Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="aed0d-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="aed0d-119">Tutte le risorse FHIR seguenti devono essere accessibili tramite riferimento diretto alle risorse.</span><span class="sxs-lookup"><span data-stu-id="aed0d-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="aed0d-120">Set di campi obbligatori minimi di conformità</span><span class="sxs-lookup"><span data-stu-id="aed0d-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="aed0d-121">Il server FHIR deve implementare l'istruzione di conformità per avere un riepilogo effettivo delle proprie funzionalità.</span><span class="sxs-lookup"><span data-stu-id="aed0d-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="aed0d-122">Prevediamo i parametri seguenti in un server di FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="aed0d-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="aed0d-123">RESTO</span><span class="sxs-lookup"><span data-stu-id="aed0d-123">REST</span></span>
   1. <span data-ttu-id="aed0d-124">Modalità</span><span class="sxs-lookup"><span data-stu-id="aed0d-124">Mode</span></span>
   2. <span data-ttu-id="aed0d-125">Interazione</span><span class="sxs-lookup"><span data-stu-id="aed0d-125">Interaction</span></span>
   3. <span data-ttu-id="aed0d-126">Risorsa: digitare</span><span class="sxs-lookup"><span data-stu-id="aed0d-126">Resource: Type</span></span>
   4. <span data-ttu-id="aed0d-127">Sicurezza: [estensione per gli URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="aed0d-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="aed0d-128">FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot mentre sosteniamo più versioni).</span><span class="sxs-lookup"><span data-stu-id="aed0d-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="aed0d-129">Per [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="aed0d-130">Paziente</span><span class="sxs-lookup"><span data-stu-id="aed0d-130">Patient</span></span>

<span data-ttu-id="aed0d-131">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi del [profilo del paziente Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="aed0d-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="aed0d-132">Name. Family</span><span class="sxs-lookup"><span data-stu-id="aed0d-132">Name.Family</span></span>
2. <span data-ttu-id="aed0d-133">Name. given</span><span class="sxs-lookup"><span data-stu-id="aed0d-133">Name.Given</span></span>
3. <span data-ttu-id="aed0d-134">Genere</span><span class="sxs-lookup"><span data-stu-id="aed0d-134">Gender</span></span>
4. <span data-ttu-id="aed0d-135">Nascita</span><span class="sxs-lookup"><span data-stu-id="aed0d-135">BirthDate</span></span>
5. <span data-ttu-id="aed0d-136">MRN (identificatore)</span><span class="sxs-lookup"><span data-stu-id="aed0d-136">MRN (Identifier)</span></span>

<span data-ttu-id="aed0d-137">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="aed0d-138">Name. use</span><span class="sxs-lookup"><span data-stu-id="aed0d-138">Name.Use</span></span>
2. <span data-ttu-id="aed0d-139">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="aed0d-139">Name.Prefix</span></span>
3. <span data-ttu-id="aed0d-140">CareProvider (questo riferimento sulla risorsa paziente deve includere i campi visualizzati nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="aed0d-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="aed0d-141">Richiesta: ottenere <Fhir-Server>/patient/<ID paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="aed0d-142">Response: {"resourceType": "patient", "ID": "<patient-ID>",.</span><span class="sxs-lookup"><span data-stu-id="aed0d-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="aed0d-143">.</span><span class="sxs-lookup"><span data-stu-id="aed0d-143"></span></span>
      <span data-ttu-id="aed0d-144">.</span><span class="sxs-lookup"><span data-stu-id="aed0d-144"></span></span>
      <span data-ttu-id="aed0d-145">"nome": [{"use": "Official", "prefix": ["Mr"], "Family": ["Chau"], "given": ["Hugh"]}], "identificatore": [{"USA": "ufficiale", "tipo": {"codifica": [{"System":http://hl7.org/fhir/v2/0203"", "codice": "Mr"}]}, "value": "1234567"}], "gender": "maschio" 1957-06-05 "," careProvider ": [{" visualizzazione ":" Jane Doe "}],}</span><span class="sxs-lookup"><span data-stu-id="aed0d-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="aed0d-146">Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="aed0d-147">ID</span><span class="sxs-lookup"><span data-stu-id="aed0d-147">id</span></span>
2. <span data-ttu-id="aed0d-148">Family: Contains = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore).</span><span class="sxs-lookup"><span data-stu-id="aed0d-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="aed0d-149">given\<= substring></span><span class="sxs-lookup"><span data-stu-id="aed0d-149">given=\<substring></span></span>
4. <span data-ttu-id="aed0d-150">Name =\<substring></span><span class="sxs-lookup"><span data-stu-id="aed0d-150">name=\<substring></span></span>
5. <span data-ttu-id="aed0d-151">nascita = (corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="aed0d-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="aed0d-152">\_conteggio (numero massimo di risultati che devono essere restituiti)</span><span class="sxs-lookup"><span data-stu-id="aed0d-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="aed0d-153">La risposta deve contenere il numero totale di record restituiti come risultato della ricerca e \_il conteggio verrà usato da PatientsApp per limitare la quantità di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="aed0d-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="aed0d-154">Identifier =\<MRN></span><span class="sxs-lookup"><span data-stu-id="aed0d-154">identifier=\<mrn></span></span>

<span data-ttu-id="aed0d-155">L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="aed0d-156">ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.</span><span class="sxs-lookup"><span data-stu-id="aed0d-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="aed0d-157">MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe.</span><span class="sxs-lookup"><span data-stu-id="aed0d-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="aed0d-158">Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR</span><span class="sxs-lookup"><span data-stu-id="aed0d-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="aed0d-159">Nome</span><span class="sxs-lookup"><span data-stu-id="aed0d-159">Name</span></span>
- <span data-ttu-id="aed0d-160">Nascita</span><span class="sxs-lookup"><span data-stu-id="aed0d-160">Birthdate</span></span>

<span data-ttu-id="aed0d-161">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="aed0d-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="aed0d-162">Richiesta: POST <Fhir-Server>/patient/_search della richiesta: given = Hugh&Family = Chau</span><span class="sxs-lookup"><span data-stu-id="aed0d-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="aed0d-163">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>",.</span><span class="sxs-lookup"><span data-stu-id="aed0d-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="aed0d-164">.</span><span class="sxs-lookup"><span data-stu-id="aed0d-164"></span></span>
      <span data-ttu-id="aed0d-165">.</span><span class="sxs-lookup"><span data-stu-id="aed0d-165"></span></span>
      <span data-ttu-id="aed0d-166">"voce": [{"risorsa": {"resourceType": "paziente", "ID": "<ID paziente>", "nome": [{"testo": "Hugh Chau", "famiglia": ["Chau"], "given": ["Hugh"]}], "gender": "maschio", "database": "1957-06-05"}, "ricerca": {"modalità": "corrispondenza"}}]</span><span class="sxs-lookup"><span data-stu-id="aed0d-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="aed0d-167">Per [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="aed0d-168">Osservazione</span><span class="sxs-lookup"><span data-stu-id="aed0d-168">Observation</span></span>

<span data-ttu-id="aed0d-169">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut Vital Signs:</span><span class="sxs-lookup"><span data-stu-id="aed0d-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="aed0d-170">Effettivo (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="aed0d-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="aed0d-171">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="aed0d-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="aed0d-172">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="aed0d-172">ValueQuantity.Value</span></span>

<span data-ttu-id="aed0d-173">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="aed0d-174">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="aed0d-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="aed0d-175">ValueQuantity. unit</span><span class="sxs-lookup"><span data-stu-id="aed0d-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="aed0d-176">Se si usano le osservazioni dei componenti, la stessa logica viene applicata per ogni osservazione del componente.</span><span class="sxs-lookup"><span data-stu-id="aed0d-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="aed0d-177">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aed0d-178">paziente =\<ID paziente\></span><span class="sxs-lookup"><span data-stu-id="aed0d-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="aed0d-179">Ordina: desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="aed0d-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="aed0d-180">Data\></span><span class="sxs-lookup"><span data-stu-id="aed0d-180">date\></span></span>

<span data-ttu-id="aed0d-181">L'obiettivo è quello di riuscire a recuperare gli ultimi segni vitali per un paziente, [VitalSigns. DSTU....] (osservazione?).</span><span class="sxs-lookup"><span data-stu-id="aed0d-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="aed0d-182">Richiesta: ottenere <Fhir-Server>/Observation? patient =<patient-ID>&_sort:d ESC = data&Category = Vital-Signs</span><span class="sxs-lookup"><span data-stu-id="aed0d-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="aed0d-183">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "digitare": "searchset", "Total": 20, "entry": [{"risorsa": {"resourceType": "osservazione", "ID": "<Resource-ID>", "Category": {"coding": [{code ":" Vital-Signs "}],}," code ": {" coding " ": [{" sistema ":"http://loinc.org"," codice ":" 39156-5 "," visualizzazione ":" BMI "}],}," effectiveDateTime ":" 2009-12-01 "," valueQuantity ": {" valore ": 34,4," unità ":" kg/m2 "," sistema ":"http://unitsofmeasure.org"," codice ":" kg/m2 "},},.</span><span class="sxs-lookup"><span data-stu-id="aed0d-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="aed0d-184">.</span><span class="sxs-lookup"><span data-stu-id="aed0d-184"></span></span>
        <span data-ttu-id="aed0d-185">.</span><span class="sxs-lookup"><span data-stu-id="aed0d-185"></span></span>
      <span data-ttu-id="aed0d-186">] }</span><span class="sxs-lookup"><span data-stu-id="aed0d-186"></span></span>

* * *

<span data-ttu-id="aed0d-187">Per [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="aed0d-188">Condizione</span><span class="sxs-lookup"><span data-stu-id="aed0d-188">Condition</span></span>

<span data-ttu-id="aed0d-189">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="aed0d-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="aed0d-190">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="aed0d-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="aed0d-191">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="aed0d-192">Data registrata</span><span class="sxs-lookup"><span data-stu-id="aed0d-192">Date Recorded</span></span>
2. <span data-ttu-id="aed0d-193">Gravità</span><span class="sxs-lookup"><span data-stu-id="aed0d-193">Severity</span></span>

<span data-ttu-id="aed0d-194">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aed0d-195">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-195">patient=\<patient id></span></span>
2. <span data-ttu-id="aed0d-196">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="aed0d-196">_count=\<max results></span></span>

<span data-ttu-id="aed0d-197">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="aed0d-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aed0d-198">Richiesta: ottenere <Fhir-Server>/Condition? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="aed0d-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="aed0d-199">Risposta: {"resourceType": "bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "Total": 1, "entry": [{"Resource": {"resourceType": "Condition", "ID": "<Resource-ID>", "code": {"coding": [{               "sistema": "http://snomed.info/sct", "codice": "386033004", "visualizzazione": "neuropatia (danni nervosi)"}]}, "dateRecorded": "2018-09-17", "gravità": {"codifica": [{"SYST em ":"http://snomed.info/sct"," codice ":" 24484000 "," visualizzazione ":" grave "}]}},}]}</span><span class="sxs-lookup"><span data-stu-id="aed0d-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="aed0d-200">Per [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="aed0d-201">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="aed0d-201">Encounter</span></span>

<span data-ttu-id="aed0d-202">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo degli incontri di base degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="aed0d-203">Stato</span><span class="sxs-lookup"><span data-stu-id="aed0d-203">Status</span></span>
2. <span data-ttu-id="aed0d-204">Digitare [0]. Codifica [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="aed0d-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="aed0d-205">Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="aed0d-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="aed0d-206">Periodo. inizio</span><span class="sxs-lookup"><span data-stu-id="aed0d-206">Period.Start</span></span>
2. <span data-ttu-id="aed0d-207">Posizione [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="aed0d-207">Location[0].Location.Display</span></span>

<span data-ttu-id="aed0d-208">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aed0d-209">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-209">patient=\<patient id></span></span>
2. <span data-ttu-id="aed0d-210">_sort: desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="aed0d-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="aed0d-211">Data></span><span class="sxs-lookup"><span data-stu-id="aed0d-211">date></span></span>
3. <span data-ttu-id="aed0d-212">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="aed0d-212">_count=\<max results></span></span>

<span data-ttu-id="aed0d-213">L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="aed0d-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="aed0d-214">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="aed0d-214">Each encounter references a location resource.</span></span> <span data-ttu-id="aed0d-215">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="aed0d-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="aed0d-216">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="aed0d-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="aed0d-217">Richiesta: ottenere <Fhir-Server>/Encounter? patient =<ID paziente>&_sort:d ESC = data&_count = 1</span><span class="sxs-lookup"><span data-stu-id="aed0d-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="aed0d-218">Risposta: {"ResourceType": "bundle", "Type": "searchset", "Total": 1, "entry": [{"" Resource ": {" ResourceType ":" Encounter "," ID ":" <Resource-ID> "," identificatore ": [{" use ":" Official "," value ":<id>" "}]," status " : "arrivata", "tipo": [{"coding": [{"display": "appuntamento"}],}], "paziente": {"riferimento": "paziente/<paziente-ID>"}, "periodo": {"Start": "09/17/2018 1:00:00 PM"}, "location": [{              "location": {"display": "Clinic-ENT"},}]}}]}</span><span class="sxs-lookup"><span data-stu-id="aed0d-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="aed0d-219">Per [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="aed0d-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="aed0d-220">AllergyIntolerance</span></span>

<span data-ttu-id="aed0d-221">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="aed0d-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="aed0d-222">Code. Text</span><span class="sxs-lookup"><span data-stu-id="aed0d-222">Code.Text</span></span>
2. <span data-ttu-id="aed0d-223">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="aed0d-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="aed0d-224">Stato</span><span class="sxs-lookup"><span data-stu-id="aed0d-224">Status</span></span>

<span data-ttu-id="aed0d-225">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="aed0d-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="aed0d-226">RecordedDate</span></span>
2. <span data-ttu-id="aed0d-227">Nota. testo</span><span class="sxs-lookup"><span data-stu-id="aed0d-227">Note.Text</span></span>
3. <span data-ttu-id="aed0d-228">Reazione [..]. Sostanza. testo</span><span class="sxs-lookup"><span data-stu-id="aed0d-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="aed0d-229">Reazione [..]. Manifestazione [..]. Testo</span><span class="sxs-lookup"><span data-stu-id="aed0d-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="aed0d-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="aed0d-230">Text.Div</span></span>

<span data-ttu-id="aed0d-231">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aed0d-232">Patient = \<id paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-232">Patient =  \<patient id></span></span>

<span data-ttu-id="aed0d-233">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="aed0d-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aed0d-234">Richiesta: ottenere <Fhir-Server>/AllergyIntolerance? patient =<ID paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="aed0d-235">Risposta: {"resourceType": "bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "Total": 1, "entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "recordedDate": "2018-09-17T07:00:00.00 0Z "," sostanza ": {" testo ":" anacardi Nuts "}," stato ":" confermato "," reazione ": [{" sostanza ": {" testo ":" Estratto di anacardio allergenico prodotto iniettabile "}," manifestati on ": [{" testo ":" reazione anafilattica "}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="aed0d-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="aed0d-236">Per [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="aed0d-237">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="aed0d-237">Medication Order</span></span>

<span data-ttu-id="aed0d-238">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="aed0d-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="aed0d-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="aed0d-239">DateWritten</span></span>
2. <span data-ttu-id="aed0d-240">Prescriber. display</span><span class="sxs-lookup"><span data-stu-id="aed0d-240">Prescriber.Display</span></span>
3. <span data-ttu-id="aed0d-241">Medicine. display (se di riferimento)</span><span class="sxs-lookup"><span data-stu-id="aed0d-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="aed0d-242">Medicine. Text (se Concept)</span><span class="sxs-lookup"><span data-stu-id="aed0d-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="aed0d-243">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="aed0d-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="aed0d-244">DateEnded</span></span>
2. <span data-ttu-id="aed0d-245">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="aed0d-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="aed0d-246">Text. div</span><span class="sxs-lookup"><span data-stu-id="aed0d-246">Text.Div</span></span>

<span data-ttu-id="aed0d-247">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aed0d-248">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-248">patient=\<patient id></span></span>
2. <span data-ttu-id="aed0d-249">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="aed0d-249">_count=\<max results></span></span>

<span data-ttu-id="aed0d-250">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="aed0d-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aed0d-251">Richiesta: ottenere <Fhir-Server>/MedicationOrder? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="aed0d-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="aed0d-252">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"Resource", "", "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medi cationCodeableConcept ": {" testo ":" Lisinopril 20 MG Oral Tablet "}," Prescriber ": {" display ":" Jane Doe "}," dosageInstruction ": [{" Text ":" 1 Daily "}]}}]}</span><span class="sxs-lookup"><span data-stu-id="aed0d-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="aed0d-253">Per [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="aed0d-254">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="aed0d-254">Coverage</span></span>

<span data-ttu-id="aed0d-255">Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="aed0d-256">Pagante</span><span class="sxs-lookup"><span data-stu-id="aed0d-256">Payor</span></span>

<span data-ttu-id="aed0d-257">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="aed0d-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aed0d-258">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-258">patient=\<patient id></span></span>

<span data-ttu-id="aed0d-259">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="aed0d-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aed0d-260">Richiesta: ottenere <Fhir-Server>/coverage? patient =<ID paziente></span><span class="sxs-lookup"><span data-stu-id="aed0d-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="aed0d-261">Response: {"resourceType": "bundle", "Type": "searchset", "Total": 1, "entry": [{"Resource", "ID": "<Resource-ID>", "piano": "nessuna assicurazione primaria", "sottoscrittore": {"riferimento": "paziente/ <ID paziente> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="aed0d-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="aed0d-262">Per [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="aed0d-263">Posizione</span><span class="sxs-lookup"><span data-stu-id="aed0d-263">Location</span></span>

<span data-ttu-id="aed0d-264">Questa risorsa viene usata solo come riferimento nella risorsa [Encounter](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="aed0d-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="aed0d-265">Per [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="aed0d-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
