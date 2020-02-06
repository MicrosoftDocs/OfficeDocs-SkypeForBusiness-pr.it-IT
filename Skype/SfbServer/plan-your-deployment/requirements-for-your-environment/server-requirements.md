---
title: Requisiti server di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: "Riepilogo: preparare i server di Skype for Business Server 2015 con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e le raccomandazioni sono qui per garantire un'installazione e una distribuzione di successo della server farm."
ms.openlocfilehash: f806137b5972968332723a370092724bd9680697
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801886"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisiti server di Skype for Business Server 2015
 
**Riepilogo:** Preparare i server di Skype for Business Server 2015 con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e le raccomandazioni sono qui per garantire un'installazione e una distribuzione di successo della server farm.

Se si cercano requisiti ambientali, ad esempio Active Directory, DNS o certificati, è possibile consultare i [requisiti ambientali per Skype for Business Server 2015](environmental-requirements.md) doc.
  
Come ci si potrebbe aspettare, i preparativi da eseguire prima di iniziare a distribuire Skype for Business Server 2015. Questo articolo illustra la pianificazione per le operazioni seguenti:
  
- [Hardware per Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemi operativi per Skype for Business Server 2015](server-requirements.md#OS)
  
- [Database di back-end che funzioneranno con Skype for Business Server 2015](server-requirements.md#DBs)
  
- [Software che deve essere installato prima di una distribuzione di Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware per Skype for Business Server 2015
<a name="Hardware"> </a>

Dopo avere disattivato la topologia e, in caso contrario, è possibile verificare le [nozioni di base sulla topologia per Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) , ma è il momento di pensare ai server. I server di Skype for Business Server 2015 richiedono hardware a 64 bit. Le nostre raccomandazioni per l'hardware sono inferiori. Non si tratta di requisiti, ma riflettono i requisiti necessari per ottenere prestazioni ottimali. Abbiamo la documentazione relativa alla pianificazione della capacità che ti aiuterà a determinare se hai bisogno di più di questo, a seconda delle circostanze.
  
Hardware consigliato per server front-end, server back-end, server Standard Edition e server di chat persistente:
  
|**Componente hardware**|**Consigliato**|
|:-----|:-----|
|CPU  <br/> |64-bit Dual Processor, hex-core, 2,26 gigahertz (GHz) o versioni successive.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |SIA  <br/> • 8 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (due dischi che usano RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • SSD (Solid State Drive) in grado di assicurare lo stesso spazio libero e prestazioni simili alle unità disco meccaniche di 8 10000 RPM.  <br/> |
|Rete  <br/> |1 adattatore di rete a doppia porta, 1 Gbps o superiore (2 schede di rete possono essere usate, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multihomed **non** sono supportate per i server front-end, i server back-end, i server Standard Edition e i server di chat permanenti. <br/> Purché non siano esposti al sistema operativo e vengano usati per monitorare e gestire l'hardware del server, è possibile che i sistemi di gestione della banda siano fuori sede, ad esempio DRAC o ILO. Questo scenario non costituisce un server multihomed ed è supportato.  <br/> |
   
Hardware consigliato per server perimetrali, mediazione autonoma, server di interoperabilità video e direttori:
  
|**Componente hardware**|**Consigliato**|
|:-----|:-----|
|CPU  <br/> |64-bit Dual Processor, quad-core, 2,26 gigahertz (GHz) o versioni successive.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |16 gigabyte.  <br/> |
|Disco  <br/> |SIA  <br/> • 4 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione di 2x RAID 1).  <br/> OPPURE  <br/> • SSD (Solid State Drive) in grado di assicurare lo stesso spazio libero e prestazioni simili alle unità disco meccaniche di 4 10000 RPM.  <br/> |
|Rete  <br/> |1 adattatore di rete a doppia porta, 1 Gbps o superiore (2 schede di rete possono essere usate, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multihomed **non** sono supportate per i server e gli amministratori di interoperabilità video. <br/> I server perimetrali richiedono due interfacce di rete che sono schede di rete a doppia porta, 1 Gbps o superiore (o due schede di rete abbinate, per un totale di quattro, ogni coppia che viene affiancata da un singolo indirizzo MAC e da un singolo indirizzo IP, per un totale di due coppie).  <br/> In Mediation Server autonomi l'installazione di schede di interfaccia di rete aggiuntive (NIC) per consentire la configurazione di un indirizzo IP PSTN specifico è supportata.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemi operativi per Skype for Business Server 2015
<a name="OS"> </a>

Dopo aver installato l'hardware, è necessario installare sistemi operativi (OS). Questi sono i sistemi operativi che ti consentiranno di installare e usare correttamente Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (è necessario l'aggiornamento cumulativo 9 o versione successiva di Skype for business). <br/> |Windows Server 2016 (è necessario l'aggiornamento cumulativo di Skype for business 5 o versioni successive. Per altre informazioni, vedere [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 R2 Datacenter OS con tutti gli aggiornamenti necessari installati.  <br/> |Sistema operativo Windows Server 2012 R2 Standard con tutti gli aggiornamenti necessari installati.  <br/> |
|Sistema operativo Windows Server 2012 Datacenter con tutti gli aggiornamenti necessari installati.  <br/> |Windows Server 2012 standard OS con tutti gli aggiornamenti necessari installati.  <br/> |
   
Se non è presente nell'elenco, non funziona correttamente, non provarlo per le nuove installazioni di Skype for Business Server 2015. Tieni presente che l'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013.  È necessario distribuire un pool separato e eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso.
  
> [!NOTE]
> Potresti aver notato che Windows Server 2008 R2 non è presente nell'elenco. Questo perché ti consigliamo di usare Windows Server 2012 R2 per tutti i nuovi server che verranno usati per SFB. È consigliabile usare Windows Server 2008 R2 solo quando sono già installati server esistenti con Lync Server 2013 e si intende eseguire un aggiornamento sul posto... Windows Server 2008 R2 ha raggiunto la fine del ciclo di vita del supporto mainstream su 1/13/2015 e raggiungerà la fine del ciclo di vita del supporto in 1/14/2020.
  
Oltre al Service Pack più recente, è necessario assicurarsi che siano installati gli aggiornamenti seguenti, se pertinente:
  
- Per Windows Server 2012, l'articolo KB 2858668 deve essere installato prima di un aggiornamento. [Ottenere qui](https://support.microsoft.com/kb/2858668/).
    
- Se si ha Windows Server 2012 R2, installare l'articolo KB 2982006 prima di eseguire l'aggiornamento. [Si trova qui](https://support.microsoft.com/kb/2982006/).
    
- Se si esegue l'aggiornamento in una casella di Windows Server 2008 R2 (vedere la nota precedente), è necessario installare prima l'articolo KB 2533623. È [a questo collegamento](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Database di back-end che funzioneranno con Skype for Business Server 2015
<a name="DBs"> </a>


Durante l'installazione di Skype for Business Server 2015 Standard Edition, è installato automaticamente anche SQL Server 2014 Express (64-bit Edition).
  
Skype for Business Server 2015 Enterprise Edition è un po' più complicato, ma l'elenco supportato è inferiore (tutto è 64 bit Edition, si noterà che non si usano le edizioni a 32 bit):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2017 Enterprise (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2016 Enterprise (64 bit Edition) con Service Pack 1 o versioni successive ed è necessario eseguire l'aggiornamento cumulativo di Skype for business 7 o versione successiva ([scaricare l'aggiornamento cumulativo di Skype for business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (64 bit Edition) ed è necessario eseguire l'aggiornamento cumulativo 6 o versioni successive ([scaricare l'aggiornamento cumulativo 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.  <br/> |
|Microsoft SQL Server 2019 standard (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2017 standard (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2016 standard (64 bit Edition) con Service Pack 1 o versioni successive ed è necessario eseguire l'aggiornamento cumulativo di Skype for business 7 o versione successiva ([scaricare l'aggiornamento cumulativo di Skype for business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 standard (64 bit Edition) ed è necessario eseguire l'aggiornamento cumulativo 6 o versioni successive ([scaricare l'aggiornamento cumulativo 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 standard (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.  <br/> |
   
Se non si vede l'edizione di SQL Server che si vuole usare in questo elenco, non è possibile usarla.
  
- Sarà inoltre necessario installare SQL Server Reporting Services per il ruolo del server di monitoraggio.
- Per un back-end SQL ben connesso, la connessione al front-end di Skype for business dovrebbe essere locale e non in un collegamento a bassa velocità. 
- La condivisione delle terminazioni SQL tra due o più pool non è supportata.

### <a name="microsoft-exchange-storage"></a>Archiviazione di Microsoft Exchange
I file di contenuto della riunione, ad esempio le presentazioni di PowerPoint, vengono archiviati come allegati. Per archiviare i dati di archiviazione di Skype for business con i dati di conformità di Exchange, è necessario usare Exchange per la distribuzione di Exchange e verificare che le dimensioni massime dello spazio di archiviazione supportino l'archiviazione dei file di contenuto della riunione. È necessario distribuire Exchange prima di distribuire e abilitare l'archiviazione con l'opzione di integrazione di Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisiti hardware e software per l'archiviazione in Skype for Business Server 2015
  
L'archiviazione non è un ruolo predefinito del server, non è necessario installare un server separato per l'archiviazione. Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in tutti i pool di front end Enterprise Edition e in ogni server Standard Edition. Sarà necessario abilitare e pubblicare la topologia di archiviazione tramite Generatore di topologie.
    
L'archiviazione usa l'archiviazione dei file di Skype for Business Server per l'archiviazione temporanea di file di contenuto della riunione, quindi non è possibile configurare un archivio di file separato per l'archiviazione.
    
L'Accodamento messaggi Microsoft non è obbligatorio.
    
Sarà necessario configurare l'infrastruttura per l'archiviazione dello spazio di archiviazione. Questo include la scelta dello spazio di archiviazione di Exchange o archiviazione tramite SQL Server.   I requisiti dell'infrastruttura di archiviazione di Skype for Business Server sono gli stessi della distribuzione di Skype for Business Server. Per informazioni dettagliate, vedere [requisiti per l'ambiente Skype for business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Per supportare gli utenti non residenti nei server Exchange o se non si vuole usare l'opzione di integrazione di Microsoft Exchange, è necessario distribuire archiviazione di archiviazione tramite un database SQL Server a 64 bit. 
    
È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account da usare per pubblicare la topologia include i diritti e le autorizzazioni di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) durante la pubblicazione della topologia. È anche possibile creare il database in un secondo momento, incluso come parte della procedura di installazione. Per informazioni dettagliate su SQL Server, vedere la [documentazione di SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
L'aumento di carico per l'archiviazione può essere significativo. Devi pertanto verificare che lo spazio su disco sia adeguato per i server front-end in cui è abilitata l'archiviazione.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Mirroring SQL, clustering SQL e SQL sempre attivati

È possibile usare il mirroring SQL o il clustering SQL con Skype for Business Server 2015, che è supportato. Il mirroring di SQL è configurato tramite il generatore di topologia di Skype for Business Server. Se si ha intenzione di configurare il clustering SQL, questo avviene in SQL Server.
  
Assicurarsi di avere una configurazione attiva/passiva per il clustering SQL, dato che è ciò che è supportato. Non condividere il nodo passivo con altre istanze SQL.
  
Per il clustering di failover è possibile avere i seguenti elementi:
  
Due nodi:
  
- Microsoft SQL Server 2019 standard (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.

- Microsoft SQL Server 2017 standard (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.

- Microsoft SQL Server 2016 standard (64 bit Edition) con Service Pack 1 o versioni successive. È consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2014 standard (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.
    
-  Microsoft SQL Server 2012 standard (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.

Sedici-nodo:

- Microsoft SQL Server 2019 Enterprise (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.

- Microsoft SQL Server 2017 Enterprise (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.

- Microsoft SQL Server 2016 Enterprise (64 bit Edition) con Service Pack 1 o versioni successive. È consigliabile eseguire il Service Pack più recente.
  
- Microsoft SQL Server 2014 Enterprise (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.
    
- Microsoft SQL Server 2012 Enterprise (64 bit Edition) e si consiglia di eseguire con il Service Pack più recente.

> [!IMPORTANT]
> Per l'aggiornamento, è consigliabile verificare che nei server front-end sia installato almeno SQL Server 2012 SP1 prima dell'aggiornamento. [Ecco un collegamento](https://www.microsoft.com/download/details.aspx?id=35575) a SP1 se si vuole scaricarlo subito.
  
Per altre informazioni sul mirroring SQL, è disponibile un server back-end a disponibilità elevata nell'argomento Skype for Business Server 2015. Configurare il clustering di SQL Server per Skype for Business Server 2015 è la procedura per preparare il clustering. Sono inoltre disponibili ulteriori collegamenti nel clustering di failover per SQL, per [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)e [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Nuovo della versione di 2015 è il supporto di SQL always on. È supportata e si può leggere altre informazioni sul [server back-end disponibilità elevata in Skype for Business server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) argomento.

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software che deve essere installato prima di una distribuzione di Skype for Business Server 2015
<a name="Software"> </a>

Ci sono alcune operazioni che è necessario installare o configurare per qualsiasi server che esegue Skype for Business Server 2015 e che sono elencati di seguito. In seguito sono previsti requisiti aggiuntivi per ruoli server specifici.
  
> [Nota!] Skype for Business Server 2015 non supporta .NET Framework 4,8.
  
 **Tutti i server:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Windows PowerShell 3,0  <br/> |Tutti i server Skype for Business Server richiedono l'installazione di Windows PowerShell 3,0.  <br/> • Se si sta eseguendo l'installazione in Windows Server 2012 o Windows Server 2012 R2, è impostato, perché è già presente.  <br/> • Se si esegue un aggiornamento in Windows Server 2008 R2, è possibile scaricare [Windows Management Framework 3,0](https://www.microsoft.com/download/details.aspx?id=34595) per accedervi. <br/> **Suggerimento:** Dopo avere installato il PowerShell corretto, verificare che sia BuildVersion 6.2.9200.0 o successiva passando al prompt di PowerShell e digitando `$PSVersionTable`. In questo articolo sono riportate le informazioni necessarie.  <br/> |
|Microsoft .NET Framework  <br/> |Servizi WCF è una **funzionalità** installata come funzionalità di Windows, in **Server Manager**non è necessario alcun download. <br/> • È necessario verificare che durante l'installazione di questa funzionalità o se è già installata e che si sta controllando che l'opzione di **attivazione http** sia anche selezionata e installata, come indicato di seguito: <br/> ![Screenshot che mostra l'opzione di attivazione HTTP nelle caratteristiche di .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Non preoccuparti se viene visualizzata una finestra popup aggiuntiva che indica che è necessario installare altre cose per l'attivazione http. Questo è normale, fare clic su OK e andare avanti. Se non viene visualizzata questa finestra, è preferibile che questi elementi siano già installati e procedere.  <br/> Microsoft .NET Framework viene in genere installato quando si installa Windows Server 2012 R2 o Windows Server 2016. Skype for Business Server funziona con le versioni seguenti di Microsoft .NET Framework:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (per Skype for Business Server CU 5 o versioni successive)  <br/>  .NET Framework 3,5 sarà probabilmente installato per impostazione predefinita nel computer Windows Server 2008 R2 (sicuramente verificare che prima di eseguire l'aggiornamento), ma in realtà non sarà presente nei server Windows Server 2012/Windows Server 2012 R2 (per le nuove installazioni). Per aggiungerlo, è necessario accedere all'unità o al supporto di installazione (la posizione in cui è stato installato Windows Server o in cui sono ora installati i file di installazione). Quindi procedere e installarlo come funzionalità da Server Manager e posizionare il puntatore sul supporto di installazione (in particolare la cartella **\sources\sxs** ) quando richiesto e continuare per installarlo. <br/> |
|Media Foundation  <br/> |Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2 Windows Media Format Runtime viene installato con Microsoft Media Foundation.  <br/> Tutti i server front-end e i server Standard Edition usati per le conferenze richiedono che Windows Media Format runtime esegua i file di Windows Media Audio (con estensione WMA) che vengono riprodotti dalle applicazioni Park, annuncio e Response Group per gli annunci e la musica.  <br/> |
|Windows Identity Foundation  <br/> |Per supportare scenari di autenticazione da server a server per Skype for Business Server 2015 è necessario Windows Identity Foundation 3,5.  <br/> • Per Windows Server 2012 e Windows Server 2012 R2, non è necessario scaricare nulla. Aprire **Server Manager**e accedere alla **procedura guidata Aggiungi ruoli e funzionalità**. **Windows Identity Foundation 3,5** è elencato nella sezione **caratteristiche** . Se è selezionata, sei bravo. In caso contrario, selezionarlo e fare clic su Avanti per raggiungere il pulsante **Installa** . <br/> |
|Strumenti di amministrazione del server remoto  <br/> |Strumenti di amministrazione del ruolo: strumenti AD DS e AD LDS  <br/> |
   
 **I server front-end e il server Standard Edition richiedono anche:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS è necessario in tutti i server front-end e in tutti i server Standard Edition, con i seguenti moduli selezionati:  <br/> • Caratteristiche HTTP comuni: documento predefinito, errori HTTP, contenuto statico  <br/> • Integrità e diagnostica: registrazione HTTP, strumenti di registrazione, traccia  <br/> • Prestazioni: compressione del contenuto statico, compressione del contenuto dinamico  <br/> • Sicurezza: filtro delle richieste, autenticazione del mapping dei certificati client, autenticazione di Windows  <br/> • Sviluppo di applicazioni: estensibilità .NET 3,5, Extensibility .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, estensioni ISAPI, filtri ISAPI  <br/> • Strumenti di gestione: console di gestione IIS, script e strumenti di gestione di IIS  <br/> Dobbiamo anche notare che è necessario anche l'accesso anonimo, ma si ottiene che quando si installa IIS, in modo da non avere un posto in cui selezionarlo nell'elenco.  <br/> |
|Runtime in formato Windows Media  <br/> | Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, è necessario installare la funzionalità **Media Foundation** in **Server Manager**. A questo punto, puoi avviare l'installazione di Skype for Business Server 2015 senza questo, ma ti verrà richiesto di installarlo e quindi riavviare il server prima che l'installazione di Skype for Business Server 2015 continui. Meglio farlo prima del tempo. <br/> |
|Silverlight  <br/> |È possibile installare la versione più recente di Silverlight in [questo collegamento](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Potrebbe essere necessario abilitare l'esplorazione della directory anche se si usa un bilanciamento del carico. In caso contrario, verrà caricata una pagina vuota in cui il bilanciamento del carico potrebbe considerare un errore. 

Per aiutarti, ecco uno script di PowerShell di esempio che puoi eseguire per automatizzare questa operazione:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Il comando Cerca i file di origine in un ordine specifico. Se si è online, il comando accede a Windows Update. Tuttavia, se si è offline, è necessario assicurarsi che i file di origine siano disponibili per il comando. Per altre informazioni sull'uso di PowerShell per l'installazione di ruoli e funzionalità, vedere [installare o disinstallare ruoli, servizi ruolo o funzionalità](https://technet.microsoft.com/library/hh831809.aspx) non dimenticare di eseguire nuovamente Windows Update dopo l'installazione dei prerequisiti, anche se si usa il comando di PowerShell.

 **Gli amministratori hanno anche bisogno di:**
  
IIS, con i moduli seguenti selezionati:
  
- Caratteristiche HTTP comuni
    
  - Documento predefinito
    
  - Errori HTTP
    
  - Contenuto statico
    
- Integrità e diagnostica
    
  - Registrazione HTTP
    
  - Strumenti di registrazione
    
  - Traccia
    
- Prestazioni
    
  - Compressione del contenuto statico
    
- Sicurezza
    
  - Filtro delle richieste
    
  - Autenticazione del mapping dei certificati client
    
  - Autenticazione di Windows
    
- Sviluppo di applicazioni
    
  - Estensibilità .NET 3,5
    
  - Estensibilità .NET 4,5
    
  - ASP.NET 3,5
    
  - ASP.NET 4,5
    
  - Estensione ISAPI
    
  - Filtri ISAPI
    
Se si sta chiedendo, si tratta dello stesso set di moduli dei server front-end e dei server Standard Edition, con gli strumenti di compressione e gestione del contenuto dinamico a sinistra.
  
Ecco anche il codice di PowerShell seguente:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Anche i server di chat persistenti devono:**
  
Accodamento messaggi, denominato anche MSMQ. Si tratta di un componente di Windows Server e può essere installato nella sezione funzionalità in Server Manager. Per saperne di più, vedere [installazione e gestione di Accodamento messaggi](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Ultime considerazioni:**
  
Non installare alcun software client del server Microsoft Internet Security and Acceleration (ISA) o qualsiasi altro software LSP (Layered Service Providers) Winsock (eventuali firewall di terze parti o software di controllo della rete anti-virus verrebbero inclusi qui) in qualsiasi server front-end o server di mediazione autonomo. La scarsità delle prestazioni del traffico multimediale è stata visualizzata durante l'installazione del software.
  

