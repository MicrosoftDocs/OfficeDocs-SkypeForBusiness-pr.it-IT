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
ms.openlocfilehash: 7570368a6b9bd889bc5ed632cd1d057d70ae791a
ms.sourcegitcommit: 086d27c9381fc1f1c6523d4c48dea275dea917b7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49986425"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizzare i dati del sistema informativo degli studenti (SIS) con Insights per l’istruzione
Fornendo un maggiore numero di dati maggiori a [Insights per l’istruzione](class-insights.md), il supporto dei docenti nei confronti degli studenti migliorerà e allo stesso tempo anche il supporto dei responsabili per l’istruzione verso i docenti.

Per fornire informazioni approfondite a livello di organizzazione, è necessario usare [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) in modo da connettersi al sistema informativo degli studenti (SIS) per far sì che Insights abbia la struttura gerarchica del sistema didattico mappata correttamente. 

La visualizzazione di Insights a livello di classe come docente *non* richiede ciò, in quanto vengono usate la struttura e le autorizzazioni della classe di Teams.

## <a name="plan-your-sis-integration"></a>Pianificare l'integrazione SIS
I dati SIS forniscono la struttura gerarchica del sistema didattico e mappa quale utente viene assegnato in una determinata posizione.

Insights offre risultati ottimali quando viene usato il formato di file [SDS V2](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format), ma supporta anche [il formato di file SDS V1](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) con *funzionalità* limitate.

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Differenze tra i formati di file SDS V1 e V2

| Tipo di dati |   V1 | V2 (scelta consigliata) |
|:--- |:--- |:--- |
| **Utenti** | Il formato V1 contiene **solo docenti**, quindi per impostare le autorizzazioni a livello di organizzazione per i responsabili dell'istruzione, è necessario cercarli e definire manualmente i permessi per ciascuno di loro. | Il formato V2 contiene **tutti i ruoli** in modo che sia possibile assegnare autorizzazioni basate sui ruoli. |
| **Organizzazioni** | Il formato V1 contiene **solo istituti di istruzione**, quindi viene visualizzato un solo livello di aggregazione (tutti gli istituti di istruzione). È possibile ingrandire un istituto di istruzione specifico usando un elenco completo. Tuttavia, tale elenco potrebbe avere un numero elevato di istituti di istruzione o contenerne diversi tipi, il che potrebbe rendere difficile il confronto (ad esempio la scuola primaria con quella secondaria o l’istituto d’arte e il liceo scientifico).<br/><br/> Quando è presente una gerarchia, è possibile creare livelli logici, ad esempio un dipartimento di scienze o arte.| Il formato V2 contiene **l'intera gerarchia del distretto o dell’istituzione**, comprese università, college, facoltà, campus, aree geografiche, programmi e così via.<br/><br/> Con una gerarchia è possibile visualizzare l'aggregazione pertinente per ogni livello, confrontare rapidamente tra le unità organizzative a ogni livello, assegnare autorizzazioni a livelli specifici, impostare gli obiettivi per livello di organizzazione e così via.|

### <a name="type-of-data-required"></a>Tipo di dati richiesti
La seguente tabella fornisce il tipo di dati necessari per sfruttare al massimo Insights.

| Tipo di dati | Esempi di cosa è necessario fornire|Perché è importante?|
|:--- |:--- |:--- |
| **Utenti** |   Ruolo (ad esempio studente)<br/> Classe/anno (ad esempio 10)<br/> Organizzazione (nome) | Quando ogni persona viene correttamente assegnata al proprio ruolo, classe/anno e organizzazione, possiamo assicurare che i riepiloghi e le aggregazioni siano corretti.|
| **Organizzazioni** | Tipo di organizzazione (ad esempio università) |   La gerarchia qui è importante. Ad esempio, le scuole potrebbero appartenere a un distretto e quel distretto, a sua volta, a uno stato.<br/> Quando un responsabile dell’istruzione di un distretto è autorizzato a visualizzare i dati, questo potrà avere accesso solo ai dati degli istituti di istruzione di quel distretto.|
| **Classi** | Titolo (ad esempio Informatica 101) | Questo specifica quali lezioni si tengono nell'organizzazione. È necessario eseguire correttamente il mapping di ciò per poter assegnare lo studente alla classe corretta. |
| **Iscrizione** | Ruolo (ad esempio studente) | Questa opzione è per studenti e docenti e consente di sapere a quale classe sono iscritti. |

> [!NOTE]
> Durante il processo di distribuzione, è possibile decidere se usare SDS per il provisioning degli utenti e delle classi in Teams o solo per fornire dati a Insights.

## <a name="best-practices"></a>Procedure consigliate
Una mapping accurato della gerarchia e che posizione occupano tutti appartengono all’interno tale gerarchia consente a Insights di fornire dati accurati e approfondimenti più precisi e pertinenti per i responsabili dell'istruzione.

Maggiori saranno i dettagli forniti, più rilevanti saranno i report e le schede in evidenza.
Di seguito sono riportate alcune procedure consigliate per garantire una distribuzione fluida di SDS in modo che gli utenti possano sfruttare al massimo Insights.

### <a name="users"></a>Utenti
*   Assicurarsi che *tutti gli utenti* siano elencati nei file forniti e sincronizzati. Questo include tutti gli studenti e il personale che devono visualizzare le unità organizzative da loro coperte.

    Se attualmente nel SIS sono elencati solo docenti, aggiungere manualmente gli altri utenti prima di caricare i file in SIS e sincronizzare i dati.

    Se mancano alcuni studenti, le statistiche raccolte da Insights sono solo degli studenti registrati e ciò renderà i dati e le conclusioni fuorvianti.
    
*   Assicurarsi di *fornire il nome e il cognome di ogni utente*. In caso contrario, se si fa riferimento al loro indirizzo di posta elettronica, questo offrirà un’esperienza povera per quanto riguarda i report e le schede in evidenza (sono schede con approfondimenti sull'attività o il rendimento degli studenti).

*   L’opzione *classe/anno deve contenere due cifre* (ad esempio, 07 per il settimo anno). Consultare l’[elenco di mapping](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported). 

*   È importante aggiungere la *classe/anno a tutti gli studenti* in modo che sia possibile filtrare i dati in base a questi criteri.    

*   Assicurarsi di *assegnare ogni utente alla propria unità organizzativa pertinente*. In tal modo, non verranno mostrati dati fuorvianti nelle schede in evidenza basati sui dati aggregati per ciascuna unità.

    *   Uno studente può essere associato a più unità organizzative, ad esempio gli studenti iscritti ad un programma speciale o due facoltà. In tal caso, bisogna immettere due righe nel file utenti per quello studente, una per ciascuna organizzazione.
    
    *   In base all'unità organizzativa per il personale, sarà possibile definire le autorizzazioni appropriate. Bisogna assicurarsi che siano associati al livello di unità corretto, in modo che ricevano le autorizzazioni di cui hanno bisogno. Ad esempio, un consulente assegnato a quattro scuole deve vedere tutte le classi di queste scuole e un preside deve vedere tutte le classi della propria scuola. 
    
*   Il ruolo è essenziale. Anche se si tratta di un elenco chiuso, è consigliabile provare a abbinare il ruolo dall’[elenco](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) al ruolo reale di ogni utente caricato. In questo modo, sarà possibile assegnare le autorizzazioni basate sui ruoli. Ad esempio, bisogna fornire a tutti i presidi le autorizzazioni per vedere le classi nel loro istituto di istruzione o a tutti i professori per vedere la proprie facoltà. 

### <a name="organizations"></a>Organizzazioni

* Assicurarsi che *la reale gerarchia dell’organizzazione corrisponda*. A questo scopo, è possibile aggiungere manualmente il file. In alcuni casi, questa gerarchia non si riflette nel sistema informativo degli studenti. Tuttavia, può comunque essere necessario visualizzare l'aggregazione pertinente per ogni livello della gerarchia, assegnare autorizzazioni a livelli specifici, impostare gli obiettivi per livello dell'organizzazione e così via. 

* Assicurarsi che *tutte le unità organizzative nella gerarchia dell’organizzazione includano studenti o classi* in modo da aggregare i dati degli studenti. È consigliabile che gli studenti siano nella parte più basa della gerarchia.

> [!NOTE]
> Per altre informazioni sulla distribuzione SDS, consultare [Pianificazione SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-using-sds"></a>Integrare SIS con SDS

School Data Sync (SDS) viene fornito con Office 365 per l’istruzione. SDS legge i dati dal sistema informativo degli studenti (SIS) di un istituto scolastico e lo integra con Teams per consentire la creazione automatica di classi online e utenti.

Inoltre, sincronizza i dati del sistema informativo degli studenti con Insights.

### <a name="sync-with-insights"></a>Sincronizzare con Insights

Prima di tutto, è necessario attivare Insights per avviare il processo di sincronizzazione.

* Nel [**portale SDS**](https://sds.microsoft.com), passare a **Impostazioni**, scorrere per il basso fino a **Raccogli dati per Insights** e verificare che sia abilitato (è *attivo* per impostazione predefinita).

* Scorrere verso il basso fino all'opzione successiva, **Sincronizza i dati dell'organizzazione da SDS (anteprima)** e attivarla.

Se l'opzione *Sincronizza i dati dell'organizzazione da SDS (anteprima)* non è disponibile nella pagina Impostazioni, passare alla [pagina di iscrizione](https://aka.ms/insights/join) per fornire le informazioni e un membro del team si metterà in contatto.

:::image type="content" source="media/insights-sds-settings.png" alt-text="Interruttori Sincronizza con Insights":::

### <a name="deploy-sds"></a>Distribuire SDS
**Se SDS è già in uso**, è consigliabile seguire le [procedure consigliate](#best-practices). 

Per sincronizzare i profili correnti con Approfondimenti, passare a **Sincronizza profilo/i**, fare clic su **Modifica** e selezionare **Sincronizza i dati dell'organizzazione da SDS**. Per la sincronizzazione iniziale, è consigliabile attendere 24 ore prima che i report siano disponibili dopo l'aggiornamento dei dati da SIS.  

**Se SDS non è ancora in uso**, è necessario [distribuirlo](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).

Durante il processo di distribuzione, è possibile decidere se usare SDS per il provisioning degli utenti e delle classi in Teams o solo per fornire dati a Insights.

> [!NOTE]
> Se si è già a metà dell'anno e i team sono già stati creati manualmente, usare SDS solo per fornire i dati a Insights e, per l’anno successivo, è consigliabile usare SDS per il provisioning di utenti e classi in Teams.

### <a name="verify-the-sync-process"></a>Verificare il processo di sincronizzazione
Viene visualizzata una nuova area di notifica accanto a Sincronizza dati organizzativi - Anteprima nella pagina Impostazioni.
 
*   Se lo stato è **In corso**, attendere fino a 24 ore dopo la distribuzione del profilo SDS.

*   Se lo stato è **Completato**, ora sarà possibile visualizzare Insights a livello dell'organizzazione e continuare con il passaggio successivo.

*   Se lo stato è **Completato con errori**, **Completato con avvisi** o **Interrotto**, scaricare il file di log contenente gli errori e gli avvisi per la sincronizzazione più recente e verificare se è possibile correggerli. 

> [!IMPORTANT]
> In caso di problemi, è possibile contattare il [supporto tecnico](https://aka.ms/edusupport) per assistenza.
