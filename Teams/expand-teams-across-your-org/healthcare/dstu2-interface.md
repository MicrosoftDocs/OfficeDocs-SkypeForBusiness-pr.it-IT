---
title: Interfaccia DSTU2 per l'integrazione di Patients App ed EHR
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
description: Informazioni sulla specifica dell'interfaccia DSTU2 in Teams, tra cui la configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft Teams Patients.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803484"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="0a6f4-103">Specifica dell'interfaccia DSTU2</span><span class="sxs-lookup"><span data-stu-id="0a6f4-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="0a6f4-104">A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="0a6f4-105">I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="0a6f4-106">Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="0a6f4-107">Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="0a6f4-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="0a6f4-108">Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="0a6f4-109">Estrai il modello Coordinamento pazienti in Elenchi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="0a6f4-110">Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="0a6f4-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="0a6f4-111">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft Teams Patients richiede la comprensione dei dati a cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="0a6f4-112">Il server FHIR deve supportare le richieste POST usando bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="0a6f4-113">Paziente</span><span class="sxs-lookup"><span data-stu-id="0a6f4-113">Patient</span></span>](#patient)
- [<span data-ttu-id="0a6f4-114">Osservazione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-114">Observation</span></span>](#observation)
- [<span data-ttu-id="0a6f4-115">Condizione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-115">Condition</span></span>](#condition)
- [<span data-ttu-id="0a6f4-116">Incontro</span><span class="sxs-lookup"><span data-stu-id="0a6f4-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="0a6f4-117">Intolleranza allergia</span><span class="sxs-lookup"><span data-stu-id="0a6f4-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="0a6f4-118">Copertura</span><span class="sxs-lookup"><span data-stu-id="0a6f4-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="0a6f4-119">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="0a6f4-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="0a6f4-120">Posizione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="0a6f4-121">La risorsa Paziente è l'unica risorsa obbligatoria senza la quale l'app non verrà caricata.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="0a6f4-122">Tuttavia, è consigliabile che il partner implementi il supporto per tutte le risorse menzionate sopra in base alle specifiche fornite di seguito per la migliore esperienza dell'utente finale con l'app Microsoft Teams Patients.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="0a6f4-123">Query dall'app Microsoft Teams Patients per più risorse pubblicano un pacchetto (BATCH) di richieste all'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="0a6f4-124">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="0a6f4-125">Per altre informazioni ed esempi, vedere [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="0a6f4-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="0a6f4-126">Tutte le risorse FHIR seguenti devono essere accessibili tramite riferimento diretto alle risorse.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="0a6f4-127">Set di campi obbligatorio minimo di conformità</span><span class="sxs-lookup"><span data-stu-id="0a6f4-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="0a6f4-128">Il server FHIR deve implementare la dichiarazione di conformità per poter disporre di un riepilogo fattuale delle sue funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="0a6f4-129">In un server DSTU2 FHIR sono previsti i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="0a6f4-130">RESTO</span><span class="sxs-lookup"><span data-stu-id="0a6f4-130">REST</span></span>

    - <span data-ttu-id="0a6f4-131">Modalità</span><span class="sxs-lookup"><span data-stu-id="0a6f4-131">Mode</span></span>
    - <span data-ttu-id="0a6f4-132">Interazione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-132">Interaction</span></span>
    - <span data-ttu-id="0a6f4-133">Risorsa: Tipo</span><span class="sxs-lookup"><span data-stu-id="0a6f4-133">Resource: Type</span></span>
    - <span data-ttu-id="0a6f4-134">Sicurezza: [estensione per GLI URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="0a6f4-135">FhirVersion (Il nostro codice richiede questa operazione per comprendere la versione a cui è necessario eseguire il pivot mentre supportiamo più versioni).</span><span class="sxs-lookup"><span data-stu-id="0a6f4-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="0a6f4-136">Vedere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="0a6f4-137">Paziente</span><span class="sxs-lookup"><span data-stu-id="0a6f4-137">Patient</span></span>

<span data-ttu-id="0a6f4-138">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente di Argonaut:These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="0a6f4-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="0a6f4-139">Name.Family</span></span>
 - <span data-ttu-id="0a6f4-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="0a6f4-140">Name.Given</span></span>
 - <span data-ttu-id="0a6f4-141">Sesso</span><span class="sxs-lookup"><span data-stu-id="0a6f4-141">Gender</span></span>
 - <span data-ttu-id="0a6f4-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="0a6f4-142">BirthDate</span></span>
 - <span data-ttu-id="0a6f4-143">MRN (Identificatore)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-143">MRN (Identifier)</span></span>

<span data-ttu-id="0a6f4-144">Oltre ai campi di Argonaut, per un'esperienza utente ottimale l'app Pazienti legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="0a6f4-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="0a6f4-145">Name.Use</span></span>
 - <span data-ttu-id="0a6f4-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="0a6f4-146">Name.Prefix</span></span>
 - <span data-ttu-id="0a6f4-147">CareProvider (Questo riferimento nella risorsa Patient deve includere i campi visualizzati nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="0a6f4-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

<span data-ttu-id="0a6f4-148">Una ricerca di risorse usa il metodo POST in /Patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="0a6f4-149">id</span><span class="sxs-lookup"><span data-stu-id="0a6f4-149">id</span></span>
 - <span data-ttu-id="0a6f4-150">family:contains=(cerca tutti i pazienti il cui nome di famiglia contiene il valore).</span><span class="sxs-lookup"><span data-stu-id="0a6f4-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="0a6f4-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="0a6f4-151">given=\<substring></span></span>
 - <span data-ttu-id="0a6f4-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="0a6f4-152">name=\<substring></span></span>
 - <span data-ttu-id="0a6f4-153">datadi nascita=(corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="0a6f4-154">\_count (numero massimo di risultati da restituire)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="0a6f4-155">La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e il conteggio verrà usato dalla PatientsApp per limitare il numero \_ di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="0a6f4-156">identificatore=\<mrn></span><span class="sxs-lookup"><span data-stu-id="0a6f4-156">identifier=\<mrn></span></span>

<span data-ttu-id="0a6f4-157">L'obiettivo è quello di poter cercare e filtrare un paziente in base a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="0a6f4-158">ID: ID risorsa di ogni risorsa in FHIR.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="0a6f4-159">MRN: questo è l'identificatore effettivo del paziente che il personale clinico conoscerebbe.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="0a6f4-160">Sappiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR</span><span class="sxs-lookup"><span data-stu-id="0a6f4-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="0a6f4-161">Nome</span><span class="sxs-lookup"><span data-stu-id="0a6f4-161">Name</span></span>
- <span data-ttu-id="0a6f4-162">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="0a6f4-162">Birthdate</span></span>

<span data-ttu-id="0a6f4-163">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-163">See the following example  of this call.</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

<span data-ttu-id="0a6f4-164">Vedere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="0a6f4-165">Osservazione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-165">Observation</span></span>

<span data-ttu-id="0a6f4-166">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo dei segni vitali di Argonaut:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="0a6f4-167">Validità (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="0a6f4-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="0a6f4-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="0a6f4-169">ValoreQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="0a6f4-169">ValueQuantity.Value</span></span>

<span data-ttu-id="0a6f4-170">Oltre ai campi di Argonaut, per un'esperienza utente ottimale l'app Pazienti legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="0a6f4-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="0a6f4-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="0a6f4-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="0a6f4-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="0a6f4-173">Se si usano osservazioni di componenti, la stessa logica si applica per ogni osservazione dei componenti.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="0a6f4-174">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a6f4-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="0a6f4-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="0a6f4-176">sort:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="0a6f4-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="0a6f4-177">L'obiettivo è recuperare i segni vitali più recenti per un paziente, [VitalSigns.DSTU.saz] (osservazione?).</span><span class="sxs-lookup"><span data-stu-id="0a6f4-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="0a6f4-178">Vedere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="0a6f4-179">Condizione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-179">Condition</span></span>

<span data-ttu-id="0a6f4-180">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo condizione [di Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="0a6f4-181">Code.Coding[0]. Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="0a6f4-182">Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0a6f4-183">Data registrazione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-183">Date Recorded</span></span>
 - <span data-ttu-id="0a6f4-184">Gravità</span><span class="sxs-lookup"><span data-stu-id="0a6f4-184">Severity</span></span>

<span data-ttu-id="0a6f4-185">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a6f4-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a6f4-186">patient=\<patient id></span></span>
 - <span data-ttu-id="0a6f4-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="0a6f4-187">_count=\<max results></span></span>

<span data-ttu-id="0a6f4-188">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-188">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

<span data-ttu-id="0a6f4-189">Vedere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="0a6f4-190">Incontro</span><span class="sxs-lookup"><span data-stu-id="0a6f4-190">Encounter</span></span>

<span data-ttu-id="0a6f4-191">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo Us Core Encounter:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="0a6f4-192">Stato</span><span class="sxs-lookup"><span data-stu-id="0a6f4-192">Status</span></span>
 - <span data-ttu-id="0a6f4-193">Type[0]. Codifica[0]. Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="0a6f4-194">Inoltre, i campi seguenti dei campi "must support" del profilo Us Core Encounter</span><span class="sxs-lookup"><span data-stu-id="0a6f4-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="0a6f4-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="0a6f4-195">Period.Start</span></span>
 - <span data-ttu-id="0a6f4-196">Location[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="0a6f4-196">Location[0].Location.Display</span></span>

<span data-ttu-id="0a6f4-197">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a6f4-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a6f4-198">patient=\<patient id></span></span>
 - <span data-ttu-id="0a6f4-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="0a6f4-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="0a6f4-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="0a6f4-200">_count=\<max results></span></span>

<span data-ttu-id="0a6f4-201">L'obiettivo è recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="0a6f4-202">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-202">Each encounter references a location resource.</span></span> <span data-ttu-id="0a6f4-203">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="0a6f4-204">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-204">See the following example of this call.</span></span>

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="0a6f4-205">Vedere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="0a6f4-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="0a6f4-206">AllergyIntolerance</span></span>

<span data-ttu-id="0a6f4-207">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Disarginamentoargia Argonaut:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="0a6f4-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="0a6f4-208">Code.Text</span></span>
 - <span data-ttu-id="0a6f4-209">Code.Coding[0]. Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="0a6f4-210">Stato</span><span class="sxs-lookup"><span data-stu-id="0a6f4-210">Status</span></span>

<span data-ttu-id="0a6f4-211">Oltre ai campi di Argonaut, per un'esperienza utente ottimale l'app Pazienti legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="0a6f4-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="0a6f4-212">RecordedDate</span></span>
 - <span data-ttu-id="0a6f4-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="0a6f4-213">Note.Text</span></span>
 - <span data-ttu-id="0a6f4-214">Reaction[..]. Sostanza.Testo</span><span class="sxs-lookup"><span data-stu-id="0a6f4-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="0a6f4-215">Reaction[..]. Manifestazione[..]. Testo</span><span class="sxs-lookup"><span data-stu-id="0a6f4-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="0a6f4-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="0a6f4-216">Text.Div</span></span>

<span data-ttu-id="0a6f4-217">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a6f4-218">Paziente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="0a6f4-218">Patient =  \<patient id></span></span>

<span data-ttu-id="0a6f4-219">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-219">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="0a6f4-220">Vedere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="0a6f4-221">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="0a6f4-221">Medication Order</span></span>

<span data-ttu-id="0a6f4-222">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut MedicationOrder:These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="0a6f4-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="0a6f4-223">DateWritten</span></span>
 - <span data-ttu-id="0a6f4-224">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="0a6f4-224">Prescriber.Display</span></span>
 - <span data-ttu-id="0a6f4-225">Medication.Display (se riferimento)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="0a6f4-226">Farmaci.Testo (se concetto)</span><span class="sxs-lookup"><span data-stu-id="0a6f4-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="0a6f4-227">Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="0a6f4-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="0a6f4-228">DateEnded</span></span>
 - <span data-ttu-id="0a6f4-229">DoseInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="0a6f4-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="0a6f4-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="0a6f4-230">Text.Div</span></span>

<span data-ttu-id="0a6f4-231">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a6f4-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a6f4-232">patient=\<patient id></span></span>
 - <span data-ttu-id="0a6f4-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="0a6f4-233">_count=\<max results></span></span>

<span data-ttu-id="0a6f4-234">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-234">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="0a6f4-235">Vedere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="0a6f4-236">Copertura</span><span class="sxs-lookup"><span data-stu-id="0a6f4-236">Coverage</span></span>

<span data-ttu-id="0a6f4-237">Questi sono i campi minimi obbligatori, non coperti dai profili Us Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="0a6f4-238">Pagatore</span><span class="sxs-lookup"><span data-stu-id="0a6f4-238">Payor</span></span>

<span data-ttu-id="0a6f4-239">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="0a6f4-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="0a6f4-240">patient=\<patient id></span></span>

<span data-ttu-id="0a6f4-241">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="0a6f4-241">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
<span data-ttu-id="0a6f4-242">Vedere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="0a6f4-243">Posizione</span><span class="sxs-lookup"><span data-stu-id="0a6f4-243">Location</span></span>

<span data-ttu-id="0a6f4-244">Questa risorsa viene usata solo come riferimento nella [risorsa](#encounter) Incontro.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="0a6f4-245">Vedere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="0a6f4-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
