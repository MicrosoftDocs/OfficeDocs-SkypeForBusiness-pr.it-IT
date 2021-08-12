---
title: Sincronizzare i dati del sistema informativo degli studenti (SIS) con Insights per l’istruzione
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Sincronizzare i dati del sistema informativo degli studenti (SIS) con Insights per l’istruzione in Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee041f0789f532e058d3cfc27d2cfa51cd88b9c511f50e52ebc36f44d0a0f33d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54293813"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizzare i dati del sistema informativo degli studenti (SIS) con Insights per l’istruzione
Fornendo un maggiore numero di dati maggiori a [Insights per l’istruzione](class-insights.md), il supporto dei docenti nei confronti degli studenti migliorerà e allo stesso tempo anche il supporto dei responsabili per l’istruzione verso i docenti.

Per fornire informazioni approfondite a livello di organizzazione, è necessario usare [School Data Sync (SDS)](/SchoolDataSync) in modo da connettersi al sistema informativo degli studenti (SIS) per far sì che Insights abbia la struttura gerarchica del sistema didattico mappata correttamente. 

La visualizzazione di Insights a livello di classe come docente *non* richiede questa sincronizzazione, in quanto vengono usate la struttura e le autorizzazioni della classe di Teams.

## <a name="plan-your-school-data-sync-integration"></a>Pianificare l'integrazione di School Data Sync
Microsoft School Data Sync (detto anche SDS) fornisce i dati sistema informativo degli studenti (detto anche SIS), la struttura gerarchica del sistema didattico e le mappe a cui l'utente è assegnato, oltre a fornire dati aggiuntivi sulla gerarchia degli studenti e dell'organizzazione.

Insights offre risultati ottimali quando viene usato con [formato di file SDS V2.1](/schooldatasync/sds-v2.1-csv-file-format), ma supporta anche il [formato di file SDS V2](/schooldatasync/sds-v2-csv-file-format) e il [formato di file SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds) *con funzionalità limitate*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Differenze tra i formati di file SDS V1 e V2

| Tipo di dati | V1 | V2 e V2.1 |
|:--- |:--- |:--- |
| **Utenti** |Supporta solo il ruolo di "docente", di conseguenza le autorizzazioni a livello di organizzazione per i dirigenti dell'istituto di istruzione devono essere impostate manualmente|Supporta più ruoli in modo che sia possibile impostare le autorizzazioni basate sui ruoli|
| **Organizzazioni** | Supporta solo 'istituti di istruzione', livello di aggregazione.<br><br>Di conseguenza, non fornisce più livelli di aggregazione e fornisce una capacità limitata di confrontare diversi tipi di istituti di istruzione(es. scuola primaria vs. secondaria, liceo scientifico vs. istituto d'arte)|Supporta la gerarchia a più livelli, inclusi distretto/istituzione, università, college, facoltà, campus, aree geografiche, programmi, ecc.<br><br>Consente più livelli di aggregazione e consente di confrontare facilmente le unità organizzative per ciascun livello, assegnare autorizzazioni a livelli specifici, impostare obiettivi per livello di organizzazione, ecc.|
| **Informazioni facoltative aggiuntive** |Nessuno|**Solo formato di file V2.1**<br><br>*Sessioni accademiche* : intervalli di tempo delle sessioni (semestri, anni scolastici e così via)<br><br>Dati demografici e bandiere studentesche*: dati come razza, etnia e genere, nonché programmi speciali (IEP, 504)|

> [!NOTE]
> I clienti non potranno eseguire l'onboarding del formato di file v2 a partire dal 15 luglio 2021 e dovranno invece usare il formato v2.1, tutti gli aggiornamenti futuri e la nuova capacità verranno eseguiti nel formato v2.1 e saranno completamente compatibili con il formato di file v1.

### <a name="best-practices"></a>Procedure consigliate

Il mapping accurato della gerarchia e della posizione che gli utenti occupano all’interno di tale gerarchia consente a Insights di fornire dati accurati e dati analitici più precisi e pertinenti per i diversi tipi di responsabili dell’istruzione.

Maggiori saranno i dettagli forniti, più rilevanti saranno i report e le schede in evidenza.

#### <a name="file-format-version-to-use-adn-data-to-sync"></a>Versione del formato file da utilizzare e dati da sincronizzare
*   Utilizzare il formato file V2.1 e sincronizzare i dati facoltativi utilizzati da Education Insights come descritto [qui](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv).

#### <a name="users-and-roles"></a>Utenti e ruoli
*   Assicurarsi che **tutti gli utenti siano elencati nei file** forniti e sincronizzati. Questo include tutti gli studenti e il personale che devono visualizzare le unità organizzative da loro coperte.
*   Se attualmente nel SIS sono elencati solo docenti, aggiungere manualmente gli altri utenti prima di caricare i file in SDS e sincronizzare i dati. Le statistiche raccolte da Insights saranno solo relative agli studenti registrati. Se mancano alcuni studenti, ciò renderà i dati e le conclusioni fuorvianti.
    
*   Se si usa SDS anche per il provisioning, assicurarsi di **specificare il nome e il cognome di ogni utente**. In caso contrario, si farà riferimento agli studenti tramite il loro indirizzo e-mail. Questo implica un'esperienza non ottimale.

*   Il livello di voto/anno deve essere basato su questo [elenco di mapping](#supported-grade-level-values). 

*   Assicurarsi di **aggiungere il livello di anno/voto a tutti gli studenti** .    

*   Assicurarsi di **assegnare ogni utente alla propria unità organizzativa pertinente**.

    *   Uno studente può essere associato a più unità organizzative, ad esempio gli studenti iscritti ad un programma speciale o due facoltà. Nel caso in cui lo studente abbia più unità organizzative, fornire una riga per ognuno nel file degli utenti per tale studente.
    
    *   L'amministratore IT può concedere autorizzazioni in base all'unità organizzativa per il personale. **Bisogna assicurarsi che i membri del personale siano associati al livello di unità corretto**, in modo che ricevano le autorizzazioni di cui hanno bisogno. Ad esempio, un consulente assegnato a quattro scuole deve vedere tutti i voti di queste scuole e un preside deve vedere tutte le classi della propria scuola. 
    
*   **Il ruolo è essenziale**. Anche se si tratta di un elenco chiuso, è consigliabile provare a abbinare il ruolo dall’[elenco](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) al ruolo reale di ogni utente caricato. Questo consentirà di assegnare le autorizzazioni basate sui ruoli. Ad esempio, bisogna fornire a tutti i presidi le autorizzazioni per vedere le classi nel loro istituto di istruzione o a tutti i professori per vedere la proprie facoltà. 

#### <a name="organizations"></a>Organizzazioni

* Assicurarsi che **la reale e completa gerarchia dell’organizzazione corrisponda**. In alcuni casi, questa gerarchia non si riflette nel sistema informativo degli studenti. In tal caso deve essere aggiunta manualmente al file CSV prima della sincronizzazione.

* Assicurarsi che **tutte le unità organizzative nell'albero dell'organizzazione includano gli studenti o le classi**. È consigliabile che gli studenti siano nella parte più basa della gerarchia.

> [!NOTE]
> Per altre informazioni sulla distribuzione SDS, consultare [Pianificazione SDS](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-data-using-sds"></a>Integrare SIS con SDS

School Data Sync (SDS) viene fornito con Office 365 per l’istruzione. Questo legge i dati dal sistema informativo degli studenti (SIS) di un istituto scolastico e lo integra con applicazioni Microsoft come Teams per consentire la creazione automatica di classi online e utenti.

Inoltre, sincronizza i dati del sistema informativo degli studenti con Insights.

Gli amministratori IT possono scegliere di usare SDS solo per il provisioning, solo per Insights o per entrambi.

Per sincronizzare le informazioni SIS con Educations Insights, seguire le istruzioni in [Come distribuire SDS per Insights](/schooldatasync/how-to-deploy-sds-for-insights).

### <a name="deploy-sds"></a>Distribuire SDS
**Se SDS è già in uso**, è consigliabile seguire le [procedure consigliate](#best-practices). 

**Se SDS non è ancora in uso**, è necessario [distribuirlo](/schooldatasync/deploying-school-data-sync).

Durante il processo di distribuzione, è possibile decidere se usare SDS per il provisioning degli utenti e delle classi in Teams o solo per fornire la gerarchia di utenti e organizzazioni anche a Insights.

> [!NOTE]
> Se si è già a metà dell'anno e i team sono già stati creati manualmente, usare SDS solo per fornire i dati della gerarchia di utenti e organizzazioni a Insights e, per l’anno successivo, è consigliabile usare SDS per il provisioning di utenti e classi anche per Teams.

### <a name="verify-the-sync-process"></a>Verificare il processo di sincronizzazione
Per verificare lo stato della sincronizzazione, seguire le istruzioni in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).

> [!IMPORTANT]
> In caso di problemi, è possibile contattare il [supporto tecnico](https://aka.ms/edusupport) per assistenza.

## <a name="supported-grade-level-values"></a>Valori di voti supportati

Nei file SDS, classe/anno sono definiti e valori enumerati, ovvero è possibile fornire solo un set selezionato di valori all'interno del file CSV. Tutti gli elementi diversi da quelli specificati genereranno un errore durante l'elaborazione della sincronizzazione.

La sezione seguente definisce i valori supportati nel file degli utenti.

### <a name="united-states--worldwide-grade-levels"></a>Stati Uniti/livelli di valutazione internazionali
|Valore nel file (colonna Classe) | Etichetta in Insights|
|:---|:---| 
|IT|Infant|
|PR|Pre-school|
|PK|Pre-kindergarten|
|TK|Transitional Kindergarten|
|KG|Kindergarten|
|01 o 1|First grade|
|02 o 2|Second grade|
|03 o 3|Third grade|
|04 o 4|Fourth grade|
|05 o 5|Fifth grade|
|06 o 6|Sixth grade|
|07 o 7|Seventh grade|
|08 o 8|Eighth grade|
|09 o 9|Ninth grade|
|10|Tenth grade|
|11|Eleventh grade|
|12|Twelfth grade|
|PS|Postsecondary|
|PS1|Postsecondary freshman|
|PS2|Postsecondary sophomore|
|PS3|Postsecondary junior|
|PS4|Postsecondary senior|
|undergraduate|Undergraduate|
|graduate|Graduate|
|postgraduate|Postgraduate (laureato con un'enfasi sulla ricerca)|
|alumni|Alumni|
|adultEducation|Adult Education|
|UG|Ungraded|
|Other|Altro|

### <a name="united-kingdom-year-groups"></a>Anni Regno Unito
|Valore nel file (colonna Classe) | Etichetta in Insights|
|:---|:---| 
|IT|Nursery|
|PR|Pre-school|
|PK|Reception|
|01 o 1|Year 1|
|02 o 2|Year 2|
|03 o 3|Year 3|
|04 o 4|Year 4|
|05 o 5|Year 5|
|06 o 6|Year 6|
|07 o 7|Year 7|
|08 o 8|Year 8|
|09 o 9|Year 9|
|10|Year 10|
|11|Year 11|
|12|Year 12|
|13|Year 13|
|PS|Postsecondary|
|PS1|Postsecondary Year 1|
|PS2|Postsecondary Year 2|
|PS3|Postsecondary Year 3|
|PS4|Postsecondary Year 4|
|undergraduate|Undergraduate|
|graduate|Graduate|
|postgraduate|Postgraduate (laureato con un'enfasi sulla ricerca)|
|alumni|Alumni|
|adultEducation|Adult Education|
|UG|Ungraded|
|Other|Altro|

