---
title: Gestire Skype for Business Server 2015 con SCOM Management Pack
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: "Riepilogo: informazioni su come configurare l'infrastruttura di Skype for Business Server 2015 per l'utilizzo con System Center Operations Manager."
ms.openlocfilehash: 7982cd26b512574864e2d53d9c8ef771781348f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816105"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Gestire Skype for Business Server 2015 con SCOM Management Pack
 
**Riepilogo:** Informazioni su come configurare l'infrastruttura di Skype for Business Server 2015 per l'utilizzo con System Center Operations Manager.
  
In un mondo ideale non si verificano problemi con Skype for Business Server 2015. Tuttavia, Skype for Business Server può essere influenzato da fattori esterni, ad esempio arresti anomali di rete e errori hardware. Usando i Management Pack di Skype for Business Server 2015, puoi identificare e risolvere i potenziali problemi in modo proattivo. In questo modo, i Management Pack di Skype for Business Server 2015 estendono le funzionalità di System Center Operations Manager.
  
Queste informazioni sono state scritte in base alla versione 9319,0 del pacchetto di monitoraggio per Skype for Business Server 2015 Communications software.
  
## <a name="configuration-overview"></a>Panoramica della configurazione

 Per configurare l'infrastruttura di Skype for Business Server 2015 per l'utilizzo con System Center Operations Manager, è necessario eseguire tre operazioni:
  
Identificare e [configurare il server di gestione principale](configure-the-primary.md). A questo scopo, è necessario installare System Center Operations Manager 2012 SP1 o R2. 
  
 Identificare e [configurare i computer di Skype for Business Server che verranno monitorati](configure-computers-to-monitor.md). Per monitorare un computer Skype for Business Server tramite System Center Operations Manager, è necessario installare i file dell'agente di System Center Operations Manager e configurare ogni server per fungere da proxy. 
  
 Identificare e [installare e configurare i nodi Watcher](watcher-nodes.md). I nodi Watcher sono computer che eseguono periodicamente transazioni sintetiche di Skype for Business Server, ovvero i cmdlet di Windows PowerShell che verificano i componenti principali di Skype for Business Server, ad esempio la possibilità di accedere al sistema o la possibilità di Exchange Instant i messaggi funzionano come previsto. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Supporto dell'agente e del server di gestione radice di System Center Operations Manager

I Management Pack possono essere usati con System Center Operations Manager 2007 R2 (64 bit) (supportato solo per scopi di migrazione) o System Center Operations Manager 2012 SP1 &amp; r2 (64 bit) o System Center operations manager 2016 (64 bit). La tabella seguente mostra le configurazioni supportate per i Management Pack per Skype for Business Server 2015: 
  
|Configurazione|Supportati?|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sì. Sia nei nodi Skype for Business Server 2015 che nel monitoraggio delle transazioni sintetiche.  <br/> |
|Server raggruppati  <br/> |Non supportato.  <br/> |
|Monitoraggio senza agenti  <br/> |Non supportato.  <br/> |
|Ambiente virtuale  <br/> |Sì.  <br/> |
|Ruoli del server appartenenti a un dominio  <br/> |Tutti i ruoli server interni di Skype for Business Server 2015 devono essere Uniti a un dominio.  <br/> |
|Ruoli server autonomi  <br/> |I server Edge di Skype for Business Server 2015 non devono essere Uniti al dominio.  <br/> |
|Limitazioni della topologia  <br/> |Tutti i ruoli del server in una distribuzione devono essere monitorati dallo stesso gruppo di gestione di Operations Manager.  <br/> |
|Nodo Watcher transazioni sintetiche  <br/> |Il monitoraggio della disponibilità degli scenari con un nodo di Watcher delle transazioni sintetiche è supportato (è necessaria una configurazione aggiuntiva). Non è necessario che i nodi Watcher siano uniti al dominio.  <br/> |
   
La tabella seguente mostra i requisiti di capacità e sistema operativo per un nodo di Watcher delle transazioni sintetiche:
  
|Componente hardware|Requisito minimo|
|:-----|:-----|
|CPU  <br/> |Una delle operazioni seguenti:  <br/> processore a 64 bit, quad-core, 2,33 GHz o superiore  <br/> processore 2-vie a 64 bit, Dual-Core, 2,33 GHz o superiore  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rete  <br/> |1 scheda di rete a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Prerequisiti

Per eseguire un nodo di Watcher delle transazioni sintetiche, è prima necessario installare quanto segue:
  
- Agente di Operations Manager di System Center 
    
-  Microsoft .NET Framework 4,5
    
- File di installazione di Skype for Business Server Core (OcsCore. msi) e Unified Communications Managed API (UCMA) (le versioni devono corrispondere alla versione di WatcherNode. msi di Skype for Business Server)
    
## <a name="files-in-this-monitoring-pack"></a>File in questo pacchetto di monitoraggio

Il pacchetto di monitoraggio per Skype for Business Server 2015 include i file seguenti:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode. msi
    
## <a name="whats-new"></a>Novità

Le caratteristiche seguenti sono nuove per i Management Pack di Skype for Business Server 2015.

- **Modifiche all' [aggiornamento di 2019 settembre](https://www.microsoft.com/en-in/download/details.aspx?id=47364) ** Alcuni avvisi hanno avuto caratteri speciali rimossi. In alcuni casi i caratteri speciali interferiscono con la funzionalità di notifica del canale di comando SCOM.

- **Individuazione automatica per l'accesso client** Le applicazioni client che si iscrivono a Skype for Business Server 2015 spesso scoprono automaticamente il server in cui effettuare l'accesso. Le transazioni sintetiche supportano ora la verifica che l'individuazione automatica sia configurata correttamente.
    
- **Intervalli di esecuzione delle transazioni sintetiche personalizzati** Per semplificare il processo di configurazione dei nodi Watcher, le transazioni sintetiche possono condividere gli account utente. Questo rallenta la frequenza con cui vengono eseguiti i test quando i test vengono serializzati per evitare conflitti. Per impostazione predefinita, le transazioni sintetiche vengono eseguite ogni 15 minuti per garantire che tutti i test abbiano il tempo per l'esecuzione. Gli amministratori che scelgono di usare più utenti o meno test per ogni utente possono ora ridurre anche l'intervallo di esecuzione.
    
- **Transazione sintetica video Interop Services** I clienti che eseguono la migrazione a Skype for Business Server 2015 da altre soluzioni fornitore spesso desiderano continuare a usare i dispositivi di teleconferenza video (VTCs) da questi altri fornitori. Video Interop server è un nuovo ruolo del server di Skype for Business Server 2015 che consente ai clienti di continuare a usare Cisco VTCs nelle sale riunioni connettendosi a Cisco CUCM tramite un trunk SIP video. Questa caratteristica aggiunge anche una transazione sintetica per verificare che il server di interoperabilità video sia alto e possa gestire le connessioni in ingresso su un trunk SIP video.
    
- **Transazione sintetica conferenza di condivisione applicazioni** La convalida dello scenario end-to-end per le conferenze di condivisione delle applicazioni è ora supportata.
    
## <a name="monitoring-scenarios"></a>Scenari di monitoraggio

Il Management Pack di Skype for Business Server 2015 sfrutta una vasta gamma di funzionalità che consentono di rilevare e diagnosticare i problemi. Queste caratteristiche consentono di ottenere una visibilità in tempo reale per l'integrità di un ambiente Skype for Business Server 2015.
  
|Scenario di monitoraggio|Descrizione|
|:-----|:-----|
|Transazioni sintetiche  <br/> | I cmdlet di Windows PowerShell per testare e aiutare a garantire l'elevata disponibilità di scenari come l'accesso, la presenza, la messaggistica istantanea e le conferenze per gli utenti. <br/> Le transazioni sintetiche possono essere eseguite da qualsiasi posizione geografica, anche all'interno dell'organizzazione, al di fuori dell'azienda e nelle filiali.  <br/> Quando una transazione sintetica non riesce, vengono creati i log HTML per determinare l'esatta natura dell'errore. Ciò include la comprensione dell'azione non riuscita, la latenza di ogni azione, la riga di comando usata per eseguire il test e l'errore specifico che si è verificato.  <br/> |
|Avvisi di affidabilità delle chiamate  <br/> |I record dettagli chiamata (CDRs) scritti dai server Skype for Business Server 2015 riflettono se gli utenti sono in grado di connettersi a una chiamata o perché viene terminata una chiamata. Chiama avvisi di affidabilità consente di eseguire una query nel database CDR per produrre avvisi che indicano quando un numero elevato di utenti riscontra problemi di connettività per le chiamate peer-to-peer o per le funzionalità di conferenza di base.  <br/> La copertura dello scenario include chiamate audio, messaggistica istantanea peer-to-peer e altre funzionalità di conferenza.  <br/> |
|Avvisi di qualità multimediale  <br/> |Query di database che esaminano i report di qualità dell'esperienza (QoE) pubblicati dai client Skype for Business Server 2015 alla fine di ogni chiamata. Queste query producono avvisi che individuano scenari in cui gli utenti hanno più probabilità di provare una qualità media compromessa durante le chiamate e le conferenze. I dati sono basati su metriche chiave, ad esempio la latenza e la perdita di pacchetti, che contribuiscono direttamente alla qualità dell'esperienza utente.  <br/> |
|Avvisi di integrità dei componenti  <br/> |I singoli componenti del server generano avvisi tramite log eventi e contatori delle prestazioni per indicare le condizioni di errore che potrebbero influire in modo significativo sugli scenari utente. Questi avvisi indicano una varietà di condizioni, ad esempio i servizi non in uso, le frequenze di errore elevate, la latenza elevata dei messaggi o i problemi di connettività.  <br/> |
|Monitoraggio dell'integrità delle dipendenze  <br/> |Skype for Business Server può non riuscire per diversi motivi esterni. Il Management Pack monitora e raccoglie i dati per le dipendenze esterne critiche che possono indicare problemi gravi. Queste dipendenze includono la disponibilità di Internet Information Services (IIS) e la CPU dei server usati per Skype for Business Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Priorità degli avvisi

Gli avvisi sono classificati nelle categorie seguenti: 
  
 **Avvisi con priorità alta:** Questi avvisi indicano le condizioni che causano interruzioni dei servizi per gruppi di utenti di grandi dimensioni e richiedono un'azione immediata. Le interruzioni rilevate da transazioni sintetiche e servizi offline (ad esempio Skype for Business Server per le conferenze audio/video) si qualificano come avvisi ad alta priorità. Al contrario, un errore del componente in un singolo computer non è un avviso con priorità alta. Skype for Business Server 2015 offre funzionalità predefinite a elevata disponibilità per queste situazioni, ad esempio più server front-end dietro i servizi di bilanciamento del carico.
  
 **Avvisi di priorità media:** Questi avvisi indicano le condizioni che influiscono su un sottoinsieme di utenti o indicano problemi di qualità delle chiamate, ad esempio errori dei componenti, latenza nello stabilimento di chiamata o una qualità audio inferiore nelle chiamate. Gli avvisi in questa categoria sono con stato, ovvero la natura delle modifiche agli avvisi in base allo stato della connessione di rete. Ad esempio, se i tempi di creazione delle chiamate indicano la latenza, ma ritornano a una soglia normale, questo avviso di priorità media verrebbe risolto automaticamente in System Center Operations Manager e gli amministratori non avrebbero bisogno di intervenire. Gli avvisi che non possono essere risolti automaticamente sono in genere indirizzati dagli amministratori nello stesso giorno lavorativo.
  
 **Altri avvisi:** Questi avvisi vengono generati da componenti che possono influire su un utente o un sottoinsieme specifico di utenti. Ad esempio, un avviso tipico consiste nel fatto che il servizio Rubrica non può analizzare la voce Active Directory® Domain Services (AD DS) per l'utente: testuser@contoso.com. Gli amministratori possono affrontare questi avvisi ogni volta che hanno tempo a disposizione.
  
### <a name="synthetic-transactions"></a>Transazioni sintetiche

I Management Pack di Skype for Business Server 2015 offrono una maggiore copertura per gli avvisi tramite transazioni sintetiche. Le transazioni sintetiche sono cmdlet di Windows PowerShell integrati nel Management Pack di Operations Manager per testare gli scenari utente end-to-end. Quando si designa un server per l'esecuzione di transazioni sintetiche, questi cmdlet vengono attivati periodicamente dal Management Pack. Gli errori derivanti da una transazione sintetica generano un avviso con stato. Ecco le transazioni sintetiche supportate per Skype for Business Server 2015:
  


|Transazioni sintetiche supportate per la registrazione, la presenza e i contatti|||
|:-----|:-----|:-----|
|1  <br/> |Registrazione (accesso utente)  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|2  <br/> |Servizio Rubrica (download file)  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|3  <br/> |Query Web Rubrica  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|4  <br/> |Icone di presenza  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|5  <br/> |Archivio contatti unificato  <br/> |Disponibile Lync Server 2013 e oltre  <br/> |
||||   

|Transazioni sintetiche supportate per i servizi peer-to-peer|||
|:-----|:-----|:-----|
|6  <br/> |Messaggistica istantanea peer-to-peer  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|7  <br/> |Video audio peer-to-peer  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|8  <br/> |MCX messaggistica istantanea peer-to-peer (mobile)  <br/> |Disponibile nella versione di 2011 di settembre di Lync Server 2010 per Skype for business 2015  <br/> |
 
> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.


|Transazioni sintetiche supportate per i servizi di conferenza e la chat persistente|||
|:-----|:-----|:-----|
|9  <br/> |Conferenze audio e video  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|10  <br/> |Conferenza dati  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|11  <br/> |Conferenza di messaggistica istantanea  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|12  <br/> | Chat persistente <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|13  <br/> |Icona di avvio di join (riunioni pianificate)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|14  <br/> |Conferenza telefonica con accesso esterno  <br/> |Novità di Skype for Business Server 2015  <br/> |
|15  <br/> |Conferenza di condivisione applicazioni  <br/> |Novità di Skype for Business Server 2015  <br/> |
|16  <br/> |Conferenza UCWA (Web Meeting join)  <br/> |Novità di Skype for Business Server 2015  <br/> |
||||

|Transazioni sintetiche supportate per le dipendenze di rete e partner|||
|:-----|:-----|:-----|
|17  <br/> |Connettività AV Edge  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|18  <br/> |Connettività di messaggistica unificata di Exchange (Voicemail) per AV Edge  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|19  <br/> |Chiamata peer-to-peer PSTN  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|20  <br/> |Messaggistica istantanea XMPP (Federazione)  <br/> |Disponibile in Lync Server 2013 e Skype for business 2015  <br/> |
|21  <br/> |Server di interoperabilità video  <br/> |Novità di Skype for Business Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Come viene arrotolato l'integrità

La tabella seguente Mostra gli Stati di integrità degli oggetti il pacchetto di monitoraggio di Skype for Business Server.
  
|Oggetto Management Pack|Descrizione|
|:-----|:-----|
|Distribuzione di Skype for Business Server  <br/> |Rappresenta la distribuzione di Skype for Business Server 2015 nell'organizzazione.  <br/> |
|Sito di Skype for Business Server  <br/> |Rappresenta diverse posizioni geografiche in cui vengono distribuiti i servizi.  <br/> |
|Pool di Skype for Business Server  <br/> |Un pool (all'interno di un sito) che fornisce servizi di comunicazione, ad esempio messaggistica istantanea e conferenze, agli utenti. Applicabile ai pool di front-end, ai pool di bordi e ai pool di Director, anche se è presente un solo computer in un pool specifico.  <br/> |
|Ruolo di Skype for Business Server  <br/> |Un ruolo del server che ospita il servizio Skype for Business Server.  <br/> |
|Servizio Skype for Business Server  <br/> |Rappresenta una funzionalità distribuita in un computer specifico, ad esempio il servizio utente in fp01.contoso.com.  <br/> |
|Componente di Skype for Business Server  <br/> |Un componente del servizio, ad esempio il componente di download della Rubrica, fa parte del servizio Web.  <br/> |
|Monitoraggio pool di Skype for Business Server  <br/> |Un'istanza di transazioni sintetiche in uso in un pool.  <br/> |
|Skype for Business Server registrar Watcher  <br/> |Un'istanza di transazioni sintetiche eseguite in un pool di registrar.  <br/> |
|Watcher per pool di servizi utente di Skype for Business Server  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool di servizi utente.  <br/> |
|Watcher pool vocale di Skype for Business Server  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool di voci.  <br/> |
|Monitoraggio della porta di Skype for Business Server  <br/> |Un'istanza di una porta controlla l'uso di un pool.  <br/> |
|Watcher URL semplice  <br/> |Esegue il sondaggio HTTPS degli URL semplici configurati in una distribuzione.  <br/> |
   
![SCOM cumulativo](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un pool di Skype for Business Server può contenere più singoli sistemi Skype for Business Server (con più di un ruolo di Skype for Business Server, il servizio Skype for Business Server e il componente Skype for Business Server). Di conseguenza, l'errore di un singolo server o componente è meno importante per l'integrità complessiva del pool di Skype for Business Server, perché gli altri server dello stesso pool possono concedere il servizio di applicazione al client. L'integrità verrà riattivata a livello di percentuale nel pool di Skype for Business Server. 
  
Skype for Business Server Pool Watcher esegue transazioni sintetiche su un pool di Skype for Business Server. L'errore consecutivo di una o più transazioni sintetiche (un processo noto come intervallo di polling consecutivo) risulterà lo stato di integrità critico per il livello del pool (peggiore di qualsiasi transazione sintetica), come illustrato nel diagramma seguente. 
  
![SCOM rollup di polling consecutivo](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Procedura consigliata: creare un Management Pack per le personalizzazioni

Per impostazione predefinita, Operations Manager salva tutte le personalizzazioni, ad esempio le sostituzioni per il Management Pack predefinito. Come procedura consigliata, è consigliabile creare un Management Pack separato per ogni pacchetto di gestione sealed che si vuole personalizzare. 
  
Quando si crea un Management Pack per l'archiviazione di impostazioni personalizzate per un Management Pack sealed, è consigliabile assegnare un nome al nuovo Management Pack in modo appropriato, ad esempio "personalizzazioni di Skype for Business Server 2015". 
  
La creazione di un nuovo Management Pack per l'archiviazione delle personalizzazioni di ogni pacchetto di gestione sealed semplifica l'esportazione delle personalizzazioni da un ambiente di test a un ambiente di produzione. In questo modo è anche più facile eliminare un Management Pack, perché è necessario eliminare eventuali dipendenze prima di poter eliminare un Management Pack. Se le personalizzazioni per tutti i Management Pack vengono salvate nel Management Pack predefinito ed è necessario eliminare un singolo Management Pack, è prima di tutto necessario eliminare il Management Pack predefinito, che elimina anche le personalizzazioni in altri Management Pack. 
  
## <a name="links"></a>Collegamenti

I collegamenti seguenti consentono di connettere le informazioni sulle attività comuni associate ai pacchetti di monitoraggio di System Center 2012:
  
- [Ciclo di vita del Management Pack](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Come importare un Management Pack in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Come eseguire l'override di una regola o di un monitor](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Come creare un account RunAs in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Gestione di account e profili in esecuzione](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Come esportare un Management Pack di Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Come rimuovere un Management Pack di Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
I collegamenti seguenti consentono di connettere le informazioni sulle attività comuni associate ai pacchetti di monitoraggio di System Center 2007:
  
- [Amministrazione del ciclo di vita del Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Come importare un Management Pack in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Come monitorare l'uso delle sostituzioni](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Come creare un account RunAs in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Come modificare un profilo RunAs esistente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Come esportare le personalizzazioni di Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Come rimuovere un Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Per domande su Operations Manager e Monitoring Pack, vedere il [Forum della community di System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Una risorsa utile è il Blog di [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) , che contiene i post "per esempio" per specifici pacchetti di monitoraggio.
  
Per altre informazioni su Operations Manager, vedere i blog seguenti: 
  
- [Blog del team di Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog di OpsMgr di Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Considerazioni su OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog di Raffaello Burri](https://rburri.wordpress.com/)
    
- [Spazio di gestione di BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Tutte le informazioni e il contenuto dei siti non Microsoft sono forniti dal proprietario o dagli utenti del sito Web. Microsoft non rilascia garanzie, espresse, implicite o statutarie, per quanto riguarda le informazioni in questo sito Web. 
  
## <a name="see-also"></a>Vedere anche

[Strumenti di gestione di Skype for Business Server 2015](../../management-tools/management-tools.md)
