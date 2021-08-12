---
title: Requisiti di sistema per Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: "Riepilogo: preparare i server Skype for Business Server 2019 e l'infrastruttura di dominio con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e i suggerimenti, insieme al DNS del certificato, alla condivisione file e alle informazioni di Active Directory, sono disponibili qui per garantire una corretta installazione e distribuzione della server farm."
ms.openlocfilehash: 3d7c8f4346ce0d965c9d9d87cc9fc124824f1d65f24cb7c05ef5d3aa58df1a07
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295983"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Requisiti di sistema per Skype for Business Server 2019
 
**Riepilogo:** Preparare l'Skype for Business Server 2019 con questo argomento. L'hardware, il sistema operativo, il software, i database, i certificati, Active Diretory, DNS e le condivisione di file sono trattati qui. Tutti i requisiti di sistema e i suggerimenti sono qui per garantire una corretta installazione e distribuzione della server farm.
  
Come ci si potrebbe aspettare, è necessario prepararsi prima di iniziare la distribuzione Skype for Business Server 2019. In questo articolo viene illustrata la pianificazione degli elementi seguenti:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Sistemi operativi](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Database di SQL back-end](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [Certificati](system-requirements.md#Certs)
  
- [Condivisione file](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware per Skype for Business Server 2019
<a name="Hardware"> </a>

Dopo aver arrestato la topologia (e in caso contrario, è possibile consultare l'argomento [Topology Basics for Skype for Business Server 2019),](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) è il momento di pensare ai server. Skype for Business Server server 2019 richiedono hardware a 64 bit. Di seguito sono riportati i suggerimenti per l'hardware. Questi non sono requisiti, ma riflettono i requisiti necessari per ottenere prestazioni ottimali. Abbiamo una documentazione sulla pianificazione della capacità che ti aiuterà a determinare se è necessario più di questo, a seconda delle circostanze.
  
Hardware consigliato per edizione Standard server:

|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 v3 con doppio processore, 6 core, 2,4 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |UNO DEI SEGUENTI:  <br/> • 8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco (due dischi con RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili a 8 unità disco meccaniche da 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a doppia porta, 1 Gbps o superiore (è possibile utilizzare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed non sono **supportate** per Front End Server, back-end server e edizione Standard server. <br/> Se non sono esposti al sistema operativo e vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multi-homed ed è supportato.  <br/> |


Hardware consigliato per Front End Server e back-end server:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 v3 con doppio processore, 6 core, 2,4 gigahertz (GHz) o superiore. <br/> I processori Intel Itanium non sono supportati per Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |64 gigabyte (GB).  <br/> |
|Disco  <br/> |UNO DEI SEGUENTI:  <br/> • 8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco (due dischi con RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili a 8 unità disco meccaniche da 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a doppia porta, 1 Gbps o superiore (è possibile utilizzare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed non sono **supportate** per Front End Server, back-end server e edizione Standard server. <br/> Se non sono esposti al sistema operativo e vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multi-homed ed è supportato.  <br/> |
   
Hardware consigliato per server perimetrali, Mediation Server autonomi e Director:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 v3 con doppio processore, 6 core, 2,4 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabyte.  <br/> |
|Disco  <br/> |UNO DEI SEGUENTI:  <br/> • 4 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione RAID 1 2x).  <br/> OPPURE  <br/> • Unità A stato solido (SSD) in grado di fornire lo stesso spazio libero e prestazioni simili a 4 unità disco meccaniche da 1.0000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete a doppia porta, 1 Gbps o superiore (è possibile utilizzare 2 schede di rete, ma devono essere associate a un singolo indirizzo MAC e a un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non sono** supportate per Video Interop Server e Director. <br/> I server perimetrali richiederanno due interfacce di rete che sono schede di rete a doppia porta, 1 Gbps o superiore (o due schede di rete associate, per un totale di quattro, ogni coppia viene associata a un singolo indirizzo MAC e a un singolo indirizzo IP, per un totale di due coppie).  <br/> Nei Mediation Server autonomi è supportata l'installazione di schede di interfaccia di rete aggiuntive per consentire la configurazione di uno specifico indirizzo IP PSTN.  <br/> |


> [!NOTE]
> Indipendentemente dal ruolo del server, si consigliano anche le impostazioni hardware seguenti per Skype for Business Server 2019 (ciò può variare a seconda del marchio di hardware acquistato, quindi fare riferimento alla documentazione del produttore per informazioni specifiche):
> - Configurazione BIOS: deve essere impostata su FLAT da NUMA.
> - Abilitare l'hyperthreading.
> - L'impostazione della coda RSS deve essere impostata su 8 code.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Sistemi operativi per Skype for Business Server 2019
<a name="OS"> </a>

Dopo aver installato l'hardware, dovrai installare il sistema operativo che ti consentirà di installare e usare correttamente Skype for Business Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Qualsiasi elemento diverso da quello dei sistemi operativi elencati qui non funzionerà correttamente. non provare per le installazioni di Skype for Business Server 2019. Ad esempio, l'opzione Server Core non è elencata e pertanto non è supportata.

> [!NOTE]
> L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013. È necessario distribuire un pool separato ed eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso. Tutti i server di un pool devono avere la stessa versione del sistema operativo.

> [!NOTE]
> 
> Se si installa Windows Admin Center 2019 nel computer Windows Server 2019, verrà richiesta una porta per l'ascolto. È possibile scegliere la porta 443, ma se nel computer è installato Skype for Business Server 2019 o se è installato Skype for Business Server 2019, è necessario scegliere un numero di porta diverso.
> 
>Perché è questo il caso? Se Windows Admin Center 2019 è in esecuzione sulla porta 443, non sarà possibile connettersi al server utilizzando il Pannello di controllo di Skype for Business, né sarà possibile connettersi a qualsiasi servizio Web interno in esecuzione nel server (servizio Web Rubrica, servizio di individuazione automatica, servizio WebTicket e così via).  In realtà, non sarà possibile connettersi ad alcun URL del servizio Web interno. Scegliere una porta diversa nel caso in cui sia necessario o si desideri inserire Windows Admin Center 2019 in un server con Skype for Business Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software da installare prima di una distribuzione Skype for Business Server 2019
<a name="Software"> </a>

È necessario installare o configurare alcuni elementi per qualsiasi server che esegue Skype for Business Server 2019. Questi sono elencati di seguito, seguiti da requisiti aggiuntivi per ruoli del server specifici.

> [!IMPORTANT]
> Skype For Business 2019 supporta .Net Framework 4.8. 
  
 **Tutti i server:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tutti Skype for Business Server server devono Windows PowerShell 3.0 installato.  <br/> • Deve essere installato per impostazione predefinita con Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |I servizi WCF sono **una funzionalità** installata come funzionalità Windows, in **Server Manager** inizialmente non sono necessari download. <br/> • È necessario assicurarsi che, quando si installa questa funzionalità o se è già installata e si sta controllando, che anche l'opzione Attivazione **HTTP** sia selezionata e installata, in questo modo: <br/> ![Screenshot che mostra l'opzione Attivazione HTTP .NET Framework 4.5 Funzionalità.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Non preoccuparti se ricevi un popup aggiuntivo che dice che è necessario installare altri elementi per l'installazione dell'attivazione HTTP. È normale; fare clic su OK e procedere. Se non si ottiene questo popup, è possibile presupporre che tali elementi siano già installati e procedere.  <br/> Microsoft .NET Framework viene in genere installato quando Windows Server 2016 è installato. Skype for Business Server richiede Microsoft .NET Framework 4.7 o 4.8, quindi probabilmente è necessario aggiornarlo. L'aggiornamento è disponibile [qui](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Ad Windows Server 2016, il Windows Media Format Runtime viene installato con Microsoft Media Foundation.  <br/> Tutti i Front End Server e i server edizione Standard utilizzati per le conferenze richiedono Windows Media Format Runtime per eseguire i file Windows Media Audio (wma) riprodotti dalle applicazioni Parcheggio di chiamata, Annuncio e Response Group per annunci e musica.  <br/> |
|Windows Identity Foundation  <br/> |È necessario Windows Identity Foundation 3.5 per supportare gli scenari di autenticazione da server a server per Skype for Business Server 2019.  <br/> • Per Windows Server 2016, non è necessario scaricare nulla. Aprire **Server Manager** e passare all'Aggiunta guidata ruoli e **funzionalità.** **Windows Identity Foundation 3.5** è elencato nella **sezione** Funzionalità. Se è selezionato, sei a posto. In caso contrario, selezionarlo **e fare clic** su Avanti per accedere al **pulsante** Installa. <br/> |
|Strumenti di amministrazione remota del server  <br/> |Strumenti di amministrazione dei ruoli: strumenti di Servizi di dominio Active Directory e AD LDS  <br/> |
   
 **I Front End Server e edizione Standard server devono inoltre:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS è necessario in tutti i Front End Server, nonché in tutti edizione Standard server, con i moduli seguenti selezionati:  <br/> • Funzionalità HTTP comuni: documento predefinito, errori HTTP, contenuto statico  <br/> • Integrità e diagnostica: registrazione HTTP, strumenti di registrazione, traccia  <br/> • Prestazioni: Compressione contenuto statico, Compressione contenuto dinamico  <br/> • Sicurezza: Filtro richieste, Autenticazione mapping certificati client, Windows autenticazione  <br/> • Sviluppo di applicazioni: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ESTENSIONI ISAPI, filtri ISAPI  <br/> • Strumenti di gestione: console di gestione IIS, script e strumenti di gestione IIS  <br/> Si noti che è necessario anche l'accesso anonimo, ma si ottiene questo quando si installa IIS, in modo da non avere una posizione per selezionarlo nell'elenco.  <br/> |
|Runtime formato Windows Media  <br/> | Ad Windows Server 2016, è necessario installare la funzionalità **Media Foundation** in **Server Manager.** In realtà è possibile avviare l'installazione di Skype for Business Server 2019 senza questa operazione, ma verrà richiesto di installarla e quindi riavviare il server, prima che l'installazione di Skype for Business Server 2019 continui. È meglio farlo in anticipo. <br/> |
|Silverlight  <br/> |È possibile installare la versione più recente di Silverlight [qui.](https://www.microsoft.com/silverlight/)  <br/> |
   
Per aiutarti, ecco uno script di PowerShell di esempio che puoi eseguire per automatizzare questa operazione:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
    
Se lo si desidera, si tratta dello stesso modulo impostato per i Front End Server e i server edizione Standard, con gli strumenti di gestione e compressione del contenuto dinamico non disponibili.
  
Di seguito è riportato anche il codice di PowerShell:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Database back-end che funzionano con Skype for Business Server 2019
<a name="DBs"> </a>

Durante l'Skype for Business Server 2019 edizione Standard, avrai SQL Server 2016 Express (edizione a 64 bit).

Skype for Business Server 2019 edizione Enterprise richiederà un SQL Server completo, come indicato di seguito (solo edizione a 64 bit; non utilizzare edizioni a 32 bit):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (edizione a 64 bit) ed è necessario eseguire con gli aggiornamenti più recenti.  <br/> |Microsoft SQL Server 2017 (edizione a 64 bit) ed è necessario eseguire con gli aggiornamenti più recenti.  <br/> |
Microsoft SQL Server 2016 (edizione a 64 bit) ed è necessario eseguire con gli aggiornamenti più recenti.|
 |

Se l'edizione SQL Server che si desidera utilizzare non è elencata qui, non è possibile utilizzarla.
  
> [!NOTE]
> È inoltre necessario installare i SQL Server Reporting Services per il ruolo Monitoring Server. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL Clustering e SQL Always On

SQL È supportato il clustering Skype for Business Server 2019. Se si desidera configurare SQL clustering, questa operazione viene eseguita in SQL Server.
  
Assicurati di avere una configurazione attiva/passiva per SQL clustering, che è supportata. Non condividere il nodo passivo con altre SQL istanza.
  
Per il clustering di failover, è possibile disporre di quanto segue:
  
Due nodi:
  
- Microsoft SQL Server 2019 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.
- Microsoft SQL Server 2017 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.
- Microsoft SQL Server 2016 Standard (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

Sedici nodi:
  
- Microsoft SQL Server 2019 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.
- Microsoft SQL Server 2017 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.
- Microsoft SQL Server 2016 Enterprise (edizione a 64 bit) ed è consigliabile eseguire con il Service Pack più recente.

SQL Always On è supportato ed è possibile leggere ulteriori informazioni in [Back End Server high availability in Skype for Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Ulteriori suggerimenti per l'installazione del server:
  
Non installare alcun software client Microsoft Internet Security and Acceleration (ISA) Server o qualsiasi altro software Winsock Layered Service Provider (LSP) (eventuali firewall di terze parti o software di ispezione della rete antivirus incluso qui) in uno dei server front-end o mediation server autonomi. Le prestazioni del traffico multimediale scarse sono state osservate durante l'installazione del software.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Sebbene gran parte dei dati di configurazione per server e servizi sia archiviata nell'archivio di gestione centrale di Skype for Business Server 2019, esistono alcuni elementi ancora archiviati in Active Directory:
  
|**Objets Active Directory**|**Tipi di oggetto**|
|:-----|:-----|
|Estensioni dello schema  <br/> |Estensioni degli oggetti utente  <br/> |
||Estensioni per Skype for Business Server 2015 e Lync Server 2013, per mantenere la compatibilità con le versioni precedenti supportate  <br/> |
|Dati  <br/> |URI SIP utente e altre impostazioni utente  <br/> |
||Oggetti contatto per le applicazioni ,ad esempio l'applicazione Response Group e il applicazione Operatore conferenza)  <br/> |
||Dati pubblicati per la compatibilità con le versioni precedenti  <br/> |
||Un punto di controllo del servizio (SCP) per l'archivio di gestione centrale  <br/> |
||Account di autenticazione Kerberos (un oggetto computer facoltativo)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo per controller di dominio

È possibile utilizzare i seguenti sistemi operativi controller di dominio:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Il livello di funzionalità del dominio di qualsiasi dominio Skype for Business Server cui si distribuisce Skype for Business Server 2019 e il livello di funzionalità della foresta di qualsiasi foresta Skype for Business Server cui si distribuisce Skype for Business Server 2019, deve essere uno dei seguenti:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
È possibile disporre di controller di dominio di sola lettura in questi ambienti? Certo, purché siano disponibili anche controller di dominio scrivibili.
  
È importante sapere che Skype for Business Server 2019 non supporta domini con etichetta singola. Quali? Se si dispone di un dominio radice denominato contoso.local, andrà bene. Se si dispone di un dominio radice denominato localmente, non funzionerà e di conseguenza non è supportato. Ulteriori informazioni sono state scritte [in questo articolo della Knowledge Base.](https://support.microsoft.com/kb/300684/)
  
Skype for Business Server 2019 inoltre non supporta la ridenominazione dei domini. Se è veramente necessario rinominare il dominio, è necessario disinstallare Skype for Business Server 2019, eseguire la ridenominazione del dominio e quindi reinstallare Skype for Business Server 2019.
  
Infine, potresti avere a che fare con un dominio con un ambiente di Servizi di dominio Active Directory bloccato e va bene così. Abbiamo altre informazioni su come distribuire Skype for Business Server 2019 in un ambiente di Servizi di dominio Active Directory bloccato nella documentazione relativa alla distribuzione.
  
### <a name="ad-topologies"></a>Topologie AD

Le topologie supportate in Skype for Business Server 2019 sono:
  
- Foresta singola con singolo dominio
    
- Foresta singola con albero singolo e più domini
    
- Foresta singola con più alberi e spazi dei nomi disgiunti
    
- Più foreste in una topologia di foreste centralizzate
    
- Più foreste in una topologia di foresta di risorse
    
- Più foreste in una topologia Skype for Business di risorse con Exchange Online
    
- Più foreste in una topologia a foresta di risorse con Skype for Business Online e Azure Active Directory Connessione
    
Sono presenti diagrammi e descrizioni che consentono di determinare quale topologia è presente nell'ambiente o cosa potrebbe essere necessario configurare prima di installare Skype for Business Server 2019. Per mantenere la semplicità, è inclusa anche una chiave:
  
![L'elemento è una chiave per le icone utilizzate Skype for Business diagrammi di topologia](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Foresta singola con singolo dominio

![Diagramma della foresta singola di Active Directory con un singolo dominio](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Non è più facile; si tratta di una foresta a dominio singolo, una topologia comune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Foresta singola con albero singolo e più domini

![Diagramma di una singola foresta, di un singolo albero e di domini mutiple](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Questo diagramma mostra una singola foresta, ma ha anche uno o più domini figlio (sono presenti tre in questo esempio specifico). Il dominio in cui vengono creati gli utenti potrebbe pertanto essere diverso da quello in cui Skype for Business Server 2019 viene distribuito. Perché preoccuparsi di questo? È importante ricordare che quando si distribuisce un pool Front End Skype for Business Server, tutti i server del pool devono essere in un singolo dominio. È possibile eseguire l'amministrazione tra domini Skype for Business Server supporto di Windows gruppi di amministratori universali.
  
Nel diagramma precedente, è possibile vedere che gli utenti di un dominio sono in grado di accedere Skype for Business Server pool dallo stesso dominio o da domini diversi, anche se tali utenti sono in un dominio figlio.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Foresta singola con più alberi e spazi dei nomi disgiunti

![Diagramma di una singola foresta, più alberi e spazi dei nomi disgiunti](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Potrebbe essere presente una topologia simile a questo diagramma, in cui è presente una foresta, ma all'interno di tale foresta sono presenti più domini, con spazi dei nomi AD separati. In questo caso, questo diagramma è una buona illustrazione, perché include utenti in tre domini diversi che accedono Skype for Business Server 2019. Linee solide indicano che stanno accedendo a un pool di Skype for Business Server nel proprio dominio, mentre una linea tratteggiata indica che stanno andando a un pool in un albero diverso del tutto.
  
Come si può vedere, gli utenti nello stesso dominio, nello stesso albero o anche in un albero diverso possono accedere correttamente ai pool.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Più foreste in una topologia di foreste centralizzate

![Più foreste in un diagramma della topologia a foresta centrale](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 supporta più foreste configurate in una topologia a foresta centrale. Se non si è certi di avere questo tipo di dati, la foresta centrale della topologia utilizza gli oggetti in essa contenuti per rappresentare gli utenti nelle altre foreste e ospita gli account utente per tutti gli utenti nella foresta.
  
Funzionamento. Un prodotto di sincronizzazione della directory (ad esempio Forefront Identity Manager o FIM) gestisce gli account utente dell'organizzazione per tutta la loro esistenza. Quando un account viene creato o eliminato da una foresta, tale modifica viene sincronizzata fino al contatto corrispondente nella foresta centrale.
  
Chiaramente, se l'infrastruttura di Active Directory è in atto, il passaggio a questa topologia potrebbe non essere facile, ma se si è già presenti o si pianifica ancora l'infrastruttura della foresta, questa può essere una buona scelta. È possibile centralizzare la distribuzione di Skype for Business Server 2019 in una singola foresta, mentre gli utenti possono cercare, comunicare e visualizzare la presenza di altri utenti in qualsiasi foresta. Tutti gli aggiornamenti dei contatti utente vengono gestiti automaticamente con il software di sincronizzazione.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Più foreste in una topologia Skype for Business di risorse locali
<a name="BKMK_multipleforestopology"> </a>

![Più foreste in un diagramma della topologia a foresta di risorse](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
È supportata anche una topologia di foresta di risorse. è dove una foresta è dedicata all'esecuzione delle applicazioni server, ad esempio Microsoft Exchange Server e Skype for Business Server 2019. Questa foresta di risorse ospita anche una rappresentazione sincronizzata degli oggetti utente attivi, ma nessun account utente abilitato all'accesso. La foresta di risorse è quindi un ambiente di servizi condivisi per altre foreste in cui risiedono gli oggetti utente e hanno una relazione di trust a livello di foresta con la foresta di risorse.
  
Tenere presente Exchange Server possono essere distribuiti nella stessa foresta di risorse Skype for Business Server o in una foresta diversa.
  
Per distribuire Skype for Business Server 2019 in questo tipo di topologia, è necessario creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste utente (se Microsoft Exchange Server è già presente nell'ambiente, questa operazione potrebbe essere eseguita automaticamente). È quindi necessario uno strumento di sincronizzazione della directory (ad esempio Forefront Identity Manager o FIM) per gestire gli account utente attraverso il ciclo di vita.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Più foreste in una topologia Skype for Business di risorse con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Questa topologia è simile alla topologia descritta in Più foreste in una Skype for Business di [foresta di risorse.](system-requirements.md#BKMK_multipleforestopology)
  
In questa topologia sono presenti una o più foreste utente e Skype for Business Server in una foresta di risorse dedicata. Exchange Server possono essere distribuiti in locale nella stessa foresta di risorse o in una foresta diversa e configurati per la distribuzione ibrida con Exchange Online oppure i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali. Non è disponibile alcun diagramma per questa topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Più foreste in una topologia a foresta di risorse con Skype for Business Online e Azure Active Directory Connessione
<a name="BKMK_multipleforestopology"> </a>

![Mostra due foreste di Active Directory, una foresta utente e una foresta di risorse. Le due foreste hanno una relazione di trust. Vengono sincronizzati con i Microsoft 365 azure AD Connessione. Tutti gli utenti sono abilitati Skype for Business tramite Microsoft 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con questo scenario, sono presenti più foreste in locale, con una topologia a foresta di risorse. Esiste una relazione di trust completo tra le foreste di Active Directory. Lo Azure Active Directory Connessione viene utilizzato per sincronizzare gli account tra le foreste utente locali e Microsoft 365 o Office 365.
  
 L'organizzazione ha anche Microsoft 365 o Office 365 e [](/azure/active-directory/connect/active-directory-aadconnect) usa Azure Active Directory Connessione per sincronizzare i propri account locali con Microsoft 365 o Office 365. Gli utenti abilitati per Skype for Business sono abilitati tramite Microsoft 365 o Office 365 e Skype for Business Online. Skype for Business Server non viene distribuito in locale.
  
L'autenticazione Single #A0 è fornita da una farm di Active Directory Federation Services che si trova nella foresta utente.
  
In questo scenario, è supportato distribuire Exchange locale, Exchange Online, una soluzione Exchange ibrida o per non distribuire Exchange affatto. Il diagramma mostra solo Exchange locale, ma anche le altre soluzioni Exchange sono completamente supportate.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Più foreste in una topologia a foresta di risorse con Skype for Business
<a name="BKMK_multipleforestopology"> </a>

In questo scenario, sono presenti una o più foreste utente locali e Skype for Business viene distribuito in una foresta di risorse dedicata ed è configurato per la modalità ibrida con Skype for Business Online. Exchange Server possono essere distribuiti in locale nella stessa foresta di risorse o in una foresta diversa e possono essere configurati per la distribuzione ibrida con Exchange Online. In alternativa, i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali.
  
Per ulteriori informazioni, vedere [Configure a multi-forest environment for hybrid Skype for Business](../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2019 richiede DNS, per i motivi seguenti:
  
- DNS consente Skype for Business Server 2019 di individuare server o pool interni, consentendo comunicazioni da server a server.
    
- DNS consente ai computer client di individuare il pool Front End o edizione Standard server utilizzato per le transazioni SIP.
    
- Associa URL semplici per conferenze ai server che ospitano tali conferenze.
    
- DNS consente agli utenti esterni e ai computer client di connettersi ai server perimetrali o al proxy inverso HTTP per la messaggistica istantanea o le conferenze.
    
- Consente ai dispositivi di comunicazioni unificate che non hanno effettuato l'accesso di individuare il pool Front End o il server edizione Standard che esegue il servizio Web Aggiornamento dispositivi per ottenere aggiornamenti e inviare log.
    
- L'utilizzo di DNS consente ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.
    
- Viene utilizzato nel bilanciamento del carico DNS.
    
È importante notare che Skype for Business Server 2019 non supporta i nomi di dominio internazionalizzati (IDN).
  
Ed è estremamente importante ricordare che qualsiasi nome in DNS sia identico al nome del computer configurato su qualsiasi server utilizzato da Skype for Business Server 2019. In particolare, non è possibile avere nomi brevi nell'ambiente e devono disporre di FQDN per Generatore di topologie.
  
Ciò sembra logico per qualsiasi computer già aggiunto a un dominio, ma se si dispone di un server perimetrale che non fa parte del dominio, potrebbe avere un nome breve predefinito, senza suffisso di dominio. Assicurarsi che non sia così, in DNS o nel server perimetrale o in qualsiasi server o pool Skype for Business Server 2019, a questo riguardo.
  
Sicuramente non usare caratteri Unicode o caratteri di sottolineatura. I caratteri standard (che sono A-Z, a-z, 0-9 e trattini) sono supportati dal DNS esterno e dalle autorità di certificazione pubbliche (è necessario assegnare nomi fqdn al nome del servizio di dominio completo nel certificato, è importante ricordare), quindi è necessario risparmiare molti problemi se si assegna questo nome in mente fin dall'inizio.
  
Per ulteriori informazioni sui requisiti DNS per Rete, vedere la [sezione Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) della documentazione relativa alla pianificazione.
  
## <a name="certificates"></a>Certificati
<a name="Certs"> </a>

Una delle operazioni più importanti che è possibile eseguire prima della distribuzione è assicurarsi di disporre dei certificati in ordine. Skype for Business Server 2019 necessita di un'infrastruttura a chiave pubblica (PKI) per le connessioni TLS (Transport Layer Security) e MTLS (Mutual Transport Layer Security). Fondamentalmente, per comunicare in modo sicuro in modo standardizzato, Skype for Business Server certificati emessi dalle Autorità di certificazione (CA).
  
Ecco alcuni degli aspetti che Skype for Business Server 2019 usa i certificati per:
  
- Connessioni TLS tra client e server
    
- Connessioni MTLS tra server
    
- Federazione con individuazione DNS automatica dei partner
    
- Accesso utente remoto per la messaggistica istantanea
    
- Accesso degli utenti esterni alle sessioni audio/video, alla condivisione di applicazioni e alle conferenze
    
- Parlare con applicazioni Web e Outlook Web Access (OWA)
    
Pertanto, la pianificazione dei certificati è un must. Esamini ora un elenco di alcuni aspetti da tenere presenti quando si richiedono certificati:
  
- Tutti i certificati del server devono supportare l'autorizzazione server (utilizzo chiavi avanzato del server).
    
- Tutti i certificati del server devono contenere un punto di distribuzione CRL (CDP).
    
- Tutti i certificati devono essere firmati utilizzando un algoritmo di firma supportato dal sistema operativo. Skype for Business Server 2019 supporta la famiglia di formati digest SHA-1 e SHA-2 (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo.
    
- La registrazione automatica è supportata per i server interni che eseguono Skype for Business Server 2019.
    
- La registrazione automatica non è supportata per Skype for Business Server server perimetrali 2019.
    
> [!NOTE]
> L'utilizzo dell'algoritmo di firma RSASSA-PSS non è supportato e può causare errori in caso di problemi di accesso e inoltro di chiamata, tra gli altri problemi. 
  
- Sono supportate le lunghezze delle chiavi di crittografia 1024, 2048 e 4096. Sono consigliate lunghezze di chiave pari o superiori a 2048.
    
- L'algoritmo predefinito del digest, o firma hash, è RSA. Sono supportati ECDH_P256, ECDH_P384 e ECDH_P521 algoritmi.
    
Questo è molto da pensare, e ci sono una varietà di livelli di comfort con la richiesta di certificati da un'autorità di certificazione. Di seguito verranno fornite ulteriori indicazioni per rendere la pianificazione il più indolore possibile.
  
### <a name="certificates-for-your-internal-servers"></a>Certificati per i server interni

Saranno necessari certificati per la maggior parte dei server interni e molto probabilmente li si otterrà da un'autorità di certificazione interna (ovvero un'autorità di certificazione che si trova nel dominio). Se lo si desidera, è possibile richiedere questi certificati a un'autorità di certificazione esterna (una che si trova su Internet). Se ti stai chiedendo a quale autorità di certificazione pubblica dovresti andare, puoi consultare l'elenco dei partner dei certificati [per le](../../SfbPartnerCertification/certification/services-ssl.md) comunicazioni unificate.
  
Saranno inoltre necessari certificati quando Skype for Business Server 2019 comunica con altre applicazioni e server, ad esempio Microsoft Exchange Server. Questo, ovviamente, deve essere un certificato che queste altre app e server possono usare in modo supportato. Skype for Business Server 2019 e altri prodotti Microsoft supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. If you're interested in this, we have an additional planning article for OAuth and Skype for Business Server 2019.
  
Skype for Business Server 2019 include anche il supporto per (senza richiedere) certificati firmati utilizzando la funzione hash crittografica SHA-256. Per supportare l'accesso esterno tramite SHA-256, il certificato esterno deve essere emesso da un'autorità di certificazione pubblica utilizzando SHA-256.
  
Per mantenere le cose semplici, i requisiti dei certificati per i server edizione Standard, i pool Front End e altri ruoli sono stati inseriti nelle tabelle seguenti, con il contoso.com fittizio usato per esempi (probabilmente si sta usando altro per l'ambiente). Si tratta di tutti i certificati server Web standard, con chiavi private non esportabili. Alcuni aspetti aggiuntivi da notare:
  
- L'utilizzo chiavi avanzato del server (EKU) viene configurato automaticamente quando si utilizza la procedura guidata per la richiesta di certificati.
    
- Ogni nome descrittivo del certificato deve essere univoco nell'archivio computer.
    
- In base ai nomi di esempio riportati di seguito, se è stato configurato sipinternal.contoso.com o sipexternal.contoso.com nel DNS, questi devono essere aggiunti al nome alternativo soggetto (SAN) del certificato.
    
Certificati per edizione Standard server:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nei edizione Standard, il nome di dominio completo del server corrisponde all'FQDN del pool.  <br/> La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde all'FQDN del server)  <br/> E  <br/> • Soddisfare GLI URL semplici  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Non è possibile sostituire l'FQDN Web interno in Generatore di topologie.  <br/> Se si dispone di più URL semplici Meet, è necessario includerli tutti come SAN.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice per l'accesso esterno  <br/> • Soddisfare GLI URL semplici per dominio SIP  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per i Front End Server in un pool Front End:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che NON corrisponde all'FQDN del server)  <br/> • FQDN server  <br/> • FQDN Skype for Business pool  <br/> E  <br/> • Soddisfare GLI URL semplici  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per il Director:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |Pool Director  <br/> |FQDN del Director, FQDN del pool di server Director.  <br/> Se questo pool è il server di accesso automatico per i client ed è necessaria una corrispondenza DNS rigida nei Criteri di gruppo, saranno necessarie anche voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde all'FQDN del server)  <br/> • FQDN server  <br/> • FQDN Skype for Business pool  <br/> E  <br/> • Soddisfare GLI URL semplici  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • Soddisfare GLI URL semplici per dominio SIP  <br/> • URL semplice per l'accesso esterno  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |L'FQDN Web esterno del Director deve essere diverso dal pool Front End o dal Front End Server.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificati per Mediation Server autonomo:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool  <br/> FQDN del server membro del pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificati per Survivable Branch Appliance (in particolare, Survivable Branch Appliance 2015 per Skype for Business Server 2019):
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del dispositivo  <br/> |SIP.\<sipdomain\> (è necessaria una sola voce per ogni dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificati per l'accesso degli utenti esterni (Edge)

Skype for Business Server 2019 supporta l'utilizzo  di un singolo certificato pubblico per l'accesso e le interfacce esterne di Web Conferencing Edge, oltre al servizio di autenticazione A/V, fornito tramite i server perimetrali. L'interfaccia interna di Edge in genere userà un certificato privato emesso dall'autorità di certificazione interna, ma se si preferisce, è possibile utilizzare anche un certificato pubblico per questo, se è di un'autorità di certificazione attendibile.
  
Anche il proxy inverso utilizzerà un certificato pubblico e crittografa la comunicazione tra il componente e i client e il componente ai server interni utilizzando HTTP (o più precisamente TLS su HTTP).
  
### <a name="certificates-for-mobility"></a>Certificati per dispositivi mobili

Se si sta distribuendo dispositivi mobili e si sta supportando l'individuazione automatica per i client mobili, sarà necessario includere nei certificati alcune voci aggiuntive del nome soggetto alternativo per supportare le connessioni protette dai client mobili.
  
Saranno necessari nomi SAN per l'individuazione automatica nei certificati seguenti:
  
- Pool Director
    
- Pool Front End
    
- Proxy inverso
    
Le specifiche sono elencate nelle tabelle seguenti.
  
Questo è il punto in cui una piccola pianificazione preliminare è buona, ma a volte è stata distribuita Skype for Business Server 2019 senza l'intenzione di distribuire dispositivi mobili e che viene rilasciata in un secondo momento quando si dispone già di certificati nell'ambiente. La loro riemissione tramite un'autorità di certificazione interna è in genere piuttosto semplice, ma con i certificati pubblici di un'autorità di certificazione pubblica, questo può essere un po' più costoso.
  
Se è quello che si sta esaminando e se si dispone di molti domini SIP (il che renderebbe più costosa l'aggiunta di SANS), è possibile configurare il proxy inverso per l'utilizzo di HTTP per la richiesta iniziale del servizio di individuazione automatica, invece di usare HTTPS (che è la configurazione predefinita). [L'articolo Plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) contiene ulteriori informazioni su questo articolo.
  
Requisiti del pool di server Director e dei certificati del pool Front End:
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica interno  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL del servizio di individuazione automatica esterno  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
In alternativa, è possibile utilizzare SAN= \* .\<sipdomain\>
  
Requisiti del certificato proxy inverso (CA pubblica):
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica esterno  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Questa san deve essere assegnata al certificato assegnato al listener SSL nel proxy inverso.
  
> [!NOTE]
> Nel listener del proxy inverso saranno disponibili sann per gli URL dei servizi Web esterni. Alcuni esempi sono SAN=skypewebextpool01.contoso.com e dirwebexternal.contoso.com, se è stato distribuito il Director( facoltativo). 
  
## <a name="file-share"></a>Condivisione file
<a name="Fileshare"> </a>

Skype for Business Server 2019 può usare la stessa condivisione file per tutti i file di archiviazione. È necessario tenere presente quanto segue:
  
- Una condivisione file deve essere in uno spazio di archiviazione collegato diretto (DAS) o in una rete di archiviazione (SAN) e questo include DFS (Distributed File System) e una matrice ridondante di dischi indipendenti (RAID) per gli archivi file. Per ulteriori informazioni su DFS per Windows Server 2012, vedere [questa pagina DFS.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- È consigliabile un cluster condiviso per la condivisione file. Se ne si usa già una, è consigliabile eseguire il clustering Windows Server 2012 versioni successive

> [!Note]
> **Perché l'ultima Windows?** Le versioni precedenti potrebbero non disporre delle autorizzazioni appropriate per abilitare tutte le funzionalità. È possibile utilizzare Amministrazione cluster per creare le condivisioni file. Per ulteriori informazioni, vedere questo articolo di supporto Come creare condivisioni file in un [cluster.](https://support.microsoft.com/help/224967)
    
> [!CAUTION]
> È necessario sapere che l'utilizzo di nas (Network Attached Storage) come condivisione file non è supportato, quindi usa una delle opzioni elencate in precedenza. Questa limitazione di supporto è causata dalla progettazione variabile dei dispositivi NAS che devono fornire l'adattabilità del file system al computer basato su Windows Server che accede al file system condiviso dei dispositivi.
