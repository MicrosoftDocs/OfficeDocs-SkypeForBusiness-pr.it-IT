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
description: "Riepilogo: preparare i server Skype for Business Server 2015 con questo argomento. L'hardware, il sistema operativo, i database, il software, tutti i requisiti di sistema e i suggerimenti sono qui per garantire una corretta installazione e distribuzione della server farm."
ms.openlocfilehash: b1e7e37e46d0f3f547ed843ce2510d8445a34267
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832076"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Requisiti del server per Skype for Business Server 2015
 
**Riepilogo:** Preparare i server Skype for Business Server 2015 con questo argomento. L'hardware, il sistema operativo, i database, il software, tutti i requisiti di sistema e i suggerimenti sono qui per garantire una corretta installazione e distribuzione della server farm.

If you're looking for environmental requirements, such as Active Directory, DNS or certificates, you can check out the [Environmental requirements for Skype for Business Server 2015](environmental-requirements.md) doc.
  
Come ci si potrebbe aspettare, è necessario prepararsi prima di iniziare a distribuire Skype for Business Server 2015. In questo articolo viene illustrata la pianificazione degli elementi seguenti:
  
- [Hardware per Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Sistemi operativi per Skype for Business Server 2015](server-requirements.md#OS)
  
- [Database back-end che funzionano con Skype for Business Server 2015](server-requirements.md#DBs)
  
- [Software che deve essere installato prima di una distribuzione di Skype for Business Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware per Skype for Business Server 2015
<a name="Hardware"> </a>

Ora che la topologia non è più disponibile (e in caso contrario, è possibile consultare l'argomento [Topology Basics for Skype for Business Server 2015),](../../plan-your-deployment/topology-basics/topology-basics.md) è il momento di pensare ai server. I server Skype for Business Server 2015 richiederanno hardware a 64 bit. I nostri consigli per l'hardware sono riportati di seguito. Non si tratta di requisiti, ma riflettono i requisiti necessari per ottenere prestazioni ottimali. È disponibile una documentazione sulla pianificazione della capacità che consente di determinare se è necessario più di questo, a seconda delle circostanze.
  
Hardware consigliato per Front End Server, server back-end, server Standard Edition e server Chat persistente:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore doppio a 64 bit, core esadecimale, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |UNO DEI DUE:  <br/> • 8 o più unità disco rigido da 1.0000 RPM con almeno 72 GB di spazio libero su disco (due dei dischi che utilizzano RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili a 8 unità disco meccaniche da 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a due porte, 1 Gbps o superiore (è possibile usare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed non sono **supportate** per i Front End Server, i server back-end, i server Standard Edition e i server Chat persistente. <br/> Finché non vengono esposti al sistema operativo e vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multi-homed ed è supportato.  <br/> |
   
Hardware consigliato per server perimetrali, Mediation Server autonomi, Server di interoperabilità video e Director:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore doppio a 64 bit, quad core, 2,26 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2015.  <br/> |
|Memoria  <br/> |16 gigabyte.  <br/> |
|Disco  <br/> |UNO DEI DUE:  <br/> • 4 o più unità disco rigido da 1.0000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione RAID 1 2x).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili a 4 unità disco meccaniche da 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a due porte, 1 Gbps o superiore (è possibile usare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non sono** supportate per Video Interop Server e Director. <br/> I server perimetrali richiederanno due interfacce di rete che sono schede di rete a doppia porta, 1 Gbps o superiore (o due schede di rete associate, per un totale di quattro, ognuna delle quali è associata a un singolo indirizzo MAC e a un singolo indirizzo IP, per un totale di due coppie).  <br/> Nei Mediation Server autonomi è supportata l'installazione di schede di interfaccia di rete aggiuntive per consentire la configurazione di uno specifico indirizzo IP PSTN.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Sistemi operativi per Skype for Business Server 2015
<a name="OS"> </a>

Dopo aver installato l'hardware, è necessario installare i sistemi operativi. Si tratta del sistema operativo che consente di installare e usare correttamente Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2019 (è necessario l'aggiornamento cumulativo 9 di Skype for Business o versione successiva). <br/> |Windows Server 2016 (è necessario l'aggiornamento cumulativo 5 di Skype for Business o versione successiva. Per ulteriori informazioni, [vedere KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Sistema operativo Windows Server 2012 R2 Datacenter con tutti gli aggiornamenti necessari installati.  <br/> |Sistema operativo Windows Server 2012 R2 Standard con tutti gli aggiornamenti necessari installati.  <br/> |
|Sistema operativo Windows Server 2012 Datacenter con tutti gli aggiornamenti necessari installati.  <br/> |Sistema operativo Windows Server 2012 Standard con tutti gli aggiornamenti necessari installati.  <br/> |
   
If it's not on this list, it won't work properly, please don't try it for new installations of Skype for Business Server 2015.

> [!NOTE]
> L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013. È necessario distribuire un pool separato ed eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso. Tutti i server di un pool devono avere la stessa versione del sistema operativo.
  
> [!NOTE]
> Potresti aver notato che Windows Server 2008 R2 non è in questo elenco. Questo perché è consigliabile utilizzare Windows Server 2012 R2 per tutti i nuovi server per SFB. È consigliabile utilizzare Windows Server 2008 R2 solo se sono già installati server con Lync Server 2013 e si intende eseguire un aggiornamento sul posto. Windows Server 2008 R2 ha raggiunto la fine del ciclo di vita del supporto Mainstream il 13/1/1/2015 e raggiungerà la fine del ciclo di vita del supporto il 14/1/1/2020.
  
Oltre al Service Pack più recente, è necessario verificare che gli aggiornamenti seguenti siano installati se pertinenti:
  
- Per Windows Server 2012, l'articolo 2858668 della Knowledge Base deve essere installato prima di un aggiornamento. [Scaricalo qui.](https://support.microsoft.com/kb/2858668/)
    
- Se si dispone di Windows Server 2012 R2, installare l'articolo 2982006 della Knowledge Base prima dell'aggiornamento. [È disponibile qui.](https://support.microsoft.com/kb/2982006/)
    
- Se si esegue l'aggiornamento in una casella di Windows Server 2008 R2 (vedere la nota precedente), è necessario installare prima l'articolo 2533623 della Knowledge Base. [È a questo collegamento.](https://support.microsoft.com/kb/2533623/)
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Database back-end che funzionano con Skype for Business Server 2015
<a name="DBs"> </a>


When installing Skype for Business Server 2015 Standard Edition, you'll have SQL Server 2014 Express (64-bit edition) is automatically installed as well.
  
Skype for Business Server 2015 Enterprise Edition è un po' più complicato, ma l'elenco supportato è riportato di seguito (tutto è un'edizione a 64 bit, si noterà, non usare le edizioni a 32 bit):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2017 Enterprise (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2016 Enterprise (edizione a 64 bit) con Service Pack 1 o versione successiva ed è necessario eseguire l'aggiornamento cumulativo 7 o versione successiva di Skype for Business ( scaricare l'aggiornamento cumulativo di[Skype for Business).](https://support.microsoft.com/help/3061064)  <br/> |Microsoft SQL Server 2014 Enterprise (edizione a 64 bit) ed è necessario eseguire l'aggiornamento cumulativo 6 o versione successiva ( scaricare l'aggiornamento[cumulativo 6).](https://support.microsoft.com/kb/3031047/)  <br/> |Microsoft SQL Server 2012 Enterprise (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.  <br/> |
|Microsoft SQL Server 2019 Standard (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2017 Standard (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente. <br/> |Microsoft SQL Server 2016 Standard (edizione a 64 bit) con Service Pack 1 o versione successiva ed è necessario eseguire l'aggiornamento cumulativo 7 o versione successiva di Skype for Business ( scaricare l'aggiornamento cumulativo di[Skype for Business).](https://support.microsoft.com/help/3061064)  <br/> |Microsoft SQL Server 2014 Standard (edizione a 64 bit) ed è necessario eseguire l'aggiornamento cumulativo 6 o versione successiva ( scaricare l'aggiornamento[cumulativo 6).](https://support.microsoft.com/kb/3031047/)  <br/> |Microsoft SQL Server 2012 Standard (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.  <br/> |
   
Se l'edizione SQL Server che vuoi usare non è elencata qui, non puoi usarla.
  
- Sarà inoltre necessario installare SQL Server Reporting Services per il ruolo Monitoring Server.
- Per un back-end SQL ben connesso, la connessione al front-end Skype for Business deve essere locale e non attraverso un collegamento a bassa velocità. 
- La SQL back-end tra due o più pool non è supportata.

### <a name="microsoft-exchange-storage"></a>Archiviazione di Microsoft Exchange
I file di contenuto delle riunioni, ad esempio le presentazioni PowerPoint, sono archiviate come allegati. Se si desidera archiviare i dati di archiviazione di Skype for Business con i dati di conformità di Exchange, è necessario utilizzare Exchange per la distribuzione di Exchange e assicurarsi che la dimensione massima di archiviazione supporti l'archiviazione dei file di contenuto delle riunioni. È necessario distribuire Exchange prima di distribuire e abilitare l'archiviazione utilizzando l'opzione di integrazione di Microsoft Exchange. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Requisiti hardware e software per l'archiviazione in Skype for Business Server 2015
  
L'archiviazione non è un ruolo del server definito, non è necessario installare un server separato per l'archiviazione. Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni pool Enterprise Edition Front End e in ogni server Standard Edition. Sarà necessario abilitare e pubblicare la topologia di archiviazione utilizzando Generatore di topologie.
    
L'archiviazione utilizza l'archiviazione dei file di Skype for Business Server per l'archiviazione temporanea dei file di contenuto delle riunioni, quindi non si configura un archivio file separato per l'archiviazione.
    
Accodamento messaggi Microsoft non è necessario.
    
Sarà necessario configurare l'infrastruttura per l'archiviazione dell'archiviazione. Ciò include la scelta dell'archiviazione di Exchange o di archiviazione tramite SQL Server.   I requisiti dell'infrastruttura di archiviazione di Skype for Business Server sono gli stessi della distribuzione di Skype for Business Server. Per informazioni dettagliate, [vedere Requisiti per l'ambiente Skype for Business.](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 
  
> [!NOTE]
> Per supportare gli utenti che non sono ospitati su server Exchange o se non si desidera utilizzare l'opzione di integrazione di Microsoft Exchange, è necessario distribuire l'archiviazione utilizzando un database SQL Server a 64 bit. 
    
È necessario configurare le piattaforme di SQL Server prima di distribuire e abilitare l'archiviazione. Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) quando si pubblica la topologia. È anche possibile creare il database successivamente, anche come parte della procedura di installazione. Per informazioni dettagliate SQL Server, vedere la [documentazione SQL Server.](https://go.microsoft.com/fwlink/p/?linkID=129045)
    
L'aumento del carico per l'archiviazione può essere significativo. È pertanto consigliabile verificare che lo spazio su disco sia sufficiente per i Front End Server in cui è abilitata l'archiviazione.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL mirroring, SQL clustering e SQL sempre attivo

You are able to use SQL Mirroring or SQL Clustering with Skype for Business Server 2015, it's supported. SQL il mirroring viene configurato tramite Generatore di topologie di Skype for Business Server. Se si ha intenzione di configurare SQL clustering, questa operazione viene eseguita in SQL Server.
  
Assicurarsi di disporre di una configurazione attiva/passiva per SQL clustering, in quanto è supportata. Non condividere il nodo passivo con altre SQL istanza.
  
Per il clustering di failover è possibile disporre di quanto segue:
  
Due nodi:
  
- Microsoft SQL Server 2019 Standard (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2017 Standard (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2016 Standard (edizione a 64 bit) con Service Pack 1 o versione successiva. È consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2014 Standard (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.
    
-  Microsoft SQL Server 2012 Standard (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.

Sedici nodi:

- Microsoft SQL Server 2019 Enterprise (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2017 Enterprise (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.

- Microsoft SQL Server 2016 Enterprise (edizione a 64 bit) con Service Pack 1 o versione successiva. È consigliabile eseguire il Service Pack più recente.
  
- Microsoft SQL Server 2014 Enterprise (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.
    
- Microsoft SQL Server 2012 Enterprise (edizione a 64 bit) ed è consigliabile eseguire il Service Pack più recente.

> [!IMPORTANT]
> Per l'aggiornamento, è necessario verificare che nei Front End Server sia installato almeno SQL Server 2012 SP1 prima dell'aggiornamento. [Ecco un collegamento a](https://www.microsoft.com/download/details.aspx?id=35575) SP1 se si desidera scaricarlo immediatamente.
  
Se è necessario leggere altre informazioni sul mirroring SQL, è disponibile un server back-end a disponibilità elevata nell'argomento Skype for Business Server 2015. Configurare SQL Server clustering per Skype for Business Server 2015 ha la procedura per prepararsi al clustering. Sono inoltre disponibili ulteriori collegamenti al clustering di failover per SQL, per [la versione 2014,](https://technet.microsoft.com/library/hh231721.aspx) [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)e [2008.](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)
  
> [!NOTE]
> Una novità della versione 2015 è il supporto di SQL Always On. È supportato ed è possibile leggere altre informazioni nell'argomento Disponibilità elevata del [server back-end in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> SQL mirroring è disponibile in Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software che deve essere installato prima di una distribuzione di Skype for Business Server 2015
<a name="Software"> </a>

Ci sono alcuni elementi che dovrai installare o configurare per qualsiasi server che esegue Skype for Business Server 2015 e sono elencati di seguito. Dopo di che sono necessari ulteriori requisiti per ruoli del server specifici.

  
 **Tutti i server:**
  
|**Software/Ruolo**|**Dettagli**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tutti i server Skype for Business Server devono Windows PowerShell 3.0.  <br/> • Se si sta eseguendo l'installazione in Windows Server 2012 o Windows Server 2012 R2, l'installazione è già presente.  <br/> • Se si esegue un aggiornamento in Windows Server 2008 R2, è possibile scaricare il [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) per ottenerlo. <br/> **Suggerimento:** Dopo aver installato PowerShell corretto, verifica che sia BuildVersion 6.2.9200.0 o versione successiva, andando al prompt di PowerShell e digitando `$PSVersionTable` . In questo modo dovrebbero essere visualizzate le informazioni necessarie.  <br/> |
|Microsoft .NET Framework  <br/> |I servizi WCF sono **funzionalità** installate come funzionalità di Windows, in **Server Manager** e non sono necessari download. <br/> • È necessario verificare, quando si installa questa funzionalità o se è già installata e si sta controllando, che anche l'opzione di attivazione **HTTP** sia selezionata e installata, come indicato di seguito: <br/> ![Screenshot che mostra l'opzione di attivazione HTTP nelle funzionalità di .NET Framework 4.5. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) Non preoccuparti se ricevi un popup aggiuntivo che ti dice che è necessario installare altri elementi per installare l'attivazione HTTP. È normale, fare clic su OK e procedere. Se non si ottiene questo popup, presupporre che gli elementi siano già installati e procedere.  <br/> Microsoft .NET Framework viene in genere installato durante l'installazione di Windows Server 2012 R2 o Windows Server 2016. Skype for Business Server funziona con le seguenti versioni di Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (per Skype for Business Server CU 5 o versioni successive)  <br/> • .NET 4.7.2 (per Skype for Business Server CU 6 o versioni successive)  <br/>  • .NET 4.8 (per Skype for Business Server CU 9 o versioni successive) <br/>  .NET Framework 3.5 verrà probabilmente installato per impostazione predefinita nel computer Windows Server 2008 R2 (verificare di essere sicuro prima di eseguire l'aggiornamento), ma in realtà non sarà nei server Windows Server 2012/Windows Server 2012 R2 (per le nuove installazioni). Per aggiungerlo, è necessario accedere all'unità o al supporto di installazione (la posizione da cui è stato installato Windows Server o la posizione in cui si trova il file di installazione). Quindi, installarla come funzionalità da Server Manager e scegliere il supporto di installazione (in particolare la **cartella \sources\sxs)** quando richiesto e continuare a installarlo. <br/> |
|Media Foundation  <br/> |Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2 Runtime formato Windows Media viene installato con Microsoft Media Foundation.  <br/> Tutti i Front End Server e i server Standard Edition utilizzati per le conferenze richiedono Runtime formato Windows Media per eseguire i file Windows Media Audio (wma) riprodotti dalle applicazioni Parcheggio di chiamata, Annuncio e Response Group per annunci e musica.  <br/> |
|Windows Identity Foundation  <br/> |È necessario Windows Identity Foundation 3.5 per supportare scenari di autenticazione da server a server per Skype for Business Server 2015.  <br/> • Per Windows Server 2012 e Windows Server 2012 R2, non è necessario scaricare nulla. Aprire **Server Manager** e passare all'Aggiunta guidata ruoli e **funzionalità.** **Windows Identity Foundation 3.5** è elencato nella **sezione** Funzionalità. Se è selezionata, sei a posto. In caso contrario, selezionarlo e fare clic su Avanti per accedere **al pulsante** Installa. <br/> |
|Strumenti di amministrazione remota del server  <br/> |Strumenti di amministrazione dei ruoli: strumenti di Ad DS e AD LDS  <br/> |
   
 **I Front End Server e il server Standard Edition necessitano anche di:**
  
|**Software/Ruolo**|**Dettagli**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS è necessario in tutti i Front End Server, nonché in tutti i server Standard Edition, con i moduli seguenti selezionati:  <br/> • Funzionalità HTTP comuni: documento predefinito, errori HTTP, contenuto statico  <br/> • Integrità e diagnostica: registrazione HTTP, strumenti di registrazione, traccia  <br/> • Prestazioni: compressione del contenuto statico, compressione del contenuto dinamico  <br/> • Sicurezza: filtro richieste, autenticazione mapping certificati client, autenticazione di Windows  <br/> • Sviluppo di applicazioni: estendibilità .NET 3.5, estendibilità .NET 4.5, ASP.NET 3.5, ASP.NET 4.5, estensioni ISAPI, filtri ISAPI  <br/> • Strumenti di gestione: console di gestione IIS, script e strumenti di gestione IIS  <br/> È anche necessario tenere presente che è necessario l'accesso anonimo, ma si ottiene questo quando si installa IIS, in modo da non avere una posizione in cui selezionarlo nell'elenco.  <br/> |
|Runtime formato Windows Media  <br/> | Per Windows Server 2016, Windows Server 2012 e Windows Server 2012 R2, dovrai installare la funzionalità **Media Foundation** in **Server Manager.** Ora, è effettivamente possibile avviare l'installazione di Skype for Business Server 2015 senza questa, ma verrà richiesto di installarla e quindi riavviare il server, prima che l'installazione di Skype for Business Server 2015 continui. È meglio farlo in anticipo. <br/> |
|Silverlight  <br/> |È possibile installare la versione più recente di Silverlight a [questo collegamento.](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> Potrebbe essere necessario abilitare l'esplorazione directory anche se si utilizza un servizio di bilanciamento del carico. In caso contrario, verrà caricata una pagina vuota che il servizio di bilanciamento del carico potrebbe considerare un errore. 

Per aiutarti, ecco uno script di PowerShell di esempio che puoi eseguire per automatizzare questa operazione:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Il comando cerca i file di origine in un ordine specifico. Se sei online, il comando accede a Windows Update. Tuttavia, se si è offline, è necessario verificare che i file di origine siano disponibili per il comando. Per ulteriori informazioni sull'utilizzo di PowerShell per installare ruoli e funzionalità, vedere Install [or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/library/hh831809.aspx) Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.

 **I director necessitano anche di:**
  
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
    
Se lo si desidera, si tratta dello stesso modulo impostato per i Front End Server e i server Standard Edition, con gli strumenti di compressione e gestione dei contenuti dinamici non disponibili.
  
E abbiamo anche un po' di codice di PowerShell per questo:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **I server Chat persistente necessitano anche di:**
  
Accodamento messaggi, denominato anche MSMQ. Si tratta di un componente di Windows Server ed è possibile installarlo nella sezione Funzionalità di Server Manager. Per ulteriori informazioni, vedere [Installing and Managing Message Queuing](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Ultimi pensieri:**
  
Non installare alcun software client Microsoft Internet Security and Acceleration (ISA) Server o qualsiasi altro software Winsock Layered Service Providers (LSP) (in questo caso sono inclusi eventuali firewall di terze parti o software di ispezione della rete antivirus) in qualsiasi server front-end o mediation server autonomo. Prestazioni del traffico multimediale scarse sono state osservate durante l'installazione del software.
  

