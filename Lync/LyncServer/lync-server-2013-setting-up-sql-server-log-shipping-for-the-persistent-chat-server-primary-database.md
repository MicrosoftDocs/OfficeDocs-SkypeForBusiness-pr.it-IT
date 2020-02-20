---
title: 'Lync Server 2013: configurazione del log shipping di SQL Server per il database primario del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d91697baca93da3e4e9ea8c446ce42e02309e6f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="000fa-102">Configurazione del log shipping di SQL Server in Lync Server 2013 per il database primario del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="000fa-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="000fa-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="000fa-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="000fa-104">Se si utilizza SQL Server Management Studio, connettersi all'istanza del database secondario di log shipping del server di chat persistente e verificare che SQL Server Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="000fa-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="000fa-105">Se si utilizza SQL Server Management Studio connesso all'istanza del database primario di Persistent Chat, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="000fa-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="000fa-106">Verificare che SQL Server Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="000fa-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="000fa-107">Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="000fa-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="000fa-108">In **Seleziona una pagina**fare clic su **log shipping delle transazioni**.</span><span class="sxs-lookup"><span data-stu-id="000fa-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="000fa-109">Selezionare la casella **di controllo Abilita come database primario in una configurazione per il log shipping** .</span><span class="sxs-lookup"><span data-stu-id="000fa-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="000fa-110">In **backup dei log delle transazioni**fare clic su **impostazioni di backup**.</span><span class="sxs-lookup"><span data-stu-id="000fa-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="000fa-111">Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="000fa-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="000fa-112">Se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova sul server primario, digitare un percorso locale per la cartella (ad esempio: c\\: backup)** .</span><span class="sxs-lookup"><span data-stu-id="000fa-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="000fa-113">Se la cartella di backup non è presente nel server primario, è possibile lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="000fa-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="000fa-114">Se l'account di servizio di SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella.</span><span class="sxs-lookup"><span data-stu-id="000fa-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="000fa-115">Configurare i **file di eliminazione precedenti e di** **avviso se nessun backup viene eseguito all'interno** dei parametri.</span><span class="sxs-lookup"><span data-stu-id="000fa-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="000fa-116">Esaminare la pianificazione di backup elencata nella casella **pianificazione** in **processo di backup**.</span><span class="sxs-lookup"><span data-stu-id="000fa-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="000fa-117">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e modificare la pianificazione di SQL Server Agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="000fa-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="000fa-118">In **compressione**selezionare **utilizza l'impostazione predefinita del server**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="000fa-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="000fa-119">In **istanze e database secondari del server**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="000fa-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="000fa-120">Fare clic su **Connetti** e connettersi all'istanza di SQL Server configurata come server secondario.</span><span class="sxs-lookup"><span data-stu-id="000fa-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="000fa-121">Nella casella **database secondario** selezionare il database di **MGC** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="000fa-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="000fa-122">Nella scheda **Inizializza database secondario** selezionare l'opzione **Sì, generare un backup completo del database primario e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.</span><span class="sxs-lookup"><span data-stu-id="000fa-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="000fa-123">Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="000fa-123">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="000fa-124">Questa cartella si trova spesso nel server secondario.</span><span class="sxs-lookup"><span data-stu-id="000fa-124">This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="000fa-125">Tenere presente la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**.</span><span class="sxs-lookup"><span data-stu-id="000fa-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="000fa-126">Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e modificare la pianificazione di SQL Server Agent in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="000fa-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="000fa-127">Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="000fa-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="000fa-128">Nella scheda **Ripristina** , in **stato di database durante il ripristino dei backup**, scegliere l'opzione **modalità No Recovery** .</span><span class="sxs-lookup"><span data-stu-id="000fa-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="000fa-129">In **delay Restoring backups almeno:**, selezionare **0 minuti**.</span><span class="sxs-lookup"><span data-stu-id="000fa-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="000fa-130">Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.</span><span class="sxs-lookup"><span data-stu-id="000fa-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="000fa-131">Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**.</span><span class="sxs-lookup"><span data-stu-id="000fa-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="000fa-132">Per personalizzare la pianificazione dell'installazione, fare clic su **pianificazione**, modificare la pianificazione di SQL Server Agent in base alle esigenze e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="000fa-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="000fa-133">Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.</span><span class="sxs-lookup"><span data-stu-id="000fa-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="000fa-134">Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="000fa-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

