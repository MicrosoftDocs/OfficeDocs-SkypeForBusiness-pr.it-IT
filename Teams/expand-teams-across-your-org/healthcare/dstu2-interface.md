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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772207"
---
# <a name="dstu2-interface-specification"></a>Specifica dell'interfaccia DSTU2

> [!NOTE]
> Efficace il 30 ottobre 2020, l'app patients è stata ritirata e sostituita dall' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams. Con gli elenchi, i team di assistenza nell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team per il monitoraggio generale dei pazienti. Vedere il modello di pazienti in elenchi per iniziare. Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md)

La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere. Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:

- [Paziente](#patient)
- [Osservazione](#observation)
- [Condizione](#condition)
- [Verificarsi](#encounter)
- [Intolleranza alle allergie](#allergyintolerance)
- [Copertura delle](#coverage)
- [Ordine dei farmaci](#medication-order)
- [Posizione](#location)

> [!NOTE]
> La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto. Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.

Le query dell'app Microsoft teams patients per più di una risorsa pubblicano un bundle (BATCH) di richieste per l'URL del server FHIR. Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Tutte le risorse FHIR seguenti devono essere accessibili tramite riferimento diretto alle risorse.

## <a name="conformance-minimum-required-field-set"></a>Set di campi obbligatori minimi di conformità

 Il server FHIR deve implementare l'istruzione di conformità per avere un riepilogo effettivo delle proprie funzionalità. Prevediamo i parametri seguenti in un server di FHIR DSTU2:

 - RESTO

    - Modalità
    - Interazione
    - Risorsa: digitare
    - Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot mentre sosteniamo più versioni).

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Per altre informazioni su questo set di campi, vedere.

## <a name="patient"></a>Paziente

Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi del [profilo del paziente Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

 - Name. Family
 - Name. given
 - Genere
 - Nascita
 - MRN (identificatore)

Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:

 - Name. use
 - Name. prefix
 - CareProvider (questo riferimento sulla risorsa paziente deve includere i campi visualizzati nell'esempio seguente).

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

Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:

 - ID
 - Family: Contains = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore).
 - given =\<substring>
 - nome =\<substring>
 - nascita = (corrispondenza esatta)
 - \_conteggio (numero massimo di risultati che devono essere restituiti) <br> La risposta deve contenere il numero totale di record restituiti come risultato della ricerca e il \_ conteggio verrà usato da PatientsApp per limitare la quantità di record restituiti.
 - Identifier =\<mrn>

L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:

- ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.
- MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe. Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR
- Nome
- Nascita

Vedere l'esempio seguente di questa chiamata.

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

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Per altre informazioni su questo set di campi, vedere.

## <a name="observation"></a>Osservazione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut Vital Signs:

 - Effettivo (data/ora o periodo)
 - Code. Coding. code
 - ValueQuantity. Value

Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:

 - Code. Coding. display
 - ValueQuantity. unit

Se si usano le osservazioni dei componenti, la stessa logica viene applicata per ogni osservazione del componente.

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id\>
 - Ordina: desc =\<field ex. date\>

L'obiettivo è quello di riuscire a recuperare gli ultimi segni vitali per un paziente, [VitalSigns. DSTU....] (osservazione?).

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

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Per altre informazioni su questo set di campi, vedere.

## <a name="condition"></a>Condizione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. Visualizzare

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

 - Data registrata
 - Gravità

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id>
 - _count =\<max results>

Vedere l'esempio seguente di questa chiamata:

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

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Per altre informazioni su questo set di campi, vedere.

## <a name="encounter"></a>Verificarsi

Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo degli incontri di base degli Stati Uniti:

 - Stato
 - Digitare [0]. Codifica [0]. Visualizzare

Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti

 - Periodo. inizio
 - Posizione [0]. Location. display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id>
 - _sort: desc =\<field ex. date>
 - _count =\<max results>

L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente. Ogni incontro fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione. Vedere l'esempio seguente di questa chiamata.

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

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Per altre informazioni su questo set di campi, vedere.

## <a name="allergyintolerance"></a>AllergyIntolerance

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut AllergyIntolerance:

 - Code. Text
 - Code. Coding [0]. Visualizzare
 - Stato

Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:

 - RecordedDate
 - Nota. testo
 - Reazione [..]. Sostanza. testo
 - Reazione [..]. Manifestazione [..]. Testo
 - Text. div

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - Paziente =  \<patient id>

Vedere l'esempio seguente di questa chiamata:

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

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Per altre informazioni su questo set di campi, vedere.

## <a name="medication-order"></a>Ordine dei farmaci

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut MedicationOrder:

 - DateWritten
 - Prescriber. display
 - Medicine. display (se di riferimento)
 - Medicine. Text (se Concept)

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

 - DateEnded
 - DosageInstruction. Text
 - Text. div

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id>
 - _count =\<max results>

Vedere l'esempio seguente di questa chiamata:

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

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Per altre informazioni su questo set di campi, vedere.

## <a name="coverage"></a>Copertura delle

Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:

 - Pagante

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id>

Vedere l'esempio seguente di questa chiamata:

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
    
[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Per altre informazioni su questo set di campi, vedere.

## <a name="location"></a>Posizione

Questa risorsa viene usata solo come riferimento nella risorsa [Encounter](#encounter) .

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Per altre informazioni su questo set di campi, vedere.
