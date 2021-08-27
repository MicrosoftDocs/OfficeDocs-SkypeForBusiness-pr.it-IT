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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informazioni sull'integrazione di Electronic Health Records nell'app Microsoft Teams Patients e nella specifica dell'interfaccia STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 64fc61072510942b67d51542095a927e7e67c697
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582330"
---
# <a name="stu3-interface-specification"></a>Specifica dell'interfaccia STU3

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente. Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti. Estrai il modello Coordinamento pazienti in Elenchi per iniziare. Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).

La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft Teams Patients richiede la comprensione dei dati a cui l'app deve accedere. Il server FHIR deve supportare le richieste POST usando bundle per le risorse seguenti:

- [Paziente](#patient)
- [Osservazione](#observation)
- [Condizione](#condition)
- [Incontro](#encounter)
- [Intolleranza allergia](#allergyintolerance)
- [Copertura](#coverage)
- [Dichiarazione sui farmaci](#medication-request) (sostituisce l'ordine dei farmaci nella versione DSTU2 della PatientsApp)
- Posizione (le informazioni necessarie per questa risorsa possono essere incluse in Encounter)

> [!NOTE]
> La risorsa Paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto); Tuttavia, è consigliabile che il partner implementi il supporto per tutte le risorse menzionate sopra in base alle specifiche fornite di seguito per la migliore esperienza dell'utente finale con l'app Microsoft Teams Patients.

Le query dell'app Microsoft Teams Patients per più risorse pubblicano un pacchetto (BATCH) di richieste all'URL del server FHIR. Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, vedere [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Dichiarazione di funzionalità

Questi sono i campi obbligatori minimi:

 - RESTO

    - Modalità
    - Interazione
    - Risorsa: Tipo
    - Sicurezza: [estensione per GLI URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (Il codice richiede questa operazione per comprendere la versione in cui è necessario eseguire il pivot).

Vedere [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) per altri dettagli su questo set di campi.

## <a name="patient"></a>Paziente

Ecco i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente di Argonaut:Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:

 - Name.Given
 - Name.Family
 - Sesso
 - BirthDate
 - MRN (Identificatore)

Oltre ai campi [di Argonaut,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] - Il riferimento GeneralPractitioner deve essere incluso nella risorsa Paziente (solo campo di visualizzazione)

Una ricerca di risorse usa il metodo POST in /Patient/_search e i parametri seguenti:

 - id
 - family=(cerca tutti i pazienti il cui nome di famiglia contiene il valore)
 - given=\<substring>
 - datadi nascita=(corrispondenza esatta)
 - gender=(i valori sono uno dei valori di administrative-gender)
 - \_count (numero massimo di risultati da restituire) <br> La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e il conteggio verrà usato dalla PatientsApp per limitare il numero \_ di record restituiti.
 - identificatore=\<mrn>

L'obiettivo è quello di poter cercare e filtrare un paziente in base a quanto segue:

- ID: ID risorsa di ogni risorsa in FHIR.
- MRN: questo è l'identificatore effettivo del paziente che il personale clinico conoscerebbe. Sappiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.
- Nome
- Data di nascita

Vedere l'esempio seguente della chiamata:

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

Vedere [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) per altri dettagli su questo set di campi.

## <a name="observation"></a>Osservazione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Vital-Signs Argonaut.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Validità (data/ora o periodo)
 - Code.Coding.Code
 - ValoreQuantity.Value

Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - Code.Coding.Display
 - ValueQuantity.Unit

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _sort=-date
 - category (verrà eseguita una query per "category=vital-signs") per recuperare l'elenco dei segni vitali.

Fare riferimento a questo esempio della chiamata:

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

Vedere [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) per altri dettagli su questo set di campi.

## <a name="condition"></a>Condizione

Ecco i campi obbligatori minimi, che sono un sottoinsieme del profilo condizione [di Argonaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Visualizzazione

Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - AssertedDate
 - Gravità

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _count=\<max results>

Vedere l'esempio seguente di questa chiamata:

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

Vedere [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) per altri dettagli su questo set di campi.

## <a name="encounter"></a>Incontro

Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo Us [Core Encounter.](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)

 - Stato
 - Type[0]. Codifica[0]. Visualizzazione

Inoltre, i campi seguenti dei campi "must support" del profilo Us Core Encounter:

 - Period.Start
 - Location[0]. Location.Display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

L'obiettivo è recuperare l'ultima posizione nota del paziente. Ogni incontro fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione.

Vedere [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) per altri dettagli su questo set di campi.

## <a name="allergyintolerance"></a>AllergyIntolerance

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Disargiscita di Argonaut:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)

 - Code.Text
 - Code.Coding[0]. Visualizzazione
 - ClinicalStatus/VerificationStatus (leggiamo entrambi)

Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere il campo seguente:

 - AssertedDate
 - Note.Text
 - Reazione
    - Sostanza (un elemento di codifica)
    - Manifestazione (un elemento di codifica)

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - Paziente =  \<patient id>

Vedere l'esempio seguente della chiamata: 

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

Vedere [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) per altri dettagli su questo set di campi.

## <a name="medication-request"></a>Richiesta di farmaci

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo della richiesta di farmaci di base [negli Stati Uniti:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)

 - Medication.Display (se Reference)
 - Medication.Text (se CodableConcept)
 - AuthoredOn
 - Requester.Agent.Display

Oltre ai campi di base degli Stati Uniti, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - DosageInstruction[..]. Testo
 - Testo

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _count=\<max results>

Vedere [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) per altri dettagli su questo set di campi.

## <a name="coverage"></a>Copertura

Questi sono i campi minimi obbligatori, non coperti dai profili Us Core o Argonaut:

 - Raggruppamento, almeno un elemento con
    - GroupDisplay
    - PlanDisplay
 - Periodo
 - SubscriberId

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - Paziente = \<patient id>

Vedere [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) per altri dettagli su questo set di campi.
