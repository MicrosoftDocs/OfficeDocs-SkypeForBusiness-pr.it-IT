---
title: Interfaccia DSTU2 dell'integrazione di Pazienti app ed EHR
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
description: Informazioni sulla specifica dell'interfaccia DSTU2 in Teams, inclusa la configurazione o la riconfigurazione di un server FHIR per l'utilizzo con l'app Pazienti di Microsoft Teams.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803484"
---
# <a name="dstu2-interface-specification"></a>Specifica dell'interfaccia DSTU2

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell'app Pazienti vengono archiviati nella cassetta postale del gruppo di Office 365 che backup il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non sono più accessibili tramite l'interfaccia utente. Gli utenti possono creare di nuovo i propri elenchi usando [l'app Elenchi.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti. Per iniziare, vedere il modello Pazienti in Elenchi. Per altre informazioni su come gestire l'app Elenchi nell'organizzazione, vedere [Gestire l'app Elenchi.](../../manage-lists-app.md)

La configurazione o la riconfigurazione di un server FHIR per l'utilizzo dell'app Pazienti di Microsoft Teams richiede la comprensione dei dati a cui l'app deve accedere. Il server FHIR deve supportare le richieste POST tramite bundle per le risorse seguenti:

- [Paziente](#patient)
- [Osservazione](#observation)
- [Condizione](#condition)
- [Incontrarsi](#encounter)
- [Intoleranza invariabile](#allergyintolerance)
- [Copertura](#coverage)
- [Ordine di farmaci](#medication-order)
- [Posizione](#location)

> [!NOTE]
> La risorsa paziente è l'unica risorsa obbligatoria (senza la quale l'app non verrà caricata affatto. Tuttavia, è consigliabile che il partner implementi il supporto per tutte le risorse menzionate sopra per specifiche fornite di seguito per la migliore esperienza utente con l'app Pazienti di Microsoft Teams.

Query dall'app Pazienti di Microsoft Teams per più di una risorsa pubblicano un bundle (BATCH) di richieste all'URL del server FHIR. Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, vedere [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Tutte le risorse FHIR seguenti devono essere accessibili con riferimento diretto alle risorse.

## <a name="conformance-minimum-required-field-set"></a>Set di campi Obbligatorio minimo di conformità

 Il server FHIR deve implementare la dichiarazione di conformità perché ci sia un riepilogo dei fatti delle sue capacità. In un server DSTU2 FHIR sono previsti i parametri seguenti:

 - REST

    - Modalità
    - Interazione
    - Risorsa: Tipo
    - Sicurezza: [estensione per GLI URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (Il nostro codice richiede questo perché comprendi la versione su cui è necessario eseguire il pivot perché supportiamo più versioni).)

Per [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) altre informazioni su questo set di campi, vedere.

## <a name="patient"></a>Paziente

Si tratta dei campi minimi obbligatori, che sono un sottoinsieme dei campi del profilo del [paziente Inaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)

 - Name.Family
 - Name.Given
 - Gender
 - BirthDate
 - MRN (identificatore)

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti legge anche i campi seguenti:

 - Name.Use
 - Name.Prefix
 - CareProvider (Questo riferimento sulla risorsa Patient deve includere i campi visualizzati nell'esempio seguente).

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

Una ricerca di risorse usa il metodo POST presso /Patient/_search e i parametri seguenti:

 - id
 - family:contains=(cerca tutti i pazienti il cui nome di famiglia contiene il valore).
 - given=\<substring>
 - name=\<substring>
 - birthdate=(corrispondenza esatta)
 - \_count (numero massimo di risultati che deve essere restituito) <br> La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e verrà usato dall'app Pazienti per limitare il numero \_ di record restituiti.
 - identifier=\<mrn>

L'obiettivo è poter cercare e filtrare un paziente in base alle condizioni seguenti:

- ID: ID risorsa di ogni risorsa disponibile in FHIR.
- MRN: l'identificatore effettivo del paziente che il personale clinico conoscerebbe. Sappiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR
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

Per [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) altre informazioni su questo set di campi, vedere.

## <a name="observation"></a>Osservazione

Si tratta dei campi minimi obbligatori, che sono un sottoinsieme del profilo dei segni essenziali dell'antasta:

 - Validità (data e ora o periodo)
 - Code.Coding.Code
 - ValueQuantity.Value

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti legge anche i campi seguenti:

 - Code.Coding.Display
 - ValueQuantity.Unit

Se si usano osservazioni dei componenti, si applica la stessa logica per ogni osservazione dei componenti.

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

L'obiettivo è quello di recuperare i segni essenziali più recenti per un paziente, [VitalSigns.DSTU.saz] (osservazione?).

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

Per [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) altre informazioni su questo set di campi, vedere.

## <a name="condition"></a>Condizione

Si tratta dei campi minimi obbligatori, che sono un sottoinsieme del profilo della [condizione Dinaut:](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Schermo

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

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

Per [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) altre informazioni su questo set di campi, vedere.

## <a name="encounter"></a>Incontrarsi

Si tratta dei campi minimi obbligatori, che sono un sottoinsieme dei campi "obbligatori" del profilo di verifica principale per gli Stati Uniti:

 - Stato
 - Digitare[0]. Codifica[0]. Schermo

Inoltre, i seguenti campi dei campi "deve supportare" del profilo Us Core Encounter

 - Period.Start
 - Location[0]. Location.Display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

L'obiettivo è quello di recuperare l'ultima posizione nota del paziente. Ogni riferimento fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione. Vedere l'esempio seguente di questa chiamata.

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

Per [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) altre informazioni su questo set di campi, vedere.

## <a name="allergyintolerance"></a>IntolerazioneSocietà

Si tratta dei campi minimi obbligatori, che sono un sottoinsieme del profilo Disapersa Avi:

 - Code.Text
 - Code.Coding[0]. Schermo
 - Stato

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti legge anche i campi seguenti:

 - RecordedDate
 - Note.Text
 - Reaction[..]. Evase.Testo
 - Reaction[..]. Evaso[..]. Testo
 - Text.Div

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

 - Patient =  \<patient id>

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

Per [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) altre informazioni su questo set di campi, vedere.

## <a name="medication-order"></a>Ordine di farmaci

Questi sono i campi minimi obbligatori, che sono un sottoinsieme del profilo Ordine Farmacia per farmaci:

 - DateWritten
 - Prescriber.Display
 - Medication.Display (se di riferimento)
 - Medication.Text (se concetto)

Oltre ai campi Clientenaut, per un'esperienza utente ottimale, l'app Pazienti può anche leggere i campi seguenti:

 - DateEnded
 - Estrazione.Testo.Istruzione.Testo
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

Per [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) altre informazioni su questo set di campi, vedere.

## <a name="coverage"></a>Copertura

Si tratta dei campi minimi obbligatori, non coperti dai profili US Core oDiscout:

 - Pagante

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
    
Per [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) altre informazioni su questo set di campi, vedere.

## <a name="location"></a>Posizione

Questa risorsa viene usata solo come riferimento per la [risorsa](#encounter) Incontra.

Per [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) altre informazioni su questo set di campi, vedere.
