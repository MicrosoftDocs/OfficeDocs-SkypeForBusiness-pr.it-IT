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
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997735"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizzare i dati del sistema informativo degli studenti (SIS) con Insights per l’istruzione
Fornendo un maggiore numero di dati maggiori a [Insights per l’istruzione](class-insights.md), il supporto dei docenti nei confronti degli studenti migliorerà e allo stesso tempo anche il supporto dei responsabili per l’istruzione verso i docenti.

Per fornire informazioni approfondite a livello di organizzazione, è necessario usare [School Data Sync (SDS)](/SchoolDataSync) in modo da connettersi al sistema informativo degli studenti (SIS) per far sì che Insights abbia la struttura gerarchica del sistema didattico mappata correttamente. 

La visualizzazione di Insights a livello di classe come docente *non* richiede questa sincronizzazione, in quanto vengono usate la struttura e le autorizzazioni della classe di Teams.

## <a name="plan-your-school-data-sync-integration"></a>Pianificare l'integrazione di School Data Sync
Microsoft School Data Sync (detto anche SDS) fornisce i dati sistema informativo degli studenti (detto anche SIS), la struttura gerarchica del sistema didattico e le mappe a cui l'utente è assegnato, oltre a fornire dati aggiuntivi sulla gerarchia degli studenti e dell'organizzazione.

Insights offre risultati ottimali quando viene usato [il formato di file SDS V2](/schooldatasync/sds-v2-csv-file-format) e versioni successive, ma supporta anche [il formato di file SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds) *con funzionalità limitate*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Differenze tra i formati di file SDS V1 e V2

Per ottenere il massimo da Insights, è consigliabile usare il formato di file v2 o v2.1 (Presto disponibili)

| Tipo di dati | V1 | V2 |
|:--- |:--- |:--- |
| **Utenti** | Il formato V1 contiene **solo docenti**, quindi per impostare le autorizzazioni a livello di organizzazione per i responsabili dell'istruzione, è necessario definire manualmente i permessi per ciascuno di loro. | Il formato V2 contiene **tutti i ruoli** in modo che sia possibile assegnare autorizzazioni basate sui ruoli. |
| **Organizzazioni** | Il formato V1 contiene **solo istituti di istruzione**, quindi viene visualizzato un solo livello di aggregazione (tutti gli istituti di istruzione). È possibile ingrandire un istituto di istruzione specifico usando un elenco completo. Tuttavia, tale elenco potrebbe avere un numero elevato di istituti di istruzione o contenerne diversi tipi, il che potrebbe rendere difficile il confronto (ad esempio la scuola primaria con quella secondaria o l’istituto d’arte e il liceo scientifico).<br/><br/> Quando è presente una gerarchia, è possibile creare livelli logici, ad esempio un dipartimento di scienze o arte.| Il formato V2 contiene **l'intera gerarchia del distretto o dell’istituzione**, comprese università, college, facoltà, campus, aree geografiche, programmi e così via.<br/><br/> Con una gerarchia è possibile visualizzare l'aggregazione pertinente per ogni livello, confrontare rapidamente tra le unità organizzative a ogni livello, assegnare autorizzazioni a livelli specifici, impostare gli obiettivi per livello di organizzazione e così via.|

> [!NOTE]
> I clienti non potranno eseguire l'onboarding del formato di file v2 a partire dal 15 luglio 2021 e dovranno invece usare il formato v2.1, tutti gli aggiornamenti futuri e la nuova capacità verranno eseguiti nel formato v2.1 e saranno completamente compatibili con il formato di file v1.

## <a name="best-practices"></a>Procedure consigliate
Il mapping accurato della gerarchia e della posizione che gli utenti occupano all’interno di tale gerarchia consente a Insights di fornire dati accurati e dati analitici più precisi e pertinenti per i diversi tipi di responsabili dell’istruzione.

Maggiori saranno i dettagli forniti, più rilevanti saranno i report e le schede in evidenza.

Ecco alcune procedure consigliate per garantire una distribuzione uniforme di SDS in modo che gli utenti possano sfruttare nel modo migliore Insights.

### <a name="file-format-version-to-ue"></a>Versione del formato di file a ue
*   Usare il formato di file V2.1 (presto disponibile) e sincronizzare i dati facoltativi usati da Education Insights

### <a name="users-and-roles"></a>Utenti e ruoli
*   Assicurarsi che **tutti gli utenti siano elencati nei file** forniti e sincronizzati. Questo include tutti gli studenti e il personale che devono visualizzare le unità organizzative da loro coperte.
    Se attualmente nel SIS sono elencati solo docenti, aggiungere manualmente gli altri utenti prima di caricare i file in SDS e sincronizzare i dati.
    Le statistiche raccolte da Insights sono solo degli studenti registrati. Se mancano alcuni studenti, ciò renderà i dati e le conclusioni fuorvianti.
    
*   Assicurarsi di **fornire il nome e il cognome di ogni utente**. In caso contrario, se si fa riferimento al loro indirizzo di posta elettronica, questo offrirà un’esperienza non ottimale per quanto riguarda i report e le schede in evidenza (sono schede con approfondimenti sull'attività o il rendimento degli studenti).

*   Il livello di voto/anno deve essere basato su questo [elenco di mapping](#supported-grade-level-values). 

*   È importante **aggiungere il livello anno/voto a tutti gli studenti** in modo che i dati delle attività possano essere aggregati e filtrati in base a esso.    

*   Assicurarsi di **assegnare ogni utente alla propria unità organizzativa pertinente**. In questo modo, Education Insights non mostrerà dati fuorvianti nei contenuti in evidenza di Education Insights.

    *   Uno studente può essere associato a più unità organizzative, ad esempio gli studenti iscritti ad un programma speciale o due facoltà. Nel caso in cui lo studente abbia più unità organizzative, fornire una riga per ognuno nel file degli utenti per tale studente.
    
    *   L'amministratore IT può concedere autorizzazioni in base all'unità organizzativa per il personale. **Bisogna assicurarsi che i membri del personale siano associati al livello di unità corretto**, in modo che ricevano le autorizzazioni di cui hanno bisogno. Ad esempio, un consulente assegnato a quattro scuole deve vedere tutti i voti di queste scuole e un preside deve vedere tutte le classi della propria scuola. 
    
*   **Il ruolo è essenziale**. Anche se si tratta di un elenco chiuso, è consigliabile provare a abbinare il ruolo dall’[elenco](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) al ruolo reale di ogni utente caricato. Questo consentirà di assegnare le autorizzazioni basate sui ruoli. Ad esempio, bisogna fornire a tutti i presidi le autorizzazioni per vedere le classi nel loro istituto di istruzione o a tutti i professori per vedere la proprie facoltà. 

### <a name="organizations"></a>Organizzazioni

* Assicurarsi che **la reale e completa gerarchia dell’organizzazione corrisponda**. A questo scopo, è possibile aggiungere manualmente il file. In alcuni casi, questa gerarchia non si riflette nel sistema informativo degli studenti. Tuttavia, può comunque essere necessario visualizzare l'aggregazione pertinente per ogni livello della gerarchia, assegnare autorizzazioni a livelli specifici, impostare gli obiettivi per livello dell'organizzazione e così via. 

* Assicurarsi che **tutte le unità organizzative nella gerarchia dell’organizzazione includano studenti o classi** in modo da aggregare i dati degli studenti. È consigliabile che gli studenti siano nella parte più basa della gerarchia.

> [!NOTE]
> Per altre informazioni sulla distribuzione SDS, consultare [Pianificazione SDS](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-data-using-sds"></a>Integrare SIS con SDS

School Data Sync (SDS) viene fornito con Office 365 per l’istruzione. SDS legge i dati dal sistema informativo degli studenti (SIS) di un istituto scolastico e lo integra con applicazioni Microsoft come Teams per consentire la creazione automatica di classi online e utenti.

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

