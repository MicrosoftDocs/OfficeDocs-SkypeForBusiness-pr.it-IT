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
ms.openlocfilehash: 9282d6b6245b92a675c69ba1fcbf4ad726cdff62
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766899"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="5a0d4-103">Specifica dell'interfaccia STU3</span><span class="sxs-lookup"><span data-stu-id="5a0d4-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a0d4-104">**Efficace il 30 ottobre 2020 l'app patients sarà deprecata e gli utenti non potranno più installarla dall'app teams Store. Ti invitiamo a iniziare a usare l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams Today.**</span><span class="sxs-lookup"><span data-stu-id="5a0d4-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="5a0d4-105">I dati dell'app patients sono archiviati nella cassetta postale del gruppo del gruppo Office 365 che appoggia il team.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="5a0d4-106">Quando l'app patients viene ritirata, tutti i dati associati verranno mantenuti in questo gruppo, ma non sarà più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="5a0d4-107">Gli utenti correnti possono ricreare gli elenchi usando l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="5a0d4-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="5a0d4-108">L' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) è preinstallata per tutti gli utenti di teams ed è disponibile come scheda in ogni team e canale.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="5a0d4-109">Con gli elenchi, i team di integrità possono creare elenchi di pazienti usando il modello di pazienti incorporati, da zero o importando dati in Excel.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="5a0d4-110">Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="5a0d4-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="5a0d4-111">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="5a0d4-112">Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="5a0d4-113">Paziente</span><span class="sxs-lookup"><span data-stu-id="5a0d4-113">Patient</span></span>](#patient)
- [<span data-ttu-id="5a0d4-114">Osservazione</span><span class="sxs-lookup"><span data-stu-id="5a0d4-114">Observation</span></span>](#observation)
- [<span data-ttu-id="5a0d4-115">Condizione</span><span class="sxs-lookup"><span data-stu-id="5a0d4-115">Condition</span></span>](#condition)
- [<span data-ttu-id="5a0d4-116">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="5a0d4-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="5a0d4-117">Intolleranza alle allergie</span><span class="sxs-lookup"><span data-stu-id="5a0d4-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="5a0d4-118">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="5a0d4-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="5a0d4-119">[Istruzione farmaco](#medication-request) (sostituisce il MedicationOrder nella versione DSTU2 di PatientsApp)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="5a0d4-120">Posizione (le informazioni necessarie da questa risorsa possono essere incluse in Encounter)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="5a0d4-121">La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto); Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="5a0d4-122">Le query dell'app Microsoft teams patients per più risorse devono pubblicare un pacchetto (BATCH) di richieste per l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="5a0d4-123">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="5a0d4-124">Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="5a0d4-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="5a0d4-125">Istruzione Capability</span><span class="sxs-lookup"><span data-stu-id="5a0d4-125">Capability Statement</span></span>

<span data-ttu-id="5a0d4-126">Questi sono i campi obbligatori minimi:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="5a0d4-127">RESTO</span><span class="sxs-lookup"><span data-stu-id="5a0d4-127">REST</span></span>

    - <span data-ttu-id="5a0d4-128">Modalità</span><span class="sxs-lookup"><span data-stu-id="5a0d4-128">Mode</span></span>
    - <span data-ttu-id="5a0d4-129">Interazione</span><span class="sxs-lookup"><span data-stu-id="5a0d4-129">Interaction</span></span>
    - <span data-ttu-id="5a0d4-130">Risorsa: digitare</span><span class="sxs-lookup"><span data-stu-id="5a0d4-130">Resource: Type</span></span>
    - <span data-ttu-id="5a0d4-131">Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="5a0d4-132">FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot.)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="5a0d4-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="5a0d4-134">Paziente</span><span class="sxs-lookup"><span data-stu-id="5a0d4-134">Patient</span></span>

<span data-ttu-id="5a0d4-135">Ecco i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente Argonaut:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="5a0d4-136">Name. given</span><span class="sxs-lookup"><span data-stu-id="5a0d4-136">Name.Given</span></span>
 - <span data-ttu-id="5a0d4-137">Name. Family</span><span class="sxs-lookup"><span data-stu-id="5a0d4-137">Name.Family</span></span>
 - <span data-ttu-id="5a0d4-138">Genere</span><span class="sxs-lookup"><span data-stu-id="5a0d4-138">Gender</span></span>
 - <span data-ttu-id="5a0d4-139">Nascita</span><span class="sxs-lookup"><span data-stu-id="5a0d4-139">BirthDate</span></span>
 - <span data-ttu-id="5a0d4-140">MRN (identificatore)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-140">MRN (Identifier)</span></span>

<span data-ttu-id="5a0d4-141">Oltre ai [campi Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="5a0d4-142">Name. use</span><span class="sxs-lookup"><span data-stu-id="5a0d4-142">Name.Use</span></span>
 - <span data-ttu-id="5a0d4-143">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="5a0d4-143">Name.Prefix</span></span>
 - <span data-ttu-id="5a0d4-144">[GeneralPractitioner]-il riferimento GeneralPractitioner deve essere incluso nella risorsa paziente (solo campo di visualizzazione)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="5a0d4-145">Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="5a0d4-146">ID</span><span class="sxs-lookup"><span data-stu-id="5a0d4-146">id</span></span>
 - <span data-ttu-id="5a0d4-147">Family = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="5a0d4-148">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="5a0d4-148">given=\<substring></span></span>
 - <span data-ttu-id="5a0d4-149">nascita = (corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="5a0d4-150">Gender = (i valori sono uno degli amministratori-gender)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="5a0d4-151">\_conteggio (numero massimo di risultati che devono essere restituiti)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="5a0d4-152">La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e il \_ conteggio verrà usato da PatientsApp per limitare il numero di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="5a0d4-153">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="5a0d4-153">identifier=\<mrn></span></span>

<span data-ttu-id="5a0d4-154">L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="5a0d4-155">ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="5a0d4-156">MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="5a0d4-157">Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="5a0d4-158">Nome</span><span class="sxs-lookup"><span data-stu-id="5a0d4-158">Name</span></span>
- <span data-ttu-id="5a0d4-159">Nascita</span><span class="sxs-lookup"><span data-stu-id="5a0d4-159">Birthdate</span></span>

<span data-ttu-id="5a0d4-160">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-160">See the following example of the call:</span></span>

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

<span data-ttu-id="5a0d4-161">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="5a0d4-162">Osservazione</span><span class="sxs-lookup"><span data-stu-id="5a0d4-162">Observation</span></span>

<span data-ttu-id="5a0d4-163">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span><span class="sxs-lookup"><span data-stu-id="5a0d4-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="5a0d4-164">Effettivo (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="5a0d4-165">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="5a0d4-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="5a0d4-166">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="5a0d4-166">ValueQuantity.Value</span></span>

<span data-ttu-id="5a0d4-167">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="5a0d4-168">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="5a0d4-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="5a0d4-169">ValueQuantity. unit</span><span class="sxs-lookup"><span data-stu-id="5a0d4-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="5a0d4-170">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5a0d4-171">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5a0d4-171">patient=\<patient id></span></span>
 - <span data-ttu-id="5a0d4-172">_sort =-data</span><span class="sxs-lookup"><span data-stu-id="5a0d4-172">_sort=-date</span></span>
 - <span data-ttu-id="5a0d4-173">Category (verrà eseguita una query per "Category = Vital-Signs") per recuperare l'elenco dei segni vitali.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="5a0d4-174">Fare riferimento a questo esempio di chiamata:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="5a0d4-175">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="5a0d4-176">Condizione</span><span class="sxs-lookup"><span data-stu-id="5a0d4-176">Condition</span></span>

<span data-ttu-id="5a0d4-177">Ecco i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span><span class="sxs-lookup"><span data-stu-id="5a0d4-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="5a0d4-178">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="5a0d4-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="5a0d4-179">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="5a0d4-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="5a0d4-180">AssertedDate</span></span>
 - <span data-ttu-id="5a0d4-181">Gravità</span><span class="sxs-lookup"><span data-stu-id="5a0d4-181">Severity</span></span>

<span data-ttu-id="5a0d4-182">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5a0d4-183">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5a0d4-183">patient=\<patient id></span></span>
 - <span data-ttu-id="5a0d4-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="5a0d4-184">_count=\<max results></span></span>

<span data-ttu-id="5a0d4-185">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-185">See the following example of this call:</span></span>

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

<span data-ttu-id="5a0d4-186">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="5a0d4-187">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="5a0d4-187">Encounter</span></span>

<span data-ttu-id="5a0d4-188">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo di confronto degli Stati Uniti](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have".</span><span class="sxs-lookup"><span data-stu-id="5a0d4-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="5a0d4-189">Stato</span><span class="sxs-lookup"><span data-stu-id="5a0d4-189">Status</span></span>
 - <span data-ttu-id="5a0d4-190">Digitare [0]. Codifica [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="5a0d4-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="5a0d4-191">Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="5a0d4-192">Periodo. inizio</span><span class="sxs-lookup"><span data-stu-id="5a0d4-192">Period.Start</span></span>
 - <span data-ttu-id="5a0d4-193">Posizione [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="5a0d4-193">Location[0].Location.Display</span></span>

<span data-ttu-id="5a0d4-194">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5a0d4-195">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5a0d4-195">patient=\<patient id></span></span>
 - <span data-ttu-id="5a0d4-196">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="5a0d4-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="5a0d4-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="5a0d4-197">_count=\<max results></span></span>

<span data-ttu-id="5a0d4-198">L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="5a0d4-199">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-199">Each encounter references a location resource.</span></span> <span data-ttu-id="5a0d4-200">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="5a0d4-201">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="5a0d4-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="5a0d4-202">AllergyIntolerance</span></span>

<span data-ttu-id="5a0d4-203">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :</span><span class="sxs-lookup"><span data-stu-id="5a0d4-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="5a0d4-204">Code. Text</span><span class="sxs-lookup"><span data-stu-id="5a0d4-204">Code.Text</span></span>
 - <span data-ttu-id="5a0d4-205">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="5a0d4-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="5a0d4-206">ClinicalStatus/VerificationStatus (leggiamo entrambi)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="5a0d4-207">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere il campo seguente:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="5a0d4-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="5a0d4-208">AssertedDate</span></span>
 - <span data-ttu-id="5a0d4-209">Nota. testo</span><span class="sxs-lookup"><span data-stu-id="5a0d4-209">Note.Text</span></span>
 - <span data-ttu-id="5a0d4-210">Reazione</span><span class="sxs-lookup"><span data-stu-id="5a0d4-210">Reaction</span></span>
    - <span data-ttu-id="5a0d4-211">Sostanza (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="5a0d4-212">Manifestazione (un elemento di codifica)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="5a0d4-213">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5a0d4-214">Paziente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="5a0d4-214">Patient =  \<patient id></span></span>

<span data-ttu-id="5a0d4-215">Vedere l'esempio seguente della chiamata:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="5a0d4-216">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="5a0d4-217">Richiesta di farmaci</span><span class="sxs-lookup"><span data-stu-id="5a0d4-217">Medication Request</span></span>

<span data-ttu-id="5a0d4-218">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo di richiesta di base per i [farmaci USA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span><span class="sxs-lookup"><span data-stu-id="5a0d4-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="5a0d4-219">Medicine. display (se di riferimento)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="5a0d4-220">Medicine. Text (se CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="5a0d4-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="5a0d4-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="5a0d4-221">AuthoredOn</span></span>
 - <span data-ttu-id="5a0d4-222">Requestr. Agent. display</span><span class="sxs-lookup"><span data-stu-id="5a0d4-222">Requester.Agent.Display</span></span>

<span data-ttu-id="5a0d4-223">Oltre ai campi principali degli Stati Uniti, per una grande esperienza utente l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="5a0d4-224">DosageInstruction[..]. Testo</span><span class="sxs-lookup"><span data-stu-id="5a0d4-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="5a0d4-225">Testo</span><span class="sxs-lookup"><span data-stu-id="5a0d4-225">Text</span></span>

<span data-ttu-id="5a0d4-226">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5a0d4-227">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="5a0d4-227">patient=\<patient id></span></span>
 - <span data-ttu-id="5a0d4-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="5a0d4-228">_count=\<max results></span></span>

<span data-ttu-id="5a0d4-229">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="5a0d4-230">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="5a0d4-230">Coverage</span></span>

<span data-ttu-id="5a0d4-231">Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="5a0d4-232">Raggruppamento, almeno un elemento con</span><span class="sxs-lookup"><span data-stu-id="5a0d4-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="5a0d4-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="5a0d4-233">GroupDisplay</span></span>
    - <span data-ttu-id="5a0d4-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="5a0d4-234">PlanDisplay</span></span>
 - <span data-ttu-id="5a0d4-235">Periodo</span><span class="sxs-lookup"><span data-stu-id="5a0d4-235">Period</span></span>
 - <span data-ttu-id="5a0d4-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="5a0d4-236">SubscriberId</span></span>

<span data-ttu-id="5a0d4-237">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a0d4-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="5a0d4-238">Paziente = \<patient id></span><span class="sxs-lookup"><span data-stu-id="5a0d4-238">Patient = \<patient id></span></span>

<span data-ttu-id="5a0d4-239">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="5a0d4-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
