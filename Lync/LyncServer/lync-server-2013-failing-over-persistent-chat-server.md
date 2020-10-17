---
title: 'Lync Server 2013: failover del server Chat persistente'
description: 'Lync Server 2013: failover del server Chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a3a8f5df203cc23be39a4a691ad713330eab59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554962"
---
# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="eefd7-103">Failover del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eefd7-103">Failing over Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eefd7-104">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="eefd7-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="eefd7-105">Il failover per il server Chat persistente è stato creato principalmente come processo manuale.</span><span class="sxs-lookup"><span data-stu-id="eefd7-105">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="eefd7-106">La procedura di failover si basa sul presupposto che il data center secondario sia attivo e in esecuzione, ma i servizi del server Chat persistente in cui si trova il database di Persistent Chat primario sono completamente non disponibili, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="eefd7-106">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="eefd7-107">Database primario del server Chat persistente e database mirror del server Chat persistente sono indesiderati.</span><span class="sxs-lookup"><span data-stu-id="eefd7-107">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="eefd7-108">Lync Server front end server è inverso.</span><span class="sxs-lookup"><span data-stu-id="eefd7-108">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="eefd7-109">La procedura prevede due passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="eefd7-109">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="eefd7-110">Ripristinare il database di Persistent Chat principale (MGC).</span><span class="sxs-lookup"><span data-stu-id="eefd7-110">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="eefd7-111">Configurazione del mirroring per il nuovo database primario.</span><span class="sxs-lookup"><span data-stu-id="eefd7-111">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="eefd7-112">Non è stato eseguito il failover del database di conformità di Persistent Chat (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="eefd7-112">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="eefd7-113">Il contenuto di questo database è temporaneo e viene eliminato durante l'elaborazione dei dati nell'adattatore di conformità.</span><span class="sxs-lookup"><span data-stu-id="eefd7-113">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="eefd7-114">La responsabilità, come amministratore di chat persistente, è quella di gestire correttamente l'output dell'adattatore per evitare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="eefd7-114">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="eefd7-115">Per eseguire il failover del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="eefd7-115">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="eefd7-116">Rimuovere il log shipping dal database del log shipping del server di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="eefd7-116">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="eefd7-117">Tramite SQL Server Management Studio connettersi all'istanza del database in cui si trova il database di backup di MGC del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="eefd7-117">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="eefd7-118">Aprire una finestra di query nel database master.</span><span class="sxs-lookup"><span data-stu-id="eefd7-118">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="eefd7-119">Usare questo comando per eliminare la distribuzione dei log:</span><span class="sxs-lookup"><span data-stu-id="eefd7-119">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="eefd7-120">Copiare i file di backup non copiati dalla condivisione di backup nella cartella di destinazione della copia del server di backup.</span><span class="sxs-lookup"><span data-stu-id="eefd7-120">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="eefd7-121">Applicare i backup dei log delle transazioni non applicati in sequenza al database secondario.</span><span class="sxs-lookup"><span data-stu-id="eefd7-121">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="eefd7-122">Per informazioni dettagliate, vedere "How to: Apply a Transaction log backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428 .</span><span class="sxs-lookup"><span data-stu-id="eefd7-122">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="eefd7-p103">Connettere il database mgc di backup. Usando la finestra di query aperta al passaggio 1b, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eefd7-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="eefd7-125">Terminare tutte le connessioni al database mgc, se disponibili:</span><span class="sxs-lookup"><span data-stu-id="eefd7-125">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="eefd7-126">**Exec SP \_ who2** per identificare le connessioni al database di MGC.</span><span class="sxs-lookup"><span data-stu-id="eefd7-126">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="eefd7-127">\*\*Kill \<spid\> \*\* per terminare queste connessioni.</span><span class="sxs-lookup"><span data-stu-id="eefd7-127">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="eefd7-128">Connettere il database:</span><span class="sxs-lookup"><span data-stu-id="eefd7-128">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="eefd7-129">**ripristinare i database di MGC con il ripristino**.</span><span class="sxs-lookup"><span data-stu-id="eefd7-129">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="eefd7-130">In Lync Server Management Shell, utilizzare il comando **Set-CsPersistentChatState-Identity "Service: atl-cs-001.litwareinc.com" – PoolState FailedOver** per eseguire il failover nel database di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="eefd7-130">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="eefd7-131">Assicurarsi di sostituire il nome di dominio completo del pool di Persistent Chat per atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="eefd7-131">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="eefd7-132">Il database mgc di backup funge ora da database primario.</span><span class="sxs-lookup"><span data-stu-id="eefd7-132">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="eefd7-133">In Lync Server Management Shell, utilizzare il cmdlet **Install-CsMirrorDatabase** per definire un mirror a disponibilità elevata per il database di backup che ora funge da database primario.</span><span class="sxs-lookup"><span data-stu-id="eefd7-133">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="eefd7-134">Usare l'istanza del database di backup come database primario e l'istanza del database mirror di backup come istanza mirror.</span><span class="sxs-lookup"><span data-stu-id="eefd7-134">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="eefd7-135">Questo mirror non corrisponde al mirror configurato inizialmente per il database primario durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="eefd7-135">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="eefd7-136">Per informazioni dettagliate, vedere la sezione "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione del mirroring SQL per la disponibilità elevata del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="eefd7-136">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="eefd7-137">Impostare i server attivi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="eefd7-137">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="eefd7-138">Dalla shell dei comandi di Lync Server, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco di server attivi.</span><span class="sxs-lookup"><span data-stu-id="eefd7-138">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eefd7-139">Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.</span><span class="sxs-lookup"><span data-stu-id="eefd7-139">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="eefd7-140">A questo punto, il failover dal database primario del server Chat persistente al database di backup del server Chat persistente è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="eefd7-140">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

