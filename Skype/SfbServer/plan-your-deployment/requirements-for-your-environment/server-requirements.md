---
title: Requisiti del server per Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "Riepilogo: preparare i server Skype for Business Server 2015 con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e i suggerimenti sono qui per garantire un'installazione e una distribuzione corretta della server farm."
ms.openlocfilehash: d1a80fd991b8fe078f2a53d73e7f37eb66903220
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104042"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisiti del server per Skype for Business Server 2015
 
**Riepilogo:** Preparare i server Skype for Business Server 2015 con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e i suggerimenti sono qui per garantire un'installazione e una distribuzione corretta della server farm.

Se si cercano requisiti ambientali, ad esempio Active Directory, DNS o certificati, è possibile consultare il documento Requisiti ambientali per [Skype for Business Server 2015.](environmental-requirements.md)
  
Come ci si potrebbe aspettare, è necessario prepararsi prima di iniziare a distribuire Skype for Business Server 2015. In questo articolo viene illustrata la pianificazione degli elementi seguenti:
  
- [Hardware per Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemi operativi per Skype for Business Server 2015](server-requirements.md#OS)
  
- [Database back-end che funzionano con Skype for Business Server 2015](server-requirements.md#DBs)
  
- [Software da installare prima di una distribuzione di Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware per Skype for Business Server 2015
<a name="Hardware"> </a>

Ora che la topologia è in calo (e in caso contrario, è possibile consultare l'argomento [Topology Basics for Skype for Business Server 2015),](../../plan-your-deployment/topology-basics/topology-basics.md) è il momento di pensare ai server. I server Skype for Business Server 2015 richiedono hardware a 64 bit. Di seguito sono riportati i suggerimenti per l'hardware. Questi non sono requisiti, ma riflettono i requisiti necessari per ottenere prestazioni ottimali. Abbiamo una documentazione sulla pianificazione della capacità che ti aiuterà a determinare se è necessario più di questo, a seconda delle circostanze.
  
Hardware consigliato per Front End Server, back-end server, server Standard Edition e server Chat persistente:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Doppio processore a 64 bit, hex-core, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |UNO DEI SEGUENTI:  <br/> • 8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco (due dischi con RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili a 8 unità disco meccaniche da 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a doppia porta, 1 Gbps o superiore (è possibile utilizzare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed non sono **supportate** per Front End Server, back-end server, server Standard Edition e server Chat persistente. <br/> Se non sono esposti al sistema operativo e vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multi-homed ed è supportato.  <br/> |
   
Hardware consigliato per server perimetrali, Mediation Server autonomi, Server di interoperabilità video e Director:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore doppio a 64 bit, quad-core, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |16 gigabyte.  <br/> |
|Disco  <br/> |UNO DEI SEGUENTI:  <br/> • 4 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione RAID 1 2x).  <br/> OPPURE  <br/> • Unità A stato solido (SSD) in grado di fornire lo stesso spazio libero e prestazioni simili a 4 unità disco meccaniche da 1.0000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a doppia porta, 1 Gbps o superiore (è possibile utilizzare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non sono** supportate per Video Interop Server e Director. <br/> I server perimetrali richiederanno due interfacce di rete che sono schede di rete a doppia porta, 1 Gbps o superiore (o due schede di rete associate, per un totale di quattro, ogni coppia viene associata a un singolo indirizzo MAC e a un singolo indirizzo IP, per un totale di due coppie).  <br/> Nei Mediation Server autonomi è supportata l'installazione di schede di interfaccia di rete aggiuntive per consentire la configurazione di uno specifico indirizzo IP PSTN.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemi operativi per Skype for Business Server 2015
<a name="OS"> </a>

Dopo aver installato l'hardware, è necessario installare i sistemi operativi. Si tratta del sistema operativo che consente di installare e utilizzare correttamente Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (è necessario l'aggiornamento cumulativo di Skype for Business 9 o versione successiva). <br/> |Windows Server 2016 (È necessario l'aggiornamento cumulativo di Skype for Business 5 o versione successiva. Per ulteriori informazioni, vedere [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Sistema operativo Windows Server 2012 R2 Datacenter con tutti gli aggiornamenti necessari installati.  <br/> |Sistema operativo Windows Server 2012 R2 Standard con tutti gli aggiornamenti necessari installati.  <br/> |
|Sistema operativo Windows Server 2012 Datacenter con tutti gli aggiornamenti necessari installati.  <br/> |Sistema operativo Windows Server 2012 Standard con tutti gli aggiornamenti necessari installati.  <br/> |
   
Se non è in questo elenco, non funzionerà correttamente, non provare per le nuove installazioni di Skype for Business Server 2015.

> [!NOTE]
> L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013. È necessario distribuire un pool separato ed eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso. Tutti i server di un pool devono avere la stessa versione del sistema operativo.
  
> [!NOTE]
> Potresti aver notato che Windows Server 2008 R2 non è in questo elenco. Questo perché è consigliabile windows Server 2012 R2 per tutti i nuovi server da usare per SFB. È consigliabile utilizzare Windows Server 2008 R2 solo se sono già installati server esistenti con Lync Server 2013 e si intende eseguire un aggiornamento sul posto. Windows Server 2008 R2 ha raggiunto la fine del ciclo di vita del supporto mainstream il 13/01/2015 e raggiungerà la fine del ciclo di vita del supporto il 14/01/2020.
  
Oltre al Service Pack più recente, è necessario verificare che gli aggiornamenti seguenti siano installati laddove pertinenti:
  
- Per Windows Server 2012, l'articolo della Knowledge Base 2858668 deve essere installato prima di un aggiornamento. [Scaricalo qui](https://support.microsoft.com/kb/2858668/).
    
- Se si dispone di Windows Server 2012 R2, installare l'articolo della Knowledge Base 2982006 prima dell'aggiornamento. [Si trova qui](https://support.microsoft.com/kb/2982006/).
    
- Se si esegue l'aggiornamento in una casella di Windows Server 2008 R2 (vedere la nota precedente), è necessario installare prima l'articolo della Knowledge Base 2533623. [È a questo collegamento](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Database back-end che funzionano con Skype for Business Server 2015
<a name="DBs"> </a>


Quando si installa Skype for Business Server 2015 Standard Edition, sarà installato automaticamente anche SQL Server 2014 Express (edizione a 64 bit).
  
Skype for Business Server 2015 Enterprise Edition è un po' più complicato, ma l'elenco supportato è riportato di seguito (tutto è un'edizione a 64 bit, noterai, non usare le edizioni a 32 bit):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2017 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2016 Enterprise (edizione a 64 bit) con Service Pack 1 o versione successiva ed è necessario eseguire l'aggiornamento cumulativo di Skype for Business 7 o versione successiva ( scaricare l'aggiornamento cumulativo[di Skype for Business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (edizione a 64 bit) ed è necessario eseguire l'aggiornamento cumulativo 6 o versione successiva ([scaricare l'aggiornamento cumulativo 6).](https://support.microsoft.com/kb/3031047/)  <br/> |Microsoft SQL Server 2012 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.  <br/> |
|Microsoft SQL Server 2019 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2017 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente. <br/> |Microsoft SQL Server 2016 Standard (edizione a 64 bit) con Service Pack 1 o versione successiva ed è necessario eseguire l'aggiornamento cumulativo di Skype for Business 7 o versione successiva ( scaricare l'aggiornamento cumulativo di[Skype for Business](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (edizione a 64 bit) ed è necessario eseguire l'aggiornamento cumulativo 6 o versione successiva ([scaricare l'aggiornamento cumulativo 6](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.  <br/> |
   
Se l'edizione SQL Server che si desidera utilizzare non è elencata qui, non è possibile utilizzarla.
  
- Sarà inoltre necessario installare SQL Server Reporting Services per il ruolo Monitoring Server.
- Per una connessione SQL back-end, la connessione al front-end Skype for Business deve essere locale e non attraverso un collegamento a bassa velocità. 
- La SQL back-end tra due o più pool non è supportata.

### <a name="microsoft-exchange-storage"></a>Archiviazione di Microsoft Exchange
I file di contenuto delle riunioni, ad esempio le presentazioni PowerPoint, sono archiviate come allegati. Se si desidera archiviare i dati di archiviazione di Skype for Business con i dati di conformità di Exchange, è necessario utilizzare Exchange per la distribuzione di Exchange e verificare che la dimensione massima di archiviazione supporti l'archiviazione dei file di contenuto delle riunioni. È necessario distribuire Exchange prima di distribuire e abilitare l'archiviazione utilizzando l'opzione di integrazione di Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisiti hardware e software per l'archiviazione in Skype for Business Server 2015
  
L'archiviazione non è un ruolo del server definito, non è necessario installare un server separato per l'archiviazione. Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni pool Enterprise Edition Front End e in ogni Server Standard. Sarà necessario abilitare e pubblicare la topologia di archiviazione utilizzando Generatore di topologie.
    
L'archiviazione usa l'archiviazione dei file di Skype for Business Server per l'archiviazione temporanea dei file di contenuto delle riunioni, quindi non si configura un archivio file separato per l'archiviazione.
    
Accodamento messaggi Microsoft non è necessario.
    
Sarà necessario configurare l'infrastruttura per l'archiviazione dell'archiviazione. Ciò include la scelta dell'archiviazione di Exchange o dell'archiviazione SQL Server.   I requisiti dell'infrastruttura di archiviazione di Skype for Business Server sono gli stessi per la distribuzione di Skype for Business Server. Per informazioni dettagliate, [vedi Requisiti per l'ambiente Skype for Business.](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 
  
> [!NOTE]
> Per supportare gli utenti che non sono ospitati su server Exchange o se non si desidera utilizzare l'opzione di integrazione di Microsoft Exchange, è necessario distribuire l'archiviazione utilizzando un database SQL Server a 64 bit. 
    
È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) quando si pubblica la topologia. È anche possibile creare il database successivamente, anche come parte della procedura di installazione. Per informazioni dettagliate SQL Server, vedere la [documentazione SQL Server.](/sql/sql-server/)
    
L'aumento del carico per l'archiviazione può essere significativo. È pertanto consigliabile verificare che lo spazio su disco sia adeguato per i Front End Server in cui è abilitata l'archiviazione.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL mirroring, SQL clustering e SQL sempre attivo

È possibile usare il mirroring SQL o SQL clustering con Skype for Business Server 2015, è supportato. SQL mirroring è configurato tramite Generatore di topologie di Skype for Business Server. Se si è intenzionati a configurare SQL clustering, questa operazione viene eseguita in SQL Server.
  
Assicurati di avere una configurazione attiva/passiva per SQL Clustering, in quanto è supportata. Non condividere il nodo passivo con altre SQL istanza.
  
Per il clustering di failover, è possibile disporre di quanto segue:
  
Due nodi:
  
- Microsoft SQL Server 2019 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

- Microsoft SQL Server 2017 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

- Microsoft SQL Server 2016 Standard (edizione a 64 bit) con Service Pack 1 o versione successiva. È consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2014 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.
    
-  Microsoft SQL Server 2012 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

Sedici nodi:

- Microsoft SQL Server 2019 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

- Microsoft SQL Server 2017 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

- Microsoft SQL Server 2016 Enterprise (edizione a 64 bit) con Service Pack 1 o versione successiva. È consigliabile eseguire il Service Pack più recente.
  
- Microsoft SQL Server 2014 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.
    
- Microsoft SQL Server 2012 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

> [!IMPORTANT]
> Per l'aggiornamento, è necessario assicurarsi che nei Front End Server sia installato almeno SQL Server 2012 SP1 prima dell'aggiornamento. [Ecco un collegamento a](https://www.microsoft.com/download/details.aspx?id=35575) SP1 se si desidera scaricarlo subito.
  
Se è necessario leggere altre informazioni sul mirroring SQL, è disponibile un server back-end a disponibilità elevata in Skype for Business Server 2015. Configurare SQL Server clustering per Skype for Business Server 2015 è la procedura per prepararsi al clustering. Sono inoltre disponibili ulteriori collegamenti al clustering di failover per SQL, per [la versione 2014,](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) [2012](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))e [2008.](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105))
  
> [!NOTE]
> Una novità della versione 2015 è il supporto di SQL Always On. È supportato ed è possibile leggere ulteriori informazioni nell'argomento [Back End Server high availability in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> SQL mirroring è disponibile in Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software da installare prima di una distribuzione di Skype for Business Server 2015
<a name="Software"> </a>

Ci sono alcuni aspetti che dovrai installare o configurare per qualsiasi server che esegue Skype for Business Server 2015 e sono elencati di seguito. Dopo di che sono requisiti aggiuntivi per ruoli del server specifici.

  
 **Tutti i server:**
  
|**Software/Ruolo**|**Dettagli**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tutti i server Skype for Business Server devono Windows PowerShell 3.0.  <br/> • Se stai eseguendo l'installazione in Windows Server 2012 o Windows Server 2012 R2, sei impostato, perché è già presente.  <br/> • Se si esegue un aggiornamento in Windows Server 2008 R2, è possibile scaricare il Windows Management Framework [3.0](https://www.microsoft.com/download/details.aspx?id=34595) per ottenerlo. <br/> **Suggerimento:** Dopo aver installato PowerShell corretto, verificare che sia BuildVersion 6.2.9200.0 o versione successiva andando al prompt di PowerShell e digitando `$PSVersionTable` . In questo modo dovrebbero essere visualizzate le informazioni necessarie.  <br/> |
|Microsoft .NET Framework  <br/> |I servizi WCF sono un elemento **Feature** installato come funzionalità di Windows, in **Server Manager** non sono necessari download. <br/> • È necessario verificare, quando si installa questa funzionalità o se è già installata e si sta controllando, che anche l'opzione Attivazione **HTTP** sia selezionata e installata, come indicato di seguito: <br/> ![Screenshot che mostra l'opzione Attivazione HTTP nelle .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) Non preoccuparti se ricevi un popup aggiuntivo che dice che è necessario installare altri elementi per l'installazione dell'attivazione HTTP. È normale, fare clic su OK e procedere. Se non viene visualizzato questo popup, presupporre che tali elementi siano già installati e procedere.  <br/> Microsoft .NET Framework viene in genere installato quando vengono installati Windows Server 2012 R2 o Windows Server 2016. Skype for Business Server funziona con le seguenti versioni di Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (per Skype for Business Server CU 5 o versioni successive)  <br/> • .NET 4.7.2 (per Skype for Business Server CU 6 o versioni successive)  <br/>  • .NET 4.8 (per Skype for Business Server CU 9 o versioni successive) <br/>  .NET Framework 3.5 verrà probabilmente installato per impostazione predefinita nel computer Windows Server 2008 R2 (sicuramente verificare di essere sicuri prima di eseguire l'aggiornamento), ma in realtà non sarà nei server Windows Server 2012/Windows Server 2012 R2 (per le nuove installazioni). Per aggiungerlo, è necessario accedere all'unità o al supporto di installazione (la posizione da cui è stato installato Windows Server o la posizione in cui si trova ora i file di installazione). Quindi, andare avanti e installarlo come funzionalità da Server Manager e puntare al supporto di installazione (in particolare la **cartella \sources\sxs)** quando richiesto e continuare a installarlo. <br/> |
|Media Foundation  <br/> |Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2 Windows Media Format Runtime viene installato con Microsoft Media Foundation.  <br/> Tutti i Front End Server e i server Standard Edition utilizzati per le conferenze richiedono Runtime formato Windows Media per eseguire i file Windows Media Audio (wma) riprodotti dalle applicazioni Parcheggio di chiamata, Annuncio e Response Group per annunci e musica.  <br/> |
|Windows Identity Foundation  <br/> |È necessario Windows Identity Foundation 3.5 per supportare gli scenari di autenticazione da server a server per Skype for Business Server 2015.  <br/> • Per Windows Server 2012 e Windows Server 2012 R2, non è necessario scaricare nulla. Aprire **Server Manager** e passare all'Aggiunta guidata ruoli e **funzionalità.** **Windows Identity Foundation 3.5** è elencato nella **sezione** Funzionalità. Se è selezionata, sei a posto. In caso contrario, selezionarlo e fare clic su Avanti per accedere **al pulsante** Installa. <br/> |
|Strumenti di amministrazione remota del server  <br/> |Strumenti di amministrazione dei ruoli: strumenti di Servizi di dominio Active Directory e AD LDS  <br/> |
   
 **I Front End Server e il server Standard Edition necessitano inoltre di:**
  
|**Software/Ruolo**|**Dettagli**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS è necessario in tutti i Front End Server, nonché in tutti i server Standard Edition, con i moduli seguenti selezionati:  <br/> • Funzionalità HTTP comuni: documento predefinito, errori HTTP, contenuto statico  <br/> • Integrità e diagnostica: registrazione HTTP, strumenti di registrazione, traccia  <br/> • Prestazioni: Compressione contenuto statico, Compressione contenuto dinamico  <br/> • Sicurezza: Filtro richieste, Autenticazione mapping certificati client, Autenticazione di Windows  <br/> • Sviluppo di applicazioni: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ESTENSIONI ISAPI, filtri ISAPI  <br/> • Strumenti di gestione: console di gestione IIS, script e strumenti di gestione IIS  <br/> È inoltre necessario notare che è necessario l'accesso anonimo, ma è possibile farlo quando si installa IIS, in modo da non avere una posizione per selezionarla nell'elenco.  <br/> |
|Runtime formato Windows Media  <br/> | Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, è necessario installare la funzionalità **Media Foundation** in **Server Manager.** A questo punto, è possibile avviare l'installazione di Skype for Business Server 2015 senza questa, ma verrà richiesto di installarla e quindi riavviare il server, prima che l'installazione di Skype for Business Server 2015 continui. È meglio farlo in anticipo. <br/> |
|Silverlight  <br/> |È possibile installare la versione più recente di Silverlight a [questo collegamento.](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> Potrebbe inoltre essere necessario abilitare l'esplorazione della directory se si utilizza un servizio di bilanciamento del carico. In caso contrario, verrà caricata una pagina vuota che il servizio di bilanciamento del carico potrebbe considerare un errore. 

Per aiutarti, ecco uno script di PowerShell di esempio che puoi eseguire per automatizzare questa operazione:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Il comando cerca i file di origine in un ordine specifico. Se si è online, il comando accede a Windows Update. Tuttavia, se si è offline, è necessario verificare che i file di origine siano disponibili per il comando. Per ulteriori informazioni sull'utilizzo di PowerShell per installare ruoli e funzionalità, vedere [Install or Uninstall Roles, Role Services, or Features](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.

 **I director hanno anche bisogno di:**
  
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
    
  - Filtro richieste
    
  - Autenticazione mapping certificati client
    
  - Autenticazione di Windows
    
- Sviluppo di applicazioni
    
  - Estendibilità .NET 3.5
    
  - Estendibilità .NET 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - Estensione ISAPI
    
  - Filtri ISAPI
    
Se lo si desidera, si tratta dello stesso modulo impostato per i Front End Server e i server Standard Edition, con gli strumenti di gestione e compressione del contenuto dinamico non disponibili.
  
Di seguito è riportato anche il codice di PowerShell:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **I server Chat persistente necessitano inoltre di:**
  
Accodamento messaggi, denominato anche MSMQ. Si tratta di un componente di Windows Server ed è possibile installarlo nella sezione Funzionalità di Server Manager. Per ulteriori informazioni, vedere [Installing and Managing Message Queuing](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11)).
  
 **Ultimi pensieri:**
  
Non installare alcun software client Microsoft Internet Security and Acceleration (ISA) Server o qualsiasi altro software Winsock Layered Service Provider (LSP) (eventuali firewall di terze parti o software di ispezione della rete antivirus incluso qui) in uno dei server front-end o mediation server autonomi. Le prestazioni del traffico multimediale scarse sono state osservate quando il software è installato.
