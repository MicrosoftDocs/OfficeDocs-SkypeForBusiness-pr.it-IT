---
title: 'Lync Server 2013: failover del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2132af73fec67ace0bffd6db1836071cb8fc2d06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531003"
---
# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="821b3-102">Failover del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="821b3-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="821b3-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="821b3-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="821b3-104">In questa procedura vengono illustrati i passaggi necessari per eseguire il ripristino da un errore del server Chat persistente e per ristabilire le operazioni dal data center principale.</span><span class="sxs-lookup"><span data-stu-id="821b3-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="821b3-105">Durante l'errore del server Chat persistente, il data center principale soffre di un'interruzione completa e i database primario e mirror diventano non disponibili.</span><span class="sxs-lookup"><span data-stu-id="821b3-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="821b3-106">Il centro dati principale esegue il failover al server di backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="821b3-107">La procedura seguente consente di ripristinare l'operatività normale dopo il backup del centro dati principale e la ricostruzione dei server.</span><span class="sxs-lookup"><span data-stu-id="821b3-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="821b3-108">La procedura presuppone che il data center principale sia stato recuperato dall'interruzione totale e che il database di MGC e il database di mgccomp siano stati ricompilati e reinstallati tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="821b3-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="821b3-109">La procedura presuppone inoltre che nessun nuovo mirror e server di backup siano stati distribuiti durante il periodo di failover e che il solo server distribuito sia il server di backup e il server mirror, come definito in [failover del server Chat persistente in Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="821b3-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="821b3-110">Questi passaggi sono pensati per consentite il ripristino della configurazione esistente prima della situazione di emergenza che ha causato il failover dal server primario a quello di backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="821b3-111">Per eseguire il failover del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="821b3-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="821b3-112">Cancellare tutti i server dall'elenco Active server Chat persistente utilizzando il `Set-CsPersistentChatActiveServer` cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="821b3-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="821b3-113">In questo modo tutti i server di chat persistente si connettono al database di MGC e al database di mgccomp durante il failback.</span><span class="sxs-lookup"><span data-stu-id="821b3-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="821b3-114">Il server SQL Server Agent sul server back-end di chat persistente secondario dovrebbe essere in esecuzione con un account con privilegi.</span><span class="sxs-lookup"><span data-stu-id="821b3-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="821b3-115">In particolare, l'account deve disporre di:</span><span class="sxs-lookup"><span data-stu-id="821b3-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="821b3-116">Accesso in lettura alla condivisione di rete in cui vengono posizionati i backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="821b3-117">Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="821b3-118">Disabilitare il mirroring nel database mgc di backup:</span><span class="sxs-lookup"><span data-stu-id="821b3-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="821b3-119">Tramite SQL Server Management Studio connettersi all'istanza di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="821b3-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="821b3-120">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="821b3-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="821b3-121">Fare clic su **Rimuovi mirroring**.</span><span class="sxs-lookup"><span data-stu-id="821b3-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="821b3-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="821b3-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="821b3-123">Eseguire gli stessi passaggi con il database mgccomp.</span><span class="sxs-lookup"><span data-stu-id="821b3-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="821b3-124">Eseguire il backup del database mgc in modo che possa essere ripristinato nel nuovo database primario:</span><span class="sxs-lookup"><span data-stu-id="821b3-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="821b3-125">Tramite SQL Server Management Studio connettersi all'istanza di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="821b3-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="821b3-p105">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Backup**. Verrà visualizzata la finestra di dialogo **Backup database**.</span><span class="sxs-lookup"><span data-stu-id="821b3-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="821b3-128">In **Tipo backup** selezionare **Completo**.</span><span class="sxs-lookup"><span data-stu-id="821b3-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="821b3-129">In **Componente di cui eseguire il backup** fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="821b3-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="821b3-130">Accettare il nome del set di backup predefinito indicato in **Nome** oppure immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="821b3-131">*\<Optional\>* In **Descrizione**immettere una descrizione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="821b3-132">Rimuovere il percorso di backup predefinito dall'elenco di destinazione.</span><span class="sxs-lookup"><span data-stu-id="821b3-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="821b3-p106">Aggiungere un file all'elenco utilizzando il percorso della posizione condivisa stabilita per il log shipping. Questo percorso è disponibile per il database primario e quello di backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="821b3-135">Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="821b3-136">Ripristinare il database primario utilizzando il database di backup creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="821b3-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="821b3-137">Tramite SQL Server Management Studio connettersi all'istanza di MGC principale.</span><span class="sxs-lookup"><span data-stu-id="821b3-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="821b3-p107">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività**, **Ripristina** e quindi fare clic su **Database**. Verrà visualizzata la finestra di dialogo **Ripristina database**.</span><span class="sxs-lookup"><span data-stu-id="821b3-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="821b3-140">Selezionare **Dispositivo di origine**.</span><span class="sxs-lookup"><span data-stu-id="821b3-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="821b3-p108">Fare clic sul pulsante Sfoglia per aprire la finestra di dialogo **Seleziona backup**. In **Supporti di backup** selezionare **File**. Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="821b3-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="821b3-144">In **Selezionare i set di backup da ripristinare** selezionare il backup.</span><span class="sxs-lookup"><span data-stu-id="821b3-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="821b3-145">Fare clic su **Opzioni** nel riquadro **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="821b3-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="821b3-146">In **Opzioni di ripristino** selezionare \*\*Sovrascrivi il database esistente \*\*.</span><span class="sxs-lookup"><span data-stu-id="821b3-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="821b3-147">In **Stato di recupero** selezionare **Lascia il database pronto per l'utilizzo**.</span><span class="sxs-lookup"><span data-stu-id="821b3-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="821b3-148">Fare clic su **OK** per avviare il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="821b3-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="821b3-149">Configurare il log shipping di SQL Server per il database primario.</span><span class="sxs-lookup"><span data-stu-id="821b3-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="821b3-150">Seguire le procedure riportate in [configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) per stabilire il log shipping per il database di MGC primario.</span><span class="sxs-lookup"><span data-stu-id="821b3-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="821b3-151">Impostare i server attivi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="821b3-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="821b3-152">Da Lync Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.</span><span class="sxs-lookup"><span data-stu-id="821b3-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="821b3-153">Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.</span><span class="sxs-lookup"><span data-stu-id="821b3-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="821b3-154">Il ripristino del pool allo stato normale viene eseguito il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="821b3-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="821b3-155">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) .</span><span class="sxs-lookup"><span data-stu-id="821b3-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

