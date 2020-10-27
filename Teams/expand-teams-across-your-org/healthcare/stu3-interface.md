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
# <a name="stu3-interface-specification"></a>Specifica dell'interfaccia STU3

> [!IMPORTANT]
> **Efficace il 30 ottobre 2020 l'app patients sarà deprecata e gli utenti non potranno più installarla dall'app teams Store. Ti invitiamo a iniziare a usare l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams Today.**
>
>I dati dell'app patients sono archiviati nella cassetta postale del gruppo del gruppo Office 365 che appoggia il team. Quando l'app patients viene ritirata, tutti i dati associati verranno mantenuti in questo gruppo, ma non sarà più possibile accedervi tramite l'interfaccia utente. Gli utenti correnti possono ricreare gli elenchi usando l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>L' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) è preinstallata per tutti gli utenti di teams ed è disponibile come scheda in ogni team e canale. Con gli elenchi, i team di integrità possono creare elenchi di pazienti usando il modello di pazienti incorporati, da zero o importando dati in Excel. Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md).

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Microsoft teams patients richiede la comprensione dei dati di cui l'app deve accedere. Il server FHIR deve supportare le richieste POST usando i bundle per le risorse seguenti:

- [Paziente](#patient)
- [Osservazione](#observation)
- [Condizione](#condition)
- [Verificarsi](#encounter)
- [Intolleranza alle allergie](#allergyintolerance)
- [Copertura delle](#coverage)
- [Istruzione farmaco](#medication-request) (sostituisce il MedicationOrder nella versione DSTU2 di PatientsApp)
- Posizione (le informazioni necessarie da questa risorsa possono essere incluse in Encounter)

> [!NOTE]
> La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto); Tuttavia, è consigliabile che il Partner implementi il supporto per tutte le risorse sopra menzionate per le specifiche fornite di seguito per ottenere la migliore esperienza utente finale con l'app Microsoft teams patients.

Le query dell'app Microsoft teams patients per più risorse devono pubblicare un pacchetto (BATCH) di richieste per l'URL del server FHIR. Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Istruzione Capability

Questi sono i campi obbligatori minimi:

 - RESTO

    - Modalità
    - Interazione
    - Risorsa: digitare
    - Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot.)

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Per altre informazioni su questo set di campi, vedere.

## <a name="patient"></a>Paziente

Ecco i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente Argonaut:

 - Name. given
 - Name. Family
 - Genere
 - Nascita
 - MRN (identificatore)

Oltre ai [campi Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

 - Name. use
 - Name. prefix
 - [GeneralPractitioner]-il riferimento GeneralPractitioner deve essere incluso nella risorsa paziente (solo campo di visualizzazione)

Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:

 - ID
 - Family = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore)
 - given =\<substring>
 - nascita = (corrispondenza esatta)
 - Gender = (i valori sono uno degli amministratori-gender)
 - \_conteggio (numero massimo di risultati che devono essere restituiti) <br> La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e il \_ conteggio verrà usato da PatientsApp per limitare il numero di record restituiti.
 - Identifier =\<mrn>

L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:

- ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.
- MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe. Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.
- Nome
- Nascita

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

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Per altre informazioni su questo set di campi, vedere.

## <a name="observation"></a>Osservazione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

 - Effettivo (data/ora o periodo)
 - Code. Coding. code
 - ValueQuantity. Value

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

 - Code. Coding. display
 - ValueQuantity. unit

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id>
 - _sort =-data
 - Category (verrà eseguita una query per "Category = Vital-Signs") per recuperare l'elenco dei segni vitali.

Fare riferimento a questo esempio di chiamata:

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

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Per altre informazioni su questo set di campi, vedere.

## <a name="condition"></a>Condizione

Ecco i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

 - Code. Coding [0]. Visualizzare

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

 - AssertedDate
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

[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Per altre informazioni su questo set di campi, vedere.

## <a name="encounter"></a>Verificarsi

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo di confronto degli Stati Uniti](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have".

 - Stato
 - Digitare [0]. Codifica [0]. Visualizzare

Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti:

 - Periodo. inizio
 - Posizione [0]. Location. display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id>
 - _sort: desc =\<field ex. date>
 - _count =\<max results>

L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente. Ogni incontro fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione.

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Per altre informazioni su questo set di campi, vedere.

## <a name="allergyintolerance"></a>AllergyIntolerance

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

 - Code. Text
 - Code. Coding [0]. Visualizzare
 - ClinicalStatus/VerificationStatus (leggiamo entrambi)

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere il campo seguente:

 - AssertedDate
 - Nota. testo
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

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Per altre informazioni su questo set di campi, vedere.

## <a name="medication-request"></a>Richiesta di farmaci

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo di richiesta di base per i [farmaci USA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

 - Medicine. display (se di riferimento)
 - Medicine. Text (se CodableConcept)
 - AuthoredOn
 - Requestr. Agent. display

Oltre ai campi principali degli Stati Uniti, per una grande esperienza utente l'app patients può anche leggere i campi seguenti:

 - DosageInstruction[..]. Testo
 - Testo

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - paziente =\<patient id>
 - _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Per altre informazioni su questo set di campi, vedere.

## <a name="coverage"></a>Copertura delle

Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:

 - Raggruppamento, almeno un elemento con
    - GroupDisplay
    - PlanDisplay
 - Periodo
 - SubscriberId

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - Paziente = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Per altre informazioni su questo set di campi, vedere.
