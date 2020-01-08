---
title: 'Lync Server 2013: Pubblicare la topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="66811-102">Pubblicare la topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66811-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66811-103">_**Argomento Ultima modifica:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="66811-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="66811-104">Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario avere effettuato l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="66811-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="66811-105">È anche possibile delegare i diritti e le autorizzazioni di amministratore appropriati.</span><span class="sxs-lookup"><span data-stu-id="66811-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="66811-106">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="66811-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="66811-107">Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="66811-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="66811-108">Dopo aver definito la topologia in Generatore di topologie, è necessario pubblicare la topologia in Central Management store.</span><span class="sxs-lookup"><span data-stu-id="66811-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="66811-109">Central Management store offre uno spazio di archiviazione schematizzato robusto dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di 2013 di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66811-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="66811-110">Consente inoltre di convalidare i dati per garantire la coerenza della configurazione.</span><span class="sxs-lookup"><span data-stu-id="66811-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="66811-111">Tutte le modifiche apportate ai dati di configurazione si verificano presso l'Central Management store, eliminando i problemi di "fuori sincrono".</span><span class="sxs-lookup"><span data-stu-id="66811-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="66811-112">Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia, inclusi i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="66811-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66811-113">SQL Server richiede un minimo di 20 GB di spazio libero su disco per pubblicare correttamente la topologia iniziale e creare il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="66811-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="66811-114">Solo per la versione Enterprise Edition: per pubblicare la topologia, il server back-end basato su SQL Server deve essere online e accessibile con le eccezioni del firewall in posizione.</span><span class="sxs-lookup"><span data-stu-id="66811-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="66811-115">Per informazioni dettagliate su come specificare le eccezioni del firewall, vedere <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">informazioni sui requisiti del firewall per SQL Server con Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66811-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="66811-116">Per informazioni dettagliate sulla configurazione di SQL Server, vedere <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configurare SQL Server per Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66811-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="66811-117">Per pubblicare una topologia</span><span class="sxs-lookup"><span data-stu-id="66811-117">To publish a topology</span></span>

1.  <span data-ttu-id="66811-118">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="66811-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="66811-119">Selezionare per aprire la topologia da un file locale.</span><span class="sxs-lookup"><span data-stu-id="66811-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="66811-120">Se ci si trova nel computer in cui è stata definita la topologia, si trova nella posizione in cui è stato salvato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="66811-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="66811-121">In genere, questa sarà la cartella documenti dell'utente che ha configurato la topologia.</span><span class="sxs-lookup"><span data-stu-id="66811-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="66811-122">Fare clic con il pulsante destro del mouse sul nodo **Lync Server 2013** e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="66811-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="66811-123">Nella pagina **pubblica la topologia** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66811-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="66811-124">Nella pagina **Crea database** selezionare i database che si desidera pubblicare.</span><span class="sxs-lookup"><span data-stu-id="66811-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66811-125">Se non si hanno i diritti appropriati per creare i database, è possibile deselezionare le caselle di controllo accanto a tali database e un utente con diritti appropriati può creare i database in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="66811-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="66811-126">Per informazioni dettagliate, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorizzazioni di distribuzione per SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="66811-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="66811-127">Facoltativamente, fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="66811-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="66811-128">Le opzioni avanzate di posizionamento dei file di dati di SQL Server consentono di selezionare tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66811-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="66811-129">**Determinare automaticamente il percorso del file di database** : questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo il log e i file di dati nella posizione migliore.</span><span class="sxs-lookup"><span data-stu-id="66811-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="66811-130">**Usare le impostazioni predefinite dell'istanza di SQL Server** : questa opzione consente di inserire file di log e di dati nel server basato su SQL Server usando le opzioni di istanza.</span><span class="sxs-lookup"><span data-stu-id="66811-130">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="66811-131">Questa opzione non usa la funzionalità operativa del server basato su SQL Server per determinare le posizioni ottimali per i registri e i dati.</span><span class="sxs-lookup"><span data-stu-id="66811-131">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="66811-132">L'amministratore di SQL Server sposterebbe in genere il log e i file di dati in posizioni appropriate per le procedure di gestione dell'organizzazione e del server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66811-132">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="66811-133">Fare clic su **OK**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="66811-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="66811-134">Nella pagina **Seleziona server di gestione centrale** selezionare un pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="66811-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="66811-135">Facoltativamente, fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="66811-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="66811-136">Le opzioni avanzate di posizionamento dei file di dati di SQL Server consentono di selezionare tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66811-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="66811-137">**Determinare automaticamente il percorso del file di database** : questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo il log e i file di dati nella posizione migliore.</span><span class="sxs-lookup"><span data-stu-id="66811-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="66811-138">**Usare le impostazioni predefinite dell'istanza di SQL Server** : questa opzione consente di inserire file di log e di dati nel server basato su SQL Server usando le opzioni di istanza.</span><span class="sxs-lookup"><span data-stu-id="66811-138">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="66811-139">Questa opzione non usa la funzionalità operativa del server basato su SQL Server per determinare le posizioni ottimali per i registri e i dati.</span><span class="sxs-lookup"><span data-stu-id="66811-139">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="66811-140">L'amministratore di SQL Server sposterebbe in genere il log e i file di dati in posizioni appropriate per le procedure di gestione dell'organizzazione e del server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66811-140">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="66811-141">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="66811-141">Click **OK**.</span></span>

9.  <span data-ttu-id="66811-142">Fare clic su **Avanti** per completare il processo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="66811-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="66811-143">Al termine del processo di pubblicazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="66811-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="66811-144">Quando la topologia è stata pubblicata correttamente, è possibile iniziare a installare una replica locale di Central Management store in ogni server che esegue Lync Server 2013 nella topologia.</span><span class="sxs-lookup"><span data-stu-id="66811-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="66811-145">È consigliabile iniziare con il primo pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="66811-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66811-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66811-146">See Also</span></span>


[<span data-ttu-id="66811-147">Configurazione di Front End Server e pool Front End per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66811-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

