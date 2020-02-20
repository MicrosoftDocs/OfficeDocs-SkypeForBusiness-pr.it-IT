---
title: 'Lync Server 2013: associazione di un archivio di monitoraggio a un pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889179c5302a0ff8d59b5cf438c7ba0ab3c489f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="224ea-102">Associazione di un archivio di monitoraggio a un pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="224ea-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="224ea-103">_**Ultimo argomento modificato:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="224ea-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="224ea-104">In Microsoft Lync Server 2013 i dati di monitoraggio possono essere raccolti solo nei pool Front end che sono stati associati a un archivio di monitoraggio, un'attività in genere eseguita si definisce un pool Front end in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="224ea-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="224ea-105">Per associare un archivio di monitoraggio a un nuovo pool Front End, è necessario selezionare l'opzione **monitoraggio (registrazione dettagli chiamata e registrazione delle metriche sulla qualità delle esperienze)** nella pagina **Seleziona funzionalità** della procedura guidata Definisci nuovo pool Front end.</span><span class="sxs-lookup"><span data-stu-id="224ea-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="224ea-106">Si noti che, se si seleziona questa opzione, è necessario specificare anche un archivio SQL per completare la procedura guidata. Tuttavia, questo archivio non deve esistere nel momento in cui viene eseguita la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="224ea-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="224ea-107">Questo significa che è possibile associare un pool a un archivio di monitoraggio, quindi installarlo e configurarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="224ea-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="224ea-108">In alternativa, è possibile associare un pool Front End esistente a un archivio di monitoraggio nuovo o diverso eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="224ea-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="224ea-109">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**, quindi fare clic su **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="224ea-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="224ea-110">Nella finestra di dialogo **Generatore di topologie** selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="224ea-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="224ea-p102">Nella finestra di dialogo **Salva con nome** immettere un nome file per la topologia corrente e quindi fare clic su **Salva**. La topologia salvata può essere successivamente recuperata e ripubblicata in caso di problemi con la nuova topologia.</span><span class="sxs-lookup"><span data-stu-id="224ea-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="224ea-113">In Generatore di topologie espandere **Lync Server 2013**, espandere il nome del sito contenente il pool Front end e quindi fare clic su Espandi **pool Enterprise Edition front end**.</span><span class="sxs-lookup"><span data-stu-id="224ea-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="224ea-114">Fare clic con il pulsante destro del mouse sul nome del pool da associare all'archivio di monitoraggio e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="224ea-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="224ea-p103">Nella finestra di dialogo **Modifica proprietà** nella scheda **Generale** selezionare l'opzione **Monitoraggio (registrazione dettagli chiamata e registrazione metrica QoE** e quindi selezionare un database di SQL Server esistente nell'elenco a discesa **Archivio SQL Server monitoraggio**. In alternativa, fare clic su **Nuovo** per associare il pool a un nuovo archivio database. Se si sceglie di utilizzare il nuovo archivio database, nella finestra di dialogo **Definisci nuovo archivio SQL** immettere il nome di dominio completo del computer SQL Server nella casella **FQDN SQL Server**. Se si desidera utilizzare l'istanza di SQL Server predefinita per l'archivio, selezionare **Istanza predefinita**, altrimenti selezionare **Istanza denominata** e immettere il nome dell'istanza nella casella **Istanza denominata**.</span><span class="sxs-lookup"><span data-stu-id="224ea-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="224ea-p104">La finestra di dialogo **Modifica proprietà** consente inoltre di creare un mirror SQL per il database di monitoraggio. Un mirror SQL consente di mantenere due copie del database di monitoraggio, una archiviata nel computer dell'archivio di monitoraggio e l'altra nel computer mirror SQL. Per abilitare il mirroring, selezionare **L'istanza SQL è in relazione di mirroring** e immettere il numero di porta del server mirror nella casella **Numero porta di mirroring**.</span><span class="sxs-lookup"><span data-stu-id="224ea-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="224ea-120">Nella finestra di dialogo **Modifica proprietà** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="224ea-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="224ea-p105">Dopo aver associato l'archivio di monitoraggio a un pool Front End, è necessario pubblicare la nuova topologia per rendere effettive le modifiche. A tale scopo, eseguire le operazioni seguenti in Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="224ea-p105">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect. To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="224ea-123">Fare clic su **Azione**, scegliere **Topologia** e quindi **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="224ea-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="224ea-124">Nella pagina **Pubblicare la topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="224ea-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="224ea-125">Nella pagina **Pubblicazione guidata completata** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="224ea-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="224ea-126">Dopo la pubblicazione della topologia, è possibile installare il database di monitoraggio nel computer che ospiterà l'archivio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="224ea-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="224ea-127">È possibile installare il database di monitoraggio utilizzando Lync Server Management Shell e Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="224ea-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="224ea-128">Per installare il database localmente, ovvero per installare il database nello stesso computer in cui è in esecuzione Lync Server Management Shell, avviare la shell di gestione nel computer appropriato e quindi digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="224ea-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="224ea-129">Quando si esegue il comando precedente, Install-CsDatabase legge la topologia di Lync Server corrente, determina quali database devono essere installati nel computer locale e quindi installa e configura automaticamente ognuno di questi database.</span><span class="sxs-lookup"><span data-stu-id="224ea-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="224ea-130">Per installare il database in un computer remoto, ovvero un computer diverso da quello in cui è in esecuzione Management Shell, è necessario includere almeno due parametri: ConfiguredDatabases e SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="224ea-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="224ea-131">Questi parametri indicano al cmdlet Install-CsDatabase di recuperare la topologia di Lync Server e quindi installano e configurano i database necessari nel computer specificato dal parametro SqlServerFqdn.</span><span class="sxs-lookup"><span data-stu-id="224ea-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="224ea-132">Il parametro SqlServerFqdn deve utilizzare un valore di parametro che rappresenta il nome di dominio completo del computer in cui devono essere installati i database.</span><span class="sxs-lookup"><span data-stu-id="224ea-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="224ea-133">Con il comando seguente ad esempio il database di monitoraggio viene installato nel computer atl-sql-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="224ea-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="224ea-134">In alternativa, è possibile installare il database di monitoraggio eseguendo la distribuzione guidata di Lync Server nel computer che ospiterà l'archivio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="224ea-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="224ea-135">A tale scopo, accedere al computer appropriato ed eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="224ea-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="224ea-136">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **distribuzione guidata di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="224ea-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="224ea-137">Nella Distribuzione guidata fare clic su **Installa o aggiorna il sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="224ea-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="224ea-138">In **Passaggio 2: Installazione o rimozione componenti di Lync Server** nella pagina **Distribuisci** fare clic su **Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="224ea-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="224ea-139">Nella pagina **Installazione componenti di Lync Server** della procedura guidata Installazione componenti di Lync Server fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="224ea-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="224ea-140">Nella pagina **Specifica percorso di MSI** Digitare il percorso del file OCSCore. msi (un file incluso nel supporto di installazione di Lync Server) e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="224ea-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="224ea-141">Nella pagina **Esecuzione comandi in corso** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="224ea-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="224ea-142">Per assicurarsi che tutti i servizi di Lync Server necessari siano stati avviati, fare clic su **Esegui** nell'intestazione **passaggio 4: avviare i servizi** nella pagina **Distribuisci** .</span><span class="sxs-lookup"><span data-stu-id="224ea-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

