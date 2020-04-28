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
ms.openlocfilehash: 2e101f6ca50a76b4b8bb9d3dd33d35fd7706a81f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905748"
---
# <a name="stu3-interface-specification"></a>Specifica dell'interfaccia STU3

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

Le query dell'app Microsoft teams patients per più risorse devono pubblicare un pacchetto (BATCH) di richieste per l'URL del server FHIR. Il server elabora ogni richiesta e restituisce un bundle delle risorse corrispondenti a ogni richiesta. Per altre informazioni ed esempi, Vedi [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).

## <a name="capability-statement"></a>Istruzione Capability

Questi sono i campi obbligatori minimi:

1. RESTO
   1. Modalità
   2. Interazione
   3. Risorsa: digitare
   4. Sicurezza: [estensione per gli URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (il nostro codice richiede questo per capire a quale versione dobbiamo eseguire il pivot.)

Per [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) altre informazioni su questo set di campi, vedere.

## <a name="patient"></a>Paziente

Ecco i campi obbligatori minimi, che sono un sottoinsieme dei campi del profilo del paziente Argonaut:

1. Name. given
2. Name. Family
3. Genere
4. Nascita
5. MRN (identificatore)

Oltre ai [campi Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

1. Name. use
2. Name. prefix
3. [GeneralPractitioner]-il riferimento GeneralPractitioner deve essere incluso nella risorsa paziente (solo campo di visualizzazione)

Una ricerca di risorse usa il metodo POST su/patient/_search e i parametri seguenti:

1. ID
2. Family = (Cerca tutti i pazienti il cui nome di famiglia contiene il valore)
3. given\<= substring>
4. nascita = (corrispondenza esatta)
5. Gender = (i valori sono uno degli amministratori-gender)
6. \_conteggio (numero massimo di risultati che devono essere restituiti) <br> La risposta deve contenere il conteggio totale dei record restituiti come risultato della ricerca e \_il conteggio verrà usato da PatientsApp per limitare il numero di record restituiti.
7. Identifier =\<MRN>

L'obiettivo è quello di essere in grado di cercare e filtrare per un paziente in base alle operazioni seguenti:

- ID: questo è l'ID risorsa che contiene tutte le risorse in FHIR.
- MRN: questo è l'identificatore effettivo per il paziente che il personale clinico saprebbe. Capiamo che questo MRN si basa sul tipo di identificatore all'interno della risorsa identificatore in FHIR.
- Nome
- Nascita

Vedere l'esempio seguente della chiamata:

* * *

    Richiesta: POST <Fhir-Server>/patient/_search richiedere il corpo: given = Ruth&Family = black
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "meta": {"lastUpdated": "2019-01-14T23:44:45.052 + 00:00"}, "tipo": "searchset", "Total": 1, "link": [{"relation": "self", "URL": <Fhir-server>/patient/_search "}]," entry ": [{" fullUrl ": <Fhir-server>/patient/<patient-ID>", "risorsa": {"resourceType": "patient", "ID": "<patient-ID>", "meta": {"VersionId": "1", "lastUpdated": "2017-10-18T18:32:37.000 + 00:00"}, "Text": {"status": "generated", "div": "<div>\n        <p>Ruth Black</p>\n      </div>"}," identificatore ": [{" USA ":" usuale "," tipo ": {" codifica ": [{" System ":https://hl7.org/fhir/v2/0203" "," codice ":" Mr "," display ":" numero di record medico "," userSelected ": false}]," testo ":" numero di record medico "}," sistemahttp://hospital.smarthealthit.org":" "," valore ":" 1234567 "}]," attivo ": vero", "nome": [{"USA": "ufficiale", "famiglia": "nero", "assegnato": ["Ruth", "C".
    ]}], "Telecom": [{"System": "telefono", "valore": "800-599-2739", "use": "Home"}, {"System": "Phone", "value": "800-808-7785", "use": "mobile"}, {"System": "mail", "value": "ruth.black@example.com"}], "gender": "femmina", "DataNascita": "1951-08-23", "indirizzo": [{"use": "Home", "line": ["26 South RdApt 22"], "City": "Sapulpa", "stato": "OK", "postalCode": "74066", "paese": "USA"}]}, "ricerca": {"modalità": "Confronta"}}]}

* * *

    Richiesta: ottenere <Fhir-Server>/patient/<ID paziente>
    
    Response: {"resourceType": "patient", "ID": "<patient-ID>", "identificatore": [{"use": "usual", "Type": {"coding": [{"System": "https://hl7.org/fhir/v2/0203", "code": "Mr",}], "Text": "numero di record medico"}, "valore": "1234567"}], "nome": [{"use": "ufficiale", "famiglia": "Adams", "assegnato": ["Daniele", "X". ]}], "sesso": "maschio", "DataNascita": "1925-12-23",}

* * *

Per [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) altre informazioni su questo set di campi, vedere.

## <a name="observation"></a>Osservazione

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo Argonaut Vital-Signs](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Effettivo (data/ora o periodo)
2. Code. Coding. code
3. ValueQuantity. Value

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

1. Code. Coding. display
2. ValueQuantity. unit

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>
2. _sort =-data
3. Category (verrà eseguita una query per "Category = Vital-Signs") per recuperare l'elenco dei segni vitali.

Fare riferimento a questo esempio di chiamata:

* * *

    Richiesta: ottenere <Fhir-Server>/Observation? patient =<patient-ID>&Category = Vital-Signs
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset", "totale": 20, "voce": [{"risorsa": {"resourceType": "osservazione", "ID": "<Resource-ID>", "Category": [{"coding": [{"System": "https://hl7.org/fhir/observation-category", "codice" codice ": {" coding ": [{" System ":"http://loinc.org"," code ":" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," valueQuantity ": {" valore ": 72,0," Unit ":" {Beats}/min "," System ":"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Per [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) altre informazioni su questo set di campi, vedere.

## <a name="condition"></a>Condizione

Ecco i campi obbligatori minimi, che sono un sottoinsieme del [profilo della condizione Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code. Coding [0]. Visualizzare

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere i campi seguenti:

1. AssertedDate
2. Gravità

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>
2. _count =\<max results>

Vedere l'esempio seguente di questa chiamata:

* * *

    Richiesta: ottenere <Fhir-Server>/Condition? patient =<patient-ID>&_count = 10
    
    Risposta: {"resourceType": "bundle", "ID": "<Bundle-ID>", "tipo": "searchset", "Total": 2, "entry": [{"Resource", "resourceType": "Condition", "ID": "<Resource-ID>", "codice": {"codifica": [{"System": "http://snomed.info/sct" "," codice ":" 185903001 "," visualizzazione ":" richiede l'immunizzazione dell'influenza ",}]}," gravità ": {" codifica ": [{" Systemhttp://snomed.info/sct":" "", "codice": "24484000", "display": "grave"}]}, "assertedDate": "2018-04-04"}},.
        .
        .
      ] }

* * *
Per [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) altre informazioni su questo set di campi, vedere.

## <a name="encounter"></a>Verificarsi

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del [profilo di confronto degli Stati Uniti](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have".

1. Stato
2. Digitare [0]. Codifica [0]. Visualizzare

Inoltre, i campi seguenti dei campi "must support" del profilo di incontri di base degli Stati Uniti:

1. Periodo. inizio
2. Posizione [0]. Location. display

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>
2. _sort: desc =\<campo ex. Data>
3. _count =\<max results>

L'obiettivo è quello di riuscire a recuperare l'ultima posizione nota del paziente. Ogni incontro fa riferimento a una risorsa posizione. Il riferimento deve includere anche il campo di visualizzazione della posizione.

Per [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) altre informazioni su questo set di campi, vedere.

## <a name="allergyintolerance"></a>AllergyIntolerance

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code. Text
2. Code. Coding [0]. Visualizzare
3. ClinicalStatus/VerificationStatus (leggiamo entrambi)

Oltre ai campi Argonaut, per una grande esperienza utente, l'app patients può anche leggere il campo seguente:

1. AssertedDate
2. Nota. testo
3. Reazione
    1. Sostanza (un elemento di codifica)
    2. Manifestazione (un elemento di codifica)

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. Patient = \<id paziente>

Vedere l'esempio seguente della chiamata: 

* * *

    Richiesta: ottenere <Fhir-Server>/AllergyIntolerance? patient =<ID paziente>
    
    Response: {"resourceType": "bundle", "ID": "<Bundle-ID>", "Type": "searchset"; "Total": 1 "," voce ": [{" risorsa ": {" resourceType ":" AllergyIntolerance "," ID ":" <Resource-ID> "," clinicalStatus ":" Active "," verificationStatus ":" confermato "," codice ": {" codifica ":" "," System "http://rxnav.nlm.nih.gov/REST/Ndfrt:" "," codice ":" N0000175503 "," display ":" solfonammide antibatterico ",}]," testo ":" solfonammide antibatterico "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," reazione ": [{" manifestazione ": [{" coding ": [{http://snomed.info/sct" System ":" "," code ":" 271807003 "," display ":" rash cutaneo ",}]," testo ":" eruzione cutanea "}],}]}}]}

* * *

Per [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) altre informazioni su questo set di campi, vedere.

## <a name="medication-request"></a>Richiesta di farmaci

Questi sono i campi obbligatori minimi, che sono un sottoinsieme del profilo di richiesta di base per i [farmaci USA](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medicine. display (se di riferimento)
2. Medicine. Text (se CodableConcept)
3. AuthoredOn
4. Requestr. Agent. display

Oltre ai campi principali degli Stati Uniti, per una grande esperienza utente l'app patients può anche leggere i campi seguenti:

1. DosageInstruction[..]. Testo
2. Testo

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. patient =\<id paziente>
2. _count =\<max results>

Per [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.

## <a name="coverage"></a>Copertura delle

Questi sono i campi obbligatori minimi, non coperti dai profili degli Stati Uniti o degli Argonauti:

1. Raggruppamento, almeno un elemento con
    1. GroupDisplay
    2. PlanDisplay
2. Periodo
3. SubscriberId

Una ricerca di risorse usa il metodo GET e i parametri seguenti:

1. Patient = \<id paziente>

Per [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) altre informazioni su questo set di campi, vedere.
