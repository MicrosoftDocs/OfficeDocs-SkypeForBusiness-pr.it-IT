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
description: "Sintesi: preparare i server di Skype for Business Server 2019 e l'infrastruttura del dominio con questo argomento. Hardware, sistema operativo, database, software, tutti i requisiti di sistema e le raccomandazioni, insieme al certificato DNS, alla condivisione file e alle informazioni di Active Directory, sono qui per garantire una corretta installazione e distribuzione della server farm."
ms.openlocfilehash: 8bb12fa9f5d0cd0144604f21d311c50f7f63b0f4
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232377"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Requisiti di sistema per Skype for Business Server 2019
 
**Riepilogo:** Preparare l'installazione di Skype for Business Server 2019 con questo argomento. L'hardware, il sistema operativo, il software, i database, i certificati, il dominio attivo, il DNS e le condivisioni di file sono descritti in questo articolo. Tutti i requisiti di sistema e i suggerimenti sono disponibili per garantire una corretta installazione e distribuzione della server farm.
  
Come si può immaginare, esistono alcuni preparativi da fare prima di iniziare a distribuire Skype for Business Server 2019. In questo articolo viene illustrata la pianificazione per le operazioni seguenti:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Sistemi operativi](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Database SQL di back-end](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [DNS (Domain Name System)](system-requirements.md#DNS)
  
- [Certificati](system-requirements.md#Certs)
  
- [Condivisione file](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware per Skype for Business Server 2019
<a name="Hardware"> </a>

Dopo aver eseguito la topologia (e, in caso contrario, è possibile consultare le [nozioni di base sulla topologia per l'argomento Skype for Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ), è il momento di pensare ai server. I server Skype for Business Server 2019 richiedono hardware a 64 bit. I suggerimenti per l'hardware sono riportati di seguito. Questi non sono requisiti, ma riflettono i requisiti necessari per ottenere prestazioni ottimali. La documentazione relativa alla pianificazione della capacità può essere utile per determinare se è necessario più di questo, a seconda delle circostanze.
  
Hardware consigliato per i server Standard Edition:

|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabyte (GB).  <br/> |
|Disco  <br/> |SIA  <br/> • 8 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (due dischi con RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili alle unità disco meccaniche a 8 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete Dual-Port, 1 Gbps o superiore (possono essere utilizzate 2 schede di rete, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non** sono supportate per i Front End Server, i server back-end e i server Standard Edition. <br/> Fintanto che non sono esposti al sistema operativo e che vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multihomed ed è supportato.  <br/> |


Hardware consigliato per i Front End Server e i server back-end:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o superiore. <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |64 gigabyte (GB).  <br/> |
|Disco  <br/> |SIA  <br/> • 8 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (due dischi con RAID 1 e 6 con RAID 10).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili alle unità disco meccaniche a 8 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete Dual-Port, 1 Gbps o superiore (possono essere utilizzate 2 schede di rete, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non** sono supportate per i Front End Server, i server back-end e i server Standard Edition. <br/> Fintanto che non sono esposti al sistema operativo e che vengono utilizzati per monitorare e gestire l'hardware del server, è possibile disporre di sistemi di gestione fuori banda, ad esempio DRAC o ILO. Questo scenario non costituisce un server multihomed ed è supportato.  <br/> |
   
Hardware consigliato per server perimetrali, Mediation Server autonomi e direttori:
  
|**Componente hardware**|**Consigliata**|
|:-----|:-----|
|CPU  <br/> |Processore Intel Xeon E5-2673 V3 Dual Processor, 6-core, 2,4 gigahertz (GHz) o superiore.  <br/> I processori Intel Itanium non sono supportati per i ruoli di Skype for Business Server 2019.  <br/> |
|Memoria  <br/> |32 gigabyte.  <br/> |
|Disco  <br/> |SIA  <br/> • 4 o più unità disco rigido da 10000 RPM con almeno 72 GB di spazio libero su disco (i dischi devono essere in una configurazione di 2x RAID 1).  <br/> OPPURE  <br/> • Unità SSD (Solid State Drive) in grado di fornire lo stesso spazio libero e prestazioni simili alle unità disco meccaniche a 4 10000 RPM.  <br/> |
|Rete  <br/> |1 scheda di rete Dual-Port, 1 Gbps o superiore (possono essere utilizzate 2 schede di rete, ma è necessario collaborare con un singolo indirizzo MAC e un singolo indirizzo IP).  <br/> Le configurazioni dual o multi-homed **non** sono supportate per i server e i direttori di interoperabilità video. <br/> I server perimetrali richiedono due interfacce di rete che sono schede di rete Dual-Port, 1 Gbps o superiore (o due schede di rete abbinate, per un totale di quattro, ciascuna coppia viene affiancata da un singolo indirizzo MAC e da un singolo indirizzo IP, per un totale di due coppie).  <br/> Nei Mediation Server autonomi, è supportata l'installazione di schede di interfaccia di rete (NIC) aggiuntive per consentire la configurazione di un indirizzo IP PSTN specifico.  <br/> |


> [!NOTE]
> Indipendentemente dal ruolo del server, si consiglia anche le seguenti impostazioni hardware per Skype for Business Server 2019 (può variare a seconda del tipo di hardware acquistato, quindi fare riferimento alla documentazione del produttore per informazioni specifiche):
> - Configurazione del BIOS: deve essere impostata su FLAT da NUMA.
> - Abilitare l'Hyper-Threading.
> - L'impostazione della coda RSS deve essere impostata su 8 code.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Sistemi operativi per Skype for Business Server 2019
<a name="OS"> </a>

Dopo aver installato l'hardware, sarà necessario installare il sistema operativo (OS) che consentirà di installare e utilizzare con successo Skype for Business Server 2019.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Un valore diverso da quello dei sistemi operativi elencati qui non funzionerà correttamente; non provare a installare Skype for Business Server 2019. Ad esempio, l'opzione core del server non è elencata e pertanto non è supportata.

> [!NOTE]
> L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013. È necessario distribuire un pool separato ed eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso. Tutti i server di un pool devono avere la stessa versione del sistema operativo.

> [!NOTE]
> 
> Se si sta installando l'interfaccia di amministrazione di Windows 2019 nel computer con Windows Server 2019, verrà richiesto di eseguire l'attesa di una porta. C'è un liklihood è possibile scegliere la porta 443, ma se il computer ha installato Skype for Business Server 2019 o se è installato Skype for Business Server 2019, è necessario scegliere un numero di porta diverso.
> 
>Perché è questo il caso? Se l'interfaccia di amministrazione di Windows 2019 è in esecuzione sulla porta 443, non sarà possibile connettersi al server utilizzando il pannello di controllo di Skype for business e non sarà possibile connettersi a qualsiasi servizio Web interno in esecuzione nel server (servizio Web della Rubrica, servizio di individuazione automatica, servizio webticket, ecc.).  In effetti, non sarà possibile connettersi a qualsiasi URL del servizio Web interno. Scegliere una porta diversa, nel caso in cui sia necessario o che si desideri inserire l'interfaccia di amministrazione di Windows 2019 su un server con Skype for Business Server 2019.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software che deve essere installato prima di una distribuzione di Skype for Business Server 2019
<a name="Software"> </a>

Ci sono alcuni aspetti che devono essere installati o configurati per qualsiasi server che esegue Skype for Business Server 2019. Di seguito sono elencati i requisiti aggiuntivi per i ruoli del server specifici.

> [!IMPORTANT]
> Skype for business 2019 supporta .NET Framework 4,8. 
  
 **Tutti i server:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Tutti i server Skype for Business Server richiedono l'installazione di Windows PowerShell 3,0.  <br/> • Questo dovrebbe essere installato per impostazione predefinita con Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |Servizi WCF è una **funzionalità** installata come funzionalità di Windows, in **Server Manager**, inizialmente nessun download necessario. <br/> • È necessario assicurarsi che, quando si installa questa funzionalità, o se è già installato e si sta verificando, che l'opzione di **attivazione http** sia anche selezionata e installata, in questo modo: <br/> ![Schermata che mostra l'opzione di attivazione HTTP nelle caratteristiche di .NET Framework 4,5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Se si riceve un popup aggiuntivo, è necessario installare altre attività per l'installazione di HTTP. Questo è normale; fare clic su OK e andare avanti. Se non si riceve questo pop-up, è possibile presumere che gli elementi siano già stati installati e procedere.  <br/> Microsoft .NET Framework è in genere installato quando è installato Windows Server 2016. Skype for Business Server richiede Microsoft .NET Framework 4,7 o 4,8, quindi probabilmente è necessario aggiornarlo. È possibile trovare l'aggiornamento [qui](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Per Windows Server 2016, il runtime del formato Windows Media viene installato con Microsoft Media Foundation.  <br/> Tutti i Front End Server e i server Standard Edition utilizzati per le conferenze richiedono il runtime del formato Windows Media per l'esecuzione dei file di Windows Media Audio (con estensione WMA) che le applicazioni Parcheggio di chiamata, annuncio e Response Group svolgono per gli annunci e la musica.  <br/> |
|Windows Identity Foundation  <br/> |È necessario che Windows Identity Foundation 3,5 supporti gli scenari di autenticazione da server a server per Skype for Business Server 2019.  <br/> • Per Windows Server 2016, non è necessario scaricare nulla. Aprire **Server Manager**e passare alla **procedura guidata Aggiungi ruoli e funzionalità**. **Windows Identity Foundation 3,5** è elencato nella sezione **features** . Se è selezionata, si è a posto. In caso contrario, selezionarlo e fare clic su **Avanti** per raggiungere il pulsante di **installazione** . <br/> |
|Strumenti di amministrazione remota del server  <br/> |Strumenti di amministrazione del ruolo: strumenti di servizi di dominio Active Directory e AD LDS  <br/> |
   
 **È inoltre necessario che i Front End Server e il server Standard Edition siano:**
  
|**Software/ruolo**|**Dettagli**|
|:-----|:-----|
|Internet Information Services (IIS)  <br/> |IIS è necessario su tutti i Front End Server, nonché su tutti i server Standard Edition, con i seguenti moduli selezionati:  <br/> • Caratteristiche HTTP comuni: documento predefinito, errori HTTP, contenuto statico  <br/> • Integrità e diagnostica: registrazione HTTP, strumenti di registrazione, tracciabilità  <br/> • Prestazioni: compressione del contenuto statico, compressione del contenuto dinamico  <br/> • Sicurezza: filtro delle richieste, autenticazione del mapping dei certificati client, autenticazione di Windows  <br/> • Sviluppo di applicazioni: estensibilità .NET 3,5, Extensibility .NET 4,5, ASP.NET 3,5, ASP.NET 4,5, estensioni ISAPI, filtri ISAPI  <br/> • Strumenti di gestione: console di gestione IIS, script e strumenti di gestione di IIS  <br/> Si noti che l'accesso anonimo è necessario anche, ma si ottiene che quando si installa IIS, quindi non si dispone di un posto per selezionarlo nell'elenco.  <br/> |
|Runtime formato Windows Media  <br/> | Per Windows Server 2016, è necessario installare la funzionalità di **Media Foundation** in **Server Manager**. È effettivamente possibile avviare l'installazione di Skype for Business Server 2019 senza questo, ma verrà richiesto di installarlo e quindi riavviare il server, prima che l'installazione di Skype for Business Server 2019 prosegua. È preferibile farlo prima del tempo. <br/> |
|Silverlight  <br/> |È possibile installare la versione più recente di [Silverlight.](https://www.microsoft.com/silverlight/)  <br/> |
   
Per ottenere assistenza, ecco uno script di PowerShell di esempio che è possibile eseguire per automatizzare la seguente operazione:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Database back-end che funzioneranno con Skype for Business Server 2019
<a name="DBs"> </a>

Quando si installa Skype for Business Server 2019 Standard Edition, SQL Server 2016 Express (64-bit Edition).

Skype for Business Server 2019 Enterprise Edition richiederà SQL Server completo, come indicato di seguito (solo versione 64 bit, non utilizzare edizioni a 32 bit):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (versione 64 bit) ed è necessario eseguire gli aggiornamenti più recenti.  <br/> |Microsoft SQL Server 2017 (versione 64 bit) ed è necessario eseguire gli aggiornamenti più recenti.  <br/> |
Microsoft SQL Server 2016 (versione 64 bit) ed è necessario eseguire gli aggiornamenti più recenti.|
 |

Se non viene visualizzata la versione di SQL Server che si desidera utilizzare nell'elenco, non è possibile utilizzarla.
  
> [!NOTE]
> È inoltre necessario installare SQL Server Reporting Services per il ruolo Monitoring Server. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL clustering e SQL always on

Il clustering SQL con Skype for Business Server 2019 è supportato. Se si desidera configurare il clustering SQL, è possibile eseguire questa operazione in SQL Server.
  
Verificare di disporre di una configurazione attiva/passiva per il clustering SQL, che è supportato. Non condividere il nodo passivo con qualsiasi altra istanza di SQL.
  
Per il clustering di failover, è possibile disporre dei seguenti elementi:
  
Due nodi:
  
- Microsoft SQL Server 2019 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.
- Microsoft SQL Server 2017 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.
- Microsoft SQL Server 2016 standard (versione 64 bit) e si consiglia di eseguire il Service Pack più recente.

Sedici-nodo:
  
- Microsoft SQL Server 2019 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.
- Microsoft SQL Server 2017 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.
- Microsoft SQL Server 2016 Enterprise (edizione 64 bit) e si consiglia di eseguire il Service Pack più recente.

SQL always on è supportato ed è possibile leggerne altre informazioni in [disponibilità elevata del server back-end in Skype for Business server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Ulteriori suggerimenti per l'installazione del server:
  
Non installare alcun software client del server Microsoft Internet Security and Acceleration (ISA) o qualsiasi altro software LSP (Layered Service Providers) di Winsock (qualsiasi software di controllo di terze parti o firewall potrebbe essere incluso in questo articolo) in uno dei server front end o di Mediation Server autonomi. Scarse prestazioni del traffico multimediale sono state visualizzate durante l'installazione del software.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Anche se gran parte dei dati di configurazione per i server e i servizi sono archiviati nell'archivio di gestione centrale di Skype for Business Server 2019, esistono ancora alcuni elementi archiviati in Active Directory:
  
|**Objets Active Directory**|**Tipi di oggetti**|
|:-----|:-----|
|Estensioni dello schema  <br/> |Estensioni degli oggetti utente  <br/> |
||Extensions for Skype for Business Server 2015 e Lync Server 2013, per mantenere la compatibilità con le versioni precedenti supportate  <br/> |
|Dati  <br/> |URI SIP dell'utente e altre impostazioni utente  <br/> |
||Oggetti contatto per le applicazioni (come l'applicazione Response Group e l'applicazione Operatore Conferenza)  <br/> |
||Dati pubblicati per la compatibilità con le versioni precedenti  <br/> |
||Un punto di controllo del servizio (SCP) per l'archivio di gestione centrale  <br/> |
||Account di autenticazione Kerberos (un oggetto computer facoltativo)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo per i controller di dominio

È possibile utilizzare i seguenti sistemi operativi per i controller di dominio:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Il livello di funzionalità del dominio di qualsiasi dominio in cui si distribuisce Skype for Business Server 2019 e il livello di funzionalità della foresta di qualsiasi foresta in cui si distribuisce Skype for Business Server 2019, deve essere uno dei seguenti:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
È possibile disporre di controller di dominio di sola lettura in questi ambienti? Certo, purché siano disponibili anche controller di dominio scrivibile.
  
È importante sapere che Skype for Business Server 2019 non supporta i domini con etichetta singola. Cosa sono? Se si dispone di un dominio radice con l'etichetta contoso. local, andrà bene. Se si dispone di un dominio radice appena denominato local, questo non funzionerà e non sarà supportato come risultato. [In questo articolo della Knowledge base](https://support.microsoft.com/kb/300684/)è stato scritto un po' di più.
  
Anche Skype for Business Server 2019 non supporta la ridenominazione dei domini. Se è necessario rinominare il dominio, è necessario disinstallare Skype for Business Server 2019, eseguire la ridenominazione del dominio e quindi reinstallare Skype for Business Server 2019.
  
Infine, è possibile che si tratti di un dominio con un ambiente AD DS bloccato e che vada bene. Sono presenti ulteriori informazioni su come distribuire Skype for Business Server 2019 in un ambiente di servizi di dominio Active Directory bloccato nella documentazione relativa alla distribuzione.
  
### <a name="ad-topologies"></a>Topologie AD

Le topologie supportate in Skype for Business Server 2019 sono:
  
- Foresta singola con singolo dominio
    
- Foresta singola con albero singolo e più domini
    
- Foresta singola con più alberi e spazi dei nomi disgiunti
    
- Più foreste in una topologia di foreste centralizzate
    
- Più foreste in una topologia di foresta di risorse
    
- Più foreste in una topologia di foresta di risorse di Skype for business con Exchange Online
    
- Più foreste in una topologia con foresta di risorse con Skype for business online e Azure Active Directory Connect
    
Sono presenti diagrammi e descrizioni che consentono di determinare la topologia nell'ambiente in uso o ciò che potrebbe essere necessario configurare prima dell'installazione di Skype for Business Server 2019. Per semplificare, è inclusa anche una chiave:
  
![La è una chiave per le icone utilizzate per i diagrammi di topologia di Skype for business](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Foresta singola con singolo dominio

![Diagramma di una foresta singola di Active Directory con un solo dominio](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Non è più facile di così; si tratta di una singola foresta di dominio, una topologia comune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Foresta singola con albero singolo e più domini

![Diagramma di singoli insiemi di strutture, albero singolo e domini di mutiple](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Questo diagramma Visualizza una singola foresta, di nuovo, ma dispone anche di uno o più domini figlio (sono presenti tre in questo esempio specifico). In questo modo, il dominio in cui vengono creati gli utenti potrebbe essere diverso dal dominio in cui è distribuito Skype for Business Server 2019. Perché preoccuparsi di questo problema? È importante tenere presente che quando si distribuisce un pool Front End di Skype for Business Server, tutti i server del pool devono trovarsi in un unico dominio. È possibile disporre di amministrazione tra domini tramite il supporto di Skype for Business Server per i gruppi di amministratori universali di Windows.
  
Nel diagramma precedente, è possibile vedere che gli utenti di un dominio sono in grado di accedere ai pool di Skype for Business Server dallo stesso dominio o da domini diversi, anche se gli utenti si trovano in un dominio figlio.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Foresta singola con più alberi e spazi dei nomi disgiunti

![Diagramma di una singola foresta, più alberi e spazi dei nomi disgiunti](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
È possibile disporre di una topologia simile a questo diagramma, in cui si dispone di una foresta, ma all'interno di tale foresta sono presenti più domini, con spazi dei nomi di Active Directory separati. In questo caso, questo diagramma è una buona illustrazione, perché include gli utenti in tre diversi domini che accedono a Skype for Business Server 2019. Le linee solide indicano che stanno accedendo a un pool di Skype for Business Server nel proprio dominio, mentre una linea tratteggiata indica che andranno a un pool in un albero diverso del tutto.
  
Come si può notare, gli utenti dello stesso dominio, lo stesso albero o persino un albero diverso possono accedere ai pool con esito positivo.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Più foreste in una topologia di foreste centralizzate

![Più foreste in un diagramma della topologia di foresta centrale](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 supporta più insiemi di strutture configurati in una topologia a foresta centralizzata. Se non si è sicuri di essere in grado di utilizzare, la foresta centrale nella topologia utilizza oggetti in esso per rappresentare gli utenti nelle altre foreste e ospita gli account utente per tutti gli utenti nella foresta.
  
Funzionamento. Un prodotto di sincronizzazione della directory, ad esempio Forefront Identity Manager o FIM, gestisce gli account utente dell'organizzazione durante la loro esistenza. Quando un account viene creato o eliminato da una foresta, la modifica viene sincronizzata con il contatto corrispondente nella foresta centrale.
  
Chiaramente, se l'infrastruttura di Active Directory è sul posto, il passaggio a questa topologia potrebbe non essere semplice, ma se si è già presenti o si pianifica l'infrastruttura della foresta, questa può essere una buona scelta. È possibile centralizzare la distribuzione di Skype for Business Server 2019 all'interno di una singola foresta, mentre gli utenti possono cercare, comunicare e visualizzare la presenza di altri utenti in qualsiasi foresta. Tutti gli aggiornamenti dei contatti utente vengono gestiti automaticamente con il software di sincronizzazione.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Più foreste in una topologia di foresta di risorse di Skype for business
<a name="BKMK_multipleforestopology"> </a>

![Più foreste in un diagramma della topologia con foresta di risorse](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
È supportata anche una topologia della foresta di risorse. è il luogo in cui una foresta è dedicata all'esecuzione delle applicazioni server, come Microsoft Exchange Server e Skype for Business Server 2019. Questa foresta di risorse ospita anche una rappresentazione sincronizzata degli oggetti utente attivi, ma non gli account utente abilitati per l'accesso. Pertanto, la foresta di risorse è un ambiente di servizi condivisi per le altre foreste in cui risiedono gli oggetti utente e dispone di una relazione di trust a livello di foresta con la foresta di risorse.
  
Si noti che Exchange Server può essere distribuito nella stessa foresta di risorse di Skype for Business Server o in una foresta diversa.
  
Per distribuire Skype for Business Server 2019 in questo tipo di topologia, è necessario creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste degli utenti (se Microsoft Exchange Server è già presente nell'ambiente, potrebbe essere possibile eseguire questa operazione). È quindi necessario uno strumento di sincronizzazione della directory (come Forefront Identity Manager o FIM) per gestire gli account utente tramite il proprio ciclo di vita.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Più foreste in una topologia di foresta di risorse di Skype for business con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Questa topologia è simile alla topologia descritta in [più foreste in una topologia di foresta di risorse di Skype for business](system-requirements.md#BKMK_multipleforestopology).
  
In questa topologia sono presenti una o più foreste di utenti e Skype for Business Server viene distribuito in una foresta di risorse dedicata. Exchange Server può essere distribuito in locale nella stessa foresta di risorse o in una foresta diversa e configurato per l'ambiente ibrido con Exchange Online oppure i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali. Per questa topologia non è disponibile alcun diagramma.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Più foreste in una topologia con foresta di risorse con Skype for business online e Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Vengono illustrati due insiemi di strutture AD, una foresta di utenti e una foresta di risorse. Le due foreste dispongono di una relazione di trust. Sono sincronizzati con Microsoft 365 utilizzando Azure AD Connect. Tutti gli utenti sono abilitati per Skype for business tramite Microsoft 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
In questo scenario, sono presenti più foreste in locale, con una topologia con foresta di risorse. Esiste una relazione di trust completa tra le foreste di Active Directory. Lo strumento Azure Active Directory Connect viene utilizzato per sincronizzare gli account tra le foreste di utenti locali e Microsoft 365 o Office 365.
  
 L'organizzazione ha anche Microsoft 365 o Office 365 e utilizza [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) per sincronizzare gli account locali con Microsoft 365 o Office 365. Gli utenti abilitati per Skype for business sono abilitati tramite Microsoft 365 o Office 365 e Skype for business online. Skype for Business Server non è distribuito in locale.
  
L'autenticazione Single Sign-on viene fornita da una farm di Active Directory Federation Services che si trova nella foresta di utenti.
  
In questo scenario, è supportata la distribuzione di Exchange locale, Exchange Online, una soluzione di Exchange ibrida o di non distribuire Exchange. Il diagramma Visualizza solo Exchange locale, ma anche le altre soluzioni Exchange sono completamente supportate.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Più foreste in una topologia con foresta di risorse con Skype for business ibrido
<a name="BKMK_multipleforestopology"> </a>

In questo scenario, esistono una o più foreste di utenti locali e Skype for business è distribuito in una foresta di risorse dedicata ed è configurato per la modalità ibrida con Skype for business online. Exchange Server può essere distribuito in locale nella stessa foresta di risorse o in una foresta diversa e può essere configurato per l'ambiente ibrido con Exchange Online. In alternativa, i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali.
  
Per ulteriori informazioni, vedere [configurare un ambiente con più foreste per la versione ibrida di Skype for business](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype for Business Server 2019 richiede DNS, per i motivi seguenti:
  
- DNS consente a Skype for Business Server 2019 di individuare i pool o i server interni, consentendo la comunicazione da server a server.
    
- DNS consente ai computer client di individuare il pool Front end o il server Standard Edition utilizzato per le transazioni SIP.
    
- Associa gli URL semplici per le conferenze ai server che ospitano tali conferenze.
    
- DNS consente agli utenti esterni e ai computer client di connettersi ai server perimetrali o al proxy inverso HTTP per la messaggistica istantanea o per le conferenze.
    
- Consente ai dispositivi per comunicazioni unificate non connessi di individuare il pool Front end o il server Standard Edition in cui è in esecuzione il servizio Web aggiornamento dispositivi per ottenere gli aggiornamenti e inviare i registri.
    
- L'utilizzo di DNS consente ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi.
    
- Viene utilizzato nel bilanciamento del carico DNS.
    
È importante tenere presente che Skype for Business Server 2019 non supporta i nomi di dominio internazionalizzati (Internationalized Domain Name).
  
Ed è estremamente importante tenere presente che qualsiasi nome in DNS deve essere identico al nome del computer configurato su qualsiasi server utilizzato da Skype for Business Server 2019. In particolare, non è possibile avere nomi di breve nell'ambiente e devono avere FQDN per il generatore di topologie.
  
Questo sembra che sarebbe logico per qualsiasi computer già aggiunto a un dominio, ma se si dispone di un server perimetrale che non è aggiunto al dominio, potrebbe avere un nome breve, senza suffisso di dominio. Verificare che non sia il caso, in DNS o nel server perimetrale, o in qualsiasi server o pool di Skype for Business Server 2019.
  
Sicuramente non usano caratteri Unicode o di sottolineatura. I caratteri standard (che sono A-Z, a-z, 0-9 e segni meno) sono supportati da DNS esterni e autorità di certificazione pubbliche (è necessario assegnare FQDN al certificato SN, è importante ricordarlo), in modo da risparmiare un sacco di problemi se il nome è in mente fin dall'inizio.
  
Per ulteriori informazioni sui requisiti DNS per la rete, vedere la sezione [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) della documentazione relativa alla pianificazione.
  
## <a name="certificates"></a>Certificati
<a name="Certs"> </a>

Una delle operazioni più importanti che è possibile eseguire prima della distribuzione è assicurarsi di disporre dei certificati in ordine. Skype for Business Server 2019 ha bisogno di un'infrastruttura a chiave pubblica (PKI) per le connessioni TLS (Transport Layer Security) e MTLS (Mutual Transport Layer Security). In sostanza, per comunicare in modo sicuro in maniera standardizzata, Skype for Business Server utilizza i certificati emessi dalle autorità di certificazione (CAs).
  
Di seguito sono riportate alcune delle operazioni che Skype for Business Server 2019 utilizza i certificati per:
  
- Connessioni TLS tra client e server
    
- Connessioni MTLS tra server
    
- Federazione con individuazione DNS automatica dei partner
    
- Accesso utente remoto per la messaggistica istantanea
    
- Accesso utente esterno alle sessioni audio/video (AV), alla condivisione di applicazioni e alle conferenze
    
- Comunicazione con le applicazioni Web e Outlook Web Access (OWA)
    
Pertanto, la pianificazione del certificato è un must. A questo punto, è possibile esaminare un elenco di alcune delle operazioni da tenere presenti quando si richiedono i certificati:
  
- Tutti i certificati del server devono supportare l'autorizzazione server (utilizzo chiavi avanzato del server).
    
- Tutti i certificati del server devono contenere un punto di distribuzione CRL (CDP).
    
- Tutti i certificati devono essere firmati utilizzando un algoritmo di firma supportato dal sistema operativo. Skype for Business Server 2019 supporta la famiglia di dimensioni digest SHA-1 e SHA-2 (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo.
    
- La registrazione automatica è supportata per i server interni che eseguono Skype for Business Server 2019.
    
- La registrazione automatica non è supportata per i server Edge di Skype for Business Server 2019.
    
> [!NOTE]
> L'utilizzo dell'algoritmo di firma RSASSA-PSS non è supportato e può comportare errori relativi ai problemi di accesso e di inoltro di chiamata, tra gli altri. 
  
- Sono supportate le lunghezze delle chiavi di crittografia pari a 1024, 2048 e 4096. È consigliabile utilizzare la lunghezza della chiave di 2048 e una maggiore.
    
- L'algoritmo digest o hash predefinito è RSA. Sono supportati anche gli algoritmi ECDH_P256, ECDH_P384 e ECDH_P521.
    
Questo è un sacco di cose da pensare, e ci sono una varietà di livelli di comfort con la richiesta di certificati da un'autorità di certificazione. Di seguito vengono fornite ulteriori indicazioni per rendere la pianificazione il più indolore possibile.
  
### <a name="certificates-for-your-internal-servers"></a>Certificati per i server interni

È necessario disporre di certificati per la maggior parte dei server interni e, molto probabilmente, è possibile ottenerli da un'autorità di certificazione interna (ovvero una CA che si trova nel dominio). Se si desidera, è possibile richiedere questi certificati da un'autorità di certificazione esterna (una che si trova su Internet). Se si sta chiedendo quale autorità di certificazione pubblica dovrebbe andare, è possibile consultare l'elenco dei partner di certificato per le [comunicazioni unificate](/SkypeForBusiness/certification/services-ssl) .
  
Sono inoltre necessari certificati quando Skype for Business Server 2019 comunica con altre applicazioni e server, ad esempio Microsoft Exchange Server. Questo, ovviamente, dovrà essere un certificato che può essere utilizzato da queste altre app e server in modo supportato. Skype for Business Server 2019 e altri prodotti Microsoft supportano il protocollo di autorizzazione aperta (OAuth) per l'autenticazione e l'autorizzazione da server a server. Se si è interessati a questo argomento, è presente un ulteriore articolo sulla pianificazione per OAuth e Skype for Business Server 2019.
  
Skype for Business Server 2019 include anche il supporto per i certificati (senza richiedere) firmati utilizzando la funzione hash di crittografia SHA-256. Per supportare l'accesso esterno tramite SHA-256, è necessario che il certificato esterno venga emesso da un'autorità di certificazione pubblica utilizzando SHA-256.
  
Per semplificare le operazioni, sono stati inseriti i requisiti dei certificati per i server Standard Edition, i pool Front end e altri ruoli, nelle tabelle seguenti, con l'contoso.com fittizio utilizzato per gli esempi (probabilmente si utilizzerà qualcos'altro per l'ambiente). Si tratta di tutti i certificati del server Web standard, con chiavi private non esportabili. Alcuni elementi aggiuntivi da prendere nota:
  
- L'utilizzo della chiave avanzata del server viene configurato automaticamente quando si utilizza la configurazione guidata certificati per richiedere i certificati.
    
- Ogni nome descrittivo del certificato deve essere univoco nell'archivio del computer.
    
- Come per i nomi di esempio riportati di seguito, se è stato configurato sipinternal.contoso.com o sipexternal.contoso.com nel DNS, è necessario aggiungerlo al nome alternativo del soggetto del certificato (SAN).
    
Certificati per i server Standard Edition:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nei server Standard Edition, il nome di dominio completo del server corrisponde al nome di dominio completo del pool.  <br/> La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde al nome di dominio completo del server)  <br/> E  <br/> • Soddisfa gli URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \* . contoso.com  <br/> |Non è possibile eseguire l'override del nome FQDN Web interno in Generatore di topologie.  <br/> Se si dispone di più URL semplici, è necessario includerli tutti come SANs.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice con accesso esterno  <br/> • Soddisfa gli URL semplici per dominio SIP  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \* . contoso.com  <br/> |Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per front end server in un pool Front end:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che non corrisponde al nome di dominio completo del server)  <br/> • FQDN del server  <br/> • FQDN del pool di Skype for business  <br/> E  <br/> • Soddisfa gli URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \* . contoso.com  <br/> |Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \* . contoso.com  <br/> |Se sono presenti più URL semplici per le riunioni, sarà necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per il server Director:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |Pool Director  <br/> |FQDN del server Director, FQDN del pool di server Director.  <br/> Se il pool è il server di accesso automatico per i client ed è richiesta la corrispondenza DNS rigorosa nei criteri di gruppo, saranno inoltre necessarie voci per SIP. SipDomain (per ogni dominio SIP di cui si dispone).  <br/> |pool.contoso.com; SAN = dir01. contoso. com  <br/> Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde al nome di dominio completo del server)  <br/> • FQDN del server  <br/> • FQDN del pool di Skype for business  <br/> E  <br/> • Soddisfa gli URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \* . contoso.com  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • Soddisfa gli URL semplici per dominio SIP  <br/> • URL semplice con accesso esterno  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |Il nome FQDN Web esterno del Director deve essere diverso dal pool Front end o dal front end server.  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \* . contoso.com  <br/> |
   
Certificati per Mediation Server autonomo:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |FQDN del pool  <br/> |FQDN del pool  <br/> FQDN del server dei membri del pool  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET  <br/> |
   
Certificati per Survivable Branch Appliance (in particolare, Survivable Branch Appliance 2015 per Skype for Business Server 2019):
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |FQDN del dispositivo  <br/> |SIP. \< SipDomain \> (è necessaria una sola voce per dominio SIP)  <br/> |SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Certificati per l'accesso degli utenti esterni (Edge)

Skype for Business Server 2019 supporta l'utilizzo di un **singolo certificato pubblico** per le interfacce esterne di Access e Web Conferencing Edge, oltre al servizio di autenticazione a/V, che è tutto fornito tramite i server perimetrali. L'interfaccia interna del server perimetrale utilizzerà in genere un certificato privato emesso dall'autorità di certificazione interna, ma se si preferisce, è possibile utilizzare un certificato pubblico anche per questo, se si tratta di una CA attendibile.
  
Il proxy inverso (RP) intende anche utilizzare un certificato pubblico e crittografa la comunicazione dal RP ai client e il RP ai server interni utilizzando HTTP (o più precisamente, TLS su HTTP).
  
### <a name="certificates-for-mobility"></a>Certificati per i dispositivi mobili

Se si sta distribuendo mobilità e si sta supportando l'individuazione automatica per i client mobili, è necessario includere alcune voci aggiuntive del nome alternativo soggetto nei certificati per supportare le connessioni sicure dai client mobili.
  
Sono necessari i nomi di SAN per l'individuazione automatica sui certificati seguenti:
  
- Pool Director
    
- Pool Front End
    
- Proxy inverso
    
Le specifiche sono elencate nelle tabelle seguenti.
  
Questo è il luogo in cui un po' di prepianificazione è valido, ma talvolta è stato distribuito Skype for Business Server 2019 senza l'intenzione di distribuire la mobilità e questo viene fornito in un secondo momento quando si dispone già di certificati nell'ambiente. La loro riemissione tramite una CA interna è in genere piuttosto semplice, ma con certificati pubblici provenienti da un'autorità di certificazione pubblica, che può essere un po' più costosa.
  
Se è ciò che si sta esaminando e se si dispone di un numero elevato di domini SIP (che renderanno l'aggiunta di SANS più onerose), è possibile configurare il proxy inverso per l'utilizzo di HTTP per la richiesta iniziale del servizio di individuazione automatica, anziché utilizzare HTTPS (che è la configurazione predefinita). L'articolo [Plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) contiene ulteriori informazioni.
  
Requisiti dei certificati per pool di server Director e front end:
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica interno  <br/> |SAN = LyncdiscoverInternal. \< SipDomain\>  <br/> |
|URL del servizio di individuazione automatica esterno  <br/> |SAN = lyncdiscover. \< SipDomain\>  <br/> |
   
In alternativa, è possibile utilizzare SAN = \* . \< SipDomain\>
  
Requisiti dei certificati per il proxy inverso (public CA):
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica esterno  <br/> |SAN = lyncdiscover. \< SipDomain\>  <br/> |
   
Questa SAN deve essere assegnata al certificato assegnato al listener SSL nel proxy inverso.
  
> [!NOTE]
> Il listener del proxy inverso avrà SANs per gli URL dei servizi Web esterni. Alcuni esempi sono SAN = skypewebextpool01. contoso. com e dirwebexternal.contoso.com, se è stato distribuito il server Director (facoltativo). 
  
## <a name="file-share"></a>Condivisione file
<a name="Fileshare"> </a>

Skype for Business Server 2019 è in grado di utilizzare la stessa condivisione file per tutti i file di archiviazione. È necessario tenere presente quanto segue:
  
- Una condivisione file deve trovarsi su una rete di archiviazione diretta (DAS, Direct Attached Storage) o su un'area di archiviazione (SAN) e include il file System distribuito (DFS) e un array di dischi indipendenti (RAID) per gli archivi di file. Per ulteriori informazioni su DFS per Windows Server 2012, vedere [Questa pagina DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- È consigliabile disporre di un cluster condiviso per la condivisione file. Se si sta già utilizzando uno, è consigliabile eseguire il clustering di Windows Server 2012 o versioni successive

> [!Note]
> **Perché le finestre più recenti?** Le versioni precedenti potrebbero non disporre delle autorizzazioni appropriate per abilitare tutte le funzionalità. È possibile utilizzare l'amministratore di cluster per creare le condivisioni di file. Per ulteriori informazioni, vedere questo articolo [di supporto su come creare condivisioni di file in un cluster](https://support.microsoft.com/help/224967) .
    
> [!CAUTION]
> È necessario sapere che l'utilizzo di Network Attached Storage (NAS) come condivisione file non è supportato, quindi utilizzare una delle opzioni sopra elencate. Questa limitazione del supporto è causata dalla progettazione variabile di dispositivi NAS che devono fornire l'adattabilità del file System al computer basato su Windows Server che accede al file system condiviso dei dispositivi.
  







