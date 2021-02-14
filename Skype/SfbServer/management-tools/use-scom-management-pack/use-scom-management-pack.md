---
title: Gestire Skype for Business Server 2015 con SCOM Management Pack
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: cfb48338d4022c1de7c5944f66d72e58dd8b403d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814846"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Gestire Skype for Business Server 2015 con SCOM Management Pack
 
**Riepilogo:** Informazioni su come configurare l'infrastruttura di Skype for Business Server 2015 per l'utilizzo con System Center Operations Manager.
  
In un mondo ideale, non si verificano mai problemi con Skype for Business Server 2015. Tuttavia, Skype for Business Server può essere influenzato da fattori esterni, ad esempio arresti anomali della rete ed errori hardware. Utilizzando i Management Pack di Skype for Business Server 2015, è possibile identificare e risolvere potenziali problemi in modo proattivo. In questo modo, i Management Pack di Skype for Business Server 2015 estendono le funzionalità di System Center Operations Manager.
  
Queste informazioni sono state scritte in base alla versione 9319.0 del software di comunicazione Monitoring Pack per Skype for Business Server 2015.
  
## <a name="configuration-overview"></a>Panoramica della configurazione

 Per configurare l'infrastruttura di Skype for Business Server 2015 per l'utilizzo con System Center Operations Manager, è necessario eseguire tre operazioni:
  
Identificare e [configurare il server di gestione principale.](configure-the-primary.md) A tale scopo, è necessario installare System Center Operations Manager 2012 SP1 o R2. 
  
 Identificare e [configurare i computer Skype for Business Server che verranno monitorati.](configure-computers-to-monitor.md) Per monitorare un computer Skype for Business Server utilizzando System Center Operations Manager, è necessario installare i file agente di System Center Operations Manager e configurare ogni server per agire come proxy. 
  
 Identificare e [installare e configurare i nodi Watcher.](watcher-nodes.md) I nodi Watcher sono computer che eseguono periodicamente transazioni sintetiche di Skype for Business Server, ovvero cmdlet di Windows PowerShell che verificano che i principali componenti di Skype for Business Server, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei, funzionino come previsto. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Supporto degli agenti e del server di gestione radice di System Center Operations Manager

I Management Pack possono essere utilizzati con System Center Operations Manager 2007 R2 (64 bit) (supportato solo a scopo di migrazione) o System Center Operations Manager 2012 SP1 &amp; R2 (64 bit) o System Center Operations Manager 2016 (64 bit). La tabella seguente mostra le configurazioni supportate per i Management Pack per Skype for Business Server 2015: 
  
|Configurazione|Supportato?|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sì. Sia nel server Skype for Business Server 2015 che nei nodi Synthetic Transaction Watcher.  <br/> |
|Server in cluster  <br/> |Non supportate.  <br/> |
|Monitoraggio senza agenti  <br/> |Non supportate.  <br/> |
|Ambiente virtuale  <br/> |Sì.  <br/> |
|Ruoli del server aggiunti a un dominio  <br/> |Tutti i ruoli server interni di Skype for Business Server 2015 devono essere aggiunti a un dominio.  <br/> |
|Ruoli del server autonomo  <br/> |I server perimetrali di Skype for Business Server 2015 non devono essere aggiunti a un dominio.  <br/> |
|Limitazioni della topologia  <br/> |Tutti i ruoli del server in una distribuzione devono essere monitorati dallo stesso gruppo di gestione di Operations Manager.  <br/> |
|Nodo Watcher delle transazioni sintetiche  <br/> |Il monitoraggio della disponibilità degli scenari con un nodo Watcher delle transazioni sintetiche è supportato (è necessaria una configurazione aggiuntiva). I nodi Watcher non devono essere aggiunti a un dominio.  <br/> |
   
Nella tabella seguente vengono illustrati i requisiti di capacità e sistema operativo per un nodo Watcher delle transazioni sintetiche:
  
|Componente hardware|Requisito minimo|
|:-----|:-----|
|CPU  <br/> |Una delle opzioni seguenti:  <br/> Processore a 64 bit, quad core, 2,33 GHz o superiore  <br/> Processore 2d a 64 bit, dual core, 2,33 GHz o superiore  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rete  <br/> |1 scheda di rete a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Prerequisiti

Per eseguire un nodo Synthetic Transaction Watcher, è necessario innanzitutto installare quanto segue:
  
- Agente System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- File di installazione principali di Skype for Business Server (OcsCore.msi) e UCMA (Unified Communications Managed API) (le versioni devono corrispondere alla versione WatcherNode.msi Skype for Business Server)
    
## <a name="files-in-this-monitoring-pack"></a>File in questo Monitoring Pack

Il Monitoring Pack per Skype for Business Server 2015 include i file seguenti:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novità

Le seguenti funzionalità sono una novità dei Management Pack di Skype for Business Server 2015.

- **Modifiche apportate [all'aggiornamento di settembre 2019](https://www.microsoft.com/en-in/download/details.aspx?id=47364)** Alcuni avvisi hanno rimosso caratteri speciali. In alcuni casi i caratteri speciali interferiscono con la funzionalità di notifica del canale di comando SCOM.

- **Individuazione automatica per l'accesso client** Le applicazioni client che a tale accesso a Skype for Business Server 2015 spesso individuano automaticamente il server a cui accedere. Le transazioni sintetiche ora supportano la verifica della corretta configurazione dell'individuazione automatica.
    
- **Intervalli di esecuzione delle transazioni sintetiche personalizzati** Per semplificare il processo di configurazione dei nodi Watcher, le transazioni sintetiche possono condividere gli account utente. In questo modo si rallenta la frequenza di esecuzione dei test durante la serializzazione dei test per evitare conflitti. Per impostazione predefinita, le transazioni sintetiche vengono eseguite ogni 15 minuti per garantire che tutti i test siano in tempo per l'esecuzione. Gli amministratori che scelgono di utilizzare più utenti o meno test per utente ora possono ridurre anche l'intervallo di esecuzione.
    
- **Transazione sintetica video Interop Services** I clienti che eseguono la migrazione a Skype for Business Server 2015 da soluzioni di altri fornitori spesso desiderano continuare a usare i dispositivi di teleconferenza video di questi altri fornitori. Video Interop Server è un nuovo ruolo del server Skype for Business Server 2015 che consente ai clienti di continuare a usare i VTC Cisco nelle proprie sale riunioni connettendosi a Cisco CUCM tramite un trunk SIP video. Questa funzionalità aggiunge inoltre una transazione sintetica per verificare che Video Interop Server sia in funzione e sia in grado di gestire le connessioni in ingresso su un trunk SIP video.
    
- **Transazione sintetica per conferenze di condivisione applicazioni** La convalida dello scenario end-to-end per le conferenze di condivisione applicazioni è ora supportata.
    
## <a name="monitoring-scenarios"></a>Scenari di monitoraggio

Skype for Business Server 2015 Management Pack sfrutta un'ampia gamma di funzionalità che consentono di rilevare e diagnosticare i problemi. Queste funzionalità offrono visibilità in tempo reale sull'integrità di un ambiente Skype for Business Server 2015.
  
|Scenario di monitoraggio|Descrizione|
|:-----|:-----|
|Transazioni sintetiche  <br/> | Windows PowerShell cmdlet per testare e garantire la disponibilità elevata di scenari come l'accesso, la presenza, la messaggistica istantanea e le conferenze per gli utenti. <br/> Le transazioni sintetiche possono essere eseguite da qualsiasi posizione geografica, anche all'interno dell'azienda, all'esterno dell'azienda e nelle succursali.  <br/> Quando si verifica un errore in una transazione sintetica, vengono creati log HTML per determinare l'esatta natura dell'errore. Ciò include la comprensione dell'azione non riuscita, della latenza di ogni azione, della riga di comando utilizzata per eseguire il test e dell'errore specifico che si è verificato.  <br/> |
|Avvisi di affidabilità delle chiamate  <br/> |Le registrazioni dettagli chiamata (CDR) scritte dai server Skype for Business Server 2015 riflettono se gli utenti sono in grado di connettersi a una chiamata o perché una chiamata viene terminata. Gli avvisi di affidabilità delle chiamate eserciteranno query nel database cdr per generare avvisi che indicano quando un numero elevato di utenti verifica problemi di connettività per le chiamate peer-to-peer o funzionalità di conferenza di base.  <br/> La copertura dello scenario include chiamate audio, messaggistica istantanea peer-to-peer e altre funzionalità di conferenza.  <br/> |
|Avvisi di qualità multimediale  <br/> |Query di database che osservano i report QoE pubblicati dai client Skype for Business Server 2015 al termine di ogni chiamata. Queste query generano avvisi che segnalano scenari in cui è più probabile che gli utenti sperimentino una qualità multimediale compromessa durante le chiamate e le conferenze. I dati si basano su metriche chiave, ad esempio la latenza e la perdita dei pacchetti, che contribuiscono direttamente alla qualità dell'esperienza utente.  <br/> |
|Avvisi di integrità dei componenti  <br/> |I singoli componenti server generano avvisi tramite registri eventi e contatori delle prestazioni per indicare condizioni di errore che possono influire in modo significativo sugli scenari utente. Questi avvisi indicano diverse condizioni, ad esempio servizi non in esecuzione, frequenze di errore elevate, latenza elevata dei messaggi o problemi di connettività.  <br/> |
|Monitoraggio dell'integrità delle dipendenze  <br/> |Skype for Business Server può non riuscire per diversi motivi esterni. Il Management Pack monitora e raccoglie i dati per le dipendenze esterne critiche che possono indicare problemi gravi. Queste dipendenze includono la disponibilità di Internet Information Services (IIS) e la CPU dei server utilizzati per Skype for Business Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Definizione della priorità degli avvisi

Gli avvisi vengono classificati nelle categorie seguenti: 
  
 **Avvisi con priorità alta:** Questi avvisi indicano condizioni che causano interruzioni del servizio per grandi gruppi di utenti e richiedono un'azione immediata. Le interruzioni rilevate da transazioni sintetiche e servizi offline (come Le conferenze audio/video di Skype for Business Server) sono qualificate come avvisi con priorità alta. Al contrario, un errore del componente in un singolo computer non è un avviso con priorità alta. Skype for Business Server 2015 include funzionalità di disponibilità elevata integrate per queste situazioni, ad esempio più Front End Server dietro i servizi di bilanciamento del carico.
  
 **Avvisi con priorità media:** Questi avvisi indicano condizioni che influiscono su un sottoinsieme di utenti o indicano problemi di qualità delle chiamate, ad esempio errori dei componenti, latenza nella definizione delle chiamate o qualità audio inferiore nelle chiamate. Gli avvisi in questa categoria sono con stato, ovvero la natura dell'avviso cambia in base allo stato della connessione di rete. Ad esempio, se gli orari di definizione delle chiamate indicano la latenza ma poi tornano a una soglia normale, questo avviso con priorità media verrà risolto automaticamente in System Center Operations Manager e gli amministratori non dovranno eseguire alcuna azione. Gli avvisi che non possono essere risolti automaticamente vengono in genere risolti dagli amministratori nello stesso giorno lavorativo.
  
 **Altri avvisi:** Questi avvisi vengono generati da componenti che potrebbero influire su un utente o un sottoinsieme di utenti specifico. Ad esempio, un avviso tipico è che il servizio Rubrica non è stato in grado di analizzare la voce di Servizi di dominio Active Directory® per l'utente: testuser@contoso.com. Gli amministratori possono risolvere questi avvisi ogni volta che hanno tempo a disposizione.
  
### <a name="synthetic-transactions"></a>Transazioni sintetiche

I Management Pack di Skype for Business Server 2015 offrono una maggiore copertura per gli avvisi tramite transazioni sintetiche. Le transazioni sintetiche Windows PowerShell cmdlet integrati nel Management Pack di Operations Manager per testare gli scenari degli utenti end-to-end. Quando si designa un server per l'esecuzione di transazioni sintetiche, questi cmdlet vengono attivati periodicamente dal Management Pack. Gli errori risultanti da una transazione sintetica generano un avviso con stato. Ecco le transazioni sintetiche supportate per Skype for Business Server 2015:
  


|Transazioni sintetiche supportate per registrazione, presenza e contatti|||
|:-----|:-----|:-----|
|1   <br/> |Registrazione (accesso utente)  <br/> |Lync Server 2010 disponibile e oltre  <br/> |
|2   <br/> |Servizio Rubrica (download di file)  <br/> |Lync Server 2010 disponibile e oltre  <br/> |
|3   <br/> |Address Book Web Query  <br/> |Lync Server 2010 disponibile e oltre  <br/> |
|4   <br/> |Presenza  <br/> |Lync Server 2010 disponibile e oltre  <br/> |
|5   <br/> |Archivio unico dei contatti  <br/> |Lync Server 2013 disponibile e oltre  <br/> |
||||   

|Transazioni sintetiche supportate per i servizi peer-to-peer|||
|:-----|:-----|:-----|
|6   <br/> |Messaggistica istantanea peer-to-peer  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|7   <br/> |Peer-to-Peer Audio Video  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|8   <br/> |Messaggio istantaneo peer-to-peer MCX (mobile)  <br/> |Disponibile nella versione di settembre 2011 di Lync Server 2010 per Skype for Business 2015  <br/> |
 
> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.


|Transazioni sintetiche supportate per conferenze e Persistent Chat|||
|:-----|:-----|:-----|
|9   <br/> |Conferenze audio e video  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|10    <br/> |Conferenze dati  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|11   <br/> |Servizio di conferenza per messaggi istantanei  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|12   <br/> | Chat persistente <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|13   <br/> |Partecipare all'icona di avvio (riunioni pianificate)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|14   <br/> |Conferenza telefonica con accesso esterno  <br/> |Novità di Skype for Business Server 2015  <br/> |
|15   <br/> |Servizio di conferenza per la condivisione di applicazioni  <br/> |Novità di Skype for Business Server 2015  <br/> |
|16   <br/> |Conferenza UCWA (partecipazione a riunioni Web)  <br/> |Novità di Skype for Business Server 2015  <br/> |
||||

|Transazioni sintetiche supportate per le dipendenze di rete e partner|||
|:-----|:-----|:-----|
|17   <br/> |AV Edge Connectivity  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|18   <br/> |AV Edge Connectivity Exchange Unified Message Connectivity (segreteria telefonica)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|19  <br/> |Chiamata peer-to-peer PSTN  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|20  <br/> |Messaggistica istantanea XMPP (federazione)  <br/> |Disponibile in Lync Server 2013 e Skype for Business 2015  <br/> |
| 21  <br/> |Server di interoperabilità video  <br/> |Novità di Skype for Business Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Implementazione dell'integrità

La tabella seguente mostra gli stati di integrità degli oggetti del monitoring pack di Skype for Business Server.
  
|Oggetto Management Pack|Descrizione|
|:-----|:-----|
|Distribuzione di Skype for Business Server  <br/> |Rappresenta la distribuzione di Skype for Business Server 2015 nell'organizzazione.  <br/> |
|Sito di Skype for Business Server  <br/> |Rappresenta posizioni geografiche diverse in cui vengono distribuiti i servizi.  <br/> |
|Skype for Business Server Pool  <br/> |Pool (all'interno di un sito) che fornisce servizi di comunicazione, ad esempio messaggistica istantanea e conferenze, agli utenti. Applicabile ai pool Front End, ai pool di server perimetrali e ai pool di server Director, anche se in un determinato pool è presente un solo computer.  <br/> |
|Ruolo del server Skype for Business  <br/> |Ruolo del server che ospita il servizio Skype for Business Server.  <br/> |
|Servizio Skype for Business Server  <br/> |Rappresenta una funzionalità distribuita in un computer specifico, ad esempio servizio utente in fp01.contoso.com.  <br/> |
|Componente Skype for Business Server  <br/> |Un componente del servizio( ad esempio, il componente di download della Rubrica fa parte del servizio Web).  <br/> |
|Skype for Business Server Pool Watcher  <br/> |Un'istanza di transazioni sintetiche in esecuzione in un pool.  <br/> |
|Skype for Business Server Registrar Watcher  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool di registrazione.  <br/> |
|Skype for Business Server User Services Pool Watcher  <br/> |Un'istanza di transazioni sintetiche eseguite in un pool di Servizi utente.  <br/> |
|Skype for Business Server Voice Pool Watcher  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool vocale.  <br/> |
|Skype for Business Server Port Watcher  <br/> |Un'istanza di Verifica porte in esecuzione in un pool.  <br/> |
|Simple URL Watcher  <br/> |Esegue il probe HTTPS degli URL semplici configurati in una distribuzione.  <br/> |
   
![SCOM Rollup](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un pool di Skype for Business Server può contenere più singoli sistemi Skype for Business Server (con più ruoli di Skype for Business Server, servizio Skype for Business Server e componenti di Skype for Business Server). Di conseguenza, l'errore di un singolo server o componente è meno critico per l'integrità complessiva del pool di Skype for Business Server, perché altri server nello stesso pool possono fornire il servizio dell'applicazione al client. L'integrità verrà rollup su un livello percentuale al pool di Skype for Business Server. 
  
Skype for Business Server Pool Watcher esegue transazioni sintetiche su un pool di Skype for Business Server. Un errore consecutivo di una o più transazioni sintetiche (un processo noto come intervallo di polling consecutivo) esegue il rollup dello stato di integrità critico al livello del pool (il peggiore di qualsiasi transazione sintetica), come illustrato nel diagramma seguente. 
  
![Polling consecutivo dell'aggiornamento cumulativo SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Procedura consigliata: Creare un Management Pack per le personalizzazioni

Per impostazione predefinita, Operations Manager salva tutte le personalizzazioni, ad esempio le sostituzioni nel Management Pack predefinito. Come procedura consigliata, è consigliabile creare un Management Pack separato per ogni Management Pack sealed che si desidera personalizzare. 
  
Quando si crea un Management Pack per l'archiviazione di impostazioni personalizzate per un Management Pack sealed, è consigliabile denominare il nuovo Management Pack in modo appropriato, ad esempio "Personalizzazioni di Skype for Business Server 2015". 
  
La creazione di un nuovo Management Pack per l'archiviazione delle personalizzazioni di ogni Management Pack sealed semplifica l'esportazione delle personalizzazioni da un ambiente di testing a un ambiente di produzione. Ciò semplifica inoltre l'eliminazione di un Management Pack, perché è necessario eliminare tutte le dipendenze prima di poter eliminare un Management Pack. Se le personalizzazioni per tutti i Management Pack vengono salvate nel Management Pack predefinito ed è necessario eliminare un singolo Management Pack, è innanzitutto necessario eliminare il Management Pack predefinito, che elimina anche le personalizzazioni in altri Management Pack. 
  
## <a name="links"></a>Collegamenti

I collegamenti seguenti connettono l'utente alle informazioni sulle attività comuni associate ai Monitoring Pack di System Center 2012:
  
- [Ciclo di vita dei Management Pack](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Come importare un Management Pack in Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Come ignorare una regola o un monitoraggio](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Come creare un account RunAs in Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Gestione di account e profili RunAs](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Come esportare un Management Pack di Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Come rimuovere un Management Pack di Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
I collegamenti seguenti connettono l'utente alle informazioni sulle attività comuni associate ai Monitoring Pack di System Center 2007:
  
- [Amministrazione del ciclo di vita del Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Come importare un Management Pack in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Come monitorare l'utilizzo delle sostituzioni](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Come creare un account RunAs in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Come modificare un profilo RunAs esistente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Come esportare le personalizzazioni dei Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Come rimuovere un Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Per domande su Operations Manager e sui Monitoring Pack, vedere il [forum della community di System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Una risorsa utile è il blog [di System Center Operations Manager Unleashed,](https://opsmgrunleashed.wordpress.com/) che contiene post di esempio per specifici Monitoring Pack.
  
Per ulteriori informazioni su Operations Manager, vedere i blog seguenti: 
  
- [Operations Manager Team Blog](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog opsMgr di Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Considerazioni su OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog di Raphael Burri](https://rburri.wordpress.com/)
    
- [Spazio di gestione di BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Tutte le informazioni e il contenuto dei siti non Microsoft vengono forniti dal proprietario o dagli utenti del sito Web. Microsoft non garantisce, espressa, implicita o statutaria, le informazioni contenute in questo sito Web. 
  
## <a name="see-also"></a>Vedere anche

[Strumenti di gestione di Skype for Business Server 2015](../../management-tools/management-tools.md)
