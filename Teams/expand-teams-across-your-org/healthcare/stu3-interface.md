---
title: Interfaccia STU3 per l'integrazione dell'app Patients e dell'EHR
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
description: Informazioni sull'integrazione di Electronic Health Records nell'app Microsoft Teams Patients e nella specifica dell'interfaccia STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803494"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="cc31b-103">Specifica dell'interfaccia STU3</span><span class="sxs-lookup"><span data-stu-id="cc31b-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="cc31b-104">A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span><span class="sxs-lookup"><span data-stu-id="cc31b-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="cc31b-105">I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team.</span><span class="sxs-lookup"><span data-stu-id="cc31b-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="cc31b-106">Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cc31b-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="cc31b-107">Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="cc31b-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="cc31b-108">Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="cc31b-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="cc31b-109">Estrai il modello Coordinamento pazienti in Elenchi per iniziare.</span><span class="sxs-lookup"><span data-stu-id="cc31b-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="cc31b-110">Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="cc31b-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="cc31b-111">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft Teams Patients richiede la comprensione dei dati a cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="cc31b-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="cc31b-112">Il server FHIR deve supportare le richieste POST usando bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="cc31b-113">Paziente</span><span class="sxs-lookup"><span data-stu-id="cc31b-113">Patient</span></span>](#patient)
- [<span data-ttu-id="cc31b-114">Osservazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-114">Observation</span></span>](#observation)
- [<span data-ttu-id="cc31b-115">Condizione</span><span class="sxs-lookup"><span data-stu-id="cc31b-115">Condition</span></span>](#condition)
- [<span data-ttu-id="cc31b-116">Incontro</span><span class="sxs-lookup"><span data-stu-id="cc31b-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="cc31b-117">Intolleranza allergia</span><span class="sxs-lookup"><span data-stu-id="cc31b-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="cc31b-118">Copertura</span><span class="sxs-lookup"><span data-stu-id="cc31b-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="cc31b-119">[Dichiarazione sui farmaci](#medication-request) (sostituisce l'ordine dei farmaci nella versione DSTU2 della PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="cc31b-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="cc31b-120">Posizione (le informazioni necessarie per questa risorsa possono essere incluse in Encounter)</span><span class="sxs-lookup"><span data-stu-id="cc31b-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="cc31b-121">La risorsa Paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto); Tuttavia, è consigliabile che il partner implementi il supporto per tutte le risorse menzionate sopra in base alle specifiche fornite di seguito per la migliore esperienza dell'utente finale con l'app Microsoft Teams Patients.</span><span class="sxs-lookup"><span data-stu-id="cc31b-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="cc31b-122">Le query dell'app Microsoft Teams Patients per più risorse pubblicano un pacchetto (BATCH) di richieste all'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="cc31b-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="cc31b-123">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="cc31b-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="cc31b-124">Per altre informazioni ed esempi, vedere [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="cc31b-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="cc31b-125">Dichiarazione di funzionalità</span><span class="sxs-lookup"><span data-stu-id="cc31b-125">Capability Statement</span></span>

<span data-ttu-id="cc31b-126">Questi sono i campi obbligatori minimi:</span><span class="sxs-lookup"><span data-stu-id="cc31b-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="cc31b-127">RESTO</span><span class="sxs-lookup"><span data-stu-id="cc31b-127">REST</span></span>

    - <span data-ttu-id="cc31b-128">Modalità</span><span class="sxs-lookup"><span data-stu-id="cc31b-128">Mode</span></span>
    - <span data-ttu-id="cc31b-129">Interazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-129">Interaction</span></span>
    - <span data-ttu-id="cc31b-130">Risorsa: Tipo</span><span class="sxs-lookup"><span data-stu-id="cc31b-130">Resource: Type</span></span>
    - <span data-ttu-id="cc31b-131">Sicurezza: [estensione per GLI URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="cc31b-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="cc31b-132">FhirVersion (Il codice richiede questa operazione per comprendere la versione in cui è necessario eseguire il pivot).</span><span class="sxs-lookup"><span data-stu-id="cc31b-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="cc31b-133">Vedere [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="cc31b-134">Paziente</span><span class="sxs-lookup"><span data-stu-id="cc31b-134">Patient</span></span>

<span data-ttu-id="cc31b-135">Ecco i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente di Argonaut:Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span><span class="sxs-lookup"><span data-stu-id="cc31b-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="cc31b-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="cc31b-136">Name.Given</span></span>
 - <span data-ttu-id="cc31b-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="cc31b-137">Name.Family</span></span>
 - <span data-ttu-id="cc31b-138">Sesso</span><span class="sxs-lookup"><span data-stu-id="cc31b-138">Gender</span></span>
 - <span data-ttu-id="cc31b-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="cc31b-139">BirthDate</span></span>
 - <span data-ttu-id="cc31b-140">MRN (Identificatore)</span><span class="sxs-lookup"><span data-stu-id="cc31b-140">MRN (Identifier)</span></span>

<span data-ttu-id="cc31b-141">Oltre ai campi [di Argonaut,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="cc31b-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="cc31b-142">Name.Use</span></span>
 - <span data-ttu-id="cc31b-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="cc31b-143">Name.Prefix</span></span>
 - <span data-ttu-id="cc31b-144">[GeneralPractitioner] - Il riferimento GeneralPractitioner deve essere incluso nella risorsa Paziente (solo campo di visualizzazione)</span><span class="sxs-lookup"><span data-stu-id="cc31b-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="cc31b-145">Una ricerca di risorse usa il metodo POST in /Patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="cc31b-146">id</span><span class="sxs-lookup"><span data-stu-id="cc31b-146">id</span></span>
 - <span data-ttu-id="cc31b-147">family=(cerca tutti i pazienti il cui nome di famiglia contiene il valore)</span><span class="sxs-lookup"><span data-stu-id="cc31b-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="cc31b-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="cc31b-148">given=\<substring></span></span>
 - <span data-ttu-id="cc31b-149">datadi nascita=(corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="cc31b-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="cc31b-150">gender=(i valori sono uno dei valori di administrative-gender)</span><span class="sxs-lookup"><span data-stu-id="cc31b-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="cc31b-151">\_count (numero massimo di risultati da restituire)</span><span class="sxs-lookup"><span data-stu-id="cc31b-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="cc31b-152">La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e il conteggio verrà usato dalla PatientsApp per limitare il numero \_ di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="cc31b-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="cc31b-153">identificatore=\<mrn></span><span class="sxs-lookup"><span data-stu-id="cc31b-153">identifier=\<mrn></span></span>

<span data-ttu-id="cc31b-154">L'obiettivo è quello di poter cercare e filtrare un paziente in base a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cc31b-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="cc31b-155">ID: ID risorsa di ogni risorsa in FHIR.</span><span class="sxs-lookup"><span data-stu-id="cc31b-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="cc31b-156">MRN: questo è l'identificatore effettivo del paziente che il personale clinico conoscerebbe.</span><span class="sxs-lookup"><span data-stu-id="cc31b-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="cc31b-157">Sappiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.</span><span class="sxs-lookup"><span data-stu-id="cc31b-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="cc31b-158">Nome</span><span class="sxs-lookup"><span data-stu-id="cc31b-158">Name</span></span>
- <span data-ttu-id="cc31b-159">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="cc31b-159">Birthdate</span></span>

<span data-ttu-id="cc31b-160">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="cc31b-160">See the following example of the call:</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

<span data-ttu-id="cc31b-161">Vedere [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="cc31b-162">Osservazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-162">Observation</span></span>

<span data-ttu-id="cc31b-163">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Vital-Signs Argonaut.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)</span><span class="sxs-lookup"><span data-stu-id="cc31b-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="cc31b-164">Validità (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="cc31b-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="cc31b-165">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="cc31b-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="cc31b-166">ValoreQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="cc31b-166">ValueQuantity.Value</span></span>

<span data-ttu-id="cc31b-167">Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="cc31b-168">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="cc31b-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="cc31b-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="cc31b-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="cc31b-170">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="cc31b-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="cc31b-171">patient=\<patient id></span></span>
 - <span data-ttu-id="cc31b-172">_sort=-date</span><span class="sxs-lookup"><span data-stu-id="cc31b-172">_sort=-date</span></span>
 - <span data-ttu-id="cc31b-173">category (verrà eseguita una query per "category=vital-signs") per recuperare l'elenco dei segni vitali.</span><span class="sxs-lookup"><span data-stu-id="cc31b-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="cc31b-174">Fare riferimento a questo esempio della chiamata:</span><span class="sxs-lookup"><span data-stu-id="cc31b-174">Refer to this example of the call:</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="cc31b-175">Vedere [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="cc31b-176">Condizione</span><span class="sxs-lookup"><span data-stu-id="cc31b-176">Condition</span></span>

<span data-ttu-id="cc31b-177">Ecco i campi obbligatori minimi, che sono un sottoinsieme del profilo condizione [di Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="cc31b-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="cc31b-178">Code.Coding[0]. Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="cc31b-179">Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="cc31b-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="cc31b-180">AssertedDate</span></span>
 - <span data-ttu-id="cc31b-181">Gravità</span><span class="sxs-lookup"><span data-stu-id="cc31b-181">Severity</span></span>

<span data-ttu-id="cc31b-182">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="cc31b-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="cc31b-183">patient=\<patient id></span></span>
 - <span data-ttu-id="cc31b-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="cc31b-184">_count=\<max results></span></span>

<span data-ttu-id="cc31b-185">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="cc31b-185">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="cc31b-186">Vedere [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="cc31b-187">Incontro</span><span class="sxs-lookup"><span data-stu-id="cc31b-187">Encounter</span></span>

<span data-ttu-id="cc31b-188">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo Us [Core Encounter.](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)</span><span class="sxs-lookup"><span data-stu-id="cc31b-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="cc31b-189">Stato</span><span class="sxs-lookup"><span data-stu-id="cc31b-189">Status</span></span>
 - <span data-ttu-id="cc31b-190">Type[0]. Codifica[0]. Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="cc31b-191">Inoltre, i campi seguenti dei campi "must support" del profilo Us Core Encounter:</span><span class="sxs-lookup"><span data-stu-id="cc31b-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="cc31b-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="cc31b-192">Period.Start</span></span>
 - <span data-ttu-id="cc31b-193">Location[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="cc31b-193">Location[0].Location.Display</span></span>

<span data-ttu-id="cc31b-194">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="cc31b-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="cc31b-195">patient=\<patient id></span></span>
 - <span data-ttu-id="cc31b-196">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="cc31b-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="cc31b-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="cc31b-197">_count=\<max results></span></span>

<span data-ttu-id="cc31b-198">L'obiettivo è recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="cc31b-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="cc31b-199">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="cc31b-199">Each encounter references a location resource.</span></span> <span data-ttu-id="cc31b-200">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="cc31b-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="cc31b-201">Vedere [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="cc31b-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="cc31b-202">AllergyIntolerance</span></span>

<span data-ttu-id="cc31b-203">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Disarginamentoargia Argonaut:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)</span><span class="sxs-lookup"><span data-stu-id="cc31b-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="cc31b-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="cc31b-204">Code.Text</span></span>
 - <span data-ttu-id="cc31b-205">Code.Coding[0]. Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="cc31b-206">ClinicalStatus/VerificationStatus (leggiamo entrambi)</span><span class="sxs-lookup"><span data-stu-id="cc31b-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="cc31b-207">Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere il campo seguente:</span><span class="sxs-lookup"><span data-stu-id="cc31b-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="cc31b-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="cc31b-208">AssertedDate</span></span>
 - <span data-ttu-id="cc31b-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="cc31b-209">Note.Text</span></span>
 - <span data-ttu-id="cc31b-210">Reazione</span><span class="sxs-lookup"><span data-stu-id="cc31b-210">Reaction</span></span>
    - <span data-ttu-id="cc31b-211">Sostanza (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="cc31b-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="cc31b-212">Manifestazione (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="cc31b-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="cc31b-213">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="cc31b-214">Paziente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="cc31b-214">Patient =  \<patient id></span></span>

<span data-ttu-id="cc31b-215">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="cc31b-215">See the following example of the call:</span></span> 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="cc31b-216">Vedere [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="cc31b-217">Richiesta di farmaci</span><span class="sxs-lookup"><span data-stu-id="cc31b-217">Medication Request</span></span>

<span data-ttu-id="cc31b-218">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo della richiesta di farmaci di base [negli Stati Uniti:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)</span><span class="sxs-lookup"><span data-stu-id="cc31b-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="cc31b-219">Medication.Display (se Reference)</span><span class="sxs-lookup"><span data-stu-id="cc31b-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="cc31b-220">Medication.Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="cc31b-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="cc31b-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="cc31b-221">AuthoredOn</span></span>
 - <span data-ttu-id="cc31b-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="cc31b-222">Requester.Agent.Display</span></span>

<span data-ttu-id="cc31b-223">Oltre ai campi di base degli Stati Uniti, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="cc31b-224">DosageInstruction[..]. Testo</span><span class="sxs-lookup"><span data-stu-id="cc31b-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="cc31b-225">Testo</span><span class="sxs-lookup"><span data-stu-id="cc31b-225">Text</span></span>

<span data-ttu-id="cc31b-226">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="cc31b-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="cc31b-227">patient=\<patient id></span></span>
 - <span data-ttu-id="cc31b-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="cc31b-228">_count=\<max results></span></span>

<span data-ttu-id="cc31b-229">Vedere [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="cc31b-230">Copertura</span><span class="sxs-lookup"><span data-stu-id="cc31b-230">Coverage</span></span>

<span data-ttu-id="cc31b-231">Questi sono i campi minimi obbligatori, non coperti dai profili Us Core o Argonaut:</span><span class="sxs-lookup"><span data-stu-id="cc31b-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="cc31b-232">Raggruppamento, almeno un elemento con</span><span class="sxs-lookup"><span data-stu-id="cc31b-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="cc31b-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="cc31b-233">GroupDisplay</span></span>
    - <span data-ttu-id="cc31b-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="cc31b-234">PlanDisplay</span></span>
 - <span data-ttu-id="cc31b-235">Periodo</span><span class="sxs-lookup"><span data-stu-id="cc31b-235">Period</span></span>
 - <span data-ttu-id="cc31b-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="cc31b-236">SubscriberId</span></span>

<span data-ttu-id="cc31b-237">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc31b-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="cc31b-238">Paziente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="cc31b-238">Patient = \<patient id></span></span>

<span data-ttu-id="cc31b-239">Vedere [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) per altri dettagli su questo set di campi.</span><span class="sxs-lookup"><span data-stu-id="cc31b-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
