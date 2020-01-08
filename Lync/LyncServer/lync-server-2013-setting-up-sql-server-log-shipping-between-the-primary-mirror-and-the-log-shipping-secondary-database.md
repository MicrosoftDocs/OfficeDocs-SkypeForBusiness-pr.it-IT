---
title: 'Lync Server 2013: Configurazione del log shipping di SQL Server tra il mirror primario e il database secondario di log shipping'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="ffe37-102">Configurazione del log shipping di SQL Server tra il mirror primario e il database secondario di log shipping in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffe37-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffe37-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ffe37-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ffe37-104">Eseguire la procedura seguente per continuare il log shipping se il database principale della chat persistente non viene superato nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="ffe37-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="ffe37-105">Eseguire manualmente il failover del database principale della chat persistente in mirror.</span><span class="sxs-lookup"><span data-stu-id="ffe37-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="ffe37-106">Questa operazione viene eseguita tramite Lync Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="ffe37-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="ffe37-107">Per informazioni dettagliate, vedere "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione di mirroring SQL per l'elevata disponibilità del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="ffe37-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="ffe37-108">In SQL Server Management Studio connettersi all'istanza del mirror del server di chat persistente principale.</span><span class="sxs-lookup"><span data-stu-id="ffe37-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="ffe37-109">Verificare che l'agente SQL Server sia in uso.</span><span class="sxs-lookup"><span data-stu-id="ffe37-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="ffe37-110">Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="ffe37-111">In **selezionare una pagina**fare clic su **distribuzione log transazioni**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="ffe37-112">Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .</span><span class="sxs-lookup"><span data-stu-id="ffe37-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="ffe37-113">In **backup del log delle transazioni**fare clic su **impostazioni di backup**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="ffe37-114">Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ffe37-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="ffe37-115">Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella finestra di dialogo **se la cartella di backup si trova nel server principale, digitare un percorso locale nella casella della cartella** .</span><span class="sxs-lookup"><span data-stu-id="ffe37-115">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="ffe37-116">Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.</span><span class="sxs-lookup"><span data-stu-id="ffe37-116">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ffe37-117">Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella.</span><span class="sxs-lookup"><span data-stu-id="ffe37-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="ffe37-118">Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.</span><span class="sxs-lookup"><span data-stu-id="ffe37-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="ffe37-119">Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="ffe37-120">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ffe37-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ffe37-121">Usa le stesse impostazioni usate per il database primario.</span><span class="sxs-lookup"><span data-stu-id="ffe37-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="ffe37-122">In **compressione**selezionare **Usa l'impostazione predefinita del server**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="ffe37-123">In **istanze server secondarie e database**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="ffe37-124">Fare clic su **Connetti**e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="ffe37-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="ffe37-125">Nella casella **database secondario** selezionare il database **MGC** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="ffe37-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="ffe37-126">Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="ffe37-127">Nella scheda **copia file** , nella **cartella di destinazione per i file copiati**, digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-127">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="ffe37-128">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="ffe37-128">This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="ffe37-129">Aprire l'elenco a discesa **configurazione script** e selezionare **configurazione script nella finestra nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ffe37-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="ffe37-130">Nella finestra nuova query, in **Proprietà database**, fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ffe37-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="ffe37-131">Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga:-- \* \* \* \* \* \* end: script da eseguire \* \* \* \* \* \*in primo piano:.</span><span class="sxs-lookup"><span data-stu-id="ffe37-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ffe37-132">L'esecuzione manuale di questo script è necessaria perché in SQL Server Management Studio non è supportato più database primari in una configurazione di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ffe37-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="ffe37-133">Selezionare **Annulla** per chiudere il pannello di configurazione del file di log shipping e stabilire una configurazione di lavoro che implementi correttamente la spedizione del file di log sia per il database primario che per il mirroring (in caso di failover).</span><span class="sxs-lookup"><span data-stu-id="ffe37-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="ffe37-134">Non eseguire manualmente il backup del database principale della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ffe37-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="ffe37-135">Questa operazione viene eseguita tramite Lync Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="ffe37-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="ffe37-136">Per informazioni dettagliate, vedere "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione di mirroring SQL per l'elevata disponibilità del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="ffe37-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ffe37-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffe37-137">See Also</span></span>


[<span data-ttu-id="ffe37-138">Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffe37-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="ffe37-139">Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffe37-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

