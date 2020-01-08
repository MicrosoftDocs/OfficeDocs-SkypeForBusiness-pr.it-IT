---
title: 'Lync Server 2013: Protezione avanzata e sicurezza dei database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 265ca1058b4f3b41c5f0dbc4c5b2cdcd631fa911
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="22556-102">Protezione avanzata e sicurezza dei database di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22556-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22556-103">_**Argomento Ultima modifica:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="22556-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="22556-104">Microsoft Lync Server 2013 dipende anche da database di SQL Server per l'archiviazione di informazioni utente, stato conferenza, dati di archiviazione e record dettagli chiamata (CDRs).</span><span class="sxs-lookup"><span data-stu-id="22556-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="22556-105">È possibile massimizzare la disponibilità dei dati di Lync Server 2013 nei database back-end di Lync Server, partizionando i dati dell'applicazione in modo da migliorare la tolleranza degli errori e semplificando la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="22556-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="22556-106">Per raggiungere questi obiettivi, partizionare i dati dell'applicazione in base a:</span><span class="sxs-lookup"><span data-stu-id="22556-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="22556-107">**Uso delle procedure**   consigliate per il partizionamento dei server separare il sistema operativo, l'applicazione e i file di programma dai file di dati.</span><span class="sxs-lookup"><span data-stu-id="22556-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="22556-108">**Archiviazione dei file di log delle transazioni e dei file**   di database archiviare separatamente questi file per aumentare la tolleranza di errore e ottimizzare il ripristino e archiviarli in un disco o un volume crittografato.</span><span class="sxs-lookup"><span data-stu-id="22556-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="22556-109">**Uso**del cluster clustering dei server back-end per ottimizzare la disponibilità di sistema di Lync Server 2013.   </span><span class="sxs-lookup"><span data-stu-id="22556-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="22556-110">**Assicurarsi che tutti i backup dei dati siano crittografati e gestiti**   correttamente, i file multimediali persi, eliminati o smarriti possano rappresentare una minaccia significativa per la sicurezza dei dati per le distribuzioni di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22556-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="22556-111">In qualsiasi server Lync Server 2013 eccetto il server Standard Edition, l'istanza di SQL Server Express (istanza di RTCLOCAL) non è accessibile in remoto e non vengono create eccezioni del firewall locale, ad eccezione di SQL Server Express in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="22556-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="22556-112">In un server Standard Edition, sia il database back-end che il Central Management store (CMS) sono configurati per l'accessibilità remota.</span><span class="sxs-lookup"><span data-stu-id="22556-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="22556-113">Per indurire i database di SQL Server, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22556-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="22556-114">Personalizzare il firewall di SQL Server Express nei server Standard Edition, limitando l'ambito dei server che possono accedere in remoto al database.</span><span class="sxs-lookup"><span data-stu-id="22556-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="22556-115">Per impostazione predefinita, qualsiasi indirizzo IP può accedere in remoto al database.</span><span class="sxs-lookup"><span data-stu-id="22556-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="22556-116">Usare Gestione configurazione SQL Server per specificare i protocolli, gli indirizzi IP e le porte per l'accesso remoto a SQL Server:</span><span class="sxs-lookup"><span data-stu-id="22556-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="22556-117">Lync Server 2013 usa il protocollo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="22556-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="22556-118">Supporta IP versione 4 (IPv4), ma non IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="22556-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="22556-119">Lync Server 2013 può funzionare in una rete con lo stack Dual IP abilitato.</span><span class="sxs-lookup"><span data-stu-id="22556-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="22556-120">Lync Server 2013 supporta più indirizzi IP (schede di indirizzi di rete multihomed).</span><span class="sxs-lookup"><span data-stu-id="22556-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="22556-121">È possibile specificare che SQL Server ascolti solo indirizzi IP specifici (indirizzo individuale o subnet) e usi solo protocolli specifici.</span><span class="sxs-lookup"><span data-stu-id="22556-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="22556-122">Lync Server 2013 supporta le porte SQL Server statiche e dinamiche.</span><span class="sxs-lookup"><span data-stu-id="22556-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="22556-123">Eseguire SQL Server in una porta statica (non predefinita) e non eseguire SQL Server browser (in modo che non possa segnalare la porta di attesa al client).</span><span class="sxs-lookup"><span data-stu-id="22556-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="22556-124">Questo richiede una configurazione personalizzata in ogni client di SQL Server, inclusi i server front-end, il server di monitoraggio, il server di archiviazione e le console di amministrazione (in cui è in corso Lync Server Management Shell, pannello di controllo di Lync Server o generatore di topologie) e tutti gli altri Server che gestiscono database Lync Server).</span><span class="sxs-lookup"><span data-stu-id="22556-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22556-125">L'accesso ai database deve essere limitato agli amministratori di database attendibili.</span><span class="sxs-lookup"><span data-stu-id="22556-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="22556-126">Un amministratore di database malintenzionato può inserire o modificare i dati nei database per acquisire privilegi sui server di Lync Server 2013 o ottenere informazioni riservate dai servizi, anche se non è stato concesso l'accesso diretto o l'amministratore del database controllo dei server di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22556-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="22556-127">Per informazioni dettagliate sulle configurazioni personalizzate e l'indurimento dei database di SQL Server, vedere l'articolo di Blog di NextHop "utilizzo di Lync Server 2010 con una configurazione [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)di rete SQL Server personalizzata".</span><span class="sxs-lookup"><span data-stu-id="22556-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22556-128">È anche possibile indurire i sistemi operativi e i server delle applicazioni ed è possibile usare criteri di gruppo per implementare il blocco della sicurezza nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22556-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="22556-129">Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">indurimento e protezione di server e applicazioni per Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="22556-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

