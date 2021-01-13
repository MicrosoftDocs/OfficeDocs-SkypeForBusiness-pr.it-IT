---
title: Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Riepilogo: informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815046"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="9784d-103">Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9784d-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9784d-104">**Riepilogo:** Informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9784d-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9784d-105">In questo argomento viene descritto come eseguire il failover e il failback del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9784d-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="9784d-106">Prima di leggere questo argomento, leggere [piano per la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="9784d-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9784d-107">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9784d-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9784d-108">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="9784d-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="9784d-109">Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="9784d-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="9784d-110">Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9784d-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="9784d-111">Failover del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="9784d-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="9784d-112">Il failover per il server Chat persistente è stato creato principalmente come processo manuale.</span><span class="sxs-lookup"><span data-stu-id="9784d-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="9784d-113">La procedura di failover si basa sul presupposto che il data center secondario sia attivo e in esecuzione, ma i servizi del server Chat persistente in cui si trova il database di Persistent Chat primario sono completamente non disponibili, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9784d-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="9784d-114">Database primario del server Chat persistente e database mirror del server Chat persistente sono indesiderati.</span><span class="sxs-lookup"><span data-stu-id="9784d-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="9784d-115">Skype for Business Server front end server è inverso.</span><span class="sxs-lookup"><span data-stu-id="9784d-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="9784d-116">La procedura prevede due passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="9784d-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="9784d-117">Ripristinare il database di Persistent Chat principale (MGC).</span><span class="sxs-lookup"><span data-stu-id="9784d-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="9784d-118">Configurazione del mirroring per il nuovo database primario.</span><span class="sxs-lookup"><span data-stu-id="9784d-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="9784d-119">Non è stato eseguito il failover del database di conformità di Persistent Chat (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="9784d-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="9784d-120">Il contenuto di questo database è temporaneo e viene eliminato durante l'elaborazione dei dati nell'adattatore di conformità.</span><span class="sxs-lookup"><span data-stu-id="9784d-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="9784d-121">La responsabilità, come amministratore di chat persistente, è quella di gestire correttamente l'output dell'adattatore per evitare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="9784d-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="9784d-122">Per eseguire il failover del server Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="9784d-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="9784d-123">Rimuovere il log shipping dal database del log shipping del server di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="9784d-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="9784d-124">Tramite SQL Server Management Studio connettersi all'istanza del database in cui si trova il database di backup di MGC del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9784d-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="9784d-125">Aprire una finestra di query nel database master.</span><span class="sxs-lookup"><span data-stu-id="9784d-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="9784d-126">Usare questo comando per eliminare la distribuzione dei log:</span><span class="sxs-lookup"><span data-stu-id="9784d-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="9784d-127">Copiare i file di backup non copiati dalla condivisione di backup nella cartella di destinazione della copia del server di backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="9784d-128">Applicare i backup dei log delle transazioni non applicati in sequenza al database secondario.</span><span class="sxs-lookup"><span data-stu-id="9784d-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="9784d-129">Per informazioni dettagliate, vedere [How to: Apply a Transaction log backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="9784d-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="9784d-p105">Connettere il database mgc di backup. Usando la finestra di query aperta al passaggio 1b, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9784d-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="9784d-132">Terminare tutte le connessioni al database mgc, se disponibili:</span><span class="sxs-lookup"><span data-stu-id="9784d-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="9784d-133">**sp_who2 EXEC** per identificare le connessioni al database di MGC.</span><span class="sxs-lookup"><span data-stu-id="9784d-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="9784d-134">**Kill \<spid\>** per terminare queste connessioni.</span><span class="sxs-lookup"><span data-stu-id="9784d-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="9784d-135">Connettere il database:</span><span class="sxs-lookup"><span data-stu-id="9784d-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="9784d-136">**ripristinare i database di MGC con il ripristino**.</span><span class="sxs-lookup"><span data-stu-id="9784d-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="9784d-137">In Skype for Business Server Management Shell, utilizzare il comando **Set-CsPersistentChatState-Identity "Service: atl-cs-001.litwareinc.com"-PoolState FailedOver** per eseguire il failover nel database di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="9784d-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="9784d-138">Assicurarsi di sostituire il nome di dominio completo del pool di Persistent Chat per atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9784d-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="9784d-139">Il database mgc di backup funge ora da database primario.</span><span class="sxs-lookup"><span data-stu-id="9784d-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="9784d-140">In Skype for Business Server Management Shell, utilizzare il cmdlet **Install-CsMirrorDatabase** per definire un mirror a disponibilità elevata per il database di backup che ora funge da database primario.</span><span class="sxs-lookup"><span data-stu-id="9784d-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="9784d-141">Usare l'istanza del database di backup come database primario e l'istanza del database mirror di backup come istanza mirror.</span><span class="sxs-lookup"><span data-stu-id="9784d-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="9784d-142">Questo mirror non corrisponde al mirror configurato inizialmente per il database primario durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="9784d-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="9784d-143">Impostare i server attivi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9784d-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="9784d-144">Da Skype for Business Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.</span><span class="sxs-lookup"><span data-stu-id="9784d-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9784d-145">Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.</span><span class="sxs-lookup"><span data-stu-id="9784d-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="9784d-146">A questo punto, il failover dal database primario del server Chat persistente al database di backup del server Chat persistente è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9784d-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="9784d-147">Esito negativo del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="9784d-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="9784d-148">In questa procedura vengono illustrati i passaggi necessari per eseguire il ripristino da un errore del server Chat persistente e per ristabilire le operazioni dal data center principale.</span><span class="sxs-lookup"><span data-stu-id="9784d-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="9784d-149">Durante l'errore del server Chat persistente, il data center principale soffre di un'interruzione completa e i database primario e mirror diventano non disponibili.</span><span class="sxs-lookup"><span data-stu-id="9784d-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="9784d-150">Il centro dati principale esegue il failover al server di backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="9784d-151">La procedura seguente consente di ripristinare l'operatività normale dopo il backup del centro dati principale e la ricostruzione dei server.</span><span class="sxs-lookup"><span data-stu-id="9784d-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="9784d-152">La procedura presuppone che il data center principale sia stato recuperato dall'interruzione totale e che il database di MGC e il database di mgccomp siano stati ricompilati e reinstallati tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9784d-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="9784d-153">La procedura presuppone inoltre che nessun nuovo mirror e server di backup siano stati distribuiti durante il periodo di failover e che il solo server distribuito sia il server di backup e il relativo server mirror, come definito in precedenza in fail over Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="9784d-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="9784d-154">Questi passaggi sono pensati per consentite il ripristino della configurazione esistente prima della situazione di emergenza che ha causato il failover dal server primario a quello di backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="9784d-155">Cancellare tutti i server dall'elenco Active server Chat persistente utilizzando il cmdlet **Set-CsPersistentChatActiveServer** da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9784d-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9784d-156">In questo modo tutti i server di chat persistente si connettono al database di MGC e al database di mgccomp durante il failback.</span><span class="sxs-lookup"><span data-stu-id="9784d-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9784d-157">Il server SQL Server Agent sul server back-end di chat persistente secondario dovrebbe essere in esecuzione con un account con privilegi.</span><span class="sxs-lookup"><span data-stu-id="9784d-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="9784d-158">In particolare, l'account deve disporre di:</span><span class="sxs-lookup"><span data-stu-id="9784d-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="9784d-159">Accesso in lettura alla condivisione di rete in cui vengono posizionati i backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="9784d-160">Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="9784d-161">Disabilitare il mirroring nel database mgc di backup:</span><span class="sxs-lookup"><span data-stu-id="9784d-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="9784d-162">Tramite SQL Server Management Studio connettersi all'istanza di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="9784d-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="9784d-163">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="9784d-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="9784d-164">Fare clic su **Rimuovi mirroring**.</span><span class="sxs-lookup"><span data-stu-id="9784d-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="9784d-165">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9784d-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="9784d-166">Eseguire gli stessi passaggi con il database mgccomp.</span><span class="sxs-lookup"><span data-stu-id="9784d-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="9784d-167">Eseguire il backup del database mgc in modo che possa essere ripristinato nel nuovo database primario:</span><span class="sxs-lookup"><span data-stu-id="9784d-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="9784d-168">Tramite SQL Server Management Studio connettersi all'istanza di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="9784d-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="9784d-p113">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Backup**. Verrà visualizzata la finestra di dialogo **Backup database**.</span><span class="sxs-lookup"><span data-stu-id="9784d-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="9784d-171">In **Tipo backup** selezionare **Completo**.</span><span class="sxs-lookup"><span data-stu-id="9784d-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="9784d-172">In **Componente di cui eseguire il backup** fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="9784d-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="9784d-173">Accettare il nome del set di backup predefinito indicato in **Nome** oppure immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="9784d-174">*\<Optional\>*  In **Descrizione** immettere una descrizione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="9784d-175">Rimuovere il percorso di backup predefinito dall'elenco di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9784d-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="9784d-p114">Aggiungere un file all'elenco utilizzando il percorso della posizione condivisa stabilita per il log shipping. Questo percorso è disponibile per il database primario e quello di backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="9784d-178">Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="9784d-179">Ripristinare il database primario utilizzando il database di backup creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="9784d-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="9784d-180">Tramite SQL Server Management Studio connettersi all'istanza di MGC principale.</span><span class="sxs-lookup"><span data-stu-id="9784d-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="9784d-p115">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività**, **Ripristina** e quindi fare clic su **Database**. Verrà visualizzata la finestra di dialogo **Ripristina database**.</span><span class="sxs-lookup"><span data-stu-id="9784d-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="9784d-183">Selezionare **Dispositivo di origine**.</span><span class="sxs-lookup"><span data-stu-id="9784d-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="9784d-p116">Fare clic sul pulsante Sfoglia per aprire la finestra di dialogo **Seleziona backup**. In **Supporti di backup** selezionare **File**. Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9784d-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="9784d-187">In **Selezionare i set di backup da ripristinare** selezionare il backup.</span><span class="sxs-lookup"><span data-stu-id="9784d-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="9784d-188">Fare clic su **Opzioni** nel riquadro **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="9784d-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="9784d-189">In **Opzioni di ripristino** selezionare **Sovrascrivi il database esistente**.</span><span class="sxs-lookup"><span data-stu-id="9784d-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="9784d-190">In **Stato di recupero** selezionare **Lascia il database pronto per l'utilizzo**.</span><span class="sxs-lookup"><span data-stu-id="9784d-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="9784d-191">Fare clic su **OK** per avviare il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="9784d-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="9784d-192">Configurare il log shipping di SQL Server per il database primario.</span><span class="sxs-lookup"><span data-stu-id="9784d-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="9784d-193">Seguire le procedure illustrate in [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) per stabilire il log shipping per il database di MGC primario.</span><span class="sxs-lookup"><span data-stu-id="9784d-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="9784d-194">Impostare i server attivi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9784d-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="9784d-195">Da Skype for Business Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.</span><span class="sxs-lookup"><span data-stu-id="9784d-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9784d-196">Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.</span><span class="sxs-lookup"><span data-stu-id="9784d-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="9784d-197">Per ripristinare il pool allo stato normale, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="9784d-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="9784d-198">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9784d-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

