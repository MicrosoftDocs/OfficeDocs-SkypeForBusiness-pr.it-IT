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
description: Integrazione dell'app EHR di Microsoft teams patients
ms.openlocfilehash: 10a6b21e583b5fdd3e70857c4cfc5e7e21a7e988
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153818"
---
# <a name="dstu2-interface-specification"></a>Specifica dell'interfaccia DSTU2

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

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

Le query dell'app Microsoft teams patients per più di una risorsa pubblicano un bundle (BATCH) di richieste per l'URL del server FHIR. Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).

Tutte le risorse FHIR seguenti devono essere accessibili tramite riferimento diretto alle risorse.

## <a name="conformance-minimum-required-field-set"></a>Set di campi obbligatori minimi di conformità

 Il server FHIR deve implementare l'istruzione di conformità per avere un riepilogo effettivo delle proprie funzionalità. Prevediamo i parametri seguenti in un server di FHIR DSTU2:

1. RESTO
   1. Modalità
   2. Interazione
   3. Risorsa: digitare
   4. Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot mentre sosteniamo più versioni).

Per [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) altre informazioni su questo set di campi, vedere.

## <a name="patient"></a>Paziente

Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi del [profilo del paziente Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

1. Name. Family
2. Name. given
3. Genere
4. Nascita
5. MRN (identificatore)

Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:

1. Name. use
2. Name. prefix
3. CareProvider (questo riferimento sulla risorsa paziente deve includere i campi visualizzati nell'esempio seguente).

* * *

    Richiesta: ottenere <Fhir-Server>/patient/<ID paziente>
    
    Response: {"resourceType": "patient", "ID": "<patient-ID>",.
      .
      .
      "nome": [{"use": "Official", "prefix": ["Mr"], "Family": ["Chau"], "given": ["Hugh"]}], "Identifier": [{"use": "ufficiale", "tipo": {"codifica": [{"System":https://hl7.org/fhir/v2/0203"" "," codice ":" Mr "}]}," valore ":" 1234567 "}]," sesso ":" maschio "," DataNascita ":" 1957-06-05 "," careProvider ": [{" display ":" Jane Doe "}],}

* * *

Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:

1. ID
2. Family: Contains = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore).
3. given\<= substring>
4. Name =\<substring>
5. nascita = (corrispondenza esatta)
6. \_conteggio (numero massimo di risultati che devono essere restituiti) <br> La risposta deve contenere il numero totale di record restituiti come risultato della ricerca e \_il conteggio verrà usato da PatientsApp per limitare la quantità di record restituiti.
7. Identifier =\<MRN>

L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:

- ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.
- MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe. Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR
- Nome
- Nascita

Vedere l'esempio seguente di questa chiamata.

* * *

    Request: POST <Fhir-Server>/patient/_search request body: given = Hugh&Family = Chau
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>",.
      .
      .
      "voce": [{"risorsa": {"resourceType": "paziente", "ID": "<ID paziente>", "nome": [{"testo": "Hugh Chau", "famiglia": ["Chau"], "given": ["Hugh"]}], "gender": "maschio", "database": "1957-06-05"}, "ricerca": {"modalità": "corrispondenza"}}]

* * *

Per [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) altre informazioni su questo set di campi, vedere.

## <a name="observation"></a>Osservazione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut Vital Signs:

 1. Effettivo (data/ora o periodo)
 2. Code. Coding. code
 3. ValueQuantity. Value

Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:

 1. Code. Coding. display
 2. ValueQuantity. unit

Se si usano le osservazioni dei componenti, la stessa logica viene applicata per ogni osservazione del componente.

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. paziente =\<ID paziente\>
2. Ordina: desc =\<campo ex. Data\>

L'obiettivo è quello di riuscire a recuperare gli ultimi segni vitali per un paziente, [VitalSigns. DSTU....] (osservazione?).

* * *

    Richiesta: ottenere <Fhir-Server>/Observation? patient =<patient-ID>&_sort:d ESC = data&Category = Vital-Signs
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "digitare": "searchset", "Total": 20, "entry": [{"risorsa": {"resourceType": "osservazione", "ID": "<Resource-ID>", "Category": {"coding": [{code ":" Vital-Signs "}],}," code ": {" coding ": [{" System ":http://loinc.org" "," code ":" 39156-5 "," display ":" BMI "}],}," effectiveDateTime ":" 2009-12-01 "," valueQuantity ": {" valore ": 34,4," unità ":" kg/m2 "," sistema ":http://unitsofmeasure.org" "," codice ":" kg/m2 "}},},.
        .
        .
      ] }

* * *

Per [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) altre informazioni su questo set di campi, vedere.

## <a name="condition"></a>Condizione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. Visualizzare

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

1. Data registrata
2. Gravità

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>
2. _count =\<max results>

Vedere l'esempio seguente di questa chiamata:

* * *

    Richiesta: ottenere <Fhir-Server>/Condition? patient =<patient-ID>&_count = 10
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"risorsa": {"resourceType": "condizione", "ID": "<Resource-ID>", "codice": {"codifica": [{"System": "http://snomed.info/sct" "," codice ":" 386033004 "," Visualizza ":" neuropatia (nervo) "}]}," dateRecorded ":" 2018-09-17 "," gravità ":" codifica ": [{") syst em ":"http://snomed.info/sct"," codice ":" 24484000 "," visualizzazione ":" grave "}]}},}]}

* * *

Per [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) altre informazioni su questo set di campi, vedere.

## <a name="encounter"></a>Verificarsi

Questi sono i campi obbligatori minimi, che sono un sottoinsieme dei campi "must have" del profilo degli incontri di base degli Stati Uniti:

1. Stato
2. Digitare [0]. Codifica [0]. Visualizzare

Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti

1. Periodo. inizio
2. Posizione [0]. Location. display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>
2. _sort: desc =\<campo ex. Data>
3. _count =\<max results>

L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente. Ogni incontro fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione. Vedere l'esempio seguente di questa chiamata.
* * *

    Richiesta: ottenere <Fhir-Server>/Encounter? patient =<ID paziente>&_sort:d ESC = data&_count = 1
    
    Response: {"ResourceType": "bundle", "Type": "searchset", "Total": 1, "entry": [{"risorsa": "" ResourceType ":" Encounter "," ID ":" <Resource-ID> "," Identifier ": [{" use ":" Official "," value ":"<id>"}]," stato ":" arrivato "," tipo ": [{" codifica ": [{" visualizzazione ":" appuntamento "}],}]," paziente ": {" riferimento ":" paziente/<paziente-ID> "}," periodo ":" inizio ":" 09/17/2018 1:00:00 PM "}," location ": [{              "location": {"display": "Clinic-ENT"},}]}}]}

* * *

Per [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) altre informazioni su questo set di campi, vedere.

## <a name="allergyintolerance"></a>AllergyIntolerance

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut AllergyIntolerance:

1. Code. Text
2. Code. Coding [0]. Visualizzare
3. Stato

Oltre ai campi Argonaut, per una grande esperienza utente l'app patients legge anche i campi seguenti:

1. RecordedDate
2. Nota. testo
3. Reazione [..]. Sostanza. testo
4. Reazione [..]. Manifestazione [..]. Testo
5. Text. div

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. Patient = \<id paziente>

Vedere l'esempio seguente di questa chiamata:

* * *

    Richiesta: ottenere <Fhir-Server>/AllergyIntolerance? patient =<ID paziente>
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"Resource": {"resourceType": "AllergyIntolerance", "ID": "<Resource-ID>", "recordedDate": "2018-09-17T07:00:00.000 Z", "sostanza": {"testo": "anacardio"}, "stato": "confermato", "reazione": [{"sostanza": {"testo": "Estratto del dado allergenico prodotto iniettabile"}, "manifestati on ": [{" testo ":" reazione anafilattica "}]}]}}]}

* * *

Per [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) altre informazioni su questo set di campi, vedere.

## <a name="medication-order"></a>Ordine dei farmaci

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo Argonaut MedicationOrder:

1. DateWritten
2. Prescriber. display
3. Medicine. display (se di riferimento)
4. Medicine. Text (se Concept)

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

1. DateEnded
2. DosageInstruction. Text
3. Text. div

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>
2. _count =\<max results>

Vedere l'esempio seguente di questa chiamata:

* * *

    Richiesta: ottenere <Fhir-Server>/MedicationOrder? patient =<patient-ID>&_count = 10
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "Total": 1, "entry": [{"Resource": {"resourceType": "MedicationOrder", "ID": "<Resource-ID>", "dateWritten": "2018-09-17", "medicationCodeableConcept": {"Text": "Lisinopril 20 MG Oral Tablet"}, "Prescriber": {"display": "Jane Doe"}, "dosageInstruction": [{"testo": "1 Daily"}]}}]}

* * *  

Per [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) altre informazioni su questo set di campi, vedere.

## <a name="coverage"></a>Copertura delle

Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:

1. Pagante

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>

Vedere l'esempio seguente di questa chiamata:

* * *

    Richiesta: ottenere <Fhir-Server>/coverage? patient =<ID paziente>
    
    Response: {"resourceType": "bundle", "digitare": "searchset", "Total": 1, "entry": [{"risorsa": {"resourceType": "coverage", "ID": "<Resource-ID>", "piano": "nessuna assicurazione primaria", "sottoscrittore": {"riferimento": "paziente/<-ID>"}}}]}

* * *

Per [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) altre informazioni su questo set di campi, vedere.

## <a name="location"></a>Posizione

Questa risorsa viene usata solo come riferimento nella risorsa [Encounter](#encounter) .

Per [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) altre informazioni su questo set di campi, vedere.
