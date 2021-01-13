---
title: Gestire Skype for Business Server 2019 utilizzando SCOM Management Pack
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: "Riepilogo: informazioni su come configurare l'infrastruttura di Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager."
ms.openlocfilehash: 21493a0d49281405b4d9d25d732f9c80c6c9dff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812776"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Gestire Skype for Business Server 2019 utilizzando SCOM Management Pack
 
**Riepilogo:** Informazioni su come configurare l'infrastruttura di Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.
  
In un ambiente ideale, non si riscontrano mai problemi con Skype for Business Server 2019. Tuttavia, Skype for Business Server può essere influenzato da fattori esterni, ad esempio incidenti di rete e guasti hardware. Utilizzando i Management Pack di Skype for Business Server 2019, è possibile identificare e risolvere i possibili problemi in modo proattivo. In questo modo, i Management Pack di Skype for Business Server 2019 estese le funzionalità di System Center Operations Manager.
  
Queste informazioni sono state scritte in base alla versione 9319,0 del software di comunicazione del Monitoring Pack per Skype for Business Server 2019.
  
## <a name="configuration-overview"></a>Panoramica della configurazione

 Per configurare l'infrastruttura di Skype for Business Server 2019 in modo che funzioni con System Center Operations Manager, è necessario eseguire tre operazioni:
  
Identificare e [configurare il server di gestione primario](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md). A tale scopo, è necessario installare System Center Operations Manager 2012 SP1 o R2. 
  
 Identificare e [configurare i computer Skype for Business Server che verranno monitorati](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md). Per monitorare un computer con Skype for Business Server tramite System Center Operations Manager, è necessario installare i file dell'agente System Center Operations Manager e configurare ogni server affinché funga da proxy. 
  
 Identificare e [installare e configurare i nodi Watcher](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md). I nodi Watcher sono computer che eseguono periodicamente transazioni sintetiche di Skype for Business Server, ovvero cmdlet di Windows PowerShell che verificano che i componenti principali di Skype for Business Server, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei, funzionino come previsto. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager Root Management Server and Agent support

I Management Pack possono essere utilizzati con System Center Operations Manager 2007 R2 (64 bit) (supportato solo a scopo di migrazione) o System Center Operations Manager 2012 SP1 &amp; R2 (64 bit). Nella tabella seguente sono riportate le configurazioni supportate per i Management Pack per Skype for Business Server 2019: 
  
|**Configurazione**|**Supportato?**|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sì. Sia su Skype for Business Server 2019 server che sui nodi di monitoraggio delle transazioni sintetiche.  <br/> |
|Server in cluster  <br/> |Non supportate.  <br/> |
|Monitoraggio senza agente  <br/> |Non supportate.  <br/> |
|Ambiente virtuale  <br/> |Sì.  <br/> |
|Ruoli del server aggiunti al dominio  <br/> |Tutti i ruoli del server interni di Skype for Business Server 2019 devono essere aggiunti a un dominio.  <br/> |
|Ruoli del server autonomo  <br/> |I server Edge di Skype for Business Server 2019 non sono tenuti a essere aggiunti al dominio.  <br/> |
|Limitazioni relative alla topologia  <br/> |Tutti i ruoli del server in una distribuzione devono essere monitorati dallo stesso gruppo di gestione di Operations Manager.  <br/> |
|Nodo Watcher transazioni sintetiche  <br/> |Monitoraggio della disponibilità degli scenari con un nodo di Watcher per le transazioni sintetiche è supportato (è necessaria una configurazione aggiuntiva). Non è necessario che i nodi Watcher siano uniti a un dominio.  <br/> |
   
Nella tabella seguente vengono illustrati i requisiti di capacità e del sistema operativo per un nodo di Watcher delle transazioni sintetiche:
  
|**Componente hardware**|**Requisiti minimi**|
|:-----|:-----|
|CPU  <br/> |Una delle opzioni seguenti:  <br/> processore a 64 bit, quad-core, 2,33 GHz o superiore  <br/> processore 2-Way a 64 bit, Dual Core, 2,33 GHz o superiore  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rete  <br/> |1 scheda di rete a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Prerequisiti

Per eseguire un nodo di monitoraggio delle transazioni sintetico, è innanzitutto necessario installare quanto segue:
  
- Agente System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server Core file di installazione (OcsCore.msi) e Unified Communications Managed API (UCMA) (le versioni devono corrispondere alla versione di Skype for Business Server WatcherNode.msi)
    
## <a name="files-in-this-monitoring-pack"></a>File in questo Monitoring Pack

Il Monitoring Pack per Skype for Business Server 2019 include i seguenti file:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novità

Le seguenti funzionalità sono nuove per i Management Pack di Skype for Business Server 2019.

- **Modifiche apportate all' [aggiornamento del 2019 settembre](https://www.microsoft.com/download/details.aspx?id=57511)** Alcuni avvisi hanno avuto caratteri speciali rimossi. In alcuni casi, i caratteri speciali interferiscono con la funzionalità di notifica del canale di comando di SCOM.

- **Individuazione automatica per l'accesso dei client** Le applicazioni client che dispongono dell'accesso a Skype for Business Server 2019 spesso scoprono automaticamente il server per l'accesso. Le transazioni sintetiche ora supportano la verifica che l'individuazione automatica sia configurata correttamente.
    
- **Intervalli di esecuzione delle transazioni sintetiche personalizzati** Per semplificare il processo di configurazione dei nodi Watcher, le transazioni sintetiche possono condividere gli account utente. Questo rallenta la frequenza con cui vengono eseguiti i test quando i test vengono serializzati per evitare conflitti. Per impostazione predefinita, le transazioni sintetiche vengono eseguite ogni 15 minuti per garantire l'esecuzione di tutti i test. Gli amministratori che scelgono di usare più utenti o meno test per utente possono ora ridurre anche l'intervallo di esecuzione.
    
- **Transazioni sintetiche di servizi di interoperabilità video** I clienti che eseguono la migrazione a Skype for Business Server 2019 da altre soluzioni fornitore spesso desiderano continuare a utilizzare i dispositivi di teleconferenza video (VTCs) da questi altri fornitori. Video Interop server è un nuovo ruolo del server di Skype for Business Server 2019 che consente ai clienti di continuare a utilizzare Cisco VTCs nelle sale conferenze collegandosi a Cisco un CUCM tramite un trunk SIP video. Questa funzionalità aggiunge anche una transazione sintetica che consente di verificare che il servizio di interoperabilità video sia attivo e che sia in grado di gestire le connessioni in ingresso su un trunk SIP video.
    
- **Transazioni sintetiche delle conferenze di condivisione applicazioni** La convalida dello scenario end-to-end per le conferenze di condivisione applicazioni è ora supportata.
    
## <a name="monitoring-scenarios"></a>Scenari di monitoraggio

Il Management Pack di Skype for Business Server 2019 sfrutta una serie di funzionalità che consentono di individuare e diagnosticare i problemi. Queste funzionalità offrono una visibilità in tempo reale per l'integrità di un ambiente di Skype for Business Server 2019.
  
|**Scenario di monitoraggio**|**Descrizione**|
|:-----|:-----|
|Transazioni sintetiche  <br/> | Cmdlet di Windows PowerShell per testare e contribuire a garantire la disponibilità elevata di scenari quali accesso, presenza, messaggistica istantanea e conferenza per gli utenti. <br/> Le transazioni sintetiche possono essere eseguite da qualsiasi posizione geografica, anche all'interno dell'organizzazione, al di fuori dell'azienda e nelle succursali.  <br/> Quando una transazione sintetica ha esito negativo, vengono creati i log HTML che consentono di determinare l'esatta natura dell'errore. Ciò include la comprensione dell'azione non riuscita, la latenza di ogni azione, la riga di comando utilizzata per eseguire il test e l'errore specifico che si è verificato.  <br/> |
|Avvisi di affidabilità delle chiamate  <br/> |Call Detail Records (CDRs) scritto da Skype for Business Server 2019 Servers riflette se gli utenti sono in grado di connettersi a una chiamata o il motivo per cui una chiamata è terminata. Avvisi di affidabilità delle chiamate eseguire una query sul database di registrazione dettagli chiamata per produrre avvisi che indicano quando un numero elevato di utenti verifica problemi di connettività per le chiamate peer-to-peer o le funzionalità di conferenza di base.  <br/> La copertura dello scenario include chiamate audio, messaggistica istantanea peer-to-peer (IM) e altre funzionalità di conferenza.  <br/> |
|Avvisi sulla qualità multimediale  <br/> |Query di database che esaminano i report di qualità di esperienza (QoE) pubblicati dai client Skype for Business Server 2019 alla fine di ogni chiamata. Queste query producono avvisi che individuano gli scenari in cui gli utenti hanno più probabilità di sperimentare la qualità media compromessa durante le chiamate e le conferenze. I dati sono basati su metriche chiave, ad esempio la latenza e la perdita di pacchetti, che contribuiscono direttamente alla qualità dell'esperienza utente.  <br/> |
|Avvisi di integrità del componente  <br/> |I singoli componenti server generano avvisi tramite i registri eventi e i contatori delle prestazioni per indicare condizioni di errore che possono influire in modo significativo sugli scenari utente. Questi avvisi indicano una serie di condizioni, ad esempio i servizi non in esecuzione, la percentuale di errori elevata, la latenza elevata dei messaggi o i problemi di connettività.  <br/> |
|Monitoraggio dell'integrità delle dipendenze  <br/> |Skype for Business Server può avere esito negativo per diversi motivi esterni. Il Management Pack monitora e raccoglie i dati per le dipendenze esterne critiche che possono indicare gravi problemi. Queste dipendenze includono la disponibilità di Internet Information Services (IIS) e la CPU dei server utilizzati per Skype for Business Server.  <br/> |
   
### <a name="alert-prioritization"></a>Priorità avvisi

Gli avvisi sono classificati nelle categorie seguenti: 
  
 **Avvisi con priorità alta:** Questi avvisi indicano le condizioni che causano interruzioni del servizio per gruppi di utenti di grandi dimensioni e richiedono un'azione immediata. Le interruzioni rilevate dalle transazioni sintetiche e dai servizi offline (come Skype for Business Server audio/video Conferencing) sono qualificate come avvisi con priorità alta. Al contrario, un errore del componente su un singolo computer non è un avviso con priorità alta. Skype for Business Server 2019 dispone di funzionalità di disponibilità elevata incorporate per queste situazioni, ad esempio più Front End Server dietro i servizi di bilanciamento del carico.
  
 **Avvisi di priorità media:** Questi avvisi indicano le condizioni che influiscono su un sottoinsieme di utenti o indicano problemi di qualità delle chiamate, ad esempio errori dei componenti, latenza nello stabilimento di chiamata o bassa qualità audio nelle chiamate. Gli avvisi in questa categoria sono di tipo stato (ovvero, la natura delle modifiche all'avviso in base allo stato della connessione di rete). Ad esempio, se i tempi di creazione di chiamata indicano latenza, ma quindi torna a una soglia normale, questo avviso di priorità media verrebbe risolto automaticamente in System Center Operations Manager e gli amministratori non avrebbero bisogno di intervenire. Gli avvisi che non possono essere risolti automaticamente vengono in genere risolti dagli amministratori nello stesso giorno lavorativo.
  
 **Altri avvisi:** Questi avvisi vengono generati da componenti che potrebbero influire su un utente o un sottoinsieme specifico di utenti. Ad esempio, un avviso tipico potrebbe essere che il servizio Rubrica non è stato in grado di analizzare la voce Active Directory® Domain Services (AD DS) per l'utente: testuser@contoso.com. Gli amministratori possono risolvere questi avvisi ogni volta che dispongono di tempo.
  
### <a name="synthetic-transactions"></a>Transazioni sintetiche

I Management Pack di Skype for Business Server 2019 offrono una maggiore copertura per gli avvisi tramite transazioni sintetiche. Le transazioni sintetiche sono cmdlet di Windows PowerShell integrati nel Management Pack di Operations Manager per testare gli scenari utente end-to-end. Quando si designa un server per l'esecuzione di transazioni sintetiche, questi cmdlet vengono attivati periodicamente dal Management Pack. Gli errori risultanti da una transazione sintetica generano un avviso con stato. Di seguito vengono richiamate le transazioni sintetiche supportate per Skype for Business Server 2019:
  
**Transazioni sintetiche supportate per la registrazione, la presenza e i contatti**

||||
|:-----|:-----|:-----|
|1   <br/> |Registrazione (accesso utente)  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|2   <br/> |Servizio Rubrica (download di file)  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|3   <br/> |Address Book Web Query  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|4   <br/> |Presenza  <br/> |Disponibile Lync Server 2010 e oltre  <br/> |
|5   <br/> |Archivio unico dei contatti  <br/> |Disponibile Lync Server 2013 e oltre  <br/> |
   
**Transazioni sintetiche supportate per i servizi peer-to-peer**

||||
|:-----|:-----|:-----|
|6   <br/> |Messaggistica istantanea peer-to-peer  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|7   <br/> |Video audio peer-to-peer  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|8   <br/> |Messaggi istantanei peer-to-peer di MCX (dispositivi mobili)  <br/> |Disponibile nella versione di settembre 2011 di Lync Server 2010 per Skype for business 2019  <br/> |
 
> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
**Transazioni sintetiche supportate per le conferenze e la chat persistente**

||||
|:-----|:-----|:-----|
|9   <br/> |Conferenze audio e video  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|10   <br/> |Servizi di conferenza dati  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|11   <br/> |Servizi di conferenza di messaggistica istantanea  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|12   <br/> | Chat persistente <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|13   <br/> |Join Launcher (riunioni pianificate)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|14   <br/> |Chiamata in conferenza  <br/> |Disponibile in Skype for Business Server 2015 e oltre <br/> |
|15   <br/> |Conferenze di condivisione applicazioni  <br/> |Disponibile in Skype for Business Server 2015 e oltre <br/> |
|16   <br/> |Conferenza di UCWA (join di riunioni Web)  <br/> |Disponibile in Skype for Business Server 2015 e oltre <br/> |
   
**Transazioni sintetiche supportate per le dipendenze di rete e partner**

||||
|:-----|:-----|:-----|
|17   <br/> |Connettività AV Edge  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|18   <br/> |Connettività di messaggistica unificata di Exchange (Voicemail) di AV Edge  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|19  <br/> |Chiamata peer-to-peer PSTN  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|20  <br/> |Messaggistica istantanea XMPP (Federazione)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
| 21  <br/> |Server di interoperabilità video  <br/> |Disponibile in Skype for Business Server 2015 e oltre  <br/> |
   
## <a name="how-health-rolls-up"></a>Come viene arrotolato l'integrità

Nella tabella seguente vengono illustrati gli Stati di integrità degli oggetti Skype for Business Server Monitoring Pack.
  
|**Oggetto Management Pack**|**Descrizione**|
|:-----|:-----|
|Distribuzione di Skype for Business Server  <br/> |Rappresenta la distribuzione di Skype for Business Server 2019 nell'organizzazione.  <br/> |
|Sito di Skype for Business Server  <br/> |Rappresenta diverse posizioni geografiche in cui vengono distribuiti i servizi.  <br/> |
|Pool di Skype for Business Server  <br/> |Un pool (all'interno di un sito) che fornisce servizi di comunicazione, quali messaggistica istantanea e conferenze, agli utenti. Applicabile ai pool Front End, ai pool di server perimetrali e ai pool di Director, anche se è presente un solo computer in un pool specifico.  <br/> |
|Ruolo del server Skype for business  <br/> |Un ruolo del server che ospita il servizio Skype for Business Server.  <br/> |
|Servizio Skype for Business Server  <br/> |Rappresenta una funzionalità distribuita su un computer specifico, ad esempio il servizio utente in fp01.contoso.com.  <br/> |
|Componente di Skype for Business Server  <br/> |Componente del servizio (ad esempio, il componente di download della Rubrica è una parte del servizio Web).  <br/> |
|Watcher del pool di Skype for Business Server  <br/> |Un'istanza di transazioni sintetiche in esecuzione in un pool.  <br/> |
|Monitoraggio della registrazione di Skype for Business Server  <br/> |Un'istanza di transazioni sintetiche che vengono eseguite su un pool di registrazione.  <br/> |
|Watcher del pool di servizi utente di Skype for Business Server  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool di servizi utente.  <br/> |
|Watcher del pool vocale di Skype for Business Server  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool di voci.  <br/> |
|Monitoraggio delle porte di Skype for Business Server  <br/> |Un'istanza di porta viene controllata in esecuzione su un pool.  <br/> |
|Watcher URL semplice  <br/> |Esegue il sondaggio HTTPS degli URL semplici configurati in una distribuzione.  <br/> |
   
![SCOM rollup](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un pool di Skype for Business Server può contenere più singoli sistemi Skype for Business Server (con più ruoli del server Skype for business, il servizio Skype for Business Server e il componente Skype for Business Server). Pertanto, l'errore di un singolo server o componente è meno critico rispetto all'integrità generale del pool di Skype for Business Server, in quanto gli altri server nello stesso pool possono fornire il servizio dell'applicazione al client. L'integrità si riavvolgerà su un livello di percentuale per il pool di Skype for Business Server. 
  
Il monitoraggio pool di Skype for Business Server esegue transazioni sintetiche su un pool di Skype for Business Server. Un errore consecutivo di una o più transazioni sintetiche, ovvero un processo noto come intervallo di polling consecutivo, eseguirà lo stato di integrità critico al livello del pool (la peggiore di qualsiasi transazione sintetica), come illustrato nel diagramma seguente. 
  
![Polling consecutivo di SCOM rollup](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Procedura consigliata: creare un Management Pack per le personalizzazioni

Per impostazione predefinita, Operations Manager salva tutte le personalizzazioni, ad esempio le sostituzioni del Management Pack predefinito. Come procedura consigliata, è consigliabile creare un Management Pack separato per ogni pacchetto di gestione sealed che si desidera personalizzare. 
  
Quando si crea un Management Pack per l'archiviazione delle impostazioni personalizzate per un pacchetto di gestione sealed, è consigliabile nominare il nuovo Management Pack in modo appropriato, ad esempio "personalizzazioni di Skype for Business Server 2019".
  
La creazione di un nuovo Management Pack per l'archiviazione delle personalizzazioni di ogni pacchetto di gestione sealed semplifica l'esportazione delle personalizzazioni da un ambiente di testing a un ambiente di produzione. In questo modo è più facile eliminare un Management Pack, perché è necessario eliminare eventuali dipendenze prima di poter eliminare un Management Pack. Se le personalizzazioni per tutti i Management Pack vengono salvate nel Management Pack predefinito ed è necessario eliminare un singolo Management Pack, è necessario innanzitutto eliminare il Management Pack predefinito, che elimina le personalizzazioni anche ad altri Management Pack. 
  
## <a name="links"></a>Collegamenti

I collegamenti seguenti consentono di connettersi alle informazioni sulle attività comuni associate a System Center 2012 Monitoring Pack:
  
- [Ciclo di vita del Management Pack](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Informazioni su come importare un Management Pack in Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Come eseguire l'override di una regola o di un monitor](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Come creare un account RunAs in Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Gestione dei profili e degli account RunAs](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Come esportare un Management Pack di Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Come rimuovere un Management Pack di Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
I collegamenti seguenti consentono di connettersi alle informazioni sulle attività comuni associate a System Center 2007 Monitoring Pack:
  
- [Amministrazione del ciclo di vita del Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Informazioni su come importare un Management Pack in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Come monitorare l'utilizzo di sostituzioni](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Come creare un account RunAs in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Come modificare un profilo di esecuzione come esistente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Informazioni su come esportare le personalizzazioni del Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Come rimuovere un Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Per domande su Operations Manager e sui Monitoring Pack, vedere [System Center Operations Manager Community Forum](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Una risorsa utile è il Blog di [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) , che contiene "per esempio" post per specifici Monitoring Pack.
  
Per ulteriori informazioni su Operations Manager, vedere i blog seguenti: 
  
- [Blog del team di Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog OpsMgr di Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Pensieri su OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog di Raphael Burri](https://rburri.wordpress.com/)
    
- [Spazio di gestione di BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Tutte le informazioni e il contenuto dei siti non Microsoft vengono forniti dal proprietario o dagli utenti del sito Web. Microsoft non fornisce alcuna garanzia, espressa, implicita o statutaria, in merito alle informazioni su questo sito Web. 
  
## <a name="see-also"></a>Vedere anche

[Strumenti di gestione di Skype for Business Server 2019](../management-tools-2019.md)
