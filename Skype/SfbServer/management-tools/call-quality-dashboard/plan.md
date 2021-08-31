---
title: Pianificare il dashboard qualità delle chiamate per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Riepilogo: informazioni su cosa considerare quando si pianifica il dashboard qualità delle chiamate.'
ms.openlocfilehash: d50b8eba500a6197eb12bad98de0ef72c054f26b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728855"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Pianificare il dashboard qualità delle chiamate per Skype for Business Server 
 
**Riepilogo:** Informazioni su cosa considerare quando si pianifica il dashboard qualità delle chiamate.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Panoramica del dashboard Skype for Business Server qualità delle chiamate

Il Skype for Business Server call quality dashboard (CQD) è un livello di report in cima al Database di qualità dell'esperienza nel Monitoring Server in Skype for Business Server. CQD usa Microsoft SQL Server Analysis Services per fornire informazioni aggregate sull'utilizzo e sulla qualità delle chiamate, nonché per filtrare e eseguire pivot sul set di dati. Le funzionalità CQD includono:
  
- **Archiviazione dei dati QoE tramite il componente di archiviazione QoE di CQD.** Il componente di archiviazione QoE può archiviare i dati QoE per una durata molto più lunga rispetto al Monitoring Server. In questo modo è possibile creare tendenze e creare report per un massimo di sette mesi di dati alla volta, con la possibilità di far scorrere la finestra dei report fino a quando sono presenti dati.
- **Creazione di report e analisi con la potenza e la velocità di Microsoft SQL Server Analysis Services.** CQD utilizza Microsoft SQL Analysis Services per fornire funzionalità di riepilogo, filtro e pivot veloci per alimentare il dashboard tramite un cubo di analisi. La velocità di esecuzione dei report e la possibilità di eseguire il drill-down nei dati possono ridurre notevolmente i tempi di analisi.
- **Nuovo schema di dati ottimizzato per la segnalazione della qualità delle chiamate.** Il cubo dispone di uno schema progettato per la creazione di report e indagini sulla qualità vocale. Gli utenti del portale possono concentrarsi sulle attività di creazione di report invece di capire come viene eseguito il mapping dello schema del database QoE Metrics alle visualizzazioni necessarie. La combinazione dell'archivio QoE e del cubo fornisce un'astrazione che riduce la complessità dei report e dell'analisi tramite CQD. Lo schema del database QoE Archive contiene inoltre tabelle che possono essere popolate con dati specifici della distribuzione per migliorare il valore complessivo dei dati.
- **Progettazione report incorporato e modifica sul posto dei report.** Il componente Portal include diversi report incorporati modellati sulla base della metodologia di qualità delle chiamate. Gli utenti del portale possono modificare i report e crearne di nuovi tramite la funzionalità di modifica del portale.
- **Accesso api Web ai dati della struttura del report e dei cubi di analisi.** Dashboard Reporting Framework non è l'unico modo per visualizzare i dati del cubo. CQD fornisce diversi esempi di utilizzo di HTML e JavaScript per recuperare dati dalle API Web CQD ed eseguire il rendering dei dati in un formato personalizzato. La combinazione dell'Editor report e delle API Web CQD consente la creazione rapida di prototipi di report e layout di report personalizzati.

> [!NOTE]
> Un amministratore può ora gestire Skype for Business Server 2019 usando [CQD versione 3](https://cqd.teams.microsoft.com) (accedere con credenziali di amministratore). Ciò richiede un'implementazione ibrida e l'uso di Call Data Connector (CDC). Per ulteriori informazioni sull'abilitazione di CDC, vedere [Plan Call Data Connector.](../../../SfbHybrid/hybrid/plan-call-data-connector.md) Per la documentazione di CQD versione 3, vedere Attivare e usare call [quality dashboard per Microsoft Teams e Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) per ulteriori informazioni su CQD versione 3.

## <a name="cqd-design-goals"></a>Obiettivi di progettazione CQD

CQD consente ai professionisti IT di utilizzare dati aggregati per identificare le aree di interesse nell'ambiente in cui si verificano problemi di qualità multimediale. Consente a un Pro IT di confrontare le statistiche per diversi gruppi di utenti e identificare tendenze e modelli. Non è incentrato sulla risoluzione di problemi relativi alle singole chiamate, ma sull'identificazione di problemi e soluzioni che verranno applicati a molti utenti in un determinato ambiente. 
  
## <a name="call-quality-dashboard-components"></a>Componenti del dashboard qualità delle chiamate

Il dashboard qualità delle chiamate è costituito da diversi database, processi e applicazioni Web di Microsoft SQL Agent. I processi di Microsoft SQL Agent copiano periodicamente i dati dal database QoE Metrics nel database QoE Archive ed elaborano il cubo con i dati nel database QoE Archive. Nel database Repository sono archiviate le definizioni di report che abilitino il portale. Il portale fornisce l'accesso del browser ai dati del cubo. 
  
I componenti CQD, inclusi i database QoE Archive, Cube e Repository, possono essere installati nel Monitoring Server, installati nel proprio server o su più server. Il metodo di installazione specifico dipende dalle esigenze di prestazioni di CQD e dall'impatto su altri processi sugli stessi server. Per ulteriori informazioni, vedere la sezione "Componenti e topologie per CQD" più avanti in questo articolo.
  
### <a name="architectural-overview"></a>Panoramica dell'architettura

Per riepilogare, CQD richiede i seguenti elementi:
  
- Due database: un database di archiviazione e un database repository.
    
- Un cubo SSAS che visualizza i dati aggregati 
    
- IIS ospita il portale Web CQD
    
![Componenti CQD.](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La stessa architettura CQD supporta Lync Server 2013 e Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD e Skype for Business rispetto a Lync 2013

 Solo in Skype for Business di lavoro sono disponibili le funzionalità seguenti:
  
- Wi-Fi segnalazione della potenza del segnale
    
- Wi-Fi report dei driver Chipset
    
- Valutare i dati della chiamata 
    
## <a name="information-available-through-cqd"></a>Informazioni disponibili tramite CQD

CQD può mostrare Skype for Business Server di flussi audio, video e di condivisione applicazioni e il conteggio delle chiamate buone e non buone, nonché i rapporti tra chiamate non buone e non buone. Le visualizzazioni possono essere suddivise in sezioni e filtrate in base a diverse dimensioni. CQD disegna i dati dal database delle metriche QoE nel Monitoring Server. I dati vengono quindi uniti a tutti i dati forniti dal cliente, ad esempio il mapping tra subnet di rete e edificio per rendere possibili report come "Qualità chiamata per edificio". 
  
CQD inoltre astrae molte delle idiosincrasie dei dati QoE interne, ad esempio "chiamante" e "chiamato", in modo che l'utente possa concentrarsi sulla creazione di visualizzazioni dei report attorno a "server" e "client". Seguendo la metodologia di qualità delle chiamate, CQD è semplificato per identificare le condizioni che le sacche di chiamate di qualità scarsa hanno in comune, uno dei tenets per migliorare la qualità delle chiamate.
  
## <a name="viewing-data-in-cqd"></a>Visualizzazione dei dati in CQD

I dati CQD possono essere visualizzati tramite il portale CQD e sono accessibili tramite chiamate API REST.
  
### <a name="cqd-portal"></a>Portale CQD

Il portale è il modo più rapido per visualizzare i dati nel cubo. Il portale include diversi report incorporati utilizzabili immediatamente. I report incorporati sono collegati in modo strutturato per guidare l'utente a sezioni più piccole e successive dei dati delle chiamate. I report incorporati evidenziano anche i diversi modi in cui i dati possono essere visualizzati dimostrando una combinazione di grafici e tabelle con pivot, filtri e misure diversi. Ogni utente che accede al portale può avere un proprio set di report che può modificare e condividere. Per ulteriori informazioni sull'utilizzo del portale Web CQD, vedere [Use Call Quality Dashboard for Skype for Business Server](use.md).
  
Sistemi operativi supportati per il portale CQD: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (solo CQD Skype for Business Server 2019).
  
Browser supportati per il portale CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>API REST

È possibile accedere ai dati del cubo anche tramite chiamate API REST. Il rendering dei dati recuperati tramite le chiamate ALL API REST può essere eseguito tramite pagine HTML. Gli utenti possono sfruttare la velocità delle query e lo schema di alto livello di CQD pur creando report personalizzati adatti alle proprie esigenze aziendali. Per altre informazioni sull'API e sugli esempi, vedi [Sviluppare il dashboard di qualità delle](develop.md)chiamate per Skype for Business Server . 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definizione dei requisiti dell'organizzazione per CQD

CQD fornisce l'archiviazione dei dati QoE e un'analisi rapida e approfondita dei dati sulla qualità delle chiamate. La guida seguente consente di decidere quando e perché distribuire CQD.
  
### <a name="when-to-deploy-cqd"></a>Quando distribuire CQD

 **CQD può essere distribuito per stabilire una misurazione della qualità delle chiamate di base, anche se un'organizzazione non ha problemi di qualità delle chiamate.** La definizione di una misurazione della qualità delle chiamate di base è importante perché ogni organizzazione ha una combinazione diversa di Wi-Fi e remoto rispetto ai dipendenti dell'ufficio. Quando si verificano problemi di qualità delle chiamate, le misurazioni più recenti della qualità delle chiamate possono essere confrontate con gli intervalli di tempo precedenti. Le funzionalità di tendenza di CQD consentono di rilevare facilmente le modifiche nella qualità delle chiamate nel tempo.
  
 **CQD può essere distribuito per individuare in modo proattivo le aree di problema che potrebbero influire sulla qualità delle chiamate.** Anche se la qualità media delle chiamate per un'organizzazione potrebbe soddisfare gli obiettivi impostati dall'organizzazione, potrebbero esserci sacche di problemi di qualità delle chiamate nascosti dietro le metriche medie. CQD consente la suddivisione delle metriche di qualità delle chiamate in base a tabelle pivot per molte dimensioni nel database QoEMetrics. Individuare gli outlier nei gruppi peer è un modo rapido per individuare in modo proattivo i problemi di qualità delle chiamate.
  
 **È consigliabile distribuire CQD in caso di problemi di qualità delle chiamate nell'organizzazione per ridurre il tempo necessario per la risoluzione dei problemi.** CQD può semplificare le indagini sulla qualità delle chiamate esistenti offrendo prestazioni di creazione di report veloci e funzionalità di drill-down dinamico. CQD è progettato per molti tipi di flussi di lavoro nelle indagini sulla qualità delle chiamate che convalidano le riparazioni nell'ambiente.
  
### <a name="why-deploy-cqd"></a>Perché distribuire CQD

 **È consigliabile distribuire CQD se i report QoE devono essere evasi per più di 3 mesi di dati.** Il database QoEMetrics e i report del server di monitoraggio sono progettati per conservare e segnalare un piccolo set di dati. Il database delle metriche QoE è ottimizzato per gli inserimenti rapidi e pertanto le prestazioni dei report possono essere ostacolate da un elevato volume di chiamate o dall'accesso di report concorrenti al database. Il database QoE Archive di CQD fornisce una seconda copia dei dati delle metriche QoE con funzionalità di conservazione molto più lunghe. Il portale è inoltre ottimizzato per visualizzare fino a 7 mesi di dati alla volta e può creare report su tutti i dati nell'archivio QoE in base alle esigenze.
  
 **È consigliabile distribuire CQD se sono necessari report QoE personalizzati.** Il portale include una funzionalità editor di report per la creazione e la creazione di prototipi di report in modo semplice e rapido. Rende inoltre disponibili API REST per l'accesso a livello di codice ai dati del cubo, consentendo una presentazione personalizzata tramite HTML/JavaScript o molti altri framework. Non è più necessario creare nuove query di SQL allo scopo di creare visualizzazioni dati personalizzate per la creazione di report.
  
 **È consigliabile distribuire CQD se la funzionalità di creazione di report QoE esistente non soddisfa la velocità o la profondità richieste dall'organizzazione.** CQD include molti report incorporati. I report sono immediatamente utili e illustrano come l'analisi progressiva dei dati possa offrire ulteriori approfondimenti a ogni livello. La gerarchia dei report consente inoltre di gestire i numerosi report in modo logico e favorisce la creazione di molti altri report facilmente accessibili e comprensibili. CQD non offre solo velocità e flessibilità, ma è anche ottimizzato per i flussi di lavoro sviluppati dalla metodologia di qualità delle chiamate.
  
## <a name="components-and-topologies-for-cqd"></a>Componenti e topologie per CQD

CQD include diversi componenti e consente di comprendere i requisiti di ogni componente e la loro relazione tra loro per ottenere la distribuzione dello strumento più semplice ed efficace. Nella tabella seguente viene descritto il componente dipendente per ogni componente CQD.
  

|**Nome componente**|**Componente dipendente**|
|:-----|:-----|
|Archivio QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portale  <br/> |Microsoft Information Services  <br/> |
|Repository Service (parte dell'installazione del portale)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Per l'archivio QoE e il cubo, alcune opzioni di distribuzione richiedono business intelligence o Enterprise edizioni di Microsoft SQL Server. Per ulteriori dettagli, vedere la sezione Requisiti di infrastruttura per [CQD](plan.md#Infrastructure_Req) riportata di seguito.
  
![Componenti CQD.](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configurazione a server singolo

Tutti i componenti CQD e i componenti dipendenti possono essere installati in un unico computer. La configurazione a casella singola è la configurazione più semplice e consente l'autonomia di CQD. CQD deve solo accedere al database delle metriche QoE nel Monitoring Server. Il server CQD può essere un computer autonomo, una macchina virtuale o anche il Monitoring Server, a seconda delle risorse disponibili del computer host e dei requisiti di prestazioni. 
  
Durante l'installazione, l'utente che esegue l'installazione deve semplicemente fornire le istanze di Microsoft SQL Server e Microsoft SQL Server Analysis Services precedentemente impostate nel computer in cui deve essere installato il servizio CQD. Per ulteriori informazioni, vedere [Deploy Call Quality Dashboard Skype for Business Server.](deploy-0.md)
  
### <a name="multiserver-configuration"></a>Configurazione multiserver

In una configurazione multiserver, L'archivio QoE, il cubo e il portale possono essere tutti in computer diversi. Esistono due utilizzi principali per la configurazione multiserver:
  
- Hosting di CQD Web Portal e CQD Cube in server diversi.
    
- Hosting di un portale di "sviluppo" separato dal portale di "produzione". 
    
  **Hosting di CQD Web Portal e CQD Cube in computer diversi.** Le organizzazioni che potrebbero avere requisiti per separare il portale CQD dall'installazione di SQL Server o che potrebbero voler combinare le edizioni di SQL Server per l'istanza di SQL Server e l'istanza di SQL Server Analysis Services possono scegliere di installare il portale CQD e il cubo CQD in computer diversi. Il componente di archiviazione QoE può anche essere l'unico componente CQD installato se l'organizzazione desidera semplicemente disporre di un metodo sostenibile per archiviare i dati QoE senza raggiungere limiti di prestazioni nel Monitoring Server.
  
![CQD a server singolo.](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosting di un portale di "sviluppo" separato dal portale di "produzione".** Le organizzazioni che sviluppano i propri report personalizzati (tramite le API REST) potrebbero preferire la distribuzione di istanze del portale aggiuntive (CQD) insieme al portale di produzione a cui gli utenti normali accedono per il monitoraggio o le indagini sulla qualità delle chiamate. Il portale di sviluppo può isolare tutte le modifiche apportate al portale dall'ambiente di produzione. I portali Web aggiuntivi possono essere distribuiti in computer diversi (illustrati di seguito) o distribuiti in directory Web diverse nello stesso computer (non visualizzato). Per ottenere questo risultato, il portale Web CQD aggiuntivo deve essere copiato manualmente nel computer di produzione perché il processo di installazione CQD distribuisce sempre il portale Web CQD nel sito Web predefinito con nomi di applicazioni Web predefiniti.
  
![Pianificare CQD Multi Server.](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologie supportate

CQD non unisce i dati di più database QoEMetrics, come nel caso in cui siano presenti più topologie di Skype for Business Server, ognuna con il proprio Monitoring Server. Ogni istanza CQD deve puntare a un database QoEMetrics. Tuttavia, poiché CQD sposta gran parte del carico di lavoro per la creazione di report al di fuori del Monitoring Server, le organizzazioni di grandi dimensioni che dovevano distribuire un Monitoring Server per topologia di Skype for Business Server dovrebbero prendere in considerazione l'utilizzo di un Monitoring Server per tutte le topologie.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisiti dell'infrastruttura per CQD
<a name="Infrastructure_Req"> </a>

CQD, inclusi tutti i componenti e i componenti dipendenti, può essere distribuito in una macchina virtuale, in una singola macchina o in più computer. Di seguito sono elencati i requisiti hardware e software minimi. La disponibilità dei dati e le prestazioni delle query possono variare da minuti a ore, a seconda del numero di utenti Skype for Business Server attivi e dell'hardware e della configurazione, pertanto alcune misurazioni delle prestazioni sono riportate di seguito.
  
|||
|:-----|:-----|
|Per CQD 2015 <br/> |  <br/> |
|Sistemi operativi supportati   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|Funzionalità SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Per CQD 2019 <br/> |  <br/> |
|Sistemi operativi supportati   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|Funzionalità SQL Server  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD utilizza Microsoft SQL Server, Microsoft SQL Server Analysis Services e Microsoft Internet Information Services in modo che i requisiti hardware e software minimi di CQD siano fondamentalmente gli stessi di tali componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione relativi all'aggiornamento dei dati (che dipenderà in parte dal volume di dati QoE generati dall'organizzazione) e dai costi di distribuzione, è consigliabile prendere ulteriori considerazioni sulla distribuzione.
  
L'elaborazione dei dati in CQD è suddivisa in due fasi principali: 
  
- Processo di archiviazione QoE
    
- Elaborazione cubo CQD
    
  **Elaborazione dell'archivio QoE.** L'attività di elaborazione QoE Archive copia i dati dal database Delle metriche QoE nel Monitoring Server al database di archiviazione QoE. Esistono due situazioni in cui il tempo di elaborazione dell'attività avrebbe caratteristiche di prestazioni fondamentalmente diverse. Il primo è dopo l'installazione iniziale di CQD. Quando l'attività viene eseguita per la prima volta dopo una nuova installazione, l'attività di elaborazione QoE Archive copierà tutti i dati presenti nel database Delle metriche QoE nel database di archiviazione QoE. Il secondo è l'elaborazione periodica dopo questo round iniziale. L'attività di elaborazione dell'archivio QoE viene eseguita ogni 15 minuti ed elabora eventuali nuovi record QoE presenti nel database delle metriche QoE. In genere, il tempo di elaborazione iniziale non è un problema perché viene eseguito solo la prima volta, quando viene installato CQD. Tuttavia, se il provisioning del server CQD è molto inferiore, questa attività può richiedere diverse ore. Fare riferimento alla tabella seguente, ad esempio i tempi di elaborazione iniziali dell'archivio QoE.
  
  **Elaborazione cubo CQD.** L'attività di elaborazione del cubo aggrega i dati dal database QoE Archive al cubo. Il tempo di elaborazione del cubo iniziale e il tempo di elaborazione successivo del cubo sono determinati dall'edizione SQL Server Analysis Services utilizzata per il cubo CQD. Se si utilizza l'edizione Standard, non vi è alcuna differenza tra il tempo di elaborazione del cubo iniziale e il tempo di elaborazione del cubo successivo perché ogni volta che i dati del cubo vengono aggiornati, sarà sempre un'elaborazione completa di tutti i dati disponibili. Ciò significa che i tempi di elaborazione del cubo aumentano con l'aumentare della quantità di dati nel database di archiviazione QoE. Poiché business intelligence Edition e edizione Enterprise di SQL Server supportano la partizione, se viene utilizzata una delle due edizioni, solo l'esecuzione iniziale e processerà tutti i dati nel database di archiviazione QoE. Nelle esecuzioni successive, quando l'attività viene attivata ogni 15 minuti, l'attività eelaborare solo i nuovi record aggiunti al database di archiviazione QoE dopo l'ultima esecuzione dell'attività. Una volta al giorno, ci sarà anche un'elaborazione completa nella partizione che contiene i dati del mese corrente.
  
Le caratteristiche del computer fisico possono influire sulle prestazioni di CQD e sulle funzionalità software disponibili SQL Server componenti. Il componente di archiviazione QoE sarà più intensivo del disco rispetto ad altri componenti, mentre il componente Cubo richiederà più CPU e memoria. Tutti questi fattori contribuiscono al tempo totale di elaborazione dei dati di CQD, che influisce direttamente sull'freshness e sulla disponibilità dei dati. Le organizzazioni devono prendere decisioni sull'hardware e sul software in base alle singole esigenze dell'organizzazione. 
  
### <a name="tested-hardware-configurations"></a>Configurazioni hardware testate

In questa sezione si presuppone che nell'ambiente sia presente un singolo database QoEMetrics. 
  
**Profili computer**

|**Computer**|**Core CPU**|**RAM**|**Archivio QoE e cubo sullo stesso disco**|**QoE Archive and SQL Temp DB on same disk**|
|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |4   <br/> |7 GB  <br/> |Sì  <br/> |Sì  <br/> |
|4 core  <br/> |4   <br/> |20 GB  <br/> |Sì  <br/> |No  <br/> |
|8 core  <br/> |8   <br/> |32 GB  <br/> |Sì  <br/> |No  <br/> |
|16 core  <br/> |16   <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Risultati delle prestazioni**

|**Computer**|**Dimensioni db metriche QoE**|**SQL partizioni**|**Tipo di disco**|**Numero di flussi**|**Processo di archiviazione iniziale**|**Processo cubo iniziale**|**Processo di archiviazione successivo**|**Processo cubo successivo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |900 MB  <br/> |Celibe/nubile  <br/> |Disco rigido virtuale (dimensione variabile)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Celibe/nubile  <br/> |Disco rigido virtuale (dimensione variabile)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Celibe/nubile  <br/> |Disco rigido virtuale (dimensione fissa)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |30+ GB  <br/> |Celibe/nubile  <br/> |Disco rigido virtuale (dimensione fissa)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Celibe/nubile  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Multiplo  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 core  <br/> |30+ GB  <br/> |Celibe/nubile  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 core  <br/> |30+ GB  <br/> |Multiplo  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 core  <br/> |200 GB  <br/> |Celibe/nubile  <br/> |Più dischi  <br/> |125 M  <br/> |6+ giorni  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 core  <br/> |500 GB  <br/> |Multiplo  <br/> |Più assi  <br/> |250 M  <br/> |8 giorni  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Non è previsto che questi dati si verifichino nelle distribuzioni reali, perché il database delle metriche QoE dovrebbe avere 9 e 18 mesi di dati, rispettivamente, ma vengono forniti qui per la completezza.
  
### <a name="service-account-requirements"></a>Requisiti dell'account di servizio

Sarà necessario un account (con accesso in lettura a QoEMetrics) che l'agente SQL nel server CQD possa utilizzare per importare dati in QoEArchiveDB.
  
Potrebbe inoltre essere necessario configurare un account separato per un processo SSAS per il pull dei dati da QoEArchiveDB (si tratta di un processo facoltativo).
  
IIS usa in genere Servizio di rete come identità del pool di app, ma può essere configurato con un account di servizio.
  
### <a name="portal-access-control"></a>Controllo di accesso al portale

Per impostazione predefinita, qualsiasi utente autenticato ha accesso. È possibile modificare questa impostazione utilizzando le regole di autorizzazione IIS per limitare l'accesso a un gruppo specifico.
  
### <a name="pre-install-requirements"></a>Requisiti di preinstallazione

Queste istruzioni presuppongono che sia già stato installato un database delle metriche QoE e che sia in esecuzione in un punto qualsiasi della Skype for Business Server di ricerca.
  
#### <a name="hardware-requirements"></a>Requisiti hardware

CQD utilizza Microsoft SQL Server, Microsoft SQL Analysis Server e Microsoft Internet Information Server in modo che i requisiti hardware e software minimi di CQD siano fondamentalmente gli stessi di tali componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione relativi all'aggiornamento dei dati (che dipenderà in parte dal volume di dati QoE generati dall'organizzazione) e dai costi di distribuzione, è consigliabile prendere ulteriori considerazioni sulla distribuzione.
  
#### <a name="software-requirements"></a>Requisiti software

Per CQD sono necessari i sistemi operativi seguenti:
  
- Windows Server 2008 R2 con IIS 7.5
    
- Windows Server 2012 con IIS 8.0
    
- Windows Server 2012 R2 con IIS 8.5

- Windows Server 2016 con IIS 10.0 (solo Skype for Business Server CQD 2019)

- Windows Server 2019 (Skype for Business Server solo CQD 2019)
    
Di seguito sono riportati i servizi ruolo IIS necessari (in ordine gerarchico):
  
- Server Web
    
  - Caratteristiche HTTP comuni
    
  - Contenuto statico
    
  - Documento predefinito
    
  - Sviluppo di applicazioni
    
  - ASP.NET
    
  - Filtri ISAPI
    
  - Diagnostica &amp; integrità
    
  - Registrazione HTTP
    
  - Sicurezza
    
  - Autorizzazione URL
    
  - Autenticazione di Windows
    
  - Strumenti di gestione
    
  - Console di gestione IIS
    
> [!NOTE]
>  Nota quanto segue per i requisiti precedenti:> sono disponibili le versioni 3.5 e 4.5 di .Net Framework. Entrambi sono necessari (in particolare, è necessario 3.5 SP1).> In alcuni sistemi, se ASP.NET viene installato prima dell'installazione di IIS, ASP.NET potrebbe non essere registrato in IIS. Il problema si manifesta con l'assenza di pool di applicazioni per la versione .Net corrispondente e manca anche la versione CLR .NET nella configurazione del pool di app. Per risolvere un problema di questo tipo Windows Server 2008 R2, eseguire `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` . In Windows Server 2012 e Windows Server 2012 R2, eseguire seguito dalla rimozione del modulo "ServiceModel" dal sito Web predefinito in Gestione IIS.> Gli strumenti di gestione sono facoltativi, ma `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` consigliati.
  
Per installare questi requisiti tramite PowerShell, eseguire le operazioni seguenti:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Sono supportate le SQL Server seguenti:
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
Business Intelligence o Enterprise edizione è consigliata per motivi di prestazioni. Queste edizioni consentono l'uso di più file di partizione che possono essere elaborati in parallelo, il che è vantaggioso per l'elaborazione di dati che si estendono su più mesi o più. 
  
Anche se non è consigliato, è supportata anche l'edizione Standard. L'elaborazione sarà vincolata a una singola partizione (che deve essere configurata durante l'installazione). 
  
In tutti i casi, è necessario installare "motore di database Services" e "Analysis Services". È consigliabile, ma non necessario, installare anche la funzionalità "Strumenti di gestione - Completa", che aggiunge SQL Server Management Studio supporto per Analysis Services. La schermata di selezione delle funzionalità dovrebbe essere simile alla figura.
  
![SQL Server requisiti delle funzionalità.](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Quando si configura l'installazione di SSAS, nella configurazione di Analysis Services impostare "Modalità server" su "Modalità multidimensionale e data mining". 
  
Per ulteriori informazioni sull'installazione e la configurazione SQL Server funzionalità di business intelligence, vedere [Install Analysis Services in Multidimensional and Data Mining Mode](/previous-versions/sql/sql-server-2012/ms143708(v=sql.110)).
  
#### <a name="account-requirements"></a>Requisiti dell'account

Tre account di servizio di dominio sono consigliati in base al principio dei privilegi minimi: 
  
- Uno che dispone già di un'entità di sicurezza di accesso per il database delle metriche QoE (con privilegio di db_datareader) e di un'entità di sicurezza di accesso nell'istanza di SQL Server Archivio QoE (necessaria per creare un oggetto Server collegato durante l'installazione). Questo account verrà utilizzato per eseguire il passaggio "QoE Archive Data" del processo SQL Server Agent.
    
    > [!NOTE]
    > Se si lavora in un ambiente fortemente bloccato, è necessario verificare che a questo account di servizio siano effettivamente concessi i diritti utente "Accesso come processo batch" e "Consenti accesso locale" sia per il SQL Server del database di monitoraggio delle metriche QoE che per il SQL Server di archiviazione QoE.
    
- Uno che verrà utilizzato per eseguire il passaggio "Process Cube" del processo SQL Server Agent. Il programma di installazione creerà un'entità di sicurezza di accesso al database di archiviazione QoE (con privilegi di lettura e scrittura) e creerà anche un membro nel ruolo QoE (con privilegi di controllo completo) per il cubo.
    
- Uno che verrà usato per eseguire il processo di lavoro IIS per i portali Web e le API Web. Il programma di installazione creerà un'entità di sicurezza di accesso al database di archiviazione QoE (con privilegi di lettura), un'entità di sicurezza di accesso al database repository (con privilegi di lettura e scrittura) e un membro in QoERole (con privilegi di controllo completo) per il cubo. 
    
    > [!NOTE]
    > Quando sia il database di archiviazione QoE che il database repository sono ospitati nello stesso SQL Server, viene creata una sola entità di sicurezza di accesso con due mapping utente. 
  
I primi due account possono essere considerati logicamente come "account di servizio back-end" e l'ultimo è un "account di servizio front-end". Sebbene non sia consigliabile, è possibile utilizzare un singolo account in tutti i casi.
  
> [!NOTE]
> L'account utente che avvia l'installazione deve disporre dell'accesso in lettura anche al database delle metriche QoE (oltre ad avere diritti di amministratore del computer nel server DB archivio QoE in cui deve essere completata l'installazione). 
  
## <a name="capacity-planning"></a>Pianificazione della capacità
<a name="Infrastructure_Req"> </a>

CQD è progettato per un impatto minimo su QoEMetrics: il codice è stato ottimizzato per non bloccare i dati e i processi di importazione sono tunable.
  
Il tipo di hardware da usare dipende dai requisiti per la velocità di esecuzione delle sincronizzazioni. Il ridimensionamento del disco è il seguente:
  
- QoEArchive è ~1,5x più grande di QoEMetrics DB inizialmente
    
- SSIS Cube comprime i dati quasi 10x rispetto a DB
    
- I dati vengono partizionati mensilmente. le partizioni possono essere eliminate
