---
title: Gestire Skype for Business Server 2019 con SCOM Management Pack
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
ms.openlocfilehash: 8f19998ad5d46074a1225ae0dd4d901bd367d823
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120385"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Gestire Skype for Business Server 2019 con SCOM Management Pack
 
**Riepilogo:** Informazioni su come configurare l'infrastruttura di Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.
  
In un mondo ideale, non si verificano mai problemi con Skype for Business Server 2019. Tuttavia, Skype for Business Server può essere influenzato da fattori esterni, ad esempio arresti anomali della rete e errori hardware. Utilizzando i Management Pack di Skype for Business Server 2019, è possibile identificare e risolvere potenziali problemi in modo proattivo. In questo modo, i Management Pack di Skype for Business Server 2019 estendono le funzionalità di System Center Operations Manager.
  
Queste informazioni sono state scritte in base alla versione 9319.0 del software di comunicazione Monitoring Pack per Skype for Business Server 2019.
  
## <a name="configuration-overview"></a>Panoramica della configurazione

 Per configurare l'infrastruttura di Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager, è necessario eseguire tre operazioni:
  
Identificare e [configurare il server di gestione principale](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md). A tale scopo, è necessario installare System Center Operations Manager 2012 SP1 o R2. 
  
 Identificare e [configurare i computer Skype for Business Server che verranno monitorati.](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md) Per monitorare un computer Skype for Business Server utilizzando System Center Operations Manager, è necessario installare i file agente di System Center Operations Manager e configurare ogni server in modo che agirà come proxy. 
  
 Identificare e [installare e configurare i nodi Watcher.](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md) I nodi Watcher sono computer che eseguono periodicamente transazioni sintetiche di Skype for Business Server Windows PowerShell cmdlet che verificano che i componenti chiave di Skype for Business Server, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei, funzionino come previsto. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Supporto agente e server di gestione radice di System Center Operations Manager

I Management Pack possono essere utilizzati con System Center Operations Manager 2007 R2 (64 bit) (supportato solo a scopo di migrazione) o System Center Operations Manager 2012 SP1 &amp; R2 (64 bit). La tabella seguente mostra le configurazioni supportate per i Management Pack per Skype for Business Server 2019: 
  
|**Configurazione**|**Supportato?**|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sì. Sia nel server Skype for Business Server 2019 che nei nodi Synthetic Transaction Watcher.  <br/> |
|Server in cluster  <br/> |Non supportate.  <br/> |
|Monitoraggio senza agenti  <br/> |Non supportate.  <br/> |
|Ambiente virtuale  <br/> |Sì.  <br/> |
|Ruoli del server aggiunti al dominio  <br/> |Tutti i ruoli del server interni di Skype for Business Server 2019 devono essere aggiunti a un dominio.  <br/> |
|Ruoli del server autonomi  <br/> |I server perimetrali di Skype for Business Server 2019 non devono essere aggiunti a un dominio.  <br/> |
|Limitazioni della topologia  <br/> |Tutti i ruoli del server in una distribuzione devono essere monitorati dallo stesso gruppo di gestione di Operations Manager.  <br/> |
|Nodo Watcher delle transazioni sintetiche  <br/> |La disponibilità dello scenario di monitoraggio con un nodo Watcher delle transazioni sintetiche è supportata (è necessaria una configurazione aggiuntiva). I nodi Watcher non devono essere aggiunti a un dominio.  <br/> |
   
Nella tabella seguente vengono illustrati i requisiti di capacità e del sistema operativo per un nodo Synthetic Transaction Watcher:
  
|**Componente hardware**|**Requisiti minimi**|
|:-----|:-----|
|CPU  <br/> |Una delle opzioni seguenti:  <br/> Processore a 64 bit, quad-core, 2,33 GHz o superiore  <br/> Processore 2d a 64 bit, dual-core, 2,33 GHz o superiore  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Rete  <br/> |1 scheda di rete a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Prerequisiti

Per eseguire un nodo Synthetic Transaction Watcher, è innanzitutto necessario installare quanto segue:
  
- Agente System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- File di installazione di base di Skype for Business Server (OcsCore.msi) e UCMA (Unified Communications Managed API) (le versioni devono corrispondere alla versione di Skype for Business Server WatcherNode.msi)
    
## <a name="files-in-this-monitoring-pack"></a>File in questo Monitoring Pack

Il Monitoring Pack per Skype for Business Server 2019 include i file seguenti:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novità

Le funzionalità seguenti sono una novità dei Management Pack di Skype for Business Server 2019.

- **Modifiche [nell'aggiornamento di settembre 2019](https://www.microsoft.com/download/details.aspx?id=57511)** Alcuni avvisi hanno rimosso caratteri speciali. In alcuni casi i caratteri speciali interferiscono con la funzionalità di notifica del canale di comando SCOM.

- **Individuazione automatica per l'accesso client** Le applicazioni client che a cui si accede a Skype for Business Server 2019 spesso individuano automaticamente il server a cui accedere. Le transazioni sintetiche ora supportano la verifica che l'individuazione automatica sia configurata correttamente.
    
- **Intervalli di esecuzione delle transazioni sintetiche personalizzati** Per semplificare il processo di configurazione dei nodi Watcher, le transazioni sintetiche possono condividere gli account utente. In questo modo si rallenta la frequenza con cui i test vengono eseguiti quando i test vengono serializzati per evitare conflitti. Per impostazione predefinita, le transazioni sintetiche vengono eseguite ogni 15 minuti per garantire che tutti i test siano in tempo per l'esecuzione. Gli amministratori che scelgono di utilizzare più utenti o meno test per utente ora possono ridurre anche l'intervallo di esecuzione.
    
- **Transazione sintetica di Video Interop Services** I clienti che eseguono la migrazione a Skype for Business Server 2019 da altre soluzioni fornitore spesso desiderano continuare a usare i dispositivi di teleconferenza video (VTC) di questi altri fornitori. Video Interop Server è un nuovo ruolo del server Skype for Business Server 2019 che consente ai clienti di continuare a usare i VTC Cisco nelle proprie sale riunioni connettendosi a Cisco CUCM tramite un trunk SIP video. Questa funzionalità aggiunge inoltre una transazione sintetica per verificare che Video Interop Server sia in funzione e sia in grado di gestire le connessioni in ingresso su un trunk SIP video.
    
- **Transazione sintetica conferenza condivisione applicazioni** La convalida degli scenari end-to-end per le conferenze di condivisione applicazioni è ora supportata.
    
## <a name="monitoring-scenarios"></a>Scenari di monitoraggio

Skype for Business Server 2019 Management Pack sfrutta un'ampia gamma di funzionalità per rilevare e diagnosticare i problemi. Queste funzionalità offrono visibilità in tempo reale sull'integrità di un ambiente Skype for Business Server 2019.
  
|**Scenario di monitoraggio**|**Descrizione**|
|:-----|:-----|
|Transazioni sintetiche  <br/> | Windows PowerShell cmdlet per testare e garantire la disponibilità elevata di scenari quali l'accesso, la presenza, la messaggistica istantanea e le conferenze per gli utenti. <br/> Le transazioni sintetiche possono essere eseguite da qualsiasi posizione geografica, anche all'interno dell'azienda, all'esterno dell'azienda e nelle succursali.  <br/> Quando una transazione sintetica ha esito negativo, vengono creati log s HTML per determinare l'esatta natura dell'errore. Ciò include la comprensione dell'azione non riuscita, della latenza di ogni azione, della riga di comando utilizzata per eseguire il test e dell'errore specifico che si è verificato.  <br/> |
|Avvisi di affidabilità delle chiamate  <br/> |I record dettagli chiamata (CDR) scritti dai server Skype for Business Server 2019 riflettono se gli utenti sono in grado di connettersi a una chiamata o perché una chiamata viene terminata. Gli avvisi di affidabilità delle chiamate interrogano il database cdR per generare avvisi che indicano quando un numero elevato di utenti verifica problemi di connettività per chiamate peer-to-peer o funzionalità di conferenza di base.  <br/> La copertura dello scenario include chiamate audio, messaggistica istantanea peer-to-peer e altre funzionalità di conferenza.  <br/> |
|Avvisi di qualità multimediale  <br/> |Query di database che osservano i report QoE pubblicati dai client Skype for Business Server 2019 al termine di ogni chiamata. Queste query generano avvisi che individuano scenari in cui è più probabile che gli utenti sperimentino una qualità multimediale compromessa durante le chiamate e le conferenze. I dati si basano su metriche chiave, come la latenza e la perdita dei pacchetti, che contribuiscono direttamente alla qualità dell'esperienza utente.  <br/> |
|Avvisi di integrità dei componenti  <br/> |I singoli componenti del server generano avvisi tramite registri eventi e contatori delle prestazioni per indicare condizioni di errore che possono influire in modo significativo sugli scenari utente. Questi avvisi indicano diverse condizioni, ad esempio servizi non in esecuzione, frequenze di errore elevate, latenza elevata dei messaggi o problemi di connettività.  <br/> |
|Monitoraggio dell'integrità delle dipendenze  <br/> |Skype for Business Server può non riuscire per diversi motivi esterni. Il Management Pack monitora e raccoglie i dati per le dipendenze esterne critiche che possono indicare problemi gravi. Queste dipendenze includono la disponibilità di Internet Information Services (IIS) e la CPU dei server utilizzati per Skype for Business Server.  <br/> |
   
### <a name="alert-prioritization"></a>Priorità degli avvisi

Gli avvisi sono classificati nelle categorie seguenti: 
  
 **Avvisi con priorità alta:** Questi avvisi indicano condizioni che causano interruzioni del servizio per gruppi di utenti di grandi dimensioni e richiedono un'azione immediata. Le interruzioni rilevate da transazioni sintetiche e servizi offline (ad esempio Audio/Videoconferenze di Skype for Business Server) sono qualificate come avvisi con priorità alta. Al contrario, un errore di componente in un singolo computer non è un avviso con priorità alta. Skype for Business Server 2019 include funzionalità a disponibilità elevata integrate per queste situazioni, ad esempio più Front End Server dietro servizi di bilanciamento del carico.
  
 **Avvisi di priorità media:** Questi avvisi indicano condizioni che influiscono su un sottoinsieme di utenti o indicano problemi di qualità delle chiamate, ad esempio errori dei componenti, latenza nello stabilire le chiamate o qualità audio inferiore nelle chiamate. Gli avvisi in questa categoria sono con stato, ovvero la natura dell'avviso cambia in base allo stato della connessione di rete. Ad esempio, se i tempi di definizione delle chiamate indicano la latenza ma poi tornano a una soglia normale, questo avviso di priorità media verrà risolto automaticamente in System Center Operations Manager e gli amministratori non dovranno eseguire alcuna azione. Gli avvisi che non possono essere risolti automaticamente vengono in genere indirizzati dagli amministratori nello stesso giorno lavorativo.
  
 **Altri avvisi:** Questi avvisi vengono generati da componenti che potrebbero influire su un utente o un sottoinsieme di utenti specifico. Ad esempio, un avviso tipico è che il servizio Rubrica non è stato in grado di analizzare la voce di Servizi di dominio Active Directory® per l'utente: testuser@contoso.com. Gli amministratori possono gestire questi avvisi ogni volta che hanno tempo a disposizione.
  
### <a name="synthetic-transactions"></a>Transazioni sintetiche

I Management Pack di Skype for Business Server 2019 offrono una maggiore copertura per gli avvisi tramite transazioni sintetiche. Le transazioni sintetiche Windows PowerShell cmdlet integrati nel Management Pack di Operations Manager per testare gli scenari degli utenti end-to-end. Quando si designa un server per l'esecuzione di transazioni sintetiche, questi cmdlet vengono attivati periodicamente dal Management Pack. Gli errori risultanti da una transazione sintetica generano un avviso con stato. Ecco le transazioni sintetiche supportate per Skype for Business Server 2019:
  
**Transazioni sintetiche supportate per registrazione, presenza e contatti**

||||
|:-----|:-----|:-----|
|1  <br/> |Registrazione (accesso utente)  <br/> |Lync Server 2010 e oltre  <br/> |
|2   <br/> |Servizio Rubrica (download di file)  <br/> |Lync Server 2010 e oltre  <br/> |
|3   <br/> |Address Book Web Query  <br/> |Lync Server 2010 e oltre  <br/> |
|4   <br/> |Presenza  <br/> |Lync Server 2010 e oltre  <br/> |
|5   <br/> |Archivio unico dei contatti  <br/> |Lync Server 2013 e oltre  <br/> |
   
**Transazioni sintetiche supportate per i servizi peer-to-peer**

||||
|:-----|:-----|:-----|
|6   <br/> |Messaggistica istantanea peer-to-peer  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|7   <br/> |Peer-to-Peer Audio Video  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|8   <br/> |Messaggio istantaneo peer-to-peer MCX (mobile)  <br/> |Disponibile nella versione di settembre 2011 di Lync Server 2010 per Skype for Business 2019  <br/> |
 
> [!NOTE]
> Il supporto MCX (Servizio per dispositivi mobili) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client mobili Skype for Business correnti usano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
**Transazioni sintetiche supportate per conferenze e Persistent Chat**

||||
|:-----|:-----|:-----|
|9   <br/> |Conferenze audio e video  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|10    <br/> |Conferenze dati  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|11   <br/> |Servizio di conferenza messaggi istantanei  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|12   <br/> | Chat persistente <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|13  <br/> |Partecipare a Launcher (riunioni pianificate)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|14   <br/> |Conferenza telefonica con accesso esterno  <br/> |Disponibile in Skype for Business Server 2015 e oltre <br/> |
|15   <br/> |Application Sharing Conferencing  <br/> |Disponibile in Skype for Business Server 2015 e oltre <br/> |
|16   <br/> |Conferenza UCWA (partecipazione a riunioni Web)  <br/> |Disponibile in Skype for Business Server 2015 e oltre <br/> |
   
**Transazioni sintetiche supportate per le dipendenze di rete e partner**

||||
|:-----|:-----|:-----|
|17   <br/> |AV Edge Connectivity  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|18   <br/> |AV Edge Connectivity Exchange Unified Message Connectivity (segreteria telefonica)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
|19  <br/> |Chiamata peer-to-peer PSTN  <br/> |Disponibile in Lync Server 2010 e oltre  <br/> |
|20  <br/> |Messaggistica istantanea XMPP (federazione)  <br/> |Disponibile in Lync Server 2013 e oltre  <br/> |
| 21  <br/> |Server di interoperabilità video  <br/> |Disponibile in Skype for Business Server 2015 e oltre  <br/> |
   
## <a name="how-health-rolls-up"></a>Come viene eseguito il rollup dell'integrità

La tabella seguente mostra gli stati di integrità degli oggetti nel Monitoring Pack di Skype for Business Server.
  
|**Oggetto Management Pack**|**Descrizione**|
|:-----|:-----|
|Distribuzione di Skype for Business Server  <br/> |Rappresenta la distribuzione di Skype for Business Server 2019 nell'organizzazione.  <br/> |
|Sito Skype for Business Server  <br/> |Rappresenta posizioni geografiche diverse in cui vengono distribuiti i servizi.  <br/> |
|Skype for Business Server Pool  <br/> |Pool (all'interno di un sito) che fornisce servizi di comunicazione, ad esempio messaggistica istantanea e conferenze, agli utenti. Applicabile ai pool Front End, ai pool di server perimetrali e ai pool di server Director, anche se in un determinato pool è presente un solo computer.  <br/> |
|Ruolo di Skype for Business Server  <br/> |Ruolo del server che ospita il servizio Skype for Business Server.  <br/> |
|Servizio Skype for Business Server  <br/> |Rappresenta una funzionalità distribuita in un computer specifico, ad esempio un servizio utente fp01.contoso.com.  <br/> |
|Componente Skype for Business Server  <br/> |Un componente del servizio, ad esempio il componente Di download della Rubrica, fa parte del servizio Web.  <br/> |
|Skype for Business Server Pool Watcher  <br/> |Un'istanza di transazioni sintetiche in esecuzione in un pool.  <br/> |
|Skype for Business Server Registrar Watcher  <br/> |Istanza di transazioni sintetiche eseguite su un pool di registrazione.  <br/> |
|Skype for Business Server User Services Pool Watcher  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool di Servizi utente.  <br/> |
|Skype for Business Server Voice Pool Watcher  <br/> |Un'istanza di transazioni sintetiche eseguite su un pool di voci.  <br/> |
|Watcher delle porte di Skype for Business Server  <br/> |Un'istanza di Port controlla l'esecuzione in un pool.  <br/> |
|Simple URL Watcher  <br/> |Esegue il probe HTTPS degli URL semplici configurati in una distribuzione.  <br/> |
   
![SCOM Rollup](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un pool di Skype for Business Server può contenere più singoli sistemi Skype for Business Server (con più di un ruolo di Skype for Business Server, il servizio Skype for Business Server e il componente Skype for Business Server). Pertanto, l'errore di un singolo server o componente è meno critico per l'integrità complessiva del pool di Skype for Business Server, perché altri server nello stesso pool possono fornire il servizio dell'applicazione al client. L'integrità verrà rollup a un livello percentuale per il pool di Skype for Business Server. 
  
Skype for Business Server Pool Watcher esegue transazioni sintetiche su un pool di Skype for Business Server. L'errore consecutivo di una o più transazioni sintetiche (un processo noto come intervallo di polling consecutivo) esegue il rollup dello stato di integrità critico al livello di pool (peggiore di qualsiasi transazione sintetica), come illustrato nel diagramma seguente. 
  
![Polling consecutivo di SCOM Rollup](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Procedura consigliata: Creare un Management Pack per le personalizzazioni

Per impostazione predefinita, Operations Manager salva tutte le personalizzazioni, ad esempio le sostituzioni nel Management Pack predefinito. Come procedura consigliata, è consigliabile creare un Management Pack separato per ogni Management Pack sealed che si desidera personalizzare. 
  
Quando si crea un Management Pack per l'archiviazione di impostazioni personalizzate per un Management Pack sealed, è consigliabile denominare il nuovo Management Pack in modo appropriato, ad esempio "Personalizzazioni di Skype for Business Server 2019".
  
La creazione di un nuovo Management Pack per l'archiviazione delle personalizzazioni di ogni Management Pack sealed semplifica l'esportazione delle personalizzazioni da un ambiente di testing a un ambiente di produzione. Ciò semplifica anche l'eliminazione di un Management Pack, perché è necessario eliminare eventuali dipendenze prima di poter eliminare un Management Pack. Se le personalizzazioni per tutti i Management Pack vengono salvate nel Management Pack predefinito ed è necessario eliminare un singolo Management Pack, è innanzitutto necessario eliminare il Management Pack predefinito, che elimina anche le personalizzazioni in altri Management Pack. 
  
## <a name="links"></a>Collegamenti

I collegamenti seguenti ti connettono alle informazioni sulle attività comuni associate ai Monitoring Pack di System Center 2012:
  
- [Ciclo di vita del Management Pack](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [Come importare un Management Pack in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [Come ignorare una regola o un monitoraggio](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [Come creare un account RunAs in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [Gestione di account e profili RunAs](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [Come esportare un Management Pack di Operations Manager](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [Come rimuovere un Management Pack di Operations Manager](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
I collegamenti seguenti ti connettono alle informazioni sulle attività comuni associate ai Monitoring Pack di System Center 2007:
  
- [Amministrazione del ciclo di vita del Management Pack](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [Come importare un Management Pack in Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [Come monitorare l'utilizzo di sostituzioni](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [Come creare un account RunAs in Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [Come modificare un profilo RunAs esistente](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [Come esportare le personalizzazioni dei Management Pack](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [Come rimuovere un Management Pack](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
Per domande su Operations Manager e sui Monitoring Pack, vedere il forum della [community di System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Una risorsa utile è il blog [di System Center Operations Manager Unleashed,](https://opsmgrunleashed.wordpress.com/) che contiene post di esempio per specifici monitoring pack.
  
Per ulteriori informazioni su Operations Manager, vedere i blog seguenti: 
  
- [Operations Manager Team Blog](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog opsMgr di Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Considerazioni su OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog di Raphael Burri](https://rburri.wordpress.com/)
    
- [BWren's Management Space](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Tutte le informazioni e i contenuti dei siti non Microsoft sono forniti dal proprietario o dagli utenti del sito Web. Microsoft non garantisce, espressa, implicita o statutaria, le informazioni contenute in questo sito Web. 
  
## <a name="see-also"></a>Vedere anche

[Strumenti di gestione di Skype for Business Server 2019](../management-tools-2019.md)