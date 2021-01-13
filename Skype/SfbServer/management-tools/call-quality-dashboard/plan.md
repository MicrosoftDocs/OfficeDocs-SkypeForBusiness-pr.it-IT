---
title: Pianificare il dashboard per la qualità delle chiamate per Skype for Business Server
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
description: 'Riepilogo: informazioni sulle considerazioni da prendere in considerazione quando si pianifica il dashboard qualità chiamata.'
ms.openlocfilehash: 6a1fc39dd26f6c4e9e455babcecb124888629179
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803176"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Pianificare il dashboard per la qualità delle chiamate per Skype for Business Server 
 
**Riepilogo:** Informazioni su cosa prendere in considerazione quando si pianifica il dashboard qualità chiamata.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Panoramica del dashboard per la qualità delle chiamate di Skype for Business Server

Skype for Business Server Call Quality Dashboard (CQD) è un livello di Reporting al di sopra del database della qualità di esperienza nel Monitoring Server in Skype for Business Server. In CQD viene utilizzato Microsoft SQL Server Analysis Services per fornire informazioni sull'utilizzo di aggregazione e sulla qualità delle chiamate, nonché per il filtro e il Pivoting sul set di dati. Le caratteristiche di CQD includono:
  
- **Archiviazione archivistica dei dati QoE tramite il componente di archiviazione QoE di CQD.** Il componente di archiviazione QoE è in grado di archiviare i dati QoE per una durata molto più lunga rispetto a quella del server di monitoraggio. In questo modo è possibile eseguire il trend e la creazione di report per un massimo di sette mesi di dati alla volta, con la possibilità di scorrere la finestra dei report fino a quando non vi sono dati.
- **Reporting e analisi utilizzando la potenza e la velocità di Microsoft SQL Server Analysis Services.** CQD utilizza Microsoft SQL Analysis Services per fornire funzionalità di riepilogo, filtro e pivoting veloci per alimentare il dashboard tramite un cubo di analisi. La velocità di esecuzione dei rapporti e la possibilità di eseguire il drill-down nei dati possono ridurre drasticamente i tempi di analisi.
- **Nuovo schema di dati ottimizzato per i report sulla qualità delle chiamate.** Il cubo ha uno schema disegnato per la creazione di report e le indagini sulla qualità vocale. Gli utenti del portale possono concentrarsi sulle attività di creazione di report anziché capire come lo schema del database delle metriche QoE è mappato alle visualizzazioni di cui hanno bisogno. La combinazione dell'archivio QoE e del cubo fornisce un'astrazione che riduce la complessità della creazione di report e dell'analisi tramite CQD. Lo schema del database di archiviazione QoE contiene anche tabelle che possono essere popolate con dati specifici della distribuzione per migliorare il valore complessivo dei dati.
- **Progettazione report incorporata e modifica del rapporto sul posto.** Il componente portale è dotato di numerosi report incorporati modellati dopo la metodologia della qualità delle chiamate. Gli utenti del portale possono modificare i report e creare nuovi rapporti tramite la funzionalità di modifica del portale.
- **Accesso API Web ai dati della struttura del report e dei cubi di analisi.** Il dashboard Reporting Framework non è l'unico modo per visualizzare i dati dal cubo. CQD fornisce diversi esempi di utilizzo di HTML e JavaScript per recuperare i dati dalle API Web di CQD ed eseguire il rendering dei dati in un formato personalizzato. La combinazione dell'editor di report e delle API Web di CQD consente di creare rapidamente prototipi di report e layout di report personalizzati.

> [!NOTE]
> Un amministratore può ora gestire Skype for Business Server 2019 utilizzando [CQD versione 3](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore). Ciò richiede un'implementazione ibrida e l'utilizzo del connettore di dati di chiamata (CDC). Per ulteriori informazioni sull'abilitazione di CDC, vedere [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) . Per la documentazione relativa a CQD versione 3, vedere [accendere e usare Call Quality dashboard per Microsoft teams e Skype for business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) per ulteriori informazioni su CQD versione 3.

## <a name="cqd-design-goals"></a>Obiettivi di progettazione di CQD

CQD consente ai professionisti IT di utilizzare dati aggregati per identificare le aree di interesse nell'ambiente in cui si verificano problemi di qualità multimediale. Consente a un professionista IT di confrontare le statistiche per i diversi gruppi di utenti e identificare le tendenze e i modelli. Non è incentrato sulla risoluzione dei singoli problemi di chiamata, ma sull'identificazione di problemi e soluzioni che si applicano a molti utenti in un determinato ambiente. 
  
## <a name="call-quality-dashboard-components"></a>Componenti del dashboard per la qualità delle chiamate

Il dashboard per la qualità delle chiamate è costituito da diversi database, processi e applicazioni Web di Microsoft SQL Agent. I processi di Microsoft SQL Agent copiano periodicamente i dati dal database di metriche QoE nel database di archiviazione QoE e elaborano il cubo con i dati nel database di archiviazione QoE. Il database del repository archivia le definizioni di report che alimentano il portale. Il portale fornisce l'accesso dei browser ai dati del cubo. 
  
I componenti di CQD, inclusi i database dell'archivio QoE, del cubo e del repository, possono essere installati nel Monitoring Server, installato nel proprio server o installati su più server. Il metodo di installazione specifico dipende dalle richieste di prestazioni di CQD e dall'impatto su altri processi negli stessi server. Per ulteriori informazioni, vedere la sezione "componenti e topologie per CQD" più avanti in questo articolo.
  
### <a name="architectural-overview"></a>Panoramica dell'architettura

Per riepilogare, CQD richiede gli elementi seguenti:
  
- Due database: database di archiviazione e database dell'archivio.
    
- Un cubo SSAS che Visualizza dati aggregati 
    
- Portale Web CQD hosts IIS
    
![Componenti di CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
La stessa architettura di CQD supporta Lync Server 2013 e Skype for business. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD e Skype for business vs Lync 2013

 Solo in un ambiente Skype for business, sono disponibili le seguenti funzionalità:
  
- Wi-Fi segnalazione della potenza del segnale
    
- Wi-Fi Reporting dei driver del chipset
    
- Valutare i dati delle chiamate 
    
## <a name="information-available-through-cqd"></a>Informazioni disponibili tramite CQD

CQD è in grado di visualizzare i conteggi del flusso di condivisione applicazioni e video di Skype for Business Server e il conteggio delle chiamate valide e negative, nonché i rapporti di chiamate non valide. Le visualizzazioni possono essere sezionate e filtrate da molte dimensioni diverse. CQD estrae i dati dal database delle metriche QoE nel Monitoring Server. I dati vengono quindi Uniti con tutti i dati forniti dal cliente, ad esempio il mapping tra la subnet e la creazione di una rete per creare report quali "qualità chiamata per edificio" possibile. 
  
CQD inoltre astrae molte delle idiosincrasie dei dati QoE interni, ad esempio "chiamante" e "chiamato", in modo che l'utente possa concentrarsi sulla creazione di visualizzazioni di report su "Server" e "client". Dopo la metodologia relativa alla qualità delle chiamate, CQD è semplificato per identificare le condizioni in cui le tasche delle chiamate povere sono in comune, uno dei principi per migliorare la qualità delle chiamate.
  
## <a name="viewing-data-in-cqd"></a>Visualizzazione dei dati in CQD

I dati di CQD possono essere visualizzati tramite il portale CQD e accessibili tramite le chiamate API REST.
  
### <a name="cqd-portal"></a>Portale di CQD

Il portale è il modo più rapido per visualizzare i dati nel cubo. Il portale è dotato di numerosi rapporti incorporati che sono utilizzabili subito. I report incorporati sono collegati in modo strutturato per indirizzare l'utente a sezioni più piccole e successive dei dati di chiamata. I report incorporati evidenziano anche i diversi modi in cui i dati possono essere visualizzati dimostrando una combinazione di grafici e tabelle con diversi pivot, filtri e misure. Ogni utente che accede al portale può disporre di un proprio insieme di report che può modificare e condividere. Per ulteriori informazioni sull'utilizzo del portale Web di CQD, vedere [Use Call Quality dashboard for Skype for Business Server](use.md).
  
Sistemi operativi supportati per il portale di CQD: Windows 8,1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (solo Skype for Business Server 2019 CQD).
  
Browser supportati per il portale di CQD: Internet Explorer 11, Internet Explorer 10 e Internet Explorer 9.
  
### <a name="rest-apis"></a>API REST

È inoltre possibile accedere ai dati del cubo tramite le chiamate API REST. I dati recuperati tramite le chiamate API REST possono essere sottoposte a rendering tramite pagine HTML. Gli utenti possono trarre vantaggio dalla velocità di query e dallo schema di livello elevato di CQD, mentre ancora la creazione di report personalizzati è adatta alle proprie esigenze aziendali. Per ulteriori informazioni sull'API e sugli esempi, vedere [develop Call Quality dashboard for Skype for Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definizione dei requisiti dell'organizzazione per CQD

CQD fornisce archiviazione dei dati QoE e analisi rapida e approfondita dei dati sulla qualità delle chiamate. La guida seguente consente di decidere quando e perché distribuire CQD.
  
### <a name="when-to-deploy-cqd"></a>Quando distribuire CQD

 **È possibile distribuire CQD per stabilire una misura di qualità delle chiamate di base, anche se un'organizzazione non verifica problemi di qualità delle chiamate.** La definizione di una misura di qualità delle chiamate di base è importante perché ogni organizzazione dispone di un diverso mix di Wi-Fi rispetto a Wired e remote rispetto ai dipendenti di Office. Quando si verificano problemi di qualità delle chiamate, le misure di qualità delle chiamate più recenti possono essere confrontate con gli intervalli di tempo precedenti. Le funzionalità di trend di CQD consentono di rilevare facilmente le modifiche apportate alla qualità delle chiamate nel tempo.
  
 **È possibile distribuire CQD per individuare in modo proattivo aree problematiche che potrebbero influire sulla qualità delle chiamate.** Anche se la qualità media delle chiamate per un'organizzazione può essere conforme ai target stabiliti dall'organizzazione, potrebbero esserci sacche di problemi di qualità delle chiamate nascosti dietro metriche medie. CQD consente di suddividere le metriche di qualità delle chiamate da una tabella pivot di molte dimensioni nel database di QoEMetrics. Lo spotting outliers nei gruppi peer rappresenta un modo rapido per individuare attivamente i problemi di qualità delle chiamate.
  
 **CQD deve essere distribuito se nell'organizzazione sono presenti problemi di qualità delle chiamate per ridurre il tempo necessario per la risoluzione dei problemi.** CQD è in grado di semplificare le indagini esistenti sulla qualità delle chiamate, offrendo funzionalità di Reporting rapido e drill-down dinamico. CQD è stato creato per molti tipi di flussi di lavoro in indagini sulla qualità delle chiamate per la convalida delle riparazioni all'ambiente.
  
### <a name="why-deploy-cqd"></a>Perché distribuire CQD

 **CQD deve essere distribuito se la segnalazione QoE deve avvenire per più di 3 mesi di dati.** I report di database e Monitoring Server di QoEMetrics sono stati concepiti per mantenere e segnalare un piccolo set di dati. Il database di metriche QoE è ottimizzato per gli inserimenti rapidi e pertanto le prestazioni dei report possono essere ostacolate da un elevato volume di chiamate o dall'accesso ai report in competizione con il database. Il database di archiviazione QoE di CQD fornisce una seconda copia dei dati della metrica QoE con funzionalità di conservazione molto più lunghe. Il portale è inoltre ottimizzato per visualizzare fino a 7 mesi di dati alla volta e può segnalare tutti i dati nell'archivio QoE in base alle esigenze.
  
 **CQD deve essere distribuito se sono necessari report QoE personalizzati.** Il portale dispone di una funzionalità di editor di report per la creazione e la prototipazione dei report in modo rapido e semplice. Inoltre, rende disponibili API REST per l'accesso programmatico ai dati del cubo, consentendo la presentazione personalizzata tramite HTML/JavaScript o molti altri Framework. Non è più necessario creare nuove query SQL ai fini della creazione di visualizzazioni dati personalizzate per i report.
  
 **CQD deve essere distribuito se la funzionalità di Reporting QoE esistente non soddisfa la velocità o la profondità richieste dall'organizzazione.** CQD viene fornito con molti report incorporati. I report sono immediatamente utili e dimostrano la graduale foratura dei dati in grado di offrire ulteriori approfondimenti a ogni livello. La gerarchia dei rapporti aiuta anche a gestire i numerosi rapporti in maniera logica e promuove la creazione di molti altri rapporti che sono facilmente accessibili e comprensibili. CQD non offre solo velocità e flessibilità, ma è ottimizzato anche per i flussi di lavoro sviluppati dalla metodologia della qualità delle chiamate.
  
## <a name="components-and-topologies-for-cqd"></a>Componenti e topologie per CQD

CQD viene fornito con diversi componenti e consente di comprendere i requisiti di ogni componente e la loro relazione tra loro per ottenere la distribuzione più semplice e ottimale dello strumento. Nella tabella seguente viene descritto il componente dipendente per ogni componente di CQD.
  

|**Nome componente**|**Componente dipendente**|
|:-----|:-----|
|Archivio QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portale  <br/> |Microsoft Information Services  <br/> |
|Servizio repository (parte dell'installazione del portale)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Per l'archiviazione e il cubo QoE, alcune opzioni di distribuzione richiedono Business Intelligence o edizioni Enterprise di Microsoft SQL Server. Per ulteriori informazioni, vedere la sezione [requisiti dell'infrastruttura per CQD](plan.md#Infrastructure_Req) .
  
![Componenti di CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configurazione a server singolo

Tutti i componenti di CQD e i componenti dipendenti possono essere installati in un unico computer. La configurazione di una singola casella è la configurazione più semplice e consente a CQD di essere indipendente. CQD avrebbe solo bisogno di accedere al database di metriche QoE sul Monitoring Server. Il server CQD può essere un computer autonomo, una macchina virtuale oppure può anche essere il Monitoring Server, in base alle risorse disponibili del computer host e ai requisiti di prestazioni. 
  
Durante l'installazione, l'utente che esegue l'installazione deve semplicemente fornire le istanze di Microsoft SQL Server e Microsoft SQL Server Analysis Services precedentemente configurate nel computer in cui deve essere installato CQD. Per ulteriori informazioni, fare riferimento a [deploy Call Quality dashboard for Skype for Business Server](deploy-0.md) .
  
### <a name="multiserver-configuration"></a>Configurazione multiserver

In una configurazione multiserver, l'archivio QoE, il cubo e il portale possono essere tutti su computer diversi. Per la configurazione multiserver sono disponibili due utilizzi principali:
  
- Hosting del portale Web di CQD e del cubo di CQD su server diversi.
    
- Hosting di un portale di "sviluppo" separato dal portale di "produzione". 
    
  **Hosting del portale Web di CQD e del cubo di CQD su computer diversi.** Le organizzazioni che potrebbero avere i requisiti per separare il portale di CQD dall'installazione di SQL Server o che potrebbero voler combinare le edizioni di SQL Server per l'istanza di SQL Server e l'istanza di SQL Server Analysis Services possono scegliere di installare il portale di CQD e il cubo di CQD in computer diversi. Il componente di archiviazione QoE può anche essere il solo componente di CQD installato se l'organizzazione vuole semplicemente avere un metodo sostenibile per archiviare i dati QoE senza raggiungere limiti di prestazioni sul Monitoring Server.
  
![CQD a server singolo](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hosting di un portale di "sviluppo" separato dal portale di "produzione".** Le organizzazioni che sviluppano i propri report personalizzati (tramite le API REST) potrebbero preferire la distribuzione di istanze di portale aggiuntive (CQD) accanto al portale di produzione che gli utenti abituali accedono per il monitoraggio o le indagini sulla qualità delle chiamate. Il portale di sviluppo è in grado di isolare le modifiche apportate al portale dall'ambiente di produzione. I portali aggiuntivi Web possono essere distribuiti su computer diversi (illustrati di seguito) oppure distribuiti in directory Web diverse nello stesso computer (non visualizzato). Per eseguire quest'ultima operazione, è necessario copiare il portale Web di CQD aggiuntivo nel computer di produzione manualmente perché il processo di installazione di CQD distribuisce sempre il portale Web di CQD nel sito Web predefinito con nomi di applicazioni Web predefiniti.
  
![Pianificare CQD multi server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologie supportate

CQD non unisce i dati provenienti da più database di QoEMetrics, come nel caso in cui vi siano più topologie di Skype for Business Server, ognuna con un proprio Monitoring Server. Ogni istanza di CQD deve puntare a un database di QoEMetrics. Tuttavia, poiché CQD sposterà gran parte del carico di lavoro di Reporting fuori dal Monitoring Server, le organizzazioni di grandi dimensioni che necessitano di distribuire un Monitoring Server per la topologia di Skype for Business Server devono considerare l'utilizzo di un server di monitoraggio per tutte le topologie.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisiti dell'infrastruttura per CQD
<a name="Infrastructure_Req"> </a>

CQD, inclusi tutti i componenti e i componenti dipendenti, può essere distribuito in una macchina virtuale, in un singolo computer o su più computer. Di seguito sono elencati i requisiti hardware e software minimi. La disponibilità dei dati e le prestazioni delle query possono variare da un minuto all'altro, a seconda del numero di utenti e hardware e configurazione attivi di Skype for Business Server, per cui sono state riportate alcune misurazioni delle prestazioni.
  
|||
|:-----|:-----|
|Per CQD 2015 <br/> |  <br/> |
|Sistemi operativi supportati   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|SQL Server supportato  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|Per CQD 2019 <br/> |  <br/> |
|Sistemi operativi supportati   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|SQL Server supportato  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD utilizza Microsoft SQL Server, Microsoft SQL Server Analysis Services e Microsoft Internet Information Services in modo che i requisiti hardware e software minimi di CQD siano sostanzialmente identici a quelli dei componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione relativi alla freschezza dei dati (che dipenderà in parte dal volume dei dati QoE generati dall'organizzazione) e ai costi di distribuzione, dovrebbero essere apportate ulteriori considerazioni sulla distribuzione.
  
L'elaborazione dei dati in CQD è suddivisa in due fasi principali: 
  
- Processo di archiviazione QoE
    
- Elaborazione del cubo di CQD
    
  **Elaborazione dell'archivio QoE.** L'attività di elaborazione dell'archivio QoE copia i dati dal database delle metriche QoE sul server di monitoraggio al database di archiviazione QoE. Esistono due situazioni in cui il tempo di elaborazione dell'attività avrebbe caratteristiche di prestazioni sostanzialmente diverse. Il primo è dopo l'installazione iniziale di CQD. Quando l'attività viene eseguita per la prima volta dopo un'installazione aggiornata, l'attività di elaborazione dell'archivio QoE copierà tutti i dati presenti nel database di metriche QoE nel database di archiviazione QoE. La seconda è l'elaborazione periodica dopo questo round iniziale. L'attività di elaborazione dell'archivio QoE verrà eseguita ogni 15 minuti e elaborerà tutti i nuovi record QoE presenti nel database di metriche QoE. In generale, il tempo di elaborazione iniziale non è un problema perché viene eseguito solo la prima volta, quando CQD è installato. Tuttavia, se il server CQD è sottoposto a provisioning gravemente, questa attività può richiedere diverse ore. Fare riferimento alla tabella seguente, ad esempio tempi di elaborazione dell'archivio QoE iniziali.
  
  **Elaborazione dei cubi di CQD.** L'attività di elaborazione del cubo aggrega i dati dal database di archivio QoE nel cubo. Il tempo di elaborazione iniziale del cubo e il successivo tempo di elaborazione del cubo sono determinati dall'edizione SQL Server Analysis Services utilizzata per il cubo di CQD. Se viene utilizzata la versione Standard Edition, non vi è alcuna differenza tra il tempo di elaborazione del cubo iniziale e quello successivo, perché ogni volta che si aggiornano i dati del cubo, sarà sempre un'elaborazione completa di tutti i dati disponibili. Questo significa che il tempo di elaborazione del cubo aumenta man mano che aumenta la quantità di dati nel database di archiviazione QoE. Poiché la Business Intelligence Edition e Enterprise Edition di SQL Server dispongono del supporto delle partizioni, se viene utilizzata una delle edizioni, solo l'esecuzione iniziale elaborerà tutti i dati nel database di archiviazione QoE. Nelle esecuzioni successive, quando l'attività viene attivata ogni 15 minuti, l'attività elaborerà solo i nuovi record aggiunti al database di archiviazione QoE dall'ultima volta che l'attività è stata eseguita. Una volta al giorno, vi sarà anche un'elaborazione completa sulla partizione contenente i dati del mese corrente.
  
Le caratteristiche del computer fisico possono influire sulle prestazioni di CQD e sulle funzionalità software disponibili nei componenti di SQL Server. Il componente di archiviazione QoE avrà un maggiore utilizzo del disco rispetto ad altri componenti, mentre il componente cubo avrà un numero maggiore di CPU e memoria intensiva. Tutti questi fattori contribuiscono alla durata complessiva dell'elaborazione dei dati di CQD, che influiscono direttamente sulla disponibilità e sulla freschezza dei dati. Le organizzazioni devono prendere decisioni sull'hardware e il software in base alle esigenze dell'organizzazione. 
  
### <a name="tested-hardware-configurations"></a>Configurazioni hardware testate

In questa sezione si presuppone la presenza di un singolo database di QoEMetrics nell'ambiente. 
  
**Profili del computer**

|**Computer**|**Core della CPU**|**RAM**|**Archivio QoE e cubo sullo stesso disco**|**Archivio QoE e SQL Temp DB sullo stesso disco**|
|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |4   <br/> |7 GB  <br/> |Sì  <br/> |Sì  <br/> |
|4 core  <br/> |4   <br/> |20 GB  <br/> |Sì  <br/> |No  <br/> |
|8 core  <br/> |8   <br/> |32 GB  <br/> |Sì  <br/> |No  <br/> |
|16 core  <br/> |16   <br/> |128 GB  <br/> |No  <br/> |No  <br/> |
   
**Risultati delle prestazioni**

|**Computer**|**Metriche QoE dimensioni DB**|**Partizioni SQL**|**Tipo di disco**|**Numero di flussi**|**Processo di archiviazione iniziale**|**Processo iniziale del cubo**|**Processo di archiviazione successivo**|**Processo di cubo successivo**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Macchina virtuale  <br/> |900 MB  <br/> |Singolo  <br/> |VHD (dimensioni variabili)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Singolo  <br/> |VHD (dimensioni variabili)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |9 GB  <br/> |Singolo  <br/> |VHD (dimensioni fisse)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|Macchina virtuale  <br/> |30 + GB  <br/> |Singolo  <br/> |VHD (dimensioni fisse)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Singolo  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 core  <br/> |9 GB  <br/> |Multiplo  <br/> |Più dischi  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|8 core  <br/> |30 + GB  <br/> |Singolo  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|8 core  <br/> |30 + GB  <br/> |Multiplo  <br/> |Più dischi  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|4 core  <br/> |200 GB  <br/> |Singolo  <br/> |Più dischi  <br/> |125 M  <br/> |6 + giorni  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 core  <br/> |500 GB  <br/> |Multiplo  <br/> |Mandrini multipli  <br/> |250 M  <br/> |8 giorni  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*Non è previsto che vengano rilevate nelle distribuzioni effettive, poiché il database di metriche QoE dovrebbe avere rispettivamente 9 e 18 mesi di dati, ma sono forniti qui per completezza.
  
### <a name="service-account-requirements"></a>Requisiti per gli account di servizio

Sarà necessario un account (con accesso in lettura a QoEMetrics) che può essere utilizzato dall'agente SQL sul server CQD per l'importazione dei dati in QoEArchiveDB.
  
Potrebbe anche essere necessario configurare un account separato per un processo SSAS per estrarre i dati da QoEArchiveDB (processo facoltativo).
  
IIS più comunemente utilizza il servizio di rete come identità del pool di applicazioni, ma può essere configurato per un account di servizio.
  
### <a name="portal-access-control"></a>Controllo di accesso al portale

Per impostazione predefinita, qualsiasi utente autenticato ha accesso. Questo può essere modificato tramite le regole di autorizzazione di IIS per limitare a un gruppo specifico.
  
### <a name="pre-install-requirements"></a>Requisiti di preinstallazione

Queste istruzioni presuppongono che un database di metriche QoE sia già stato installato e che sia in esecuzione da qualche parte nella topologia di Skype for Business Server.
  
#### <a name="hardware-requirements"></a>Requisiti hardware

CQD utilizza Microsoft SQL Server, Microsoft SQL Analysis Server e Microsoft Internet Information Server in modo che i requisiti hardware e software minimi di CQD siano sostanzialmente identici a quelli dei componenti dipendenti. Tuttavia, in base ai requisiti dell'organizzazione relativi alla freschezza dei dati (che dipenderà in parte dal volume dei dati QoE generati dall'organizzazione) e ai costi di distribuzione, dovrebbero essere apportate ulteriori considerazioni sulla distribuzione.
  
#### <a name="software-requirements"></a>Requisiti software

Per CQD sono necessari i sistemi operativi seguenti:
  
- Windows Server 2008 R2 con IIS 7,5
    
- Windows Server 2012 con IIS 8,0
    
- Windows Server 2012 R2 con IIS 8,5

- Windows Server 2016 con IIS 10,0 (solo per CQD di Skype for Business Server 2019)

- Windows Server 2019 (solo CQD di Skype for Business Server 2019)
    
Di seguito sono riportati i servizi ruolo IIS necessari (in ordine gerarchico):
  
- Server Web
    
  - Caratteristiche HTTP comuni
    
  - Contenuto statico
    
  - Documento predefinito
    
  - Sviluppo di applicazioni
    
  - ASP.NET
    
  - Filtri ISAPI
    
  - Diagnostica di integrità &amp;
    
  - Registrazione HTTP
    
  - Sicurezza
    
  - Autorizzazione URL
    
  - Autenticazione di Windows
    
  - Strumenti di gestione
    
  - Console di gestione IIS
    
> [!NOTE]
>  Tenere presente quanto segue per i requisiti di cui sopra: sono disponibili le versioni di > 3,5 e 4,5 di .NET Framework. Entrambi sono necessari (in particolare, è necessario 3,5 SP1). > in alcuni sistemi, se ASP.NET è impostato prima dell'installazione di IIS, ASP.NET potrebbe non essere registrato in IIS. Il problema si manifesta con l'assenza di pool di applicazioni per la versione .NET corrispondente e manca anche la versione CLR .NET nella configurazione del pool di applicazioni. Per risolvere un problema di questo tipo in Windows Server 2008 R2, eseguire `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` . In Windows Server 2012 e Windows Server 2012 R2, eseguire  `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` seguito rimuovendo il modulo "ServiceModel" dal sito Web predefinito in Gestione IIS. > gli strumenti di gestione sono facoltativi, ma sono consigliati.
  
Per installare questi requisiti tramite PowerShell, eseguire le operazioni seguenti:
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Sono supportate le versioni di SQL Server seguenti:
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
La Business Intelligence o Enterprise Edition è consigliata per motivi di prestazioni. Queste edizioni consentono l'utilizzo di più file di partizione che possono essere elaborati in parallelo, il che è utile per l'elaborazione dei dati che si estendono su più mesi o più. 
  
Anche se non consigliato, Standard Edition è supportato. L'elaborazione sarà vincolata a una singola partizione (che deve essere configurata durante l'installazione). 
  
In tutti i casi, è necessario installare "Servizi motore di database" e "Analysis Services". È consigliabile, ma non è necessario, installare anche la caratteristica "strumenti di gestione-completamento", che aggiunge il supporto di SQL Server Management Studio per Analysis Services. La schermata di selezione delle caratteristiche dovrebbe essere simile alla figura.
  
![Requisiti delle funzionalità di SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Quando si configura il programma di installazione di SSAS, nella configurazione di Analysis Services impostare "modalità server" su "Multidimensional and data mining Mode". 
  
Per ulteriori informazioni sull'installazione e sulla configurazione delle funzionalità di business intelligence di SQL Server, vedere [Install Analysis Services in Multidimensional and data mining Mode](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisiti per gli account

Sono consigliati tre account del servizio di dominio sul principio del privilegio minimo: 
  
- Uno che già dispone di un'entità di sicurezza dell'account di accesso per il database di metriche QoE (con privilegi db_datareader) e un'entità di sicurezza dell'account di accesso nell'istanza di SQL Server di archiviazione QoE (necessaria per creare un oggetto server collegato durante l'installazione). Questo account verrà utilizzato per eseguire il passaggio "dati di archiviazione QoE" del processo di SQL Server Agent.
    
    > [!NOTE]
    > Se si lavora in un ambiente fortemente bloccato, è necessario verificare che l'account di servizio sia effettivamente concesso "accesso come processo batch" e "Consenti log on localmente" diritti utente su entrambi i database di monitoraggio metriche QoE Monitoring SQL Server e l'archivio QoE SQL Server.
    
- Uno che verrà utilizzato per eseguire il passaggio "processo cubo" del processo di SQL Server Agent. Il programma di installazione creerà un'entità di sicurezza per l'accesso al database di archiviazione QoE (con privilegi di lettura e scrittura) e creerà anche un membro nel ruolo QoE (con privilegi di controllo completo) per il cubo.
    
- Uno che verrà utilizzato per eseguire il processo di lavoro IIS per i portali Web e le API Web. Il programma di installazione creerà un'entità di sicurezza dell'account di accesso per il database di archiviazione QoE (con privilegi di lettura), un'entità di sicurezza dell'account di accesso per il database di repository (con privilegi di lettura e scrittura) e un membro in QoERole (con privilegi di controllo completo) per il cubo. 
    
    > [!NOTE]
    > Quando entrambi i database di archiviazione QoE e il database dell'archivio sono ospitati nello stesso SQL Server, viene creata una sola entità di sicurezza per gli account di accesso con due mapping degli utenti. 
  
I primi due account possono essere considerati logicamente come "account del servizio back-end" e l'ultimo account è un "account del servizio front end". Anche se non consigliato, è possibile utilizzare un singolo account in tutti i casi.
  
> [!NOTE]
> L'account utente che avvia l'installazione deve disporre di accesso in lettura al database delle metriche QoE e (oltre a disporre di diritti di amministratore del computer nel server di archiviazione di database QoE in cui deve essere eseguita l'installazione). 
  
## <a name="capacity-planning"></a>Pianificazione della capacità
<a name="Infrastructure_Req"> </a>

CQD è stato ideato per un impatto minimo su QoEMetrics: il codice è stato ottimizzato per non bloccare i dati e i processi di importazione sono sintonizzabili.
  
Il tipo di hardware da utilizzare dipende dai requisiti necessari per la rapida esecuzione delle sincronizzazioni. Il ridimensionamento del disco è il seguente:
  
- QoEArchive è ~ 1.5 x più grande di QoEMetrics DB inizialmente
    
- Il cubo SSIS comprime i dati quasi 10x rispetto a DB
    
- I dati vengono partizionati mensilmente; le partizioni possono essere eliminate
    

