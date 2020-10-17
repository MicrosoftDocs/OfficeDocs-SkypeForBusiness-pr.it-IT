---
title: 'Lync Server 2013: indurimento e protezione dei database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536913"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="dbd19-102">Indurimento e protezione dei database di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbd19-102">Hardening and protecting the databases of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbd19-103">_**Ultimo argomento modificato:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="dbd19-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="dbd19-104">Microsoft Lync Server 2013 dipende anche da database di SQL Server per l'archiviazione delle informazioni utente, dello stato delle conferenze, dei dati di archiviazione e delle registrazioni dettagli chiamata (CDRs).</span><span class="sxs-lookup"><span data-stu-id="dbd19-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="dbd19-105">Per massimizzare la disponibilità dei dati di Lync Server 2013 nei database back-end di Lync Server, è possibile suddividere i dati dell'applicazione in modo da migliorare la tolleranza di errore e semplificare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="dbd19-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="dbd19-106">Per raggiungere questi obiettivi, suddividere i dati dell'applicazione per:</span><span class="sxs-lookup"><span data-stu-id="dbd19-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="dbd19-107">**Utilizzo delle procedure**     consigliate per il partizionamento del server Separare i file del sistema operativo, dell'applicazione e del programma dai file di dati.</span><span class="sxs-lookup"><span data-stu-id="dbd19-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="dbd19-108">**Archiviazione dei file di registro delle transazioni e dei file**     di database Archiviare questi file separatamente per aumentare la tolleranza di errore e ottimizzare il ripristino e archiviarli su un disco o un volume crittografato.</span><span class="sxs-lookup"><span data-stu-id="dbd19-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="dbd19-109">**Utilizzo del clustering**     di server Eseguire il clustering dei server back-end per ottimizzare la disponibilità del sistema di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbd19-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="dbd19-110">**Verificare che tutti i backup dei dati siano crittografati e gestiti correttamente**     I supporti di backup persi, ignorati o fuori luogo possono rappresentare una minaccia significativa per la sicurezza dei dati per le distribuzioni di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbd19-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="dbd19-111">In qualsiasi server Lync Server 2013 eccetto il server Standard Edition, l'istanza di SQL Server Express (istanza di RTCLOCAL) non è accessibile in remoto e non viene creata alcuna eccezione del firewall locale, ad eccezione di SQL Server Express su un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="dbd19-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="dbd19-112">In un server Standard Edition, sia il database back-end che l'archivio di gestione centrale (CMS) sono configurati per essere accessibili in remoto.</span><span class="sxs-lookup"><span data-stu-id="dbd19-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="dbd19-113">Per indurire i database di SQL Server, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbd19-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="dbd19-114">Personalizzare il firewall di SQL Server Express nei server Standard Edition, limitando l'ambito dei server che possono accedere in remoto al database.</span><span class="sxs-lookup"><span data-stu-id="dbd19-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="dbd19-115">Per impostazione predefinita, qualsiasi indirizzo IP può accedere in remoto al database.</span><span class="sxs-lookup"><span data-stu-id="dbd19-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="dbd19-116">Utilizzare Gestione configurazione SQL Server per specificare i protocolli, gli indirizzi IP e le porte per l'accesso remoto a SQL Server:</span><span class="sxs-lookup"><span data-stu-id="dbd19-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="dbd19-117">Lync Server 2013 utilizza il protocollo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="dbd19-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="dbd19-118">Supporta IP versione 4 (IPv4), ma non IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="dbd19-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dbd19-119">Lync Server 2013 può funzionare in una rete con doppio stack IP abilitato.</span><span class="sxs-lookup"><span data-stu-id="dbd19-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="dbd19-120">Lync Server 2013 supporta più indirizzi IP (schede indirizzi di rete multihomed).</span><span class="sxs-lookup"><span data-stu-id="dbd19-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="dbd19-121">È possibile specificare che SQL Server ascolti solo indirizzi IP specifici (indirizzo individuale o subnet) e utilizzi solo protocolli specifici.</span><span class="sxs-lookup"><span data-stu-id="dbd19-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="dbd19-122">Lync Server 2013 supporta le porte SQL Server statiche e dinamiche.</span><span class="sxs-lookup"><span data-stu-id="dbd19-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="dbd19-123">Eseguire SQL Server in una porta statica (non predefinita) e non eseguire SQL Server browser (pertanto non è possibile segnalare la porta di attesa al client).</span><span class="sxs-lookup"><span data-stu-id="dbd19-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="dbd19-124">Questo richiede una configurazione personalizzata su ogni client SQL Server, compresi front end server, Monitoring Server, server di archiviazione e console amministrative (in cui è in esecuzione Lync Server Management Shell, il pannello di controllo di Lync Server o il generatore di topologie) e tutti gli altri server che eseguono i database di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbd19-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dbd19-125">L'accesso ai database deve essere limitato agli amministratori di database attendibili.</span><span class="sxs-lookup"><span data-stu-id="dbd19-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="dbd19-126">Un amministratore di database dannoso potrebbe inserire o modificare i dati nei database per acquisire i privilegi sui server Lync Server 2013 o ottenere informazioni riservate dai servizi, anche se all'amministratore del database non è stato concesso l'accesso diretto o il controllo dei server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbd19-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="dbd19-127">Per informazioni dettagliate sulle configurazioni personalizzate e sull'indurimento dei database di SQL Server, vedere l'articolo del Blog di NextHop "utilizzo di Lync Server 2010 con una configurazione di rete di SQL Server personalizzata" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .</span><span class="sxs-lookup"><span data-stu-id="dbd19-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dbd19-128">È inoltre possibile indurire i sistemi operativi e i server applicazioni ed è possibile utilizzare criteri di gruppo per implementare blocchi di sicurezza nella distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbd19-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="dbd19-129">Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">hardening and protecting Servers and Applications for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dbd19-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

