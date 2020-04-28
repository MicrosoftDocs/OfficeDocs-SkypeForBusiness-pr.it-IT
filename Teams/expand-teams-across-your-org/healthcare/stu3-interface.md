---
title: Interfaccia STU3 dell'app pazienti e integrazione di EHR
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
description: Informazioni su come integrare i record sanitari elettronici nell'app Microsoft teams patients e la specifica dell'interfaccia STU3.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e101f6ca50a76b4b8bb9d3dd33d35fd7706a81f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905748"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="41e52-103">Specifica dell'interfaccia STU3</span><span class="sxs-lookup"><span data-stu-id="41e52-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="41e52-104">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="41e52-105">Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="41e52-106">Paziente</span><span class="sxs-lookup"><span data-stu-id="41e52-106">Patient</span></span>](#patient)
- [<span data-ttu-id="41e52-107">Osservazione</span><span class="sxs-lookup"><span data-stu-id="41e52-107">Observation</span></span>](#observation)
- [<span data-ttu-id="41e52-108">Condizione</span><span class="sxs-lookup"><span data-stu-id="41e52-108">Condition</span></span>](#condition)
- [<span data-ttu-id="41e52-109">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="41e52-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="41e52-110">Intolleranza alle allergie</span><span class="sxs-lookup"><span data-stu-id="41e52-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="41e52-111">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="41e52-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="41e52-112">[Istruzione farmaco](#medication-request) (sostituisce il MedicationOrder nella versione DSTU2 di PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="41e52-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="41e52-113">Posizione (le informazioni necessarie da questa risorsa possono essere incluse in Encounter)</span><span class="sxs-lookup"><span data-stu-id="41e52-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="41e52-114">La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto); Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.</span><span class="sxs-lookup"><span data-stu-id="41e52-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="41e52-115">Le query dell'app Microsoft teams patients per più risorse devono pubblicare un pacchetto (BATCH) di richieste per l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="41e52-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="41e52-116">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="41e52-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="41e52-117">Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="41e52-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="41e52-118">Istruzione Capability</span><span class="sxs-lookup"><span data-stu-id="41e52-118">Capability Statement</span></span>

<span data-ttu-id="41e52-119">Questi sono i campi obbligatori minimi:</span><span class="sxs-lookup"><span data-stu-id="41e52-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="41e52-120">RESTO</span><span class="sxs-lookup"><span data-stu-id="41e52-120">REST</span></span>
   1. <span data-ttu-id="41e52-121">Modalità</span><span class="sxs-lookup"><span data-stu-id="41e52-121">Mode</span></span>
   2. <span data-ttu-id="41e52-122">Interazione</span><span class="sxs-lookup"><span data-stu-id="41e52-122">Interaction</span></span>
   3. <span data-ttu-id="41e52-123">Risorsa: digitare</span><span class="sxs-lookup"><span data-stu-id="41e52-123">Resource: Type</span></span>
   4. <span data-ttu-id="41e52-124">Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="41e52-124">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="41e52-125">FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot.)</span><span class="sxs-lookup"><span data-stu-id="41e52-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="41e52-126">Per [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="41e52-127">Paziente</span><span class="sxs-lookup"><span data-stu-id="41e52-127">Patient</span></span>

<span data-ttu-id="41e52-128">Ecco i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente Argonaut:</span><span class="sxs-lookup"><span data-stu-id="41e52-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="41e52-129">Name. given</span><span class="sxs-lookup"><span data-stu-id="41e52-129">Name.Given</span></span>
2. <span data-ttu-id="41e52-130">Name. Family</span><span class="sxs-lookup"><span data-stu-id="41e52-130">Name.Family</span></span>
3. <span data-ttu-id="41e52-131">Genere</span><span class="sxs-lookup"><span data-stu-id="41e52-131">Gender</span></span>
4. <span data-ttu-id="41e52-132">Nascita</span><span class="sxs-lookup"><span data-stu-id="41e52-132">BirthDate</span></span>
5. <span data-ttu-id="41e52-133">MRN (identificatore)</span><span class="sxs-lookup"><span data-stu-id="41e52-133">MRN (Identifier)</span></span>

<span data-ttu-id="41e52-134">Oltre ai [campi Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="41e52-135">Name. use</span><span class="sxs-lookup"><span data-stu-id="41e52-135">Name.Use</span></span>
2. <span data-ttu-id="41e52-136">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="41e52-136">Name.Prefix</span></span>
3. <span data-ttu-id="41e52-137">[GeneralPractitioner]-il riferimento GeneralPractitioner deve essere incluso nella risorsa paziente (solo campo di visualizzazione)</span><span class="sxs-lookup"><span data-stu-id="41e52-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="41e52-138">Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="41e52-139">ID</span><span class="sxs-lookup"><span data-stu-id="41e52-139">id</span></span>
2. <span data-ttu-id="41e52-140">Family = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore)</span><span class="sxs-lookup"><span data-stu-id="41e52-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="41e52-141">given\<= substring></span><span class="sxs-lookup"><span data-stu-id="41e52-141">given=\<substring></span></span>
4. <span data-ttu-id="41e52-142">nascita = (corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="41e52-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="41e52-143">Gender = (i valori sono uno degli amministratori-gender)</span><span class="sxs-lookup"><span data-stu-id="41e52-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="41e52-144">\_conteggio (numero massimo di risultati che devono essere restituiti)</span><span class="sxs-lookup"><span data-stu-id="41e52-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="41e52-145">La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e \_il conteggio verrà usato da PatientsApp per limitare il numero di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="41e52-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="41e52-146">Identifier =\<MRN></span><span class="sxs-lookup"><span data-stu-id="41e52-146">identifier=\<mrn></span></span>

<span data-ttu-id="41e52-147">L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="41e52-148">ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.</span><span class="sxs-lookup"><span data-stu-id="41e52-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="41e52-149">MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe.</span><span class="sxs-lookup"><span data-stu-id="41e52-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="41e52-150">Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.</span><span class="sxs-lookup"><span data-stu-id="41e52-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="41e52-151">Nome</span><span class="sxs-lookup"><span data-stu-id="41e52-151">Name</span></span>
- <span data-ttu-id="41e52-152">Nascita</span><span class="sxs-lookup"><span data-stu-id="41e52-152">Birthdate</span></span>

<span data-ttu-id="41e52-153">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="41e52-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="41e52-154">Richiesta: POST <Fhir-Server>/patient/_search richiedere il corpo: given = Ruth&Family = black</span><span class="sxs-lookup"><span data-stu-id="41e52-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="41e52-155">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "Total": 1, "link": [{"relation": "self", "URL": <Fhir-server>/patient/_search "}]," entry ": [{" fullUrl ": <Fhir-server>/patient/<patient-ID>", "risorsa": {"resourceType": "patient", "ID": "<patient-ID>", "meta": {"VersionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "Text": {"status": "generated", "div": "</span><span class="sxs-lookup"><span data-stu-id="41e52-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="41e52-156">\n</span><span class="sxs-lookup"><span data-stu-id="41e52-156">\n</span></span>        <p><span data-ttu-id="41e52-157">Ruth Black</span><span class="sxs-lookup"><span data-stu-id="41e52-157">Ruth Black</span></span></p><span data-ttu-id="41e52-158">\n</span><span class="sxs-lookup"><span data-stu-id="41e52-158">\n</span></span>      </div><span data-ttu-id="41e52-159">"}," identificatore ": [{" USA ":" usuale "," tipo ": {" codifica ": [{" System ":https://hl7.org/fhir/v2/0203" "," codice ":" Mr "," display ":" numero di record medico "," userSelected ": false}]," testo ":" numero di record medico "}," sistemahttp://hospital.smarthealthit.org":" "," valore ":" 1234567 "}]," attivo ": vero", "nome": [{"USA": "ufficiale", "famiglia": "nero", "assegnato": ["Ruth", "C".</span><span class="sxs-lookup"><span data-stu-id="41e52-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="41e52-160">]}], "Telecom": [{"System": "telefono", "valore": "800-599-2739", "use": "Home"}, {"System": "Phone", "value": "800-808-7785", "use": "mobile"}, {"System": "mail", "value": "ruth.black@example.com"}], "gender": "femmina", "DataNascita": "1951-08-23", "indirizzo": [{"use": "Home", "line": ["26 South RdApt 22"], "City": "Sapulpa", "stato": "OK", "postalCode": "74066", "paese": "USA"}]}, "ricerca": {"modalità": "Confronta"}}]}</span><span class="sxs-lookup"><span data-stu-id="41e52-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="41e52-161">Richiesta: ottenere <Fhir-Server>/patient/<ID paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="41e52-162">Response: {"resourceType": "patient", "ID": "<patient-ID>", "identificatore": [{"use": "usual", "Type": {"coding": [{"System": "https://hl7.org/fhir/v2/0203", "code": "Mr",}], "Text": "numero di record medico"}, "valore": "1234567"}], "nome": [{"use": "ufficiale", "famiglia": "Adams", "assegnato": ["Daniele", "X".</span><span class="sxs-lookup"><span data-stu-id="41e52-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="41e52-163">]}], "sesso": "maschio", "DataNascita": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="41e52-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="41e52-164">Per [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-164">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="41e52-165">Osservazione</span><span class="sxs-lookup"><span data-stu-id="41e52-165">Observation</span></span>

<span data-ttu-id="41e52-166">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="41e52-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="41e52-167">Effettivo (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="41e52-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="41e52-168">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="41e52-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="41e52-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="41e52-169">ValueQuantity.Value</span></span>

<span data-ttu-id="41e52-170">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="41e52-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="41e52-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="41e52-172">ValueQuantity. unit</span><span class="sxs-lookup"><span data-stu-id="41e52-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="41e52-173">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="41e52-174">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-174">patient=\<patient id></span></span>
2. <span data-ttu-id="41e52-175">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="41e52-175">_sort=-date</span></span>
3. <span data-ttu-id="41e52-176">Category (verrà eseguita una query per "Category = Vital-Signs") per recuperare l'elenco dei segni vitali.</span><span class="sxs-lookup"><span data-stu-id="41e52-176">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="41e52-177">Fare riferimento a questo esempio di chiamata:</span><span class="sxs-lookup"><span data-stu-id="41e52-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="41e52-178">Richiesta: ottenere <Fhir-Server>/Observation? patient =<patient-ID>&Category = Vital-Signs</span><span class="sxs-lookup"><span data-stu-id="41e52-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="41e52-179">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "totale": 20, "voce": [{"risorsa": {"resourceType": "osservazione", "ID": "<Resource-ID>", "Category": [{"coding": [{"System": "https://hl7.org/fhir/observation-category", "codice" codice ": {" coding ": [{" System ":"http://loinc.org"," code ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" valore ": 72,0," Unit ":" {Beats}/min "," System ":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="41e52-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="41e52-180">.</span><span class="sxs-lookup"><span data-stu-id="41e52-180">.</span></span>
        <span data-ttu-id="41e52-181">.</span><span class="sxs-lookup"><span data-stu-id="41e52-181">.</span></span>
      <span data-ttu-id="41e52-182">] }</span><span class="sxs-lookup"><span data-stu-id="41e52-182">] }</span></span>

* * *

<span data-ttu-id="41e52-183">Per [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="41e52-184">Condizione</span><span class="sxs-lookup"><span data-stu-id="41e52-184">Condition</span></span>

<span data-ttu-id="41e52-185">Ecco i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="41e52-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="41e52-186">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="41e52-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="41e52-187">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="41e52-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="41e52-188">AssertedDate</span></span>
2. <span data-ttu-id="41e52-189">Gravità</span><span class="sxs-lookup"><span data-stu-id="41e52-189">Severity</span></span>

<span data-ttu-id="41e52-190">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="41e52-191">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-191">patient=\<patient id></span></span>
2. <span data-ttu-id="41e52-192">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="41e52-192">_count=\<max results></span></span>

<span data-ttu-id="41e52-193">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="41e52-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="41e52-194">Richiesta: ottenere <Fhir-Server>/Condition? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="41e52-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="41e52-195">Risposta: {"resourceType": "bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "Total": 2, "entry": [{"Resource", "resourceType": "Condition", "ID": "<Resource-ID>", "codice": {"codifica": [{"System": "http://snomed.info/sct" "," codice ":" 185903001 "," visualizzazione ":" richiede l'immunizzazione dell'influenza ",}]}," gravità ": {" codifica ": [{" Systemhttp://snomed.info/sct":" "", "codice": "24484000", "display": "grave"}]}, "assertedDate": "2018-04-04"}},.</span><span class="sxs-lookup"><span data-stu-id="41e52-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="41e52-196">.</span><span class="sxs-lookup"><span data-stu-id="41e52-196">.</span></span>
        <span data-ttu-id="41e52-197">.</span><span class="sxs-lookup"><span data-stu-id="41e52-197">.</span></span>
      <span data-ttu-id="41e52-198">] }</span><span class="sxs-lookup"><span data-stu-id="41e52-198">] }</span></span>

* * *
<span data-ttu-id="41e52-199">Per [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-199">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="41e52-200">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="41e52-200">Encounter</span></span>

<span data-ttu-id="41e52-201">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo di confronto degli Stati Uniti](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have".</span><span class="sxs-lookup"><span data-stu-id="41e52-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="41e52-202">Stato</span><span class="sxs-lookup"><span data-stu-id="41e52-202">Status</span></span>
2. <span data-ttu-id="41e52-203">Digitare [0]. Codifica [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="41e52-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="41e52-204">Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="41e52-204">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="41e52-205">Periodo. inizio</span><span class="sxs-lookup"><span data-stu-id="41e52-205">Period.Start</span></span>
2. <span data-ttu-id="41e52-206">Posizione [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="41e52-206">Location[0].Location.Display</span></span>

<span data-ttu-id="41e52-207">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="41e52-208">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-208">patient=\<patient id></span></span>
2. <span data-ttu-id="41e52-209">_sort: desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="41e52-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="41e52-210">Data></span><span class="sxs-lookup"><span data-stu-id="41e52-210">date></span></span>
3. <span data-ttu-id="41e52-211">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="41e52-211">_count=\<max results></span></span>

<span data-ttu-id="41e52-212">L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="41e52-212">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="41e52-213">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="41e52-213">Each encounter references a location resource.</span></span> <span data-ttu-id="41e52-214">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="41e52-214">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="41e52-215">Per [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-215">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="41e52-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="41e52-216">AllergyIntolerance</span></span>

<span data-ttu-id="41e52-217">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="41e52-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="41e52-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="41e52-218">Code.Text</span></span>
2. <span data-ttu-id="41e52-219">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="41e52-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="41e52-220">ClinicalStatus/VerificationStatus (leggiamo entrambi)</span><span class="sxs-lookup"><span data-stu-id="41e52-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="41e52-221">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere il campo seguente:</span><span class="sxs-lookup"><span data-stu-id="41e52-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="41e52-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="41e52-222">AssertedDate</span></span>
2. <span data-ttu-id="41e52-223">Nota. testo</span><span class="sxs-lookup"><span data-stu-id="41e52-223">Note.Text</span></span>
3. <span data-ttu-id="41e52-224">Reazione</span><span class="sxs-lookup"><span data-stu-id="41e52-224">Reaction</span></span>
    1. <span data-ttu-id="41e52-225">Sostanza (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="41e52-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="41e52-226">Manifestazione (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="41e52-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="41e52-227">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="41e52-228">Patient = \<id paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-228">Patient =  \<patient id></span></span>

<span data-ttu-id="41e52-229">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="41e52-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="41e52-230">Richiesta: ottenere <Fhir-Server>/AllergyIntolerance? patient =<ID paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="41e52-231">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset"; "Total": 1 "," voce ": [{" risorsa ": {" resourceType ":" AllergyIntolerance "," ID ":" <Resource-ID> "," clinicalStatus ":" Active "," verificationStatus ":" confermato "," codice ": {" codifica ":" "," System "http://rxnav.nlm.nih.gov/REST/Ndfrt:" "," codice ":" N0000175503 "," display ":" solfonammide antibatterico ",}]," testo ":" solfonammide antibatterico "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," reazione ": [{" manifestazione ": [{" coding ": [{http://snomed.info/sct" System ":" "," code ":" 271807003 "," display ":" rash cutaneo ",}]," testo ":" eruzione cutanea "}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="41e52-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="41e52-232">Per [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-232">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="41e52-233">Richiesta di farmaci</span><span class="sxs-lookup"><span data-stu-id="41e52-233">Medication Request</span></span>

<span data-ttu-id="41e52-234">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo di richiesta di base per i [farmaci USA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="41e52-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="41e52-235">Medicine. display (se di riferimento)</span><span class="sxs-lookup"><span data-stu-id="41e52-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="41e52-236">Medicine. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="41e52-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="41e52-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="41e52-237">AuthoredOn</span></span>
4. <span data-ttu-id="41e52-238">Requestr. Agent. display</span><span class="sxs-lookup"><span data-stu-id="41e52-238">Requester.Agent.Display</span></span>

<span data-ttu-id="41e52-239">Oltre ai campi principali degli Stati Uniti, per una grande esperienza utente l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="41e52-240">DosageInstruction[..]. Testo</span><span class="sxs-lookup"><span data-stu-id="41e52-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="41e52-241">Testo</span><span class="sxs-lookup"><span data-stu-id="41e52-241">Text</span></span>

<span data-ttu-id="41e52-242">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="41e52-243">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-243">patient=\<patient id></span></span>
2. <span data-ttu-id="41e52-244">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="41e52-244">_count=\<max results></span></span>

<span data-ttu-id="41e52-245">Per [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="41e52-246">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="41e52-246">Coverage</span></span>

<span data-ttu-id="41e52-247">Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:</span><span class="sxs-lookup"><span data-stu-id="41e52-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="41e52-248">Raggruppamento, almeno un elemento con</span><span class="sxs-lookup"><span data-stu-id="41e52-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="41e52-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="41e52-249">GroupDisplay</span></span>
    2. <span data-ttu-id="41e52-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="41e52-250">PlanDisplay</span></span>
2. <span data-ttu-id="41e52-251">Periodo</span><span class="sxs-lookup"><span data-stu-id="41e52-251">Period</span></span>
3. <span data-ttu-id="41e52-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="41e52-252">SubscriberId</span></span>

<span data-ttu-id="41e52-253">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e52-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="41e52-254">Patient = \<id paziente></span><span class="sxs-lookup"><span data-stu-id="41e52-254">Patient = \<patient id></span></span>

<span data-ttu-id="41e52-255">Per [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="41e52-255">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
