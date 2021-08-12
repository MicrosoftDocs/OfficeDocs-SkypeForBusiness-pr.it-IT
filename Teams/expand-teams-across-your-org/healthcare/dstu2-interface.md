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
ms.openlocfilehash: 8ec2b1a88d99937e83bc8553f7dbcdd8d92f78b5a8e5708301147a26f0cffe4a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308765"
---
# <a name="dstu2-interface-specification"></a>Specifica dell'interfaccia DSTU2

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
- [Ordine dei farmaci](#medication-order)
- [Posizione](#location)

> [!NOTE]
> La risorsa Paziente è l'unica risorsa obbligatoria senza la quale l'app non verrà caricata. Tuttavia, è consigliabile che il partner implementi il supporto per tutte le risorse menzionate sopra in base alle specifiche fornite di seguito per la migliore esperienza dell'utente finale con l'app Microsoft Teams Patients.

Query dall'app Microsoft Teams Patients per più risorse pubblicano un pacchetto (BATCH) di richieste all'URL del server FHIR. Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, vedere [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Tutte le risorse FHIR seguenti devono essere accessibili tramite riferimento diretto alle risorse.

## <a name="conformance-minimum-required-field-set"></a>Set di campi obbligatorio minimo di conformità

 Il server FHIR deve implementare la dichiarazione di conformità per poter disporre di un riepilogo fattuale delle sue funzionalità. In un server DSTU2 FHIR sono previsti i parametri seguenti:

 - RESTO

    - Modalità
    - Interazione
    - Risorsa: Tipo
    - Sicurezza: [estensione per GLI URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (Il nostro codice richiede questa operazione per comprendere la versione a cui è necessario eseguire il pivot mentre supportiamo più versioni).

Vedere [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) per altri dettagli su questo set di campi.

## <a name="patient"></a>Paziente

Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente di Argonaut:These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:

 - Name.Family
 - Name.Given
 - Sesso
 - BirthDate
 - MRN (Identificatore)

Oltre ai campi di Argonaut, per un'esperienza utente ottimale l'app Pazienti legge anche i campi seguenti:

 - Name.Use
 - Name.Prefix
 - CareProvider (Questo riferimento nella risorsa Patient deve includere i campi visualizzati nell'esempio seguente).

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

Una ricerca di risorse usa il metodo POST in /Patient/_search e i parametri seguenti:

 - id
 - family:contains=(cerca tutti i pazienti il cui nome di famiglia contiene il valore).
 - given=\<substring>
 - name=\<substring>
 - datadi nascita=(corrispondenza esatta)
 - \_count (numero massimo di risultati da restituire) <br> La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e il conteggio verrà usato dalla PatientsApp per limitare il numero \_ di record restituiti.
 - identificatore=\<mrn>

L'obiettivo è quello di poter cercare e filtrare un paziente in base a quanto segue:

- ID: ID risorsa di ogni risorsa in FHIR.
- MRN: questo è l'identificatore effettivo del paziente che il personale clinico conoscerebbe. Sappiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR
- Nome
- Data di nascita

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

Vedere [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) per altri dettagli su questo set di campi.

## <a name="observation"></a>Osservazione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo dei segni vitali di Argonaut:

 - Validità (data/ora o periodo)
 - Code.Coding.Code
 - ValoreQuantity.Value

Oltre ai campi di Argonaut, per un'esperienza utente ottimale l'app Pazienti legge anche i campi seguenti:

 - Code.Coding.Display
 - ValueQuantity.Unit

Se si usano osservazioni di componenti, la stessa logica si applica per ogni osservazione dei componenti.

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

L'obiettivo è recuperare i segni vitali più recenti per un paziente, [VitalSigns.DSTU.saz] (osservazione?).

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

Vedere [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) per altri dettagli su questo set di campi.

## <a name="condition"></a>Condizione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo condizione [di Argonaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Visualizzazione

Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - Data registrazione
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

Vedere [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) per altri dettagli su questo set di campi.

## <a name="encounter"></a>Incontro

Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo Us Core Encounter:

 - Stato
 - Type[0]. Codifica[0]. Visualizzazione

Inoltre, i campi seguenti dei campi "must support" del profilo Us Core Encounter

 - Period.Start
 - Location[0]. Location.Display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

L'obiettivo è recuperare l'ultima posizione nota del paziente. Ogni incontro fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione. Vedere l'esempio seguente di questa chiamata.

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

Vedere [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) per altri dettagli su questo set di campi.

## <a name="allergyintolerance"></a>AllergyIntolerance

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Disarginamentoargia Argonaut:

 - Code.Text
 - Code.Coding[0]. Visualizzazione
 - Stato

Oltre ai campi di Argonaut, per un'esperienza utente ottimale l'app Pazienti legge anche i campi seguenti:

 - RecordedDate
 - Note.Text
 - Reaction[..]. Sostanza.Testo
 - Reaction[..]. Manifestazione[..]. Testo
 - Text.Div

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

Vedere [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) per altri dettagli su questo set di campi.

## <a name="medication-order"></a>Ordine dei farmaci

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut MedicationOrder:These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:

 - DateWritten
 - Prescriber.Display
 - Medication.Display (se riferimento)
 - Farmaci.Testo (se concetto)

Oltre ai campi di Argonaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - DateEnded
 - DoseInstruction.Text
 - Text.Div

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _count=\<max results>

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

Vedere [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) per altri dettagli su questo set di campi.

## <a name="coverage"></a>Copertura

Questi sono i campi minimi obbligatori, non coperti dai profili Us Core o Argonaut:

 - Pagatore

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>

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
    
Vedere [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) per altri dettagli su questo set di campi.

## <a name="location"></a>Posizione

Questa risorsa viene usata solo come riferimento nella [risorsa](#encounter) Incontro.

Vedere [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) per altri dettagli su questo set di campi.
