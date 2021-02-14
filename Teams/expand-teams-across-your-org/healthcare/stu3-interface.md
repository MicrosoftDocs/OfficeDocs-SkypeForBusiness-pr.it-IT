---
title: Interfaccia STU3 dell'integrazione di Applicazioni pazienti ed EHR
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
description: Informazioni sull'integrazione di record sanitari elettronici nell'app Pazienti di Microsoft Teams e nella specifica dell'interfaccia STU3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803494"
---
# <a name="stu3-interface-specification"></a>Specifica dell'interfaccia STU3

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell'app Pazienti vengono archiviati nella cassetta postale del gruppo di Office 365 che backup il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non sono più accessibili tramite l'interfaccia utente. Gli utenti possono creare di nuovo i propri elenchi usando [l'app Elenchi.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti. Per iniziare, vedere il modello Pazienti in Elenchi. Per altre informazioni su come gestire l'app Elenchi nell'organizzazione, vedere [Gestire l'app Elenchi.](../../manage-lists-app.md)

La configurazione o la riconfigurazione di un server FHIR per l'utilizzo dell'app Pazienti di Microsoft Teams richiede la comprensione dei dati a cui l'app deve accedere. Il server FHIR deve supportare le richieste POST tramite bundle per le risorse seguenti:

- [Paziente](#patient)
- [Osservazione](#observation)
- [Condizione](#condition)
- [Incontrarsi](#encounter)
- [Intolernza invariabile](#allergyintolerance)
- [Copertura](#coverage)
- [Dichiarazione dei](#medication-request) farmaci (sostituisce l'Ordine dei farmaci nella versione DSTU2 dell'App pazienti)
- Posizione (le informazioni necessarie per questa risorsa possono essere incluse in Incontrata)

> [!NOTE]
> La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto); Tuttavia, è consigliabile che il partner implementi il supporto per tutte le risorse menzionate sopra per specifiche fornite di seguito per la migliore esperienza utente con l'app Pazienti di Microsoft Teams.

Le query eseguite dall'app Pazienti di Microsoft Teams per più di una risorsa pubblicano un bundle (BATCH) di richieste nell'URL del server FHIR. Il server deve elaborare ogni richiesta e restituire un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, vedere [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Istruzione Capability

Questi sono i campi minimi obbligatori:

 - REST

    - Modalità
    - Interazione
    - Risorsa: Tipo
    - Sicurezza: [estensione per GLI URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (Il nostro codice richiede questo perché comprendi la versione a cui è necessario eseguire il pivot).

Per [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) altre informazioni su questo set di campi, vedere.

## <a name="patient"></a>Paziente

Ecco i campi minimi obbligatori, che sono un sottoinsieme dei campi del profilo del paziente Inaut:

 - Name.Given
 - Name.Family
 - Gender
 - BirthDate
 - MRN (identificatore)

Oltre ai campi [Clientenaut,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] - Il riferimento GeneralPractitioner deve essere incluso nella risorsa del paziente (solo campo di visualizzazione)

Una ricerca di risorse usa il metodo POST presso /Patient/_search e i parametri seguenti:

 - id
 - family=(cerca tutti i pazienti il cui nome di famiglia contiene il valore)
 - given=\<substring>
 - birthdate=(corrispondenza esatta)
 - gender=(i valori sono uno dei sessi amministrativi)
 - \_count (numero massimo di risultati che deve essere restituito) <br> La risposta deve contenere il numero totale di record restituiti come risultato della ricerca e il conteggio verrà usato dalla PatientsApp per limitare il numero \_ di record restituiti.
 - identifier=\<mrn>

L'obiettivo è poter cercare e filtrare un paziente in base alle condizioni seguenti:

- ID: ID risorsa di ogni risorsa disponibile in FHIR.
- MRN: l'identificatore effettivo del paziente che il personale clinico conoscerebbe. Sappiamo che questo VALORE si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.
- Nome
- Data di nascita

Vedere l'esempio seguente di chiamata:

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

Per [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) altre informazioni su questo set di campi, vedere.

## <a name="observation"></a>Osservazione

Si tratta dei campi minimi obbligatori, che sono un sottoinsieme dell'Vital-Signs [aziendale.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Validità (data e ora o periodo)
 - Code.Coding.Code
 - ValueQuantity.Value

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - Code.Coding.Display
 - ValueQuantity.Unit

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _sort=-date
 - categoria (verrà eseguita una query per "categoria=segni essenziali") per recuperare l'elenco dei segni essenziali.

Fai riferimento a questo esempio della chiamata:

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

Per [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) altre informazioni su questo set di campi, vedere.

## <a name="condition"></a>Condizione

Ecco i campi minimi obbligatori, che sono un sottoinsieme del profilo della [condizione Dinaut.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Schermo

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

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

Per [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) altre informazioni su questo set di campi, vedere.

## <a name="encounter"></a>Incontrarsi

Si tratta dei campi minimi obbligatori, [](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) che sono un sottoinsieme dei campi "obbligatori" del profilo di verifica principale per gli Stati Uniti.

 - Stato
 - Digitare[0]. Codifica[0]. Schermo

Inoltre, i campi seguenti del profilo US Core Encounter "devono supportare":

 - Period.Start
 - Location[0]. Location.Display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

L'obiettivo è quello di recuperare l'ultima posizione nota del paziente. Ogni riferimento fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione.

Per [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) altre informazioni su questo set di campi, vedere.

## <a name="allergyintolerance"></a>IntolerazioneSocietà

Si tratta dei campi minimi obbligatori, che sono un sottoinsieme del profilo [Disapersa Avi:](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)

 - Code.Text
 - Code.Coding[0]. Schermo
 - ClinicStatus/VerificationStatus (vengono lette entrambe)

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere il campo seguente:

 - AssertedDate
 - Note.Text
 - Reazione
    - Evaso (un elemento di programmazione)
    - Invasa (un elemento di programmazione)

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - Patient =  \<patient id>

Vedere l'esempio seguente di chiamata: 

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

Per [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) altre informazioni su questo set di campi, vedere.

## <a name="medication-request"></a>Richiesta di farmaci

Questi sono i campi minimi obbligatori, che sono un sottoinsieme del profilo della richiesta di farmaci fondamentali degli Stati [Uniti:](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)

 - Medication.Display (se di riferimento)
 - Medication.Text (se CodableConcept)
 - AuthoredOn
 - Requester.Agent.Display

Oltre ai campi Us Core, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - <b0>Invariva istruzioni[..]. Testo
 - Testo

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _count=\<max results>

Per [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.

## <a name="coverage"></a>Copertura

Si tratta dei campi minimi obbligatori, non coperti dai profili US Core oDiscout:

 - Raggruppamento, almeno un elemento con
    - GroupDisplay
    - PlanDisplay
 - Periodo
 - SubscriberId

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - Patient = \<patient id>

Per [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.
