---
title: Requisiti del server per Skype for Business Server 2015
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
description: 'Sintesi: preparare i server Skype for Business Server 2015 con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e suggerimenti sono disponibili per garantire una corretta installazione e distribuzione della server farm.'
ms.openlocfilehash: 02ccebca4eebef84638992dd88ba45040e733d19
ms.sourcegitcommit: b1f7f1435c5e72c2eea4069fbb0bea29b197cb80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342456"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisiti del server per Skype for Business Server 2015
 
**Riepilogo:** Preparare i server Skype for Business Server 2015 con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e suggerimenti sono disponibili per garantire una corretta installazione e distribuzione della server farm.

Se si cercano requisiti per l'ambiente, ad esempio Active Directory, DNS o certificati, è possibile consultare i [requisiti ambientali di Skype for Business Server 2015](environmental-requirements.md) doc.
  
Come si può immaginare, esistono alcuni preparativi da fare prima di iniziare a distribuire Skype for Business Server 2015. In questo articolo viene illustrata la pianificazione per le operazioni seguenti:
  
- [Hardware per Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemi operativi per Skype for Business Server 2015](server-requirements.md#OS)
  
- [Database back-end che funzioneranno con Skype for Business Server 2015](server-requirements.md#DBs)
  
- [Software che deve essere installato prima di una distribuzione di Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware per Skype for Business Server 2015
<a name="Hardware"> </a>

Dopo aver incassato la topologia (e, in caso contrario, è possibile consultare le [nozioni di base sulla topologia per l'argomento Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) ), è il momento di pensare ai server. I server Skype for Business Server 2015 richiederanno hardware a 64 bit. I suggerimenti per l'hardware sono riportati di seguito. Questi non sono requisiti, ma riflettono i requisiti necessari per ottenere prestazioni ottimali. La documentazione relativa alla pianificazione della capacità può essere utile per determinare se è necessario più di questo, a seconda delle circostanze.
  
Hardware consigliato per Front End Server, server back-end, server Standard Edition e server Chat persistente:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |processore duale a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |SIA  <br/> • 8 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (due dischi con RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili alle unità disco meccaniche a 8 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete Dual-Port, 1 Gbps o superiore (possono essere utilizzate 2 schede di rete, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non** sono supportate per Front End Server, server back-end, server Standard Edition e server Chat persistente. <br/> Fintanto che non sono esposti al sistema operativo e che vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multihomed ed è supportato.  <br/> |
   
Hardware consigliato per server perimetrali, Mediation Server autonomi, server di interoperabilità video e direttori:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |processore duale a 64 bit, quad-core, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |16 gigabyte.  <br/> |
|Disco  <br/> |SIA  <br/> • 4 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione di 2x RAID 1).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili alle unità disco meccaniche a 4 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete Dual-Port, 1 Gbps o superiore (possono essere utilizzate 2 schede di rete, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non** sono supportate per i server e i direttori di interoperabilità video. <br/> I server perimetrali richiedono due interfacce di rete che sono schede di rete Dual-Port, 1 Gbps o superiore (o due schede di rete abbinate, per un totale di quattro, ciascuna coppia viene affiancata da un singolo indirizzo MAC e da un singolo indirizzo IP, per un totale di due coppie).  <br/> In Mediation Server autonomi l'installazione di schede di interfaccia di rete (NIC) aggiuntive per consentire la configurazione di un indirizzo IP PSTN specifico è supportata.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemi operativi per Skype for Business Server 2015
<a name="OS"> </a>

Dopo aver installato l'hardware, è necessario installare i sistemi operativi (OS). Questi sono i sistemi operativi che consentono di installare e utilizzare con successo Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (è necessario l'aggiornamento cumulativo 9 o versione successiva di Skype for business). <br/> |Windows Server 2016 (è necessario l'aggiornamento cumulativo di Skype for business 5 o versione successiva. Per ulteriori informazioni, vedere [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 R2 Datacenter OS con tutti gli aggiornamenti necessari installati.  <br/> |Sistema operativo Windows Server 2012 R2 Standard con tutti gli aggiornamenti necessari installati.  <br/> |
|Windows Server 2012 Datacenter OS con tutti gli aggiornamenti necessari installati.  <br/> |Sistema operativo Windows Server 2012 Standard con tutti gli aggiornamenti necessari installati.  <br/> |
   
Se non è presente nell'elenco, non funzionerà correttamente, non provare a utilizzare le nuove installazioni di Skype for Business Server 2015.

> [!NOTE]
> L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013. È necessario distribuire un pool separato ed eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso. Tutti i server di un pool devono avere la stessa versione del sistema operativo.
  
> [!NOTE]
> Potrebbe essere stato notato che Windows Server 2008 R2 non è presente nell'elenco. Ciò è dovuto al fatto che è consigliabile utilizzare Windows Server 2012 R2 per tutti i nuovi server che devono essere utilizzati per questo. È consigliabile utilizzare Windows Server 2008 R2 solo quando si dispone di server esistenti con Lync Server 2013 già installato e si intende eseguire un aggiornamento sul posto. Windows Server 2008 R2 ha raggiunto la fine del ciclo di vita del supporto mainstream su 1/13/2015 e raggiungerà la fine del relativo ciclo di vita del supporto su 1/14/2020.
  
Oltre al Service Pack più recente, è necessario assicurarsi che siano installati gli aggiornamenti seguenti, se rilevanti:
  
- Per Windows Server 2012, l'articolo KB 2858668 deve essere installato prima di un aggiornamento. [Ottenerlo qui](https://support.microsoft.com/kb/2858668/).
    
- Se si dispone di Windows Server 2012 R2, installare l'articolo KB 2982006 prima dell'aggiornamento. [Si trova qui](https://support.microsoft.com/kb/2982006/).
    
- Se si esegue l'aggiornamento su una finestra di Windows Server 2008 R2 (vedere la nota precedente), è necessario installare prima l'articolo KB 2533623. È [a questo collegamento](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Database back-end che funzioneranno con Skype for Business Server 2015
<a name="DBs"> </a>


Durante l'installazione di Skype for Business Server 2015 Standard Edition, è installato automaticamente anche SQL Server 2014 Express (64-bit Edition).
  
Skype for Business Server 2015 Enterprise Edition è un po' più complicato, ma l'elenco supportato è il seguente (tutto è a 64 bit, si noterà, si prega di non utilizzare edizioni a 32 bit):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2017 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2016 Enterprise (edizione 64 bit) con Service Pack 1 o versioni successive ed è necessario eseguire l'aggiornamento cumulativo di Skype for business 7 o versione successiva ([scaricare l'aggiornamento cumulativo di Skype for business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (edizione 64 bit) ed è necessario eseguire l'aggiornamento cumulativo 6 o versioni successive ([scaricare l'aggiornamento cumulativo 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.  <br/> |
|Microsoft SQL Server 2019 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2017 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2016 standard (64 bit Edition) con Service Pack 1 o versioni successive ed è necessario eseguire l'aggiornamento cumulativo di Skype for business 7 o versione successiva ([scaricare l'aggiornamento cumulativo di Skype for business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 standard (versione 64 bit) ed è necessario eseguire l'aggiornamento cumulativo 6 o versioni successive ([scaricare l'aggiornamento cumulativo 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.  <br/> |
   
Se non viene visualizzata la versione di SQL Server che si desidera utilizzare nell'elenco, non è possibile utilizzarla.
  
- Sarà inoltre necessario installare SQL Server Reporting Services per il ruolo Monitoring Server.
- Per un back-end SQL ben connesso, la connessione al front-end di Skype for business dovrebbe essere locale e non in un collegamento a bassa velocità. 
- La condivisione di back-end SQL tra due o più pool non è supportata.

### <a name="microsoft-exchange-storage"></a>Archiviazione di Microsoft Exchange
I file di contenuto delle riunioni, ad esempio le presentazioni PowerPoint, sono archiviate come allegati. Se si desidera archiviare i dati di archiviazione di Skype for business con i dati di conformità di Exchange, è necessario utilizzare Exchange per la distribuzione di Exchange e verificare che le dimensioni massime di archiviazione supportino l'archiviazione dei file di contenuto della riunione. È necessario distribuire Exchange prima della distribuzione e dell'abilitazione dell'archiviazione tramite l'opzione di integrazione di Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisiti hardware e software per l'archiviazione in Skype for Business Server 2015
  
L'archiviazione non è un ruolo del server definito, non è necessario installare un server separato per l'archiviazione. Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in tutti i pool Enterprise Edition front end e in tutti i server Standard Edition. Sarà necessario abilitare e pubblicare la topologia di archiviazione utilizzando Generatore di topologie.
    
L'archiviazione utilizza l'archiviazione file di Skype for Business Server per l'archiviazione temporanea dei file di contenuto della riunione, quindi non è necessario configurare un archivio file separato per l'archiviazione.
    
Accodamento messaggi Microsoft non è necessario.
    
Sarà necessario configurare l'infrastruttura per l'archiviazione. Ciò include la scelta dello spazio di archiviazione di Exchange o di archiviazione tramite SQL Server.   I requisiti dell'infrastruttura di archiviazione di Skype for Business Server sono uguali a quelli per la distribuzione di Skype for Business Server. Per informazioni dettagliate, vedere [requisiti per l'ambiente Skype for business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Per supportare gli utenti che non sono ospitati nei server di Exchange o se non si desidera utilizzare l'opzione di integrazione di Microsoft Exchange, è necessario distribuire l'archiviazione di archiviazione utilizzando un database di SQL Server a 64 bit. 
    
È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) quando si pubblica la topologia. È anche possibile creare il database successivamente, anche come parte della procedura di installazione. Per informazioni dettagliate su SQL Server, vedere la [documentazione di SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
L'aumento del carico per l'archiviazione può essere significativo. Pertanto, è necessario assicurarsi che lo spazio su disco sia adeguato per i front end server in cui l'archiviazione è abilitata.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Mirroring SQL, clustering SQL e SQL always on

È possibile usare il mirroring SQL o il clustering SQL con Skype for Business Server 2015, è supportato. Il mirroring di SQL è configurato tramite il generatore di topologie di Skype for Business Server. Se si è intenzionati a configurare il clustering SQL, questo viene completato in SQL Server.
  
Assicurarsi di disporre di una configurazione attiva/passiva per il clustering SQL, in quanto è ciò che è supportato. Non condividere il nodo passivo con qualsiasi altra istanza di SQL.
  
Per il clustering di failover, è possibile disporre dei seguenti elementi:
  
Due nodi:
  
- Microsoft SQL Server 2019 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.

- Microsoft SQL Server 2017 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.

- Microsoft SQL Server 2016 standard (versione 64 bit) con Service Pack 1 o versione successiva. È consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2014 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.
    
-  Microsoft SQL Server 2012 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.

Sedici-nodo:

- Microsoft SQL Server 2019 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.

- Microsoft SQL Server 2017 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.

- Microsoft SQL Server 2016 Enterprise (edizione 64 bit) con Service Pack 1 o versione successiva. È consigliabile eseguire il Service Pack più recente.
  
- Microsoft SQL Server 2014 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.
    
- Microsoft SQL Server 2012 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.

> [!IMPORTANT]
> Per l'aggiornamento, è necessario verificare che nei server front end sia installato almeno SQL Server 2012 SP1 prima dell'aggiornamento. Di seguito viene indicato [un collegamento](https://www.microsoft.com/download/details.aspx?id=35575) al Service Pack 1 se si desidera scaricarlo immediatamente.
  
Per ulteriori informazioni sul mirroring SQL, è disponibile un server back-end a disponibilità elevata nell'argomento Skype for Business Server 2015. Configurare il clustering di SQL Server per Skype for Business Server 2015 è la procedura per ottenere il clustering pronto. Sono inoltre disponibili ulteriori collegamenti per il clustering di failover per SQL, per [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)e [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> New to the 2015 release è il supporto di SQL always on. È supportato e è possibile leggerne altre informazioni nell'argomento [disponibilità elevata del server back-end in Skype for Business server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software che deve essere installato prima di una distribuzione di Skype for Business Server 2015
<a name="Software"> </a>

Ci sono alcuni aspetti che devono essere installati o configurati per qualsiasi server che esegue Skype for Business Server 2015 e che sono elencati di seguito. Dopo di che sono necessari ulteriori requisiti per ruoli del server specifici.

  
 **Tutti i server:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tutti i server Skype for Business Server richiedono l'installazione di Windows PowerShell 3,0.  <br/> • Se si sta eseguendo l'installazione in Windows Server 2012 o Windows Server 2012 R2, è necessario che sia già presente.  <br/> • Se si esegue un aggiornamento su Windows Server 2008 R2, è possibile scaricare [Windows Management Framework 3,0](https://www.microsoft.com/download/details.aspx?id=34595) per ottenerlo. <br/> **Suggerimento:** Dopo aver installato la PowerShell corretta, verificare che sia BuildVersion 6.2.9200.0 o versione successiva, accedendo al prompt di PowerShell e digitando `$PSVersionTable` . In questo caso, vengono fornite le informazioni necessarie.  <br/> |
|Microsoft .NET Framework  <br/> |Servizi WCF è una **funzionalità** installata come funzionalità di Windows, in **Server Manager**, nessun download necessario. <br/> • È necessario assicurarsi che, quando si installa questa funzionalità, o se è già installato e si sta verificando, che l'opzione di **attivazione http** sia anche selezionata e installata, come indicato di seguito: <br/> ![Schermata che mostra l'opzione di attivazione HTTP nelle caratteristiche di .NET Framework 4,5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) Se si riceve un popup aggiuntivo, è necessario installare altre attività per l'installazione di HTTP. Questo è normale, fare clic su OK e andare avanti. Se non si riceve questo pop-up, si presuppone che tali elementi siano già stati installati e che sia possibile procedere.  <br/> Microsoft .NET Framework è in genere installato quando Windows Server 2012 R2 o Windows Server 2016 sono installati. Skype for Business Server è compatibile con le versioni di Microsoft .NET Framework seguenti:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (per i rilasci di Skype for Business Server CU 5 o versioni successive)  <br/> • .NET 4.7.2 (per Skype for Business Server CU 6 o versioni successive)  <br/>  • .NET 4,8 (per Skype for Business Server CU 9 o versioni successive) <br/>  .NET Framework 3,5 è probabile che sia installato per impostazione predefinita nel computer con Windows Server 2008 R2 (verificare definitivamente prima di eseguire l'aggiornamento), ma in realtà non sarà presente nei server Windows Server 2012/Windows Server 2012 R2 (per le nuove installazioni). Per aggiungerlo, è necessario accedere all'unità o al supporto di installazione (la posizione in cui è stato installato Windows Server o i file di installazione). Quindi, procedere e installarlo come caratteristica da Server Manager, quindi scegliere il supporto di installazione (in particolare la cartella **\sources\sxs** ) quando richiesto e continuare a installarlo. <br/> |
|Media Foundation  <br/> |Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2 il runtime del formato Windows Media viene installato con Microsoft Media Foundation.  <br/> Tutti i Front End Server e i server Standard Edition utilizzati per le conferenze richiedono il runtime del formato Windows Media per l'esecuzione dei file di Windows Media Audio (con estensione WMA) che le applicazioni Parcheggio di chiamata, annuncio e Response Group svolgono per gli annunci e la musica.  <br/> |
|Windows Identity Foundation  <br/> |È necessario che Windows Identity Foundation 3,5 supporti gli scenari di autenticazione da server a server per Skype for Business Server 2015.  <br/> • Per Windows Server 2012 e Windows Server 2012 R2, non è necessario scaricare nulla. Aprire **Server Manager**e passare alla **procedura guidata Aggiungi ruoli e funzionalità**. **Windows Identity Foundation 3,5** è elencato nella sezione **features** . Se è selezionata, si è a posto. In caso contrario, selezionarlo e fare clic su Avanti per raggiungere il pulsante di **installazione** . <br/> |
|Strumenti di amministrazione remota del server  <br/> |Strumenti di amministrazione del ruolo: strumenti di servizi di dominio Active Directory e AD LDS  <br/> |
   
 **È inoltre necessario che i Front End Server e il server Standard Edition siano:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS è necessario su tutti i Front End Server, nonché su tutti i server Standard Edition, con i seguenti moduli selezionati:  <br/> • Caratteristiche HTTP comuni: documento predefinito, errori HTTP, contenuto statico  <br/> • Integrità e diagnostica: registrazione HTTP, strumenti di registrazione, tracciabilità  <br/> • Prestazioni: compressione del contenuto statico, compressione del contenuto dinamico  <br/> • Sicurezza: filtro delle richieste, autenticazione del mapping dei certificati client, autenticazione di Windows  <br/> • Sviluppo di applicazioni: estensibilità .NET 3,5, Extensibility .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, estensioni ISAPI, filtri ISAPI  <br/> • Strumenti di gestione: console di gestione IIS, script e strumenti di gestione di IIS  <br/> È inoltre necessario tenere presente che è necessaria anche l'accesso anonimo, ma quando si installa IIS, non si dispone di un posto per selezionarlo nell'elenco.  <br/> |
|Runtime formato Windows Media  <br/> | Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, è necessario installare la funzionalità di **Media Foundation** in **Server Manager**. A questo punto, è possibile avviare l'installazione di Skype for Business Server 2015 senza questo, ma verrà richiesto di installarlo e quindi riavviare il server, prima che l'installazione di Skype for Business Server 2015 prosegua. Meglio farlo prima del tempo. <br/> |
|Silverlight  <br/> |È possibile installare la versione più recente di Silverlight in [questo collegamento](https://www.microsoft.com/silverlight/).  <br/> |
   
> [!NOTE] 
> Se si utilizza un bilanciamento del carico, potrebbe essere necessario abilitare l'esplorazione della directory. In caso contrario, verrà caricata una pagina vuota che potrebbe prendere in considerazione un errore. 

Per ottenere assistenza, ecco uno script di PowerShell di esempio che è possibile eseguire per automatizzare la seguente operazione:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Il comando Cerca i file di origine in un ordine specifico. Se si è online, il comando accede a Windows Update. Tuttavia, se non si è in linea, è necessario verificare che i file di origine siano disponibili per il comando. Per ulteriori informazioni sull'utilizzo di PowerShell per l'installazione di ruoli e funzionalità, vedere [installare o disinstallare ruoli, servizi ruolo o funzionalità](https://technet.microsoft.com/library/hh831809.aspx) non dimenticare di eseguire di nuovo Windows Update dopo aver installato i prerequisiti, anche se si utilizza il comando di PowerShell.

 **I direttori devono inoltre:**
  
IIS, con i seguenti moduli selezionati:
  
- Caratteristiche HTTP comuni
    
  - Documento predefinito
    
  - Errori HTTP
    
  - Contenuto statico
    
- Integrità e diagnostica
    
  - Registrazione HTTP
    
  - Strumenti di registrazione
    
  - Analisi della
    
- Prestazioni
    
  - Compressione del contenuto statico
    
- Sicurezza
    
  - Filtro richieste
    
  - Autenticazione mapping certificati client
    
  - Autenticazione di Windows
    
- Sviluppo di applicazioni
    
  - Estensibilità .NET 3,5
    
  - Estendibilità .NET 4.5
    
  - ASP.NET 3,5
    
  - ASP.NET 4,5
    
  - Estensione ISAPI
    
  - Filtri ISAPI
    
Se si sta chiedendo, è lo stesso set di moduli dei front end server e dei server Standard Edition, con gli strumenti di gestione e compressione del contenuto dinamici lasciati fuori.
  
Anche per questo è presente un codice PowerShell:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **È inoltre necessario disporre di server Chat persistente:**
  
Accodamento messaggi, denominato anche MSMQ. Si tratta di un componente di Windows Server ed è possibile installarlo nella sezione funzionalità in Server Manager. Per ulteriori informazioni, vedere [l'installazione e la gestione di Accodamento messaggi](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Ultimo pensiero:**
  
Non installare alcun software client del server Microsoft Internet Security and Acceleration (ISA) o qualsiasi altro software LSP (Layered Service Providers) di Winsock (qualsiasi software di controllo di terze parti o firewall potrebbe essere incluso in questo articolo) in uno dei server front end o di Mediation Server autonomi. Le scarse prestazioni del traffico multimediale sono state osservate quando il software è installato.
  

