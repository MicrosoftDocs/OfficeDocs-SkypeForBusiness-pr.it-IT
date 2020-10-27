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
ms.openlocfilehash: d29dab88f6ee53eb4c758f6c95f71278e20ecdbe
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766979"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="bcdf9-103">Specifica dell'interfaccia DSTU2</span><span class="sxs-lookup"><span data-stu-id="bcdf9-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcdf9-104">**Efficace il 30 ottobre 2020 l'app patients sarà deprecata e gli utenti non potranno più installarla dall'app teams Store. Ti invitiamo a iniziare a usare l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams Today.**</span><span class="sxs-lookup"><span data-stu-id="bcdf9-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="bcdf9-105">I dati dell'app patients sono archiviati nella cassetta postale del gruppo del gruppo Office 365 che appoggia il team.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="bcdf9-106">Quando l'app patients viene ritirata, tutti i dati associati verranno mantenuti in questo gruppo, ma non sarà più possibile accedervi tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="bcdf9-107">Gli utenti correnti possono ricreare gli elenchi usando l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="bcdf9-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="bcdf9-108">L' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) è preinstallata per tutti gli utenti di teams ed è disponibile come scheda in ogni team e canale.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="bcdf9-109">Con gli elenchi, i team di integrità possono creare elenchi di pazienti usando il modello di pazienti incorporati, da zero o importando dati in Excel.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="bcdf9-110">Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="bcdf9-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="bcdf9-111">La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="bcdf9-112">Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="bcdf9-113">Paziente</span><span class="sxs-lookup"><span data-stu-id="bcdf9-113">Patient</span></span>](#patient)
- [<span data-ttu-id="bcdf9-114">Osservazione</span><span class="sxs-lookup"><span data-stu-id="bcdf9-114">Observation</span></span>](#observation)
- [<span data-ttu-id="bcdf9-115">Condizione</span><span class="sxs-lookup"><span data-stu-id="bcdf9-115">Condition</span></span>](#condition)
- [<span data-ttu-id="bcdf9-116">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="bcdf9-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="bcdf9-117">Intolleranza alle allergie</span><span class="sxs-lookup"><span data-stu-id="bcdf9-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="bcdf9-118">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="bcdf9-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="bcdf9-119">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="bcdf9-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="bcdf9-120">Posizione</span><span class="sxs-lookup"><span data-stu-id="bcdf9-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="bcdf9-121">La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="bcdf9-122">Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="bcdf9-123">Le query dell'app Microsoft teams patients per più di una risorsa pubblicano un bundle (BATCH) di richieste per l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="bcdf9-124">Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="bcdf9-125">Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .</span><span class="sxs-lookup"><span data-stu-id="bcdf9-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="bcdf9-126">Tutte le risorse FHIR seguenti devono essere accessibili tramite riferimento diretto alle risorse.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="bcdf9-127">Set di campi obbligatori minimi di conformità</span><span class="sxs-lookup"><span data-stu-id="bcdf9-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="bcdf9-128">Il server FHIR deve implementare l'istruzione di conformità per avere un riepilogo effettivo delle proprie funzionalità.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="bcdf9-129">Prevediamo i parametri seguenti in un server di FHIR DSTU2:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="bcdf9-130">RESTO</span><span class="sxs-lookup"><span data-stu-id="bcdf9-130">REST</span></span>

    - <span data-ttu-id="bcdf9-131">Modalità</span><span class="sxs-lookup"><span data-stu-id="bcdf9-131">Mode</span></span>
    - <span data-ttu-id="bcdf9-132">Interazione</span><span class="sxs-lookup"><span data-stu-id="bcdf9-132">Interaction</span></span>
    - <span data-ttu-id="bcdf9-133">Risorsa: digitare</span><span class="sxs-lookup"><span data-stu-id="bcdf9-133">Resource: Type</span></span>
    - <span data-ttu-id="bcdf9-134">Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="bcdf9-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="bcdf9-135">FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot mentre sosteniamo più versioni).</span><span class="sxs-lookup"><span data-stu-id="bcdf9-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="bcdf9-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="bcdf9-137">Paziente</span><span class="sxs-lookup"><span data-stu-id="bcdf9-137">Patient</span></span>

<span data-ttu-id="bcdf9-138">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi del [profilo del paziente Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="bcdf9-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="bcdf9-139">Name. Family</span><span class="sxs-lookup"><span data-stu-id="bcdf9-139">Name.Family</span></span>
 - <span data-ttu-id="bcdf9-140">Name. given</span><span class="sxs-lookup"><span data-stu-id="bcdf9-140">Name.Given</span></span>
 - <span data-ttu-id="bcdf9-141">Genere</span><span class="sxs-lookup"><span data-stu-id="bcdf9-141">Gender</span></span>
 - <span data-ttu-id="bcdf9-142">Nascita</span><span class="sxs-lookup"><span data-stu-id="bcdf9-142">BirthDate</span></span>
 - <span data-ttu-id="bcdf9-143">MRN (identificatore)</span><span class="sxs-lookup"><span data-stu-id="bcdf9-143">MRN (Identifier)</span></span>

<span data-ttu-id="bcdf9-144">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="bcdf9-145">Name. use</span><span class="sxs-lookup"><span data-stu-id="bcdf9-145">Name.Use</span></span>
 - <span data-ttu-id="bcdf9-146">Name. prefix</span><span class="sxs-lookup"><span data-stu-id="bcdf9-146">Name.Prefix</span></span>
 - <span data-ttu-id="bcdf9-147">CareProvider (questo riferimento sulla risorsa paziente deve includere i campi visualizzati nell'esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="bcdf9-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="bcdf9-148">Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="bcdf9-149">ID</span><span class="sxs-lookup"><span data-stu-id="bcdf9-149">id</span></span>
 - <span data-ttu-id="bcdf9-150">Family: Contains = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore).</span><span class="sxs-lookup"><span data-stu-id="bcdf9-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="bcdf9-151">given =\<substring></span><span class="sxs-lookup"><span data-stu-id="bcdf9-151">given=\<substring></span></span>
 - <span data-ttu-id="bcdf9-152">nome =\<substring></span><span class="sxs-lookup"><span data-stu-id="bcdf9-152">name=\<substring></span></span>
 - <span data-ttu-id="bcdf9-153">nascita = (corrispondenza esatta)</span><span class="sxs-lookup"><span data-stu-id="bcdf9-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="bcdf9-154">\_conteggio (numero massimo di risultati che devono essere restituiti)</span><span class="sxs-lookup"><span data-stu-id="bcdf9-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="bcdf9-155">La risposta deve contenere il numero totale di record restituiti come risultato della ricerca e il \_ conteggio verrà usato da PatientsApp per limitare la quantità di record restituiti.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="bcdf9-156">Identifier =\<mrn></span><span class="sxs-lookup"><span data-stu-id="bcdf9-156">identifier=\<mrn></span></span>

<span data-ttu-id="bcdf9-157">L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="bcdf9-158">ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="bcdf9-159">MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="bcdf9-160">Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR</span><span class="sxs-lookup"><span data-stu-id="bcdf9-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="bcdf9-161">Nome</span><span class="sxs-lookup"><span data-stu-id="bcdf9-161">Name</span></span>
- <span data-ttu-id="bcdf9-162">Nascita</span><span class="sxs-lookup"><span data-stu-id="bcdf9-162">Birthdate</span></span>

<span data-ttu-id="bcdf9-163">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="bcdf9-164">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="bcdf9-165">Osservazione</span><span class="sxs-lookup"><span data-stu-id="bcdf9-165">Observation</span></span>

<span data-ttu-id="bcdf9-166">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut Vital Signs:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="bcdf9-167">Effettivo (data/ora o periodo)</span><span class="sxs-lookup"><span data-stu-id="bcdf9-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="bcdf9-168">Code. Coding. code</span><span class="sxs-lookup"><span data-stu-id="bcdf9-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="bcdf9-169">ValueQuantity. Value</span><span class="sxs-lookup"><span data-stu-id="bcdf9-169">ValueQuantity.Value</span></span>

<span data-ttu-id="bcdf9-170">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="bcdf9-171">Code. Coding. display</span><span class="sxs-lookup"><span data-stu-id="bcdf9-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="bcdf9-172">ValueQuantity. unit</span><span class="sxs-lookup"><span data-stu-id="bcdf9-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="bcdf9-173">Se si usano le osservazioni dei componenti, la stessa logica viene applicata per ogni osservazione del componente.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="bcdf9-174">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bcdf9-175">paziente =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="bcdf9-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="bcdf9-176">Ordina: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="bcdf9-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="bcdf9-177">L'obiettivo è quello di riuscire a recuperare gli ultimi segni vitali per un paziente, [VitalSigns. DSTU....] (osservazione?).</span><span class="sxs-lookup"><span data-stu-id="bcdf9-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="bcdf9-178">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="bcdf9-179">Condizione</span><span class="sxs-lookup"><span data-stu-id="bcdf9-179">Condition</span></span>

<span data-ttu-id="bcdf9-180">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span><span class="sxs-lookup"><span data-stu-id="bcdf9-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="bcdf9-181">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="bcdf9-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="bcdf9-182">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="bcdf9-183">Data registrata</span><span class="sxs-lookup"><span data-stu-id="bcdf9-183">Date Recorded</span></span>
 - <span data-ttu-id="bcdf9-184">Gravità</span><span class="sxs-lookup"><span data-stu-id="bcdf9-184">Severity</span></span>

<span data-ttu-id="bcdf9-185">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bcdf9-186">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bcdf9-186">patient=\<patient id></span></span>
 - <span data-ttu-id="bcdf9-187">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="bcdf9-187">_count=\<max results></span></span>

<span data-ttu-id="bcdf9-188">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-188">See the following example of this call:</span></span>

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

<span data-ttu-id="bcdf9-189">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="bcdf9-190">Verificarsi</span><span class="sxs-lookup"><span data-stu-id="bcdf9-190">Encounter</span></span>

<span data-ttu-id="bcdf9-191">Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo degli incontri di base degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="bcdf9-192">Stato</span><span class="sxs-lookup"><span data-stu-id="bcdf9-192">Status</span></span>
 - <span data-ttu-id="bcdf9-193">Digitare [0]. Codifica [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="bcdf9-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="bcdf9-194">Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="bcdf9-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="bcdf9-195">Periodo. inizio</span><span class="sxs-lookup"><span data-stu-id="bcdf9-195">Period.Start</span></span>
 - <span data-ttu-id="bcdf9-196">Posizione [0]. Location. display</span><span class="sxs-lookup"><span data-stu-id="bcdf9-196">Location[0].Location.Display</span></span>

<span data-ttu-id="bcdf9-197">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bcdf9-198">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bcdf9-198">patient=\<patient id></span></span>
 - <span data-ttu-id="bcdf9-199">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="bcdf9-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="bcdf9-200">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="bcdf9-200">_count=\<max results></span></span>

<span data-ttu-id="bcdf9-201">L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="bcdf9-202">Ogni incontro fa riferimento a una risorsa posizione.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-202">Each encounter references a location resource.</span></span> <span data-ttu-id="bcdf9-203">Il riferimento deve includere anche il campo di visualizzazione della posizione.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="bcdf9-204">Vedere l'esempio seguente di questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-204">See the following example of this call.</span></span>

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

<span data-ttu-id="bcdf9-205">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="bcdf9-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="bcdf9-206">AllergyIntolerance</span></span>

<span data-ttu-id="bcdf9-207">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut AllergyIntolerance:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="bcdf9-208">Code. Text</span><span class="sxs-lookup"><span data-stu-id="bcdf9-208">Code.Text</span></span>
 - <span data-ttu-id="bcdf9-209">Code. Coding [0]. Visualizzare</span><span class="sxs-lookup"><span data-stu-id="bcdf9-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="bcdf9-210">Stato</span><span class="sxs-lookup"><span data-stu-id="bcdf9-210">Status</span></span>

<span data-ttu-id="bcdf9-211">Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="bcdf9-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="bcdf9-212">RecordedDate</span></span>
 - <span data-ttu-id="bcdf9-213">Nota. testo</span><span class="sxs-lookup"><span data-stu-id="bcdf9-213">Note.Text</span></span>
 - <span data-ttu-id="bcdf9-214">Reazione [..]. Sostanza. testo</span><span class="sxs-lookup"><span data-stu-id="bcdf9-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="bcdf9-215">Reazione [..]. Manifestazione [..]. Testo</span><span class="sxs-lookup"><span data-stu-id="bcdf9-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="bcdf9-216">Text. div</span><span class="sxs-lookup"><span data-stu-id="bcdf9-216">Text.Div</span></span>

<span data-ttu-id="bcdf9-217">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bcdf9-218">Paziente =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="bcdf9-218">Patient =  \<patient id></span></span>

<span data-ttu-id="bcdf9-219">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-219">See the following example of this call:</span></span>

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

<span data-ttu-id="bcdf9-220">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="bcdf9-221">Ordine dei farmaci</span><span class="sxs-lookup"><span data-stu-id="bcdf9-221">Medication Order</span></span>

<span data-ttu-id="bcdf9-222">Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut MedicationOrder:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="bcdf9-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="bcdf9-223">DateWritten</span></span>
 - <span data-ttu-id="bcdf9-224">Prescriber. display</span><span class="sxs-lookup"><span data-stu-id="bcdf9-224">Prescriber.Display</span></span>
 - <span data-ttu-id="bcdf9-225">Medicine. display (se di riferimento)</span><span class="sxs-lookup"><span data-stu-id="bcdf9-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="bcdf9-226">Medicine. Text (se Concept)</span><span class="sxs-lookup"><span data-stu-id="bcdf9-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="bcdf9-227">Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="bcdf9-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="bcdf9-228">DateEnded</span></span>
 - <span data-ttu-id="bcdf9-229">DosageInstruction. Text</span><span class="sxs-lookup"><span data-stu-id="bcdf9-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="bcdf9-230">Text. div</span><span class="sxs-lookup"><span data-stu-id="bcdf9-230">Text.Div</span></span>

<span data-ttu-id="bcdf9-231">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bcdf9-232">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bcdf9-232">patient=\<patient id></span></span>
 - <span data-ttu-id="bcdf9-233">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="bcdf9-233">_count=\<max results></span></span>

<span data-ttu-id="bcdf9-234">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-234">See the following example of this call:</span></span>

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

<span data-ttu-id="bcdf9-235">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="bcdf9-236">Copertura delle</span><span class="sxs-lookup"><span data-stu-id="bcdf9-236">Coverage</span></span>

<span data-ttu-id="bcdf9-237">Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="bcdf9-238">Pagante</span><span class="sxs-lookup"><span data-stu-id="bcdf9-238">Payor</span></span>

<span data-ttu-id="bcdf9-239">Una ricerca di risorse usa il metodo GET e i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bcdf9-240">paziente =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bcdf9-240">patient=\<patient id></span></span>

<span data-ttu-id="bcdf9-241">Vedere l'esempio seguente di questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="bcdf9-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="bcdf9-242">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="bcdf9-243">Posizione</span><span class="sxs-lookup"><span data-stu-id="bcdf9-243">Location</span></span>

<span data-ttu-id="bcdf9-244">Questa risorsa viene usata solo come riferimento nella risorsa [Encounter](#encounter) .</span><span class="sxs-lookup"><span data-stu-id="bcdf9-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="bcdf9-245">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Per altre informazioni su questo set di campi, vedere.</span><span class="sxs-lookup"><span data-stu-id="bcdf9-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
