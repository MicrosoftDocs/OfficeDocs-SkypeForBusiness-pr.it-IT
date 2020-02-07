---
title: Interfaccia STU3 dell'app pazienti e integrazione di EHR
author: jambirk
ms.author: jambirk
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
description: Integrazione dell'app EHR di Microsoft teams patients
ms.openlocfilehash: 6c7638436f35a1e460c176964dfc63624985b12e
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827634"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="411c8-103">Specifica dell'interfaccia STU3</span><span class="sxs-lookup"><span data-stu-id="411c8-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="411c8-104">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="411c8-105">Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="411c8-106">Paziente</span><span class="sxs-lookup"><span data-stu-id="411c8-106">Patient</span></span>](#patient)
- [<span data-ttu-id="411c8-107">Osservazione</span><span class="sxs-lookup"><span data-stu-id="411c8-107">Observation</span></span>](#observation)
- [<span data-ttu-id="411c8-108">Condizione</span><span class="sxs-lookup"><span data-stu-id="411c8-108">Condition</span></span>](#condition)
- [<span data-ttu-id="411c8-109">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="411c8-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="411c8-110">Intolleranza alle allergie</span><span class="sxs-lookup"><span data-stu-id="411c8-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="411c8-111">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="411c8-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="411c8-112">[Istruzione farmaco](#medication-request) (sostituisce il MedicationOrder nella versione DSTU2 di PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="411c8-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="411c8-113">Posizione (le informazioni necessarie da questa risorsa possono essere incluse in Encounter)</span><span class="sxs-lookup"><span data-stu-id="411c8-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="411c8-114">La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto); Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.</span><span class="sxs-lookup"><span data-stu-id="411c8-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="411c8-115">Le query dell'app Microsoft teams patients per più risorse devono pubblicare un pacchetto (BATCH) di richieste per l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="411c8-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="411c8-116">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="411c8-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="411c8-117">Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span><span class="sxs-lookup"><span data-stu-id="411c8-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="411c8-118">Istruzione Capability</span><span class="sxs-lookup"><span data-stu-id="411c8-118">Capability Statement</span></span>

<span data-ttu-id="411c8-119">Questi sono i campi obbligatori minimi:</span><span class="sxs-lookup"><span data-stu-id="411c8-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="411c8-120">RESTO</span><span class="sxs-lookup"><span data-stu-id="411c8-120">REST</span></span>
   1. <span data-ttu-id="411c8-121">Modalità</span><span class="sxs-lookup"><span data-stu-id="411c8-121">Mode</span></span>
   2. <span data-ttu-id="411c8-122">Interazione</span><span class="sxs-lookup"><span data-stu-id="411c8-122">Interaction</span></span>
   3. <span data-ttu-id="411c8-123">Risorsa: digitare</span><span class="sxs-lookup"><span data-stu-id="411c8-123">Resource: Type</span></span>
   4. <span data-ttu-id="411c8-124">Sicurezza: [estensione per gli URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="411c8-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="411c8-125">FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot.)</span><span class="sxs-lookup"><span data-stu-id="411c8-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="411c8-126">Per [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="411c8-127">Paziente</span><span class="sxs-lookup"><span data-stu-id="411c8-127">Patient</span></span>

<span data-ttu-id="411c8-128">Ecco i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente Argonaut:</span><span class="sxs-lookup"><span data-stu-id="411c8-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="411c8-129">Name. given</span><span class="sxs-lookup"><span data-stu-id="411c8-129">Name.Given</span></span>
2. <span data-ttu-id="411c8-130">Name. Family</span><span class="sxs-lookup"><span data-stu-id="411c8-130">Name.Family</span></span>
3. <span data-ttu-id="411c8-131">Genere</span><span class="sxs-lookup"><span data-stu-id="411c8-131">Gender</span></span>
4. <span data-ttu-id="411c8-132">Nascita</span><span class="sxs-lookup"><span data-stu-id="411c8-132">BirthDate</span></span>
5. <span data-ttu-id="411c8-133">MRN (identificatore)</span><span class="sxs-lookup"><span data-stu-id="411c8-133">MRN (Identifier)</span></span>

<span data-ttu-id="411c8-134">Oltre ai [campi Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="411c8-135">Name. use</span><span class="sxs-lookup"><span data-stu-id="411c8-135">Name.Use</span></span>
2. <span data-ttu-id="411c8-136">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="411c8-136">Name.Prefix</span></span>
3. <span data-ttu-id="411c8-137">[GeneralPractitioner]-il riferimento GeneralPractitioner deve essere incluso nella risorsa paziente (solo campo di visualizzazione)</span><span class="sxs-lookup"><span data-stu-id="411c8-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="411c8-138">Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="411c8-139">ID</span><span class="sxs-lookup"><span data-stu-id="411c8-139">id</span></span>
2. <span data-ttu-id="411c8-140">Family = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore)</span><span class="sxs-lookup"><span data-stu-id="411c8-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="411c8-141">given\<= substring></span><span class="sxs-lookup"><span data-stu-id="411c8-141">given=\<substring></span></span>
4. <span data-ttu-id="411c8-142">nascita = (corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="411c8-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="411c8-143">Gender = (i valori sono uno degli amministratori-gender)</span><span class="sxs-lookup"><span data-stu-id="411c8-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="411c8-144">\_conteggio (numero massimo di risultati che devono essere restituiti)</span><span class="sxs-lookup"><span data-stu-id="411c8-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="411c8-145">La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e \_il conteggio verrà usato da PatientsApp per limitare il numero di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="411c8-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="411c8-146">Identifier =\<MRN></span><span class="sxs-lookup"><span data-stu-id="411c8-146">identifier=\<mrn></span></span>

<span data-ttu-id="411c8-147">L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="411c8-148">ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.</span><span class="sxs-lookup"><span data-stu-id="411c8-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="411c8-149">MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe.</span><span class="sxs-lookup"><span data-stu-id="411c8-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="411c8-150">Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.</span><span class="sxs-lookup"><span data-stu-id="411c8-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="411c8-151">Nome</span><span class="sxs-lookup"><span data-stu-id="411c8-151">Name</span></span>
- <span data-ttu-id="411c8-152">Nascita</span><span class="sxs-lookup"><span data-stu-id="411c8-152">Birthdate</span></span>

<span data-ttu-id="411c8-153">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="411c8-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="411c8-154">Richiesta: POST <Fhir-Server>/patient/_search richiedere il corpo: given = Ruth&Family = black</span><span class="sxs-lookup"><span data-stu-id="411c8-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="411c8-155">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "Total": 1, "link": [{"relation": "self", "URL": <Fhir-server>/patient/_search "}]," entry ": [{" fullUrl ": <Fhir-server>/patient/<patient-ID>", "risorsa": {"resourceType": "patient", "ID": "<patient-ID>", "meta": {"VersionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "Text": {"status": "generated", "div": "</span><span class="sxs-lookup"><span data-stu-id="411c8-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="411c8-156">\n</span><span class="sxs-lookup"><span data-stu-id="411c8-156">\n</span></span>        <p><span data-ttu-id="411c8-157">Ruth Black</span><span class="sxs-lookup"><span data-stu-id="411c8-157">Ruth Black</span></span></p><span data-ttu-id="411c8-158">\n</span><span class="sxs-lookup"><span data-stu-id="411c8-158">\n</span></span>      </div><span data-ttu-id="411c8-159">"}," identificatore ": [{" USA ":" usuale "," tipo ": {" codifica ": [{" System ":http://hl7.org/fhir/v2/0203" "," codice ":" Mr "," display ":" numero di record medico "," userSelected ": false}]," testo ":" numero di record medico "}," sistemahttp://hospital.smarthealthit.org":" "," valore ":" 1234567 "}]," attivo ": vero", "nome": [{"USA": "ufficiale", "famiglia": "nero", "assegnato": ["Ruth", "C".</span><span class="sxs-lookup"><span data-stu-id="411c8-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="411c8-160">]}], "Telecom": [{"System": "telefono", "valore": "800-599-2739", "use": "Home"}, {"System": "Phone", "value": "800-808-7785", "use": "mobile"}, {"System": "mail", "value": "ruth.black@example.com"}], "gender": "femmina", "DataNascita": "1951-08-23", "indirizzo": [{"use": "Home", "line": ["26 South RdApt 22"], "City": "Sapulpa", "stato": "OK", "postalCode": "74066", "paese": "USA"}]}, "ricerca": {"modalità": "Confronta"}}]}</span><span class="sxs-lookup"><span data-stu-id="411c8-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="411c8-161">Richiesta: ottenere <Fhir-Server>/patient/<ID paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="411c8-162">Response: {"resourceType": "patient", "ID": "<patient-ID>", "identificatore": [{"use": "usual", "Type": {"coding": [{"System": "http://hl7.org/fhir/v2/0203", "code": "Mr",}], "Text": "numero di record medico"}, "valore": "1234567"}], "nome": [{"use": "ufficiale", "famiglia": "Adams", "assegnato": ["Daniele", "X".</span><span class="sxs-lookup"><span data-stu-id="411c8-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="411c8-163">]}], "sesso": "maschio", "DataNascita": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="411c8-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="411c8-164">Per [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="411c8-165">Osservazione</span><span class="sxs-lookup"><span data-stu-id="411c8-165">Observation</span></span>

<span data-ttu-id="411c8-166">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="411c8-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="411c8-167">Effettivo (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="411c8-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="411c8-168">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="411c8-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="411c8-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="411c8-169">ValueQuantity.Value</span></span>

<span data-ttu-id="411c8-170">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="411c8-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="411c8-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="411c8-172">ValueQuantity. unit</span><span class="sxs-lookup"><span data-stu-id="411c8-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="411c8-173">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="411c8-174">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-174">patient=\<patient id></span></span>
2. <span data-ttu-id="411c8-175">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="411c8-175">_sort=-date</span></span>
3. <span data-ttu-id="411c8-176">Category (verrà eseguita una query per "Category = Vital-Signs") per recuperare l'elenco dei segni vitali.</span><span class="sxs-lookup"><span data-stu-id="411c8-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="411c8-177">Fare riferimento a questo esempio di chiamata:</span><span class="sxs-lookup"><span data-stu-id="411c8-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="411c8-178">Richiesta: ottenere <Fhir-Server>/Observation? patient =<patient-ID>&Category = Vital-Signs</span><span class="sxs-lookup"><span data-stu-id="411c8-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="411c8-179">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "totale": 20, "voce": [{"risorsa": {"resourceType": "osservazione", "ID": "<Resource-ID>", "Category": [{"coding": [{"System": "http://hl7.org/fhir/observation-category", "codice" codice ": {" coding ": [{" System ":"http://loinc.org"," code ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" valore ": 72,0," Unit ":" {Beats}/min "," System ":"http://unitsofmeasure.org",}}},.</span><span class="sxs-lookup"><span data-stu-id="411c8-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="411c8-180">.</span><span class="sxs-lookup"><span data-stu-id="411c8-180">.</span></span>
        <span data-ttu-id="411c8-181">.</span><span class="sxs-lookup"><span data-stu-id="411c8-181">.</span></span>
      <span data-ttu-id="411c8-182">] }</span><span class="sxs-lookup"><span data-stu-id="411c8-182">] }</span></span>

* * *

<span data-ttu-id="411c8-183">Per [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="411c8-184">Condizione</span><span class="sxs-lookup"><span data-stu-id="411c8-184">Condition</span></span>

<span data-ttu-id="411c8-185">Ecco i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="411c8-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="411c8-186">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="411c8-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="411c8-187">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="411c8-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="411c8-188">AssertedDate</span></span>
2. <span data-ttu-id="411c8-189">Gravità</span><span class="sxs-lookup"><span data-stu-id="411c8-189">Severity</span></span>

<span data-ttu-id="411c8-190">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="411c8-191">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-191">patient=\<patient id></span></span>
2. <span data-ttu-id="411c8-192">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="411c8-192">_count=\<max results></span></span>

<span data-ttu-id="411c8-193">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="411c8-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="411c8-194">Richiesta: ottenere <Fhir-Server>/Condition? patient =<patient-ID>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="411c8-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="411c8-195">Risposta: {"resourceType": "bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "Total": 2, "entry": [{"Resource", "resourceType": "Condition", "ID": "<Resource-ID>", "codice": {"codifica": [{"System": "http://snomed.info/sct" "," codice ":" 185903001 "," visualizzazione ":" richiede l'immunizzazione dell'influenza ",}]}," gravità ": {" codifica ": [{" Systemhttp://snomed.info/sct":" "", "codice": "24484000", "display": "grave"}]}, "assertedDate": "2018-04-04"}},.</span><span class="sxs-lookup"><span data-stu-id="411c8-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="411c8-196">.</span><span class="sxs-lookup"><span data-stu-id="411c8-196">.</span></span>
        <span data-ttu-id="411c8-197">.</span><span class="sxs-lookup"><span data-stu-id="411c8-197">.</span></span>
      <span data-ttu-id="411c8-198">] }</span><span class="sxs-lookup"><span data-stu-id="411c8-198">] }</span></span>

* * *
<span data-ttu-id="411c8-199">Per [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="411c8-200">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="411c8-200">Encounter</span></span>

<span data-ttu-id="411c8-201">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo di confronto degli Stati Uniti](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have".</span><span class="sxs-lookup"><span data-stu-id="411c8-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="411c8-202">Stato</span><span class="sxs-lookup"><span data-stu-id="411c8-202">Status</span></span>
2. <span data-ttu-id="411c8-203">Digitare [0]. Codifica [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="411c8-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="411c8-204">Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="411c8-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="411c8-205">Periodo. inizio</span><span class="sxs-lookup"><span data-stu-id="411c8-205">Period.Start</span></span>
2. <span data-ttu-id="411c8-206">Posizione [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="411c8-206">Location[0].Location.Display</span></span>

<span data-ttu-id="411c8-207">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="411c8-208">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-208">patient=\<patient id></span></span>
2. <span data-ttu-id="411c8-209">_sort: desc =\<campo ex.</span><span class="sxs-lookup"><span data-stu-id="411c8-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="411c8-210">Data></span><span class="sxs-lookup"><span data-stu-id="411c8-210">date></span></span>
3. <span data-ttu-id="411c8-211">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="411c8-211">_count=\<max results></span></span>

<span data-ttu-id="411c8-212">L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="411c8-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="411c8-213">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="411c8-213">Each encounter references a location resource.</span></span> <span data-ttu-id="411c8-214">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="411c8-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="411c8-215">Per [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="411c8-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="411c8-216">AllergyIntolerance</span></span>

<span data-ttu-id="411c8-217">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="411c8-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="411c8-218">Code. Text</span><span class="sxs-lookup"><span data-stu-id="411c8-218">Code.Text</span></span>
2. <span data-ttu-id="411c8-219">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="411c8-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="411c8-220">ClinicalStatus/VerificationStatus (leggiamo entrambi)</span><span class="sxs-lookup"><span data-stu-id="411c8-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="411c8-221">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere il campo seguente:</span><span class="sxs-lookup"><span data-stu-id="411c8-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="411c8-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="411c8-222">AssertedDate</span></span>
2. <span data-ttu-id="411c8-223">Nota. testo</span><span class="sxs-lookup"><span data-stu-id="411c8-223">Note.Text</span></span>
3. <span data-ttu-id="411c8-224">Reazione</span><span class="sxs-lookup"><span data-stu-id="411c8-224">Reaction</span></span>
    1. <span data-ttu-id="411c8-225">Sostanza (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="411c8-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="411c8-226">Manifestazione (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="411c8-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="411c8-227">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="411c8-228">Patient = \<id paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-228">Patient =  \<patient id></span></span>

<span data-ttu-id="411c8-229">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="411c8-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="411c8-230">Richiesta: ottenere <Fhir-Server>/AllergyIntolerance? patient =<ID paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="411c8-231">Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"risorsa": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "clinicalStatus": "attivo", "verificationStatus": "confermato", "codice": {"codifica": [{"System": "http://rxnav.nlm.nih.gov/REST/Ndfrt" "," codice ":" N0000175503 "," visualizzazione ":" solfonammide antibatterico ",}]," testo ":" solfonammide Ant ibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," reazione ": [{" manifestazione ": [{" codifica ": [{" System ":"http://snomed.info/sct"," codice ":" 271807003 "," display ":" rash cutaneo ",}]," testo ":" eruzione cutanea "}]</span><span class="sxs-lookup"><span data-stu-id="411c8-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="411c8-232">Per [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="411c8-233">Richiesta di farmaci</span><span class="sxs-lookup"><span data-stu-id="411c8-233">Medication Request</span></span>

<span data-ttu-id="411c8-234">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo di richiesta di base per i [farmaci USA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="411c8-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="411c8-235">Medicine. display (se di riferimento)</span><span class="sxs-lookup"><span data-stu-id="411c8-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="411c8-236">Medicine. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="411c8-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="411c8-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="411c8-237">AuthoredOn</span></span>
4. <span data-ttu-id="411c8-238">Requestr. Agent. display</span><span class="sxs-lookup"><span data-stu-id="411c8-238">Requester.Agent.Display</span></span>

<span data-ttu-id="411c8-239">Oltre ai campi principali degli Stati Uniti, per una grande esperienza utente l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="411c8-240">DosageInstruction[..]. Testo</span><span class="sxs-lookup"><span data-stu-id="411c8-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="411c8-241">Testo</span><span class="sxs-lookup"><span data-stu-id="411c8-241">Text</span></span>

<span data-ttu-id="411c8-242">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="411c8-243">patient =\<id paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-243">patient=\<patient id></span></span>
2. <span data-ttu-id="411c8-244">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="411c8-244">_count=\<max results></span></span>

<span data-ttu-id="411c8-245">Per [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="411c8-246">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="411c8-246">Coverage</span></span>

<span data-ttu-id="411c8-247">Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:</span><span class="sxs-lookup"><span data-stu-id="411c8-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="411c8-248">Raggruppamento, almeno un elemento con</span><span class="sxs-lookup"><span data-stu-id="411c8-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="411c8-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="411c8-249">GroupDisplay</span></span>
    2. <span data-ttu-id="411c8-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="411c8-250">PlanDisplay</span></span>
2. <span data-ttu-id="411c8-251">Periodo</span><span class="sxs-lookup"><span data-stu-id="411c8-251">Period</span></span>
3. <span data-ttu-id="411c8-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="411c8-252">SubscriberId</span></span>

<span data-ttu-id="411c8-253">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="411c8-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="411c8-254">Patient = \<id paziente></span><span class="sxs-lookup"><span data-stu-id="411c8-254">Patient = \<patient id></span></span>

<span data-ttu-id="411c8-255">Per [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="411c8-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
