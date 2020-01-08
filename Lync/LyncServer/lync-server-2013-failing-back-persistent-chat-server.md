---
title: 'Lync Server 2013: Failback del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="cd36a-102">Failback del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd36a-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd36a-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="cd36a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="cd36a-104">Questa procedura descrive i passaggi necessari per il ripristino da un errore del server di chat persistente e per ristabilire le operazioni dal centro dati principale.</span><span class="sxs-lookup"><span data-stu-id="cd36a-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="cd36a-105">Durante l'errore del server di chat persistente, il centro dati principale soffre l'interruzione completa e i database primari e mirror diventano non disponibili.</span><span class="sxs-lookup"><span data-stu-id="cd36a-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="cd36a-106">Il data center principale viene superato nel server di backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="cd36a-107">La procedura seguente ripristina il normale funzionamento dopo il backup del data center principale e i server sono stati ricompilati.</span><span class="sxs-lookup"><span data-stu-id="cd36a-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="cd36a-108">La procedura presuppone che il centro dati principale sia stato recuperato dall'interruzione totale e che il database di MGC e il database di mgccomp siano stati ricostruiti e reinstallati usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="cd36a-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="cd36a-109">La procedura presuppone inoltre che non siano stati distribuiti nuovi mirror e server di backup durante il periodo di failover e che l'unico server distribuito sia il server di backup e il relativo server mirror, come definito in mancanza di un [server di chat persistente in Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="cd36a-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="cd36a-110">Questi passaggi sono progettati per recuperare la configurazione come esisteva prima del disastro, causando il failover dal server primario al server di backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="cd36a-111">Per non ripristinare il server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="cd36a-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="cd36a-112">Cancellare tutti i server dall'elenco Active server Chat persistente usando il `Set-CsPersistentChatActiveServer` cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cd36a-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="cd36a-113">In questo articolo vengono arrestati tutti i server di chat persistenti che si connettono al database mgc e mgccomp durante il failback.</span><span class="sxs-lookup"><span data-stu-id="cd36a-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd36a-114">L'agente SQL Server nel server di chat secondario persistente deve essere in uso in un account con privilegi.</span><span class="sxs-lookup"><span data-stu-id="cd36a-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="cd36a-115">In particolare, l'account deve includere:</span><span class="sxs-lookup"><span data-stu-id="cd36a-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="cd36a-116">Accesso in lettura alla condivisione di rete in cui vengono inseriti i backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cd36a-117">Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="cd36a-118">Disabilitare il mirroring nel database di backup MGC:</span><span class="sxs-lookup"><span data-stu-id="cd36a-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="cd36a-119">Con SQL Server Management Studio connettersi all'istanza di backup MGC.</span><span class="sxs-lookup"><span data-stu-id="cd36a-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="cd36a-120">Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **Specchia**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="cd36a-121">Fare clic su **Rimuovi mirroring**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="cd36a-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="cd36a-123">Eseguire gli stessi passaggi con il database mgccomp.</span><span class="sxs-lookup"><span data-stu-id="cd36a-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="cd36a-124">Eseguire il backup del database di MGC in modo che possa essere ripristinato nel nuovo database primario:</span><span class="sxs-lookup"><span data-stu-id="cd36a-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="cd36a-125">Con SQL Server Management Studio connettersi all'istanza di backup MGC.</span><span class="sxs-lookup"><span data-stu-id="cd36a-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="cd36a-126">Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **backup**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-126">Right-click the mgc database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="cd36a-127">Verrà visualizzata la finestra di dialogo **backup database** .</span><span class="sxs-lookup"><span data-stu-id="cd36a-127">The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="cd36a-128">In **tipo di backup**selezionare **completo**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="cd36a-129">Per il **componente backup**fare clic su **database**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="cd36a-130">Accettare il nome predefinito del set di backup consigliato in **nome**o immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="cd36a-131">\* \<Facoltativo\> \* In **Descrizione**immettere una descrizione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="cd36a-132">Rimuovere la posizione di backup predefinita dall'elenco di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd36a-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="cd36a-133">Aggiungere un file all'elenco usando il percorso della posizione di condivisione stabilita per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="cd36a-133">Add a file to the list by using the path to the share location that you established for log shipping.</span></span> <span data-ttu-id="cd36a-134">Questo percorso è disponibile per il database principale e per il database di backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-134">This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="cd36a-135">Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="cd36a-136">Ripristinare il database principale usando il database di backup creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="cd36a-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="cd36a-137">Con SQL Server Management Studio, connettersi all'istanza di MGC primaria.</span><span class="sxs-lookup"><span data-stu-id="cd36a-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="cd36a-138">Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**, scegliere **Ripristina**e quindi fare clic su **database**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-138">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span> <span data-ttu-id="cd36a-139">Verrà visualizzata la finestra di dialogo **Ripristina database** .</span><span class="sxs-lookup"><span data-stu-id="cd36a-139">The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="cd36a-140">Selezionare **da dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="cd36a-141">Fare clic sul pulsante Sfoglia, che apre la finestra di dialogo **specifica backup** .</span><span class="sxs-lookup"><span data-stu-id="cd36a-141">Click the browse button, which opens the **Specify Backup** dialog box.</span></span> <span data-ttu-id="cd36a-142">In **supporto di backup**selezionare **file**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-142">In **Backup media**, select **File**.</span></span> <span data-ttu-id="cd36a-143">Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-143">Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="cd36a-144">In **selezionare i set di backup da ripristinare**selezionare il backup.</span><span class="sxs-lookup"><span data-stu-id="cd36a-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="cd36a-145">Fare clic su **Opzioni** nel riquadro **Seleziona pagina** .</span><span class="sxs-lookup"><span data-stu-id="cd36a-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="cd36a-146">In **Opzioni di ripristino**selezionare **sovrascrivere il database esistente**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="cd36a-147">In **stato di ripristino**selezionare **lascia il database pronto per l'uso**.</span><span class="sxs-lookup"><span data-stu-id="cd36a-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="cd36a-148">Fare clic su **OK** per avviare il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="cd36a-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="cd36a-149">Configurare la distribuzione del log di SQL Server per il database principale.</span><span class="sxs-lookup"><span data-stu-id="cd36a-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="cd36a-150">Seguire le procedure descritte in [configurazione del server di chat persistente per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) per stabilire la distribuzione del log per il database mgc principale.</span><span class="sxs-lookup"><span data-stu-id="cd36a-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="cd36a-151">Impostare i server attivi della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cd36a-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="cd36a-152">Da Lync Server Management Shell utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco di server attivi.</span><span class="sxs-lookup"><span data-stu-id="cd36a-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd36a-153">Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database.</span><span class="sxs-lookup"><span data-stu-id="cd36a-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="cd36a-154">Il comando Ripristina lo stato normale del pool viene eseguito in Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="cd36a-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="cd36a-155">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) .</span><span class="sxs-lookup"><span data-stu-id="cd36a-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

