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
ms.openlocfilehash: 4fb3a38fadf2a8a063715e389718859dcc7ddbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122410"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="93cde-103">Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="93cde-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="93cde-104">**Riepilogo:** Informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="93cde-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="93cde-105">In questo argomento viene descritto come eseguire il failover e il fail back del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="93cde-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="93cde-106">Prima di leggere questo argomento, leggere Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat [persistente in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="93cde-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="93cde-107">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="93cde-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="93cde-108">La stessa funzionalità è disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="93cde-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="93cde-109">Per ulteriori informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="93cde-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="93cde-110">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="93cde-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="93cde-111">Failover del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="93cde-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="93cde-112">Il failover per il server Chat persistente è progettato principalmente come processo manuale.</span><span class="sxs-lookup"><span data-stu-id="93cde-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="93cde-113">La procedura di failover si basa sul presupposto che il data center secondario sia in esecuzione, ma i servizi del server Chat persistente in cui si trova il database di Chat persistente principale non sono completamente disponibili, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="93cde-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="93cde-114">Il database primario del server Chat persistente e il database mirror del server Chat persistente non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="93cde-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="93cde-115">Skype for Business Server Front End Server non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="93cde-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="93cde-116">La procedura prevede due passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="93cde-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="93cde-117">Ripristinare il database principale di Persistent Chat (mgc).</span><span class="sxs-lookup"><span data-stu-id="93cde-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="93cde-118">Configurazione del mirroring per il nuovo database primario.</span><span class="sxs-lookup"><span data-stu-id="93cde-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="93cde-119">Il database di conformità di Persistent Chat (mgccomp) non viene superato.</span><span class="sxs-lookup"><span data-stu-id="93cde-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="93cde-120">Il contenuto di questo database è temporaneo e viene eliminato durante l'elaborazione dei dati nell'adattatore di conformità.</span><span class="sxs-lookup"><span data-stu-id="93cde-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="93cde-121">È responsabilità dell'amministratore di Persistent Chat gestire correttamente l'output della scheda per evitare la perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="93cde-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="93cde-122">Per eseguire il failover del server Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="93cde-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="93cde-123">Rimuovere il log shipping dal database di log shipping di backup del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="93cde-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="93cde-124">Utilizzando SQL Server Management Studio, connettersi all'istanza del database in cui si trova il database mgc di backup del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="93cde-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="93cde-125">Aprire una finestra di query nel database master.</span><span class="sxs-lookup"><span data-stu-id="93cde-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="93cde-126">Usare questo comando per eliminare la distribuzione dei log:</span><span class="sxs-lookup"><span data-stu-id="93cde-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="93cde-127">Copiare i file di backup non copiati dalla condivisione di backup nella cartella di destinazione della copia del server di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="93cde-128">Applicare i backup dei log delle transazioni non applicati in sequenza al database secondario.</span><span class="sxs-lookup"><span data-stu-id="93cde-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="93cde-129">Per informazioni dettagliate, vedere Procedura: Applicazione di un backup del log delle transazioni [(Transact-SQL)](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105)).</span><span class="sxs-lookup"><span data-stu-id="93cde-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105)).</span></span>
    
4. <span data-ttu-id="93cde-p105">Connettere il database mgc di backup. Usando la finestra di query aperta al passaggio 1b, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93cde-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="93cde-132">Terminare tutte le connessioni al database mgc, se disponibili:</span><span class="sxs-lookup"><span data-stu-id="93cde-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="93cde-133">**exec sp_who2** identificare le connessioni al database mgc.</span><span class="sxs-lookup"><span data-stu-id="93cde-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="93cde-134">**kill \<spid\>** per terminare queste connessioni.</span><span class="sxs-lookup"><span data-stu-id="93cde-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="93cde-135">Connettere il database:</span><span class="sxs-lookup"><span data-stu-id="93cde-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="93cde-136">**ripristinare il database mgc con ripristino**.</span><span class="sxs-lookup"><span data-stu-id="93cde-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="93cde-137">In Skype for Business Server Management Shell, utilizzare il comando **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** per eseguire il failover al database di backup mgc.</span><span class="sxs-lookup"><span data-stu-id="93cde-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="93cde-138">Assicurarsi di sostituire il nome di dominio completo del pool di Persistent Chat con atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="93cde-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="93cde-139">Il database mgc di backup funge ora da database primario.</span><span class="sxs-lookup"><span data-stu-id="93cde-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="93cde-140">In Skype for Business Server Management Shell, utilizzare il cmdlet **Install-CsMirrorDatabase** per stabilire un mirror a disponibilità elevata per il database di backup che ora funge da database primario.</span><span class="sxs-lookup"><span data-stu-id="93cde-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="93cde-141">Usare l'istanza del database di backup come database primario e l'istanza del database mirror di backup come istanza mirror.</span><span class="sxs-lookup"><span data-stu-id="93cde-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="93cde-142">Questo mirror non corrisponde al mirror configurato inizialmente per il database primario durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="93cde-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="93cde-143">Impostare i server attivi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="93cde-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="93cde-144">Da Skype for Business Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.</span><span class="sxs-lookup"><span data-stu-id="93cde-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="93cde-145">Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.</span><span class="sxs-lookup"><span data-stu-id="93cde-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="93cde-146">A questo punto, il failover dal database primario del server Chat persistente al database di backup del server Chat persistente viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="93cde-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="93cde-147">Fail back del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="93cde-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="93cde-148">In questa procedura vengono descritti i passaggi necessari per il ripristino da un errore del server Chat persistente e per ristabilire le operazioni dal data center principale.</span><span class="sxs-lookup"><span data-stu-id="93cde-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="93cde-149">Durante un errore del server Chat persistente, il data center principale subisce un'interruzione completa e i database primario e mirror non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="93cde-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="93cde-150">Il centro dati principale esegue il failover al server di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="93cde-151">La procedura seguente consente di ripristinare l'operatività normale dopo il backup del centro dati principale e la ricostruzione dei server.</span><span class="sxs-lookup"><span data-stu-id="93cde-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="93cde-152">La procedura presuppone che il data center principale sia stato ripristinato dall'interruzione totale e che il database mgc e il database mgccomp siano stati ricostruiti e reinstallati utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="93cde-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="93cde-153">La procedura presuppone inoltre che non siano stati distribuiti nuovi server mirror e di backup durante il periodo di failover e che l'unico server distribuito sia il server di backup e il relativo server mirror, come definito in precedenza in Failover del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="93cde-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="93cde-154">Questi passaggi sono pensati per consentite il ripristino della configurazione esistente prima della situazione di emergenza che ha causato il failover dal server primario a quello di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="93cde-155">Cancellare tutti i server dall'elenco Server Chat persistente Active Server utilizzando il cmdlet **Set-CsPersistentChatActiveServer** da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="93cde-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="93cde-156">In questo modo tutti i server Chat persistente non si connettono al database mgc e al database mgccomp durante il failback.</span><span class="sxs-lookup"><span data-stu-id="93cde-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="93cde-157">L'SQL Server sul server back-end secondario del server Chat persistente deve essere in esecuzione con un account con privilegi.</span><span class="sxs-lookup"><span data-stu-id="93cde-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="93cde-158">In particolare, l'account deve disporre di:</span><span class="sxs-lookup"><span data-stu-id="93cde-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="93cde-159">Accesso in lettura alla condivisione di rete in cui vengono posizionati i backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="93cde-160">Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="93cde-161">Disabilitare il mirroring nel database mgc di backup:</span><span class="sxs-lookup"><span data-stu-id="93cde-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="93cde-162">Usando SQL Server Management Studio, connettersi all'istanza mgc di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="93cde-163">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="93cde-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="93cde-164">Fare clic su **Rimuovi mirroring**.</span><span class="sxs-lookup"><span data-stu-id="93cde-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="93cde-165">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="93cde-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="93cde-166">Eseguire gli stessi passaggi con il database mgccomp.</span><span class="sxs-lookup"><span data-stu-id="93cde-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="93cde-167">Eseguire il backup del database mgc in modo che possa essere ripristinato nel nuovo database primario:</span><span class="sxs-lookup"><span data-stu-id="93cde-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="93cde-168">Usando SQL Server Management Studio, connettersi all'istanza mgc di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="93cde-p113">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Backup**. Verrà visualizzata la finestra di dialogo **Backup database**.</span><span class="sxs-lookup"><span data-stu-id="93cde-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="93cde-171">In **Tipo backup** selezionare **Completo**.</span><span class="sxs-lookup"><span data-stu-id="93cde-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="93cde-172">In **Componente di cui eseguire il backup** fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="93cde-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="93cde-173">Accettare il nome del set di backup predefinito indicato in **Nome** oppure immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="93cde-174">*\<Optional\>*  In **Descrizione** immettere una descrizione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="93cde-175">Rimuovere il percorso di backup predefinito dall'elenco di destinazione.</span><span class="sxs-lookup"><span data-stu-id="93cde-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="93cde-p114">Aggiungere un file all'elenco utilizzando il percorso della posizione condivisa stabilita per il log shipping. Questo percorso è disponibile per il database primario e quello di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="93cde-178">Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="93cde-179">Ripristinare il database primario utilizzando il database di backup creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="93cde-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="93cde-180">Usando SQL Server Management Studio, connettersi all'istanza mgc principale.</span><span class="sxs-lookup"><span data-stu-id="93cde-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="93cde-p115">Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività**, **Ripristina** e quindi fare clic su **Database**. Verrà visualizzata la finestra di dialogo **Ripristina database**.</span><span class="sxs-lookup"><span data-stu-id="93cde-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="93cde-183">Selezionare **Dispositivo di origine**.</span><span class="sxs-lookup"><span data-stu-id="93cde-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="93cde-p116">Fare clic sul pulsante Sfoglia per aprire la finestra di dialogo **Seleziona backup**. In **Supporti di backup** selezionare **File**. Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="93cde-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="93cde-187">In **Selezionare i set di backup da ripristinare** selezionare il backup.</span><span class="sxs-lookup"><span data-stu-id="93cde-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="93cde-188">Fare clic su **Opzioni** nel riquadro **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="93cde-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="93cde-189">In **Opzioni di ripristino** selezionare **Sovrascrivi il database esistente**.</span><span class="sxs-lookup"><span data-stu-id="93cde-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="93cde-190">In **Stato di recupero** selezionare **Lascia il database pronto per l'utilizzo**.</span><span class="sxs-lookup"><span data-stu-id="93cde-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="93cde-191">Fare clic su **OK** per avviare il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="93cde-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="93cde-192">Configurare SQL Server log shipping per il database primario.</span><span class="sxs-lookup"><span data-stu-id="93cde-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="93cde-193">Seguire le procedure descritte in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) per stabilire il log shipping per il database mgc primario.</span><span class="sxs-lookup"><span data-stu-id="93cde-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="93cde-194">Impostare i server attivi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="93cde-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="93cde-195">Da Skype for Business Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.</span><span class="sxs-lookup"><span data-stu-id="93cde-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="93cde-196">Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.</span><span class="sxs-lookup"><span data-stu-id="93cde-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="93cde-197">Per ripristinare lo stato normale del pool, eseguire il comando Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="93cde-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="93cde-198">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState.](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="93cde-198">For more information, see the help topic for the [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
