---
title: 'Lync Server 2013: Failover del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="dee28-102">Failover del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dee28-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dee28-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="dee28-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="dee28-104">Il failover per il server di chat persistente è progettato per essere principalmente un processo manuale.</span><span class="sxs-lookup"><span data-stu-id="dee28-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="dee28-105">La procedura di failover si basa sul presupposto che il data center secondario sia attivo e funzionante, ma i servizi di Persistent Chat Server in cui si trova il database principale della chat persistente sono completamente non disponibili, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="dee28-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="dee28-106">Il database primario del server Chat persistente e il database mirror del server di chat persistente non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="dee28-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="dee28-107">Il server front-end di Lync Server non è più presente.</span><span class="sxs-lookup"><span data-stu-id="dee28-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="dee28-108">La procedura si basa su due passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="dee28-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="dee28-109">Recuperare il database principale della chat persistente (MGC).</span><span class="sxs-lookup"><span data-stu-id="dee28-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="dee28-110">Stabilire il mirroring per il nuovo database primario.</span><span class="sxs-lookup"><span data-stu-id="dee28-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="dee28-111">Il database di conformità della chat persistente (mgccomp) non viene superato.</span><span class="sxs-lookup"><span data-stu-id="dee28-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="dee28-112">Il contenuto di questo database è temporaneo e viene eliminato quando l'adattatore di conformità elabora i dati.</span><span class="sxs-lookup"><span data-stu-id="dee28-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="dee28-113">È tua responsabilità, come amministratore della chat persistente, gestire correttamente l'output della scheda per evitare perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="dee28-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="dee28-114">Per eseguire il failover del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="dee28-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="dee28-115">Rimuovere il log shipping dal database di log shipping del server di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="dee28-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="dee28-116">In SQL Server Management Studio connettersi all'istanza del database in cui si trova il database di backup di MGC del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dee28-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="dee28-117">Aprire una finestra di query nel database master.</span><span class="sxs-lookup"><span data-stu-id="dee28-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="dee28-118">Usare il comando seguente per eliminare il log shipping:</span><span class="sxs-lookup"><span data-stu-id="dee28-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="dee28-119">Copiare i file di backup non copiati dalla condivisione di backup alla cartella di destinazione della copia del server di backup.</span><span class="sxs-lookup"><span data-stu-id="dee28-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="dee28-120">Applicare i backup del log delle transazioni non applicati in sequenza al database secondario.</span><span class="sxs-lookup"><span data-stu-id="dee28-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="dee28-121">Per informazioni dettagliate, vedere "procedura: applicare un backup del log delle transazioni (Transact-SQL) http://go.microsoft.com/fwlink/p/?linkid=247428" at.</span><span class="sxs-lookup"><span data-stu-id="dee28-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="dee28-122">Porta il database di backup MGC online.</span><span class="sxs-lookup"><span data-stu-id="dee28-122">Bring the backup mgc database online.</span></span> <span data-ttu-id="dee28-123">Usando la finestra della query visualizzata nel passaggio 1b, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dee28-123">Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="dee28-124">Terminare tutte le connessioni al database di MGC, se presenti:</span><span class="sxs-lookup"><span data-stu-id="dee28-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="dee28-125">**Exec SP\_who2** per identificare le connessioni al database di MGC.</span><span class="sxs-lookup"><span data-stu-id="dee28-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="dee28-126">\*\*uccidere \<SPID\> \*\* per terminare queste connessioni.</span><span class="sxs-lookup"><span data-stu-id="dee28-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="dee28-127">Porta il database online:</span><span class="sxs-lookup"><span data-stu-id="dee28-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="dee28-128">**ripristinare il database di MGC con il ripristino**.</span><span class="sxs-lookup"><span data-stu-id="dee28-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="dee28-129">In Lync Server Management Shell usare il comando **Set-CsPersistentChatState-Identity "Service: atl-cs-001.litwareinc.com"-PoolState FailedOver** per eseguire il failover nel database di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="dee28-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="dee28-130">Assicurarsi di sostituire il nome di dominio completo del pool di chat persistente per atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="dee28-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="dee28-131">Il database di backup di MGC ora funge da database primario.</span><span class="sxs-lookup"><span data-stu-id="dee28-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="dee28-132">In Lync Server Management Shell usare il cmdlet **Install-CsMirrorDatabase** per stabilire un mirror di disponibilità elevata per il database di backup che ora funge da database primario.</span><span class="sxs-lookup"><span data-stu-id="dee28-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="dee28-133">Usa l'istanza del database di backup come database principale e l'istanza del database mirror di backup come istanza di mirror.</span><span class="sxs-lookup"><span data-stu-id="dee28-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="dee28-134">Questo non è lo stesso mirror di quello inizialmente configurato per il database principale durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="dee28-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="dee28-135">Per informazioni dettagliate, vedere la sezione "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione di mirroring SQL per l'elevata disponibilità del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="dee28-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="dee28-136">Impostare i server attivi della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dee28-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="dee28-137">Nella shell dei comandi di Lync Server usare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco di server attivi.</span><span class="sxs-lookup"><span data-stu-id="dee28-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dee28-138">Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database.</span><span class="sxs-lookup"><span data-stu-id="dee28-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="dee28-139">A questo punto, il failover dal database primario del server di chat persistente al database di backup del server di chat persistente viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="dee28-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

