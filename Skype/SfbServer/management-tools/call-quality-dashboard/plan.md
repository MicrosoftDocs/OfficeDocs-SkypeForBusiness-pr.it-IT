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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Riepilogo: informazioni su cosa considerare quando si pianifica il dashboard qualità delle chiamate.'
ms.openlocfilehash: 6a1fc39dd26f6c4e9e455babcecb124888629179
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803176"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Pianificare il dashboard qualità delle chiamate per Skype for Business Server 
 
**Riepilogo:** Informazioni su cosa considerare quando si pianifica il dashboard qualità delle chiamate.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Panoramica del dashboard qualità delle chiamate di Skype for Business Server

Skype for Business Server Call Quality Dashboard (CQD) è un livello di reporting in cima al database di qualità dell'esperienza nel Monitoring Server in Skype for Business Server. CQD utilizza Microsoft SQL Server Analysis Services per fornire informazioni aggregate sull'utilizzo e sulla qualità delle chiamate, nonché per filtrare e eseguire pivot sul set di dati. Le funzionalità CQD includono:
  
- **Archiviazione dei dati QoE tramite il componente di archiviazione QoE di CQD.** Il componente di archiviazione QoE può archiviare i dati QoE per una durata molto più lunga di quella del Monitoring Server. In questo modo è possibile creare tendenze e creare report per un massimo di sette mesi di dati alla volta, con la possibilità di far scorrere la finestra dei report fino a quando sono presenti dati.
- **Creazione di report e analisi con la potenza e la velocità di Microsoft SQL Server Analysis Services.** CQD utilizza Microsoft SQL Analysis Services per fornire funzionalità di riepilogo, filtro e pivot rapido per alimentare il dashboard tramite un cubo di analisi. La creazione di report sulla velocità di esecuzione e la possibilità di eseguire il drill-down nei dati possono ridurre notevolmente i tempi di analisi.
- **Nuovo schema di dati ottimizzato per la segnalazione della qualità delle chiamate.** Il cubo dispone di uno schema progettato per la creazione di report e indagini sulla qualità vocale. Gli utenti del portale possono concentrarsi sulle attività di creazione di report invece di capire in che modo lo schema del database metriche QoE è mappato alle visualizzazioni necessarie. La combinazione dell'archivio QoE e del cubo offre un'astrazione che riduce la complessità delle relazioni e dell'analisi tramite CQD. Lo schema del database QoE Archive contiene inoltre tabelle che possono essere popolate con dati specifici della distribuzione per migliorare il valore complessivo dei dati.
- **Progettazione report incorporato e modifica di report sul posto.** Il componente Portale include diversi report incorporati modellati sulla base della metodologia di qualità delle chiamate. Gli utenti del portale possono modificare i report e crearne di nuovi tramite la funzionalità di modifica del portale.
- **Accesso api Web alla struttura del report e ai dati del cubo di analisi.** Dashboard Reporting Framework non è l'unico modo per visualizzare i dati del cubo. CQD fornisce diversi esempi di utilizzo di HTML e JavaScript per recuperare dati dalle API Web CQD ed eseguire il rendering dei dati in un formato personalizzato. La combinazione dell'editor di report e delle API Web CQD consente la creazione rapida di prototipi di report e layout di report personalizzati.

> [!NOTE]
> Un amministratore può ora gestire Skype for Business Server 2019 con [CQD versione 3](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore). Ciò richiede un'implementazione ibrida e l'utilizzo di Call Data Connector (CDC). Per ulteriori informazioni sull'abilitazione del servizio CDC, vedere [Plan Call Data Connector.](/SkypeForBusiness/hybrid/plan-call-data-connector) Per la documentazione CQD versione 3, vedere Attivare e usare call [quality dashboard per Microsoft Teams](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) e Skype for Business online per ulteriori informazioni su CQD versione 3.

## <a name="cqd-design-goals"></a>Obiettivi di progettazione CQD

La DQD consente ai professionisti IT di utilizzare dati aggregati per identificare le aree di interesse nell'ambiente in cui si verificano problemi di qualità multimediale. Consente a un professionista IT di confrontare le statistiche per diversi gruppi di utenti e di identificare tendenze e modelli. Non è incentrato sulla risoluzione di singoli problemi di chiamata, ma sull'identificazione di problemi e soluzioni che verranno applicati a molti utenti in un determinato ambiente. 
  
## <a name="call-quality-dashboard-components"></a>Componenti del dashboard qualità delle chiamate

Il dashboard qualità delle chiamate è costituito da diversi database, processi, processi e applicazioni Web di Microsoft SQL Agent. I processi di Microsoft SQL Agent copiano periodicamente i dati dal database delle metriche QoE nel database QoE Archive ed elaborano il cubo con i dati nel database QoE Archive. Nel database repository vengono archiviate le definizioni di report che si riferiscono al portale. Il portale consente l'accesso da parte del browser ai dati del cubo. 
  
I componenti CQD, inclusi i database QoE Archive, Cube e Repository, possono essere installati nel Monitoring Server, installati nel proprio server o in più server. Il metodo di installazione specifico dipende dalle esigenze di prestazioni del DQD e dall'impatto sugli altri processi sugli stessi server. Per ulteriori informazioni, vedere la sezione "Componenti e topologie per CQD" più avanti in questo articolo.
  
### <a name="architectural-overview"></a>Panoramica dell'architettura

Per riassumere, CQD richiede gli elementi seguenti:
  
- Due database: un database Archive e un database repository.
    
- Un cubo SSAS che visualizza i dati aggregati 
    
- IIS ospita il portale Web CQD
    
![Componenti CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La stessa architettura CQD supporta Lync Server 2013 e Skype for Business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD e Skype for Business rispetto a Lync 2013

 Solo in un ambiente Skype for Business sono disponibili le seguenti funzionalità:
  
- Wi-Fi segnalazione della potenza del segnale
    
- Wi-Fi report dei driver chipset
    
- Valutare i dati della chiamata 
    
## <a name="information-available-through-cqd"></a>Informazioni disponibili tramite CQD

CQD può mostrare i conteggi dei flussi audio, video e di condivisione applicazioni di Skype for Business Server e il numero di chiamate buone e non buone, nonché i rapporti tra chiamate non buone e non buone. Le visualizzazioni possono essere suddivise e filtrate in base a diverse dimensioni. CQD disegna i dati dal database delle metriche QoE nel Monitoring Server. I dati vengono quindi uniti a tutti i dati forniti dal cliente, ad esempio il mapping tra subnet di rete e edificio per rendere possibili report come "Qualità delle chiamate per edificio". 
  
CQD inoltre astrae molte delle idiosincrasie dei dati QoE interne, ad esempio "chiamante" e "chiamato", in modo che l'utente possa concentrarsi sulla creazione di visualizzazioni di report attorno a "server" e "client". Seguendo la metodologia di qualità delle chiamate, CQD è semplificato per identificare le condizioni che le sacche di chiamate di qualità scarsa hanno in comune, uno dei tenets per migliorare la qualità delle chiamate.
  
## <a name="viewing-data-in-cqd"></a>Visualizzazione dei dati in CQD

I dati CQD possono essere visualizzati tramite il portale CQD e accessibili tramite chiamate ALL API REST.
  
### <a name="cqd-portal"></a>Portale CQD

Il portale è il modo più rapido per visualizzare i dati nel cubo. Il portale include diversi report predefiniti utilizzabili immediatamente. I report predefiniti sono collegati in modo strutturato per guidare l'utente a sezioni sempre più piccole e più piccole dei dati delle chiamate. I report predefiniti evidenziano inoltre i diversi modi in cui i dati possono essere visualizzati dimostrando una combinazione di grafici e tabelle con pivot, filtri e misure diversi. Ogni utente che accede al portale può avere un proprio set di report che può modificare e condividere. Per ulteriori informazioni sull'utilizzo del portale Web CQD, vedere [Usare call quality dashboard per Skype for Business Server.](use.md)
  
Sistemi operativi supportati per il portale CQD: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (solo DQD di Skype for Business Server 2019).
  
Browser supportati per il portale CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>API REST

È inoltre possibile accedere ai dati del cubo tramite chiamate ALL API REST. Il rendering dei dati recuperati tramite le chiamate all'API REST può essere eseguito tramite pagine HTML. Gli utenti possono sfruttare la velocità delle query e lo schema di alto livello di CQD pur creando report personalizzati adatti alle proprie esigenze aziendali. Per ulteriori informazioni sull'API e sugli esempi, vedere [Develop Call Quality Dashboard per Skype for Business Server.](develop.md) 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definizione dei requisiti dell'organizzazione per CQD

CQD fornisce l'archiviazione dei dati QoE e un'analisi rapida e approfondita dei dati sulla qualità delle chiamate. La guida seguente ti aiuta a decidere quando e perché distribuire CQD.
  
### <a name="when-to-deploy-cqd"></a>Quando distribuire CQD

 **Il DQD può essere distribuito per stabilire una misurazione della qualità delle chiamate di base, anche se un'organizzazione non ha problemi di qualità delle chiamate.** La definizione di una misurazione della qualità delle chiamate di base è importante perché ogni organizzazione ha una combinazione diversa di Wi-Fi rispetto ai lavoratori in ufficio e cablati e remoti. Quando si verificano problemi di qualità delle chiamate, le misurazioni della qualità delle chiamate più recenti possono essere confrontate con gli intervalli di tempo precedenti. Le funzionalità di tendenza di CQD consentono di rilevare facilmente le modifiche alla qualità delle chiamate nel tempo.
  
 **La DQD può essere distribuita per individuare in modo proattivo le aree con problemi che potrebbero influire sulla qualità delle chiamate.** Anche se la qualità media delle chiamate per un'organizzazione potrebbe soddisfare gli obiettivi impostati dall'organizzazione, potrebbero esserci sacche di problemi di qualità delle chiamate nascosti dietro le metriche medie. CQD consente di scomposizione come tabella pivot delle metriche di qualità delle chiamate per molte dimensioni nel database QoEMetrics. Individuare gli outlier nei gruppi peer è un modo rapido per individuare in modo proattivo i problemi di qualità delle chiamate.
  
 **La DQD deve essere distribuita in caso di problemi di qualità delle chiamate nell'organizzazione per ridurre il tempo necessario per la risoluzione dei problemi.** CQD può semplificare le indagini sulla qualità delle chiamate esistenti offrendo prestazioni di creazione di report veloci e funzionalità di drill-down dinamico. CQD è progettato per molti tipi di flussi di lavoro nelle indagini sulla qualità delle chiamate per la convalida delle riparazioni nell'ambiente.
  
### <a name="why-deploy-cqd"></a>Perché distribuire CQD

 **La DQD deve essere distribuita se i report QoE devono essere evasi per più di 3 mesi di dati.** I report del database QoEMetrics e del monitoring server sono progettati per conservare e segnalare un piccolo set di dati. Il database delle metriche QoE è ottimizzato per inserimenti rapidi e pertanto la segnalazione delle prestazioni può essere ostacolata da un numero elevato di chiamate o dall'accesso di report concorrenti al database. Il database QoE Archive di CQD fornisce una seconda copia dei dati della metrica QoE con funzionalità di conservazione molto più lunghe. Il portale è inoltre ottimizzato per visualizzare fino a 7 mesi di dati alla volta e può creare report su tutti i dati nell'archivio QoE in base alle esigenze.
  
 **La DQD deve essere distribuita se sono necessari report QoE personalizzati.** Il portale include una funzionalità editor di report per la creazione e la creazione di prototipi di report in modo semplice e rapido. Rende inoltre disponibili API REST per l'accesso programmatico ai dati del cubo, consentendo una presentazione personalizzata tramite HTML/JavaScript o molti altri framework. Non è più necessario creare nuove query di SQL allo scopo di creare visualizzazioni dati personalizzate per la creazione di report.
  
 **La DQD deve essere distribuita se la funzionalità di report QoE esistente non soddisfa la velocità o la profondità richieste dall'organizzazione.** CQD include molti report predefiniti. I report sono immediatamente utili e mostrano in che modo l'analisi progressiva dei dati può offrire ulteriori approfondimenti a ogni livello. La gerarchia dei report consente inoltre di gestire i numerosi report in modo logico e favorisce la creazione di molti più report facilmente accessibili e comprensibili. CQD non offre solo velocità e flessibilità, ma è anche ottimizzato per i flussi di lavoro sviluppati dalla metodologia di qualità delle chiamate.
  
## <a name="components-and-topologies-for-cqd"></a>Componenti e topologie per CQD

CQD include diversi componenti e consente di comprendere i requisiti di ogni componente e la relativa relazione tra loro per ottenere la distribuzione dello strumento più semplice e con le migliori prestazioni. Nella tabella seguente viene descritto il componente dipendente per ogni componente CQD.
  

|**Nome componente**|**Componente dipendente**|
|:-----|:-----|
|Archivio QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portale  <br/> |Microsoft Information Services  <br/> |
|Servizio repository (parte dell'installazione del portale)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Per l'archiviazione QoE e il cubo, alcune opzioni di distribuzione richiedono le edizioni Business Intelligence o Enterprise di Microsoft SQL Server. Per altri dettagli, fai riferimento alla sezione [Requisiti dell'infrastruttura per CQD](plan.md#Infrastructure_Req) riportata di seguito.
  
![Componenti CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configurazione a server singolo

Tutti i componenti CQD e i componenti dipendenti possono essere installati in un unico computer. La configurazione a casella singola è la configurazione più semplice e consente l'autonomia di CQD. CQD avrebbe solo bisogno di accedere al database delle metriche QoE nel Monitoring Server. Il server CQD può essere un computer autonomo, una macchina virtuale o anche il Monitoring Server, a seconda delle risorse disponibili del computer host e dei requisiti di prestazioni. 
  
Durante l'installazione, l'utente che esegue l'installazione deve semplicemente fornire le istanze di Microsoft SQL Server e Microsoft SQL Server Analysis Services precedentemente impostate nel computer in cui deve essere installato il DQD. Per altre informazioni, fare riferimento a [Deploy Call Quality Dashboard per Skype for Business Server.](deploy-0.md)
  
### <a name="multiserver-configuration"></a>Configurazione multiserver

In una configurazione multiserver, l'archivio QoE, il cubo e il portale possono essere tutti presenti in computer diversi. Esistono due utilizzi principali per la configurazione multiserver:
  
- Hosting di CQD Web Portal e CQD Cube in server diversi.
    
- Hosting di un portale di "sviluppo" separato dal portale di "produzione". 
    
  **Hosting di CQD Web Portal e CQD Cube in computer diversi.** Le organizzazioni che potrebbero avere requisiti per separare il portale CQD dall'installazione di SQL Server o che potrebbero voler combinare le edizioni SQL Server per l'istanza di SQL Server e l'istanza di SQL Server Analysis Services possono scegliere di installare il portale CQD e il cubo CQD in computer diversi. Il componente di archiviazione QoE può anche essere l'unico componente CQD installato se l'organizzazione desidera semplicemente disporre di un metodo sostenibile per archiviare i dati QoE senza raggiungere i limiti di prestazioni nel Monitoring Server.
  
![Single Server CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosting di un portale di "sviluppo" separato dal portale di "produzione".** Le organizzazioni che sviluppano report personalizzati (tramite le API REST) potrebbero preferire la distribuzione di istanze aggiuntive del portale (CQD) insieme al portale di produzione a cui gli utenti normali accedono per il monitoraggio o le indagini sulla qualità delle chiamate. Il portale di sviluppo può isolare qualsiasi modifica apportata al portale dall'ambiente di produzione. I portali Web aggiuntivi possono essere distribuiti in computer diversi (illustrati di seguito) o in directory Web diverse nello stesso computer (non mostrato). Per ottenere questo risultato, il portale Web CQD aggiuntivo deve essere copiato manualmente nel computer di produzione perché il processo di installazione CQD distribuisce sempre il portale Web CQD nel sito Web predefinito con nomi di applicazioni Web predefiniti.
  
![Pianificare CQD Multi Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologie supportate

CQD non unisce i dati di più database QoEMetrics, come nel caso in cui siano presenti più topologie di Skype for Business Server, ognuna con il proprio Monitoring Server. Ogni istanza CQD deve puntare a un database QoEMetrics. Tuttavia, poiché CQD sposterà gran parte del carico di lavoro di reporting dal Monitoring Server, le organizzazioni di grandi dimensioni che dovevano distribuire un Monitoring Server per topologia di Skype for Business Server dovrebbero prendere in considerazione l'uso di un Monitoring Server per tutte le topologie.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisiti dell'infrastruttura per CQD
<a name="Infrastructure_Req"> </a>

La DQD, inclusi tutti i componenti e i componenti dipendenti, può essere distribuita in una macchina virtuale, in una singola macchina o in più computer. I requisiti software e hardware minimi sono elencati di seguito. La disponibilità dei dati e le prestazioni delle query possono variare da minuti a ore, a seconda del numero di utenti di Skype for Business Server attivi e dell'hardware e della configurazione, pertanto di seguito sono riportate alcune misurazioni delle prestazioni.
  
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
   
CQD utilizza Microsoft SQL Server, Microsoft SQL Server Analysis Services e Microsoft Internet Information Services quindi i requisiti hardware e software minimi di CQD sono fondamentalmente gli stessi di tali componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione relativi all'aggiornamento dei dati (che dipenderà in parte dal volume di dati QoE generati dall'organizzazione) e dai costi di distribuzione, è necessario tenere presenti ulteriori considerazioni sulla distribuzione.
  
L'elaborazione dei dati in CQD è suddivisa in due fasi principali: 
  
- Processo di archiviazione QoE
    
- Elaborazione dei cubi CQD
    
  **Elaborazione dell'archivio QoE.** L'attività di elaborazione dell'archivio QoE copia i dati dal database delle metriche QoE nel Monitoring Server al database QoE Archive. Esistono due situazioni in cui il tempo di elaborazione dell'attività avrebbe caratteristiche di prestazioni fondamentalmente diverse. Il primo è dopo l'installazione iniziale di CQD. Quando l'attività viene eseguita per la prima volta dopo una nuova installazione, l'attività di elaborazione dell'archivio QoE copierà tutti i dati presenti nel database delle metriche QoE nel database di archiviazione QoE. Il secondo è l'elaborazione periodica dopo questo round iniziale. L'attività di elaborazione dell'archivio QoE viene eseguita ogni 15 minuti ed elabora i nuovi record QoE presenti nel database delle metriche QoE. In genere, il tempo di elaborazione iniziale non è un problema perché viene eseguito solo la prima volta, quando viene installato CQD. Tuttavia, se il provisioning del server CQD è molto inferiore, questa attività può richiedere diverse ore. Fare riferimento alla tabella seguente, ad esempio i tempi di elaborazione iniziali dell'archivio QoE.
  
  **Elaborazione del cubo CQD.** L'attività di elaborazione del cubo aggrega i dati del database Archive QoE nel cubo. Il tempo di elaborazione iniziale del cubo e il tempo di elaborazione successivo del cubo sono determinati dall'SQL Server Analysis Services utilizzato per il cubo CQD. Se si utilizza l'edizione Standard, non esiste alcuna differenza tra il tempo di elaborazione iniziale del cubo e il tempo di elaborazione del cubo successivo perché ogni volta che i dati del cubo vengono aggiornati, sarà sempre un'elaborazione completa di tutti i dati disponibili. Ciò significa che il tempo di elaborazione dei cubi aumenta con l'aumentare della quantità di dati nel database QoE Archive. Poiché Business Intelligence Edition ed Enterprise Edition di SQL Server supportano le partizioni, se si usa una delle due edizioni, solo l'esecuzione iniziale eelaborare tutti i dati nel database QoE Archive. Nelle esecuzioni successive, quando l'attività viene attivata ogni 15 minuti, l'attività eelaborare solo i nuovi record aggiunti al database QoE Archive dall'ultima esecuzione dell'attività. Una volta al giorno, ci sarà anche un'elaborazione completa nella partizione che contiene i dati del mese corrente.
  
Le caratteristiche del computer fisico possono influire sulle prestazioni della DQD, nonché sulle funzionalità software disponibili dai SQL Server componenti. Il componente di archiviazione QoE richiederà un utilizzo maggiore del disco rispetto ad altri componenti, mentre il componente Cubo richiederà un utilizzo maggiore della CPU e della memoria. Tutti questi fattori contribuiscono al tempo totale di elaborazione dei dati di CQD, che influisce direttamente sull'freshness e sulla disponibilità dei dati. Le organizzazioni devono prendere decisioni relative all'hardware e al software in base alle singole esigenze dell'organizzazione. 
  
### <a name="tested-hardware-configurations"></a>Configurazioni hardware testate

In questa sezione si presuppone che nell'ambiente sia presente un singolo database QoEMetrics. 
  
**Profili computer**

|**Computer**|**Core CPU**|**RAM**|**Archivio QoE e cubo sullo stesso disco**|**Archivio QoE e SQL database temporaneo sullo stesso disco**|
|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |4   <br/> |7 GB  <br/> |Sì  <br/> |Sì  <br/> |
|4 core  <br/> |4   <br/> |20 GB  <br/> |Sì  <br/> |No  <br/> |
|8 core  <br/> |8   <br/> |32 GB  <br/> |Sì  <br/> |No  <br/> |
|16 core  <br/> |16   <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Risultati delle prestazioni**

|**Computer**|**Dimensioni del database della metrica QoE**|**SQL partizioni**|**Tipo di disco**|**Numero di flussi**|**Processo di archiviazione iniziale**|**Processo cubo iniziale**|**Processo di archiviazione successivo**|**Processo cubo successivo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |900 MB  <br/> |Single  <br/> |Disco rigido virtuale (dimensione variabile)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Single  <br/> |Disco rigido virtuale (dimensione variabile)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Single  <br/> |Disco rigido virtuale (dimensione fissa)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |30+ GB  <br/> |Single  <br/> |Disco rigido virtuale (dimensione fissa)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Single  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Multiplo  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 core  <br/> |30+ GB  <br/> |Single  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 core  <br/> |30+ GB  <br/> |Multiplo  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 core  <br/> |200 GB  <br/> |Single  <br/> |Più dischi  <br/> |125 M  <br/> |6+ giorni  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 core  <br/> |500 GB  <br/> |Multiplo  <br/> |Spindle multipli  <br/> |250 M  <br/> |8 giorni  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Non è previsto che questi dati si verifichino nelle distribuzioni reali, perché il database delle metriche QoE deve avere 9 e 18 mesi di dati, rispettivamente, ma qui vengono forniti per completezza.
  
### <a name="service-account-requirements"></a>Requisiti degli account di servizio

Sarà necessario un account (con accesso in lettura a QoEMetrics) che l'agente SQL nel server CQD possa usare per importare dati in QoEArchiveDB.
  
Potrebbe inoltre essere necessario configurare un account separato per un processo SSAS per il pull dei dati da QoEArchiveDB (questo è un processo facoltativo).
  
IIS utilizza in genere Servizio di rete come identità del pool di app, ma può essere configurato con un account di servizio.
  
### <a name="portal-access-control"></a>Controllo dell'accesso al portale

Per impostazione predefinita, qualsiasi utente autenticato ha accesso. È possibile modificare questa impostazione utilizzando le regole di autorizzazione di IIS per limitare l'accesso a un gruppo specifico.
  
### <a name="pre-install-requirements"></a>Requisiti per la preinstallazione

Queste istruzioni presuppongono che sia già stato installato e in esecuzione un database delle metriche QoE nella topologia di Skype for Business Server.
  
#### <a name="hardware-requirements"></a>Requisiti hardware

CQD utilizza Microsoft SQL Server, Microsoft SQL Analysis Server e Microsoft Internet Information Server, quindi i requisiti hardware e software minimi di CQD sono fondamentalmente gli stessi di tali componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione relativi all'aggiornamento dei dati (che dipenderà in parte dal volume di dati QoE generati dall'organizzazione) e dai costi di distribuzione, è necessario tenere presenti ulteriori considerazioni sulla distribuzione.
  
#### <a name="software-requirements"></a>Requisiti software

Per CQD sono necessari i sistemi operativi seguenti:
  
- Windows Server 2008 R2 con IIS 7.5
    
- Windows Server 2012 con IIS 8.0
    
- Windows Server 2012 R2 con IIS 8.5

- Windows Server 2016 con IIS 10.0 (solo DQD di Skype for Business Server 2019)

- Windows Server 2019 (solo DQD di Skype for Business Server 2019)
    
Di seguito sono riportati i servizi ruolo IIS necessari (in ordine gerarchico):
  
- Server Web
    
  - Caratteristiche HTTP comuni
    
  - Contenuto statico
    
  - Documento predefinito
    
  - Sviluppo di applicazioni
    
  - ASP.NET
    
  - Filtri ISAPI
    
  - Diagnostica &amp; dell'integrità
    
  - Registrazione HTTP
    
  - Sicurezza
    
  - Autorizzazione URL
    
  - Autenticazione di Windows
    
  - Strumenti di gestione
    
  - Console di gestione IIS
    
> [!NOTE]
>  Nota quanto segue per i requisiti precedenti:> sono disponibili le versioni 3.5 e 4.5 di .Net Framework. Entrambi sono necessari (in particolare, è necessario 3.5 SP1).> In alcuni sistemi, se ASP.NET è installato prima dell'installazione di IIS, ASP.NET potrebbe non essere registrato in IIS. Il problema si manifesta in assenza di pool di applicazioni per la versione .Net corrispondente e manca anche la versione .NET CLR nella configurazione del pool di app. Per risolvere un problema di questo tipo in Windows Server 2008 R2, eseguire `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` . In Windows Server 2012 e Windows Server 2012 R2, eseguire seguito dalla rimozione del modulo "ServiceModel" dal sito Web predefinito in Gestione IIS.> Gli strumenti di gestione sono facoltativi, ma  `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` consigliati.
  
Per installare questi requisiti tramite PowerShell, eseguire le operazioni seguenti:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Sono supportate le versioni SQL Server seguenti:
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
L'edizione Business Intelligence o Enterprise è consigliata per motivi di prestazioni. Queste edizioni consentono l'uso di più file di partizione che possono essere elaborati in parallelo, il che è utile per l'elaborazione di dati che si estendono per più mesi o più. 
  
Anche se non è consigliabile, è supportata anche l'edizione Standard. L'elaborazione sarà vincolata a una singola partizione (che deve essere configurata durante l'installazione). 
  
In tutti i casi è necessario installare "Servizi motore di database" e "Analysis Services". È consigliabile, ma non necessario, installare anche la funzionalità "Strumenti di gestione - Completa", che aggiunge SQL Server Management Studio supporto per Analysis Services. La schermata di selezione delle funzionalità dovrebbe essere simile alla figura.
  
![SQL Server delle funzionalità](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Quando si configura l'installazione di SSAS, nella configurazione di Analysis Services impostare "Modalità server" su "Modalità multidimensionale e data mining". 
  
Per ulteriori informazioni sull'installazione e la configurazione di SQL Server business intelligence, vedere [Install Analysis Services in Multidimensional and Data Mining Mode.](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx)
  
#### <a name="account-requirements"></a>Requisiti per gli account

Sono consigliati tre account del servizio di dominio in base al principio dei privilegi minimi: 
  
- Uno che dispone già di un'entità di sicurezza di accesso per il database delle metriche QoE (con privilegi di db_datareader) e di un'entità di sicurezza di accesso nell'istanza di SQL Server Archivio QoE (necessaria per creare un oggetto Server collegato durante l'installazione). Questo account verrà utilizzato per eseguire il passaggio "QoE Archive Data" del processo SQL Server Agent.
    
    > [!NOTE]
    > Se si lavora in un ambiente fortemente bloccato, è necessario verificare che all'account di servizio siano effettivamente concessi i diritti utente "Accesso come processo batch" e "Consenti accesso locale" sia per il SQL Server del database di monitoraggio delle metriche QoE che per il SQL Server di archiviazione QoE.
    
- Uno che verrà utilizzato per eseguire il passaggio "Process Cube" del SQL Server Agent. Il programma di installazione creerà un'entità di sicurezza di accesso al database Archive QoE (con privilegi di lettura e scrittura) e creerà inoltre un membro nel ruolo QoE (con privilegi di controllo completo) per il cubo.
    
- Uno che verrà utilizzato per eseguire il processo di lavoro IIS per i portali Web e le API Web. Il programma di installazione creerà un'entità di sicurezza di accesso per il database Archive QoE (con privilegi di lettura), un'entità di sicurezza di accesso al database repository (con privilegi di lettura e scrittura) e un membro in QoERole (con privilegi di controllo completo) per il cubo. 
    
    > [!NOTE]
    > Quando il database QoE Archive e il database repository sono ospitati nello stesso SQL Server, viene creata una sola entità di sicurezza di accesso con due mapping di utenti. 
  
I primi due account possono essere considerati logicamente "account di servizio back-end" e l'ultimo account è un "account di servizio front-end". Anche se non è consigliabile, è possibile utilizzare un singolo account in tutti i casi.
  
> [!NOTE]
> L'account utente che avvia l'installazione deve disporre anche dell'accesso in lettura al database delle metriche QoE (oltre ad avere diritti di amministratore del computer nel server db archivio QoE in cui deve essere completata l'installazione). 
  
## <a name="capacity-planning"></a>Pianificazione della capacità
<a name="Infrastructure_Req"> </a>

CQD è progettato per un impatto minimo sulle metriche QoE: il codice è stato ottimizzato per non bloccare i dati e i processi di importazione sono regolabili.
  
Il tipo di hardware da usare dipende dai requisiti per la velocità di esecuzione delle sincronizzazioni. Il ridimensionamento del disco è il seguente:
  
- QoEArchive è circa 1,5x più grande di QoEMetrics DB inizialmente
    
- Il cubo SSIS comprime i dati quasi 10x rispetto al database
    
- I dati vengono partizionati mensilmente; le partizioni possono essere eliminate
    

