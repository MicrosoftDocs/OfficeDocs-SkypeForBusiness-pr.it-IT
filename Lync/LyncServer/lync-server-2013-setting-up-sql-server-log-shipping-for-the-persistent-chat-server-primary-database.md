---
title: 'Lync Server 2013: Configurazione del log shipping di SQL Server per il database primario del server chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de2285d77ba2228b90d244c841efc0b986bf454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="4ba25-102">Configurazione del log shipping di SQL Server in Lync Server 2013 per il database primario del server chat persistente</span><span class="sxs-lookup"><span data-stu-id="4ba25-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ba25-103">_**Argomento Ultima modifica:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="4ba25-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="4ba25-104">In SQL Server Management Studio connettersi all'istanza del database di log shipping secondario del server di chat persistente e verificare che SQL Server Agent sia in uso.</span><span class="sxs-lookup"><span data-stu-id="4ba25-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="4ba25-105">Con SQL Server Management Studio connesso all'istanza del database primario della chat persistente, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="4ba25-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="4ba25-106">Verificare che l'agente SQL Server sia in uso.</span><span class="sxs-lookup"><span data-stu-id="4ba25-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="4ba25-107">Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="4ba25-108">In **selezionare una pagina**fare clic su **distribuzione log transazioni**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="4ba25-109">Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .</span><span class="sxs-lookup"><span data-stu-id="4ba25-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="4ba25-110">In **backup del log delle transazioni**fare clic su **impostazioni di backup**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="4ba25-111">Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4ba25-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="4ba25-112">Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova nel server principale, digitare un percorso locale alla cartella (esempio: c:\\backup)** .</span><span class="sxs-lookup"><span data-stu-id="4ba25-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="4ba25-113">Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.</span><span class="sxs-lookup"><span data-stu-id="4ba25-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4ba25-114">Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella.</span><span class="sxs-lookup"><span data-stu-id="4ba25-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="4ba25-115">Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.</span><span class="sxs-lookup"><span data-stu-id="4ba25-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="4ba25-116">Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="4ba25-117">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4ba25-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="4ba25-118">In **compressione**selezionare **Usa l'impostazione predefinita del server**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="4ba25-119">In **istanze server secondarie e database**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="4ba25-120">Fare clic su **Connetti** e Connetti all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="4ba25-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="4ba25-121">Nella casella **database secondario** selezionare il database **MGC** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="4ba25-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="4ba25-122">Nella scheda **Inizializza database secondario** scegliere l'opzione **Sì, generare un backup completo del database principale e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="4ba25-123">Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4ba25-123">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="4ba25-124">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="4ba25-124">This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="4ba25-125">Nota la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="4ba25-126">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4ba25-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="4ba25-127">Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4ba25-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="4ba25-128">Nella scheda **Ripristina** , in **stato del database durante il ripristino dei backup**, scegliere l'opzione **Nessuna modalità di recupero** .</span><span class="sxs-lookup"><span data-stu-id="4ba25-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="4ba25-129">In **delay Restoring backups almeno:** selezionare **0 minuti**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="4ba25-130">Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="4ba25-131">Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="4ba25-132">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**, regolare la pianificazione di SQL Server Agent come richiesto e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ba25-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="4ba25-133">Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4ba25-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="4ba25-134">Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ba25-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

