---
title: Pianificare il dashboard per la qualità delle chiamate per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Riepilogo: informazioni su cosa tenere in considerazione quando si pianifica il dashboard qualità chiamata.'
ms.openlocfilehash: c98828f8fed3567a892e20dcab8040bb731c91f2
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328438"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Pianificare il dashboard per la qualità delle chiamate per Skype for Business Server 
 
**Riepilogo:** Informazioni su cosa tenere in considerazione quando si pianifica il dashboard qualità chiamata.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Panoramica del dashboard sulla qualità delle chiamate di Skype for Business Server

Skype for Business Server Call Quality Dashboard (Call Quality Dashboard) è un livello di Reporting superiore al database di qualità dell'esperienza nel server di monitoraggio in Skype for Business Server. Call Quality dashboard USA Microsoft SQL Server Analysis Services per consentire l'utilizzo aggregato e le informazioni sulla qualità delle chiamate, nonché per filtrare e ruotare il set di dati. Le caratteristiche di Call Quality dashboard includono:
  
- **Archiviazione degli archivi dei dati QoE tramite il componente archivio QoE di Call Quality dashboard.** Il componente archivio QoE può archiviare i dati QoE per una durata molto più lunga rispetto a quella del server di monitoraggio. In questo modo è possibile creare tendenze e report per un massimo di sette mesi di dati alla volta, con la possibilità di scorrere la finestra dei report fino a quando sono presenti dati.
- **Creazione di report e analisi con la potenza e la velocità di Microsoft SQL Server Analysis Services.** Call Quality dashboard USA Microsoft SQL Analysis Services per creare rapidamente funzionalità di riepilogo, filtro e rotazione per alimentare il dashboard tramite un cubo di analisi. La velocità di esecuzione della segnalazione e la possibilità di eseguire il drill-down dei dati possono ridurre drasticamente i tempi di analisi.
- **Nuovo schema di dati ottimizzato per i report sulla qualità delle chiamate.** Il cubo ha uno schema progettato per la creazione di report e indagini di qualità vocale. Gli utenti del portale possono concentrarsi sulle attività di creazione di report anziché capire in che modo lo schema di database delle metriche QoE esegue il mapping alle visualizzazioni necessarie. La combinazione dell'archivio QoE e del cubo offre un'astrazione che riduce la complessità della creazione di report e dell'analisi tramite Call Quality dashboard. Lo schema di database di archiviazione QoE contiene anche tabelle che possono essere popolate con dati specifici della distribuzione per migliorare il valore complessivo dei dati.
- **Progettazione report incorporata e modifica del report sul posto.** Il componente portale include diversi report predefiniti modellati dopo la metodologia di qualità delle chiamate. Gli utenti del portale possono modificare i report e creare nuovi report tramite la funzionalità di modifica del portale.
- **Accesso alle API Web per la struttura del report e i dati del cubo di analisi.** Dashboard Reporting Framework non è l'unico modo per visualizzare i dati dal cubo. Call Quality dashboard offre diversi esempi di uso di HTML e JavaScript per recuperare i dati dalle API Web di Call Quality dashboard ed eseguire il rendering dei dati in un formato personalizzato. La combinazione dell'editor report e delle API Web Call Quality dashboard consente la prototipazione rapida di report e layout di report personalizzati.

> [!NOTE]
> Un amministratore può ora gestire Skype for Business Server 2019 usando [Call Quality dashboard versione 3](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore). Questo richiede un'implementazione ibrida e l'uso del connettore dati chiamata (CDC). Per altre informazioni sull'abilitazione di CDC, vedere [Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) . Per la documentazione di Call Quality dashboard versione 3, vedere [attivare e usare la chiamata Quality dashboard per Microsoft teams e Skype for business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) per altre informazioni su Call Quality dashboard versione 3.

## <a name="cqd-design-goals"></a>Obiettivi di progettazione Call Quality dashboard

Call Quality dashboard consente ai professionisti IT di usare i dati aggregati per identificare le aree di interesse nell'ambiente in cui si verificano problemi di qualità multimediale. Consente a un professionista IT di confrontare le statistiche per diversi gruppi di utenti e identificare tendenze e modelli. Non è focalizzato sulla risoluzione dei singoli problemi di chiamata, ma sull'individuazione di problemi e soluzioni che verranno applicati a molti utenti in un ambiente specifico. 
  
## <a name="call-quality-dashboard-components"></a>Componenti dashboard qualità chiamata

Il dashboard qualità chiamata è costituito da diversi database, processi e applicazioni Web di Microsoft SQL Agent. I processi di Microsoft SQL Agent copiano periodicamente i dati dal database di metriche QoE nel database di archiviazione QoE ed elaborano il cubo con i dati nel database di archivio QoE. Il database del repository archivia le definizioni di report che alimentano il portale. Il portale fornisce l'accesso al browser ai dati del cubo. 
  
I componenti Call Quality dashboard, inclusi i database archivio QoE, cubo e repository, possono essere installati nel server di monitoraggio, installati nel proprio server o installati in più server. Il metodo di installazione specifico dipende dalle esigenze di prestazioni di Call Quality dashboard e dall'impatto di altri processi sugli stessi server. Per altre informazioni, vedere la sezione "componenti e topologie per Call Quality Dashboard" più avanti in questo articolo.
  
### <a name="architectural-overview"></a>Panoramica dell'architettura

Per riepilogare, Call Quality Dashboard richiede gli elementi seguenti:
  
- Due database: un database di archiviazione e un database del repository.
    
- Un cubo SSAS che Visualizza i dati aggregati 
    
- IIS ospita il portale Web Call Quality dashboard
    
![Componenti Call Quality dashboard](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La stessa architettura Call Quality dashboard supporta Lync Server 2013 e Skype for business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>Call Quality dashboard e Skype for business vs Lync 2013

 In un ambiente Skype for business è disponibile solo le funzionalità seguenti:
  
- Segnalazione Wi-Fi della potenza del segnale
    
- Creazione di report Wi-Fi dei driver del chipset
    
- Valutare i dati delle chiamate 
    
## <a name="information-available-through-cqd"></a>Informazioni disponibili tramite Call Quality dashboard

Call Quality dashboard può visualizzare i conteggi dei flussi di condivisione di file audio, video e applicazioni di Skype for Business Server e il conteggio delle chiamate positive e negative, nonché i rapporti di chiamate non valide. Le visualizzazioni possono essere affettate e filtrate da molte dimensioni diverse. Call Quality dashboard estrae i dati dal database di metriche QoE nel server di monitoraggio. I dati vengono quindi Uniti a tutti i dati forniti dal cliente, ad esempio il mapping della subnet-to-Building di rete per creare report come "qualità di chiamata per edificio". 
  
Call Quality dashboard astrae anche molte delle idiosincrasie dei dati QoE interni, ad esempio "chiamante" e "chiamato", in modo che l'utente possa concentrarsi sulla creazione di visualizzazioni di report intorno a "Server" e "client". Seguendo la metodologia della qualità delle chiamate, Call Quality dashboard è semplificato per identificare le condizioni che le tasche delle chiamate scadenti hanno in comune, uno dei principi per migliorare la qualità delle chiamate.
  
## <a name="viewing-data-in-cqd"></a>Visualizzazione dei dati in Call Quality dashboard

I dati di Call Quality dashboard possono essere visualizzati tramite il portale di Call Quality dashboard e accessibili tramite le chiamate API REST.
  
### <a name="cqd-portal"></a>Portale Call Quality dashboard

Il portale è il modo più rapido per visualizzare i dati nel cubo. Il portale include diversi report predefiniti che possono essere usati immediatamente. I report predefiniti sono collegati in modo strutturato per guidare l'utente a sezioni più piccole e piccole dei dati delle chiamate. I report predefiniti evidenziano anche i diversi modi in cui i dati possono essere visualizzati dimostrando una combinazione di grafici e tabelle con pivot, filtri e misure diversi. Ogni utente che accede al portale può avere il proprio set di report che può modificare e condividere. Per altre informazioni sull'uso del portale Web Call Quality dashboard, vedere usare il [dashboard qualità chiamata per Skype for Business Server](use.md).
  
Sistemi operativi supportati per il portale di Call Quality Dashboard: Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (solo Skype for Business Server 2019 Call Quality Dashboard).
  
Browser supportati per il portale di Call Quality Dashboard: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>API REST

È anche possibile accedere ai dati del cubo tramite le chiamate API REST. I dati recuperati tramite le chiamate API REST possono essere renderizzati tramite pagine HTML. Gli utenti possono sfruttare la velocità di query e lo schema di alto livello di Call Quality dashboard, mentre continuano a creare report personalizzati adatti alle esigenze aziendali. Per altre informazioni sull'API e gli esempi, vedere [sviluppare il dashboard per la qualità delle chiamate per Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definizione dei requisiti dell'organizzazione per Call Quality dashboard

Call Quality dashboard fornisce l'archiviazione dei dati QoE e l'analisi rapida e profonda dei dati sulla qualità delle chiamate. La guida seguente consente di decidere quando e perché distribuire Call Quality dashboard.
  
### <a name="when-to-deploy-cqd"></a>Quando distribuire Call Quality dashboard

 **Call Quality dashboard può essere distribuito per stabilire una misurazione della qualità delle chiamate di base, anche se un'organizzazione non riscontra problemi di qualità delle chiamate.** La definizione di una misurazione della qualità delle chiamate di base è importante perché ogni organizzazione ha una combinazione diversa di Wi-Fi rispetto a Wired e remote versus Office worker. Quando sorgono problemi di qualità delle chiamate, le misure di qualità delle chiamate più recenti possono essere confrontate con gli intervalli di tempo precedenti. Le caratteristiche di tendenza di Call Quality dashboard permettono un facile rilevamento delle modifiche nella qualità delle chiamate nel tempo.
  
 **Call Quality dashboard può essere distribuito per trovare in modo proattivo aree problematiche che potrebbero avere un impatto sulla qualità delle chiamate.** Anche se la qualità media delle chiamate per un'organizzazione può soddisfare le destinazioni impostate dall'organizzazione, è possibile che si verifichino problemi di qualità delle chiamate nascoste dietro la metrica media. Call Quality dashboard consente la ripartizione delle metriche di qualità delle chiamate in base a tabelle pivot per molte dimensioni nel database QoEMetrics. L'individuazione di valori anomali nei gruppi peer è un modo rapido per individuare in maniera proattiva i problemi di qualità delle chiamate.
  
 **Call Quality dashboard deve essere distribuito se sono presenti problemi di qualità delle chiamate nell'organizzazione per ridurre il tempo necessario per la risoluzione dei problemi.** Call Quality dashboard può semplificare le indagini esistenti sulla qualità delle chiamate offrendo funzionalità rapide per la creazione di report e capacità di drill-down dinamiche. Call Quality dashboard è progettato per molti tipi di flussi di lavoro in indagini sulla qualità delle chiamate per la convalida delle riparazioni per l'ambiente.
  
### <a name="why-deploy-cqd"></a>Perché distribuire Call Quality dashboard

 **Call Quality dashboard deve essere distribuito se la segnalazione QoE deve avvenire per più di 3 mesi di dati.** I report del database di QoEMetrics e del server di monitoraggio sono progettati per mantenere e segnalare un set di dati di piccole dimensioni. Il database delle metriche QoE è ottimizzato per gli inserimenti rapidi e, pertanto, la segnalazione delle prestazioni può essere ostacolata da un grande volume di chiamate o da un report di accesso al database. Il database di archiviazione QoE di Call Quality dashboard offre una seconda copia dei dati relativi alle metriche QoE con funzionalità di conservazione molto più lunghe. Il portale è anche ottimizzato per visualizzare fino a 7 mesi di dati alla volta e può segnalare tutti i dati nell'archivio QoE in base alle esigenze.
  
 **Call Quality dashboard deve essere distribuito se sono necessari report QoE personalizzati.** Il portale ha una caratteristica di editor di report per la creazione e la prototipazione di report in modo rapido e semplice. Rende inoltre disponibili le API di REST per l'accesso a livello di codice ai dati del cubo, consentendo la presentazione personalizzata usando HTML/JavaScript o molti altri Framework. Non è più necessario creare nuove query SQL per la creazione di visualizzazioni dati personalizzate per i report.
  
 **Call Quality dashboard deve essere distribuito se la funzionalità di segnalazione QoE esistente non soddisfa la velocità o la profondità richieste dall'organizzazione.** Call Quality dashboard include molti report predefiniti. I report sono immediatamente utili e dimostrano come la foratura progressiva dei dati possa offrire ulteriori informazioni su ogni livello. La gerarchia Reports aiuta anche a gestire i numerosi report in modo logico e promuove la creazione di molti altri report facilmente accessibili e comprensibili. Call Quality Dashboard non offre solo velocità e flessibilità, ma è anche ottimizzato per i flussi di lavoro sviluppati dalla metodologia di qualità delle chiamate.
  
## <a name="components-and-topologies-for-cqd"></a>Componenti e topologie per Call Quality dashboard

Call Quality dashboard include diversi componenti e consente di comprendere i requisiti di ogni componente e la loro relazione tra loro per ottenere la distribuzione più semplice e ottimale dello strumento. La tabella seguente descrive il componente dipendente per ogni componente Call Quality dashboard.
  

|**Nome componente**|**Componente dipendente**|
|:-----|:-----|
|Archivio QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portale  <br/> |Microsoft Information Services  <br/> |
|Servizio repository (parte dell'installazione del portale)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Per l'archivio e il cubo QoE, alcune opzioni di distribuzione richiedono le edizioni Business Intelligence o Enterprise di Microsoft SQL Server. Per altre informazioni, vedere la sezione [requisiti per l'infrastruttura per Call Quality dashboard](plan.md#Infrastructure_Req) .
  
![Componenti Call Quality dashboard](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configurazione Single Server

Tutti i componenti Call Quality dashboard e i componenti dipendenti possono essere installati su un unico computer. La configurazione di una singola casella è la configurazione più semplice e consente a Call Quality dashboard di essere indipendente. Call Quality dashboard avrebbe solo bisogno di accedere al database delle metriche QoE nel server di monitoraggio. Il server Call Quality dashboard può essere un computer autonomo, una macchina virtuale o può anche essere il server di monitoraggio, a seconda delle risorse disponibili del computer host e dei requisiti di prestazioni. 
  
Durante l'installazione, l'utente che esegue l'installazione deve semplicemente specificare le istanze di Microsoft SQL Server e Microsoft SQL Server Analysis Services precedentemente configurate nel computer in cui deve essere installato Call Quality dashboard. Per altre informazioni, fare riferimento a [distribuzione di Call Quality dashboard per Skype for Business Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configurazione multiserver

In una configurazione multiserver, l'archivio QoE, il cubo e il portale possono essere tutti su computer diversi. Per la configurazione multiserver sono disponibili due usi principali:
  
- Hosting di Call Quality dashboard Web Portal e Call Quality dashboard Cube in server diversi.
    
- Hosting di un portale "Development" separato dal portale "produzione". 
    
  **Hosting di Call Quality dashboard Web Portal e Call Quality dashboard Cube in computer diversi.** Le organizzazioni che potrebbero avere requisiti per separare il portale di Call Quality dashboard dall'installazione di SQL Server o che potrebbero voler combinare le edizioni di SQL Server per l'istanza di SQL Server e l'istanza di SQL Server Analysis Services possono scegliere di installare il portale di Call Quality dashboard e Cubo di Call Quality dashboard su computer diversi. Il componente archivio QoE può anche essere l'unico componente Call Quality dashboard installato se l'organizzazione vuole semplicemente avere un metodo sostenibile per archiviare i dati QoE senza raggiungere limiti di prestazioni nel server di monitoraggio.
  
![Call Quality Dashboard server singolo](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosting di un portale "Development" separato dal portale "produzione".** Le organizzazioni che sviluppano i propri report personalizzati (tramite le API REST) potrebbero preferire la distribuzione di istanze aggiuntive (Call Quality Dashboard) del portale accanto al portale di produzione che gli utenti abituali accedono per il monitoraggio o le indagini sulla qualità delle chiamate. Il portale di sviluppo può isolare le eventuali modifiche apportate al portale dall'ambiente di produzione. I portali Web aggiuntivi possono essere distribuiti in computer diversi (illustrato di seguito) o distribuiti in directory Web diverse nello stesso computer (non visualizzate). Per eseguire quest'ultimo, il portale Web Call Quality dashboard aggiuntivo deve essere copiato manualmente nel computer di produzione perché il processo di configurazione di Call Quality dashboard distribuisce sempre il portale Web di Call Quality dashboard al sito Web predefinito con i nomi predefiniti delle applicazioni Web.
  
![Pianificare Call Quality dashboard multi server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologie supportate

Call Quality Dashboard non unisce dati provenienti da più database QoEMetrics, come nel caso di più topologie di Skype for Business Server, ognuna con il proprio server di monitoraggio. Ogni istanza di Call Quality dashboard deve puntare a un database di QoEMetrics. Tuttavia, poiché Call Quality dashboard sposterà gran parte del carico di lavoro di Reporting fuori del server di monitoraggio, le grandi organizzazioni che necessitano di distribuire un server di monitoraggio per la topologia di Skype for Business Server dovrebbero prendere in considerazione l'uso di un server di monitoraggio per tutte le topologie.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisiti per l'infrastruttura per Call Quality dashboard
<a name="Infrastructure_Req"> </a>

Call Quality dashboard, inclusi tutti i componenti e i componenti dipendenti, può essere distribuito in una macchina virtuale, in un singolo computer o in più computer. Di seguito sono elencati i requisiti minimi per software e hardware. La disponibilità dei dati e le prestazioni delle query possono variare da minuti a ora, a seconda del numero di utenti e hardware e della configurazione attivi di Skype for Business Server, quindi alcune misurazioni delle prestazioni sono indicate di seguito.
  
|||
|:-----|:-----|
|Per Call Quality dashboard 2015 <br/> |  <br/> |
|Sistemi operativi supportati  <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server supportato  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Per Call Quality dashboard 2019 <br/> |  <br/> |
|Sistemi operativi supportati  <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server supportato  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
Call Quality dashboard USA Microsoft SQL Server, Microsoft SQL Server Analysis Services e Microsoft Internet Information Services in modo che i requisiti hardware e software minimi di Call Quality dashboard siano sostanzialmente gli stessi di questi componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione intorno alla freschezza dei dati (che dipenderà in parte dal volume dei dati QoE generati dall'organizzazione) e dai costi di distribuzione, è necessario apportare ulteriori considerazioni sulla distribuzione.
  
L'elaborazione dei dati in Call Quality dashboard è suddivisa in due fasi principali: 
  
- Processo di archiviazione QoE
    
- Elaborazione del cubo Call Quality dashboard
    
  **Elaborazione degli archivi QoE.** L'attività di elaborazione degli archivi QoE consente di copiare i dati dal database di metriche QoE nel server di monitoraggio al database di archiviazione QoE. Esistono due situazioni in cui il tempo di elaborazione dell'attività avrebbe caratteristiche di prestazioni radicalmente diverse. La prima è dopo l'installazione iniziale di Call Quality dashboard. Quando l'attività viene eseguita per la prima volta dopo una nuova installazione, l'attività di elaborazione degli archivi QoE copierà tutti i dati presenti nel database di metriche QoE nel database di archiviazione QoE. La seconda è l'elaborazione periodica dopo il turno iniziale. L'attività di elaborazione degli archivi QoE verrà eseguita ogni 15 minuti ed elaborerà i nuovi record QoE presenti nel database delle metriche QoE. In genere, il tempo di elaborazione iniziale non è un problema perché viene eseguito solo la prima volta, quando Call Quality dashboard è installato. Tuttavia, se il server Call Quality dashboard è sottoposto a provisioning gravemente, questa attività può richiedere diverse ore. Fare riferimento alla tabella seguente, ad esempio tempi di elaborazione degli archivi QoE iniziali.
  
  **Elaborazione del cubo Call Quality dashboard.** L'attività di elaborazione del cubo aggrega i dati del database di archivio QoE nel cubo. Il tempo di elaborazione iniziale del cubo e il tempo di elaborazione successivo del cubo sono determinati da SQL Server Analysis Services Edition usato per il cubo Call Quality dashboard. Se viene usata l'edizione standard, non c'è differenza tra il tempo di elaborazione del cubo iniziale e il tempo di elaborazione del cubo successivo, perché ogni volta che i dati del cubo vengono aggiornati, sarà sempre un'elaborazione completa di tutti i dati disponibili. Questo significa che il tempo di elaborazione del cubo aumenta man mano che aumenta la quantità di dati nel database di archivio QoE. Poiché la versione Business Intelligence Edition e Enterprise Edition di SQL Server include il supporto per le partizioni, se viene usata un'edizione, solo l'esecuzione iniziale elaborerà tutti i dati nel database di archivio QoE. Nelle esecuzioni successive, quando l'attività viene attivata ogni 15 minuti, l'attività elaborerà solo i nuovi record aggiunti al database di archiviazione QoE dall'ultima volta che l'attività è stata eseguita. Una volta al giorno, sarà disponibile anche un'elaborazione completa nella partizione che contiene i dati del mese corrente.
  
Le caratteristiche del computer fisico possono influire sulle prestazioni di Call Quality dashboard e sulle caratteristiche software disponibili nei componenti di SQL Server. Il componente archivio QoE sarà più intenso rispetto ad altri componenti, mentre il componente cubo sarà più intensivo di CPU e memoria. Tutti questi fattori contribuiscono al tempo totale di elaborazione dei dati di Call Quality dashboard, che influenza direttamente la disponibilità e la freschezza dei dati. Le organizzazioni dovrebbero prendere decisioni sull'hardware e il software in base alle singole esigenze dell'organizzazione. 
  
### <a name="tested-hardware-configurations"></a>Configurazioni hardware testate

Questa sezione presuppone che esista un singolo DB QoEMetrics nell'ambiente. 
  
**Profili macchina**

|**Computer**|**Core della CPU**|**RAM**|**Archivio QoE e cubo nello stesso disco**|**Archivio QoE e SQL Temp DB sullo stesso disco**|
|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |4  <br/> |7 GB  <br/> |Sì  <br/> |Sì  <br/> |
|4 core  <br/> |4  <br/> |20 GB  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|8 core  <br/> |8  <br/> |32 GB  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|16 core  <br/> |16  <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Risultati delle prestazioni**

|**Computer**|**Dimensioni DB QoE metriche**|**Partizioni SQL**|**Tipo di disco**|**Numero di flussi**|**Processo di archiviazione iniziale**|**Processo cubo iniziale**|**Processo di archiviazione successivo**|**Processo cubo successivo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |900 MB  <br/> |Singola  <br/> |VHD (dimensione variabile)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Singola  <br/> |VHD (dimensione variabile)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Singola  <br/> |VHD (dimensioni fisse)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |30 + GB  <br/> |Singola  <br/> |VHD (dimensioni fisse)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Singola  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Più  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 core  <br/> |30 + GB  <br/> |Singola  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 core  <br/> |30 + GB  <br/> |Più  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 core  <br/> |200 GB  <br/> |Singola  <br/> |Più dischi  <br/> |125 M  <br/> |6 + giorni  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 core  <br/> |500 GB  <br/> |Più  <br/> |Più mandrini  <br/> |250 M  <br/> |8 giorni  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Non si prevede che questi vengano rilevati in distribuzioni reali perché il database delle metriche QoE dovrebbe avere rispettivamente 9 e 18 mesi di dati, ma sono forniti qui per la completezza.
  
### <a name="service-account-requirements"></a>Requisiti per l'account del servizio

È necessario un account (con accesso in lettura a QoEMetrics) che l'agente SQL nel server Call Quality dashboard può usare per l'importazione di dati in QoEArchiveDB.
  
Potrebbe essere necessario configurare un account separato per un processo SSAS per estrarre i dati da QoEArchiveDB (si tratta di un processo facoltativo).
  
In genere, IIS usa il servizio di rete come identità del pool di app, ma può essere configurato in un account del servizio.
  
### <a name="portal-access-control"></a>Controllo di accesso portale

Per impostazione predefinita, qualsiasi utente autenticato ha accesso. Questa operazione può essere modificata usando le regole di autorizzazione di IIS per limitarle a un gruppo specifico.
  
### <a name="pre-install-requirements"></a>Requisiti di pre-installazione

Queste istruzioni presuppongono che un database di metriche QoE sia già stato installato e venga eseguito da qualche parte nella topologia di Skype for Business Server.
  
#### <a name="hardware-requirements"></a>Requisiti hardware

Call Quality dashboard USA Microsoft SQL Server, Microsoft SQL Analysis Server e Microsoft Internet Information Server in modo che i requisiti hardware e software minimi di Call Quality dashboard siano sostanzialmente gli stessi di questi componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione intorno alla freschezza dei dati (che dipenderà in parte dal volume dei dati QoE generati dall'organizzazione) e dai costi di distribuzione, è necessario apportare ulteriori considerazioni sulla distribuzione.
  
#### <a name="software-requirements"></a>Requisiti software

Per Call Quality dashboard sono necessari i sistemi operativi seguenti:
  
- Windows Server 2008 R2 con IIS 7,5
    
- Windows Server 2012 con IIS 8,0
    
- Windows Server 2012 R2 con IIS 8,5

- Windows Server 2016 con IIS 10,0 (solo per Skype for Business Server 2019 Call Quality Dashboard)

- Windows Server 2019 (solo per Skype for Business Server 2019 Call Quality Dashboard)
    
Di seguito sono riportati i servizi ruolo IIS necessari (in ordine gerarchico):
  
- Server Web
    
  - Caratteristiche HTTP comuni
    
  - Contenuto statico
    
  - Documento predefinito
    
  - Sviluppo di applicazioni
    
  - ASP.NET
    
  - Filtri ISAPI
    
  - Diagnostica &amp; per l'integrità
    
  - Registrazione HTTP
    
  - Sicurezza
    
  - Autorizzazione URL
    
  - Autenticazione di Windows
    
  - Strumenti di gestione
    
  - Console di gestione di IIS
    
> [!NOTE]
>  Tenere presente quanto segue per i requisiti seguenti: sono disponibili le versioni > 3,5 e 4,5 di .NET Framework. Entrambi sono obbligatori (in particolare, è necessario 3,5 SP1). > in alcuni sistemi, se ASP.NET è configurato prima dell'installazione di IIS, ASP.NET potrebbe non essere registrato in IIS. Il problema si manifesta in assenza di pool di applicazioni per la versione di .NET corrispondente e manca anche della versione CLR .NET nella configurazione del pool di app. Per risolvere un problema di questo tipo in Windows Server 2008 R2 `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`, eseguire. In Windows Server 2012 e Windows Server 2012 R2 eseguire `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` le operazioni seguite rimuovendo il modulo "ServiceModel" dal sito Web predefinito in Gestione IIS. > gli strumenti di gestione sono facoltativi, ma consigliati.
  
Per installare questi requisiti con PowerShell, eseguire le operazioni seguenti:
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Sono supportate le versioni seguenti di SQL Server:
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 (solo per Skype for Business Server 2019 Call Quality Dashboard)
    
Business Intelligence o Enterprise Edition è consigliato per motivi di prestazioni. Queste edizioni consentono l'uso di più file di partizione che possono essere elaborati in parallelo, che è vantaggioso per l'elaborazione dei dati che si estendono più mesi o più. 
  
Anche se non è consigliabile, anche Standard Edition è supportato. L'elaborazione sarà vincolata a una singola partizione (che deve essere configurata durante l'installazione). 
  
In tutti i casi deve essere installato "Database Engine Services" e "Analysis Services". È consigliabile ma non necessario installare anche la caratteristica "strumenti di gestione-completamento", che aggiunge il supporto di SQL Server Management Studio per Analysis Services. La schermata di selezione delle caratteristiche dovrebbe essere simile alla figura.
  
![Requisiti di funzionalità di SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Quando si configura la configurazione di SSAS, nella configurazione di Analysis Services impostare "modalità server" su "modalità multidimensionale e data mining". 
  
Per altre informazioni sull'installazione e la configurazione delle funzionalità di SQL Server Business Intelligence, vedere [installare Analysis Services in modalità multidimensionale e data mining](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisiti per l'account

I tre account di servizio del dominio sono consigliati per il principio del privilegio minimo: 
  
- Uno che ha già sia un'entità di sicurezza di accesso per il database di metriche QoE (con privilegio db_datareader) che un'identità di sicurezza dell'account di accesso nell'istanza di SQL Server di archiviazione QoE (necessaria per creare un oggetto server collegato durante l'installazione). Questo account verrà usato per eseguire il passaggio "dati archivio QoE" del processo di SQL Server Agent.
    
- Uno che verrà usato per eseguire il passaggio "processo cubo" del processo di SQL Server Agent. Il programma di installazione creerà un'identità di sicurezza dell'account di accesso al database di archiviazione QoE (con privilegi di lettura e scrittura) e creerà anche un membro nel ruolo QoE (con privilegi di controllo completo) per il cubo.
    
- Uno che verrà usato per eseguire il processo di lavoro di IIS per i portali Web e le API Web. La configurazione creerà un'identità di sicurezza dell'account di accesso al database di archiviazione QoE (con privilegio di lettura), un'entità di sicurezza dell'account di accesso al database del repository (con privilegi di lettura e scrittura) e un membro in QoERole (con privilegi di controllo completo) per il cubo. 
    
    > [!NOTE]
    > Quando il database di archivio QoE e il database del repository sono ospitati nello stesso SQL Server, viene creata una sola entità di sicurezza per l'accesso con due mapping utente. 
  
I primi due account possono essere considerati logicamente come "account del servizio di back-end" e l'ultimo account è un "account del servizio front-end". Anche se non è consigliabile, è possibile usare un singolo account in tutti i casi.
  
> [!NOTE]
> L'account utente che avvia l'installazione deve avere accesso in lettura alla metrica QoE DB, oltre ad avere diritti di amministratore del computer nel server di archiviazione QoE in cui deve essere eseguito l'installazione. 
  
## <a name="capacity-planning"></a>Pianificazione della capacità
<a name="Infrastructure_Req"> </a>

Call Quality dashboard è progettato per un impatto minimo su QoEMetrics: il codice è stato ottimizzato per non bloccare i dati e i processi di importazione sono sintonizzabili.
  
Il tipo di hardware da usare dipende dai requisiti per l'esecuzione rapida delle sincronizzazioni. Il ridimensionamento del disco è il seguente:
  
- QoEArchive è ~ 1,5 x maggiore di QoEMetrics DB inizialmente
    
- Il cubo SSIS comprime i dati quasi 10x rispetto a DB
    
- I dati vengono partizionati mensilmente; le partizioni possono essere eliminate
    

