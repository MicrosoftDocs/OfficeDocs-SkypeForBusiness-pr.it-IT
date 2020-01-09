---
title: Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Riepilogo: informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: d46e34485f231d313475b4fdc5948a7262b324ed
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991981"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="e56cb-103">Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="e56cb-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e56cb-104">**Riepilogo:** Informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server di chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e56cb-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e56cb-105">Questo argomento descrive come eseguire il failover e il failover del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e56cb-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="e56cb-106">Prima di leggere questo argomento, leggere [piano per la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e [configurare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="e56cb-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e56cb-107">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e56cb-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e56cb-108">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="e56cb-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="e56cb-109">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="e56cb-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e56cb-110">Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e56cb-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="e56cb-111">Failover del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="e56cb-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="e56cb-112">Il failover per il server di chat persistente è progettato per essere principalmente un processo manuale.</span><span class="sxs-lookup"><span data-stu-id="e56cb-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="e56cb-113">La procedura di failover si basa sul presupposto che il data center secondario sia attivo e funzionante, ma i servizi di Persistent Chat Server in cui si trova il database principale della chat persistente sono completamente non disponibili, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e56cb-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="e56cb-114">Il database primario del server Chat persistente e il database mirror del server di chat persistente non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="e56cb-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="e56cb-115">Il server front-end di Skype for Business Server non è più presente.</span><span class="sxs-lookup"><span data-stu-id="e56cb-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="e56cb-116">La procedura si basa su due passaggi di base:</span><span class="sxs-lookup"><span data-stu-id="e56cb-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="e56cb-117">Recuperare il database principale della chat persistente (MGC).</span><span class="sxs-lookup"><span data-stu-id="e56cb-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="e56cb-118">Stabilire il mirroring per il nuovo database primario.</span><span class="sxs-lookup"><span data-stu-id="e56cb-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="e56cb-119">Il database di conformità della chat persistente (mgccomp) non viene superato.</span><span class="sxs-lookup"><span data-stu-id="e56cb-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="e56cb-120">Il contenuto di questo database è temporaneo e viene eliminato quando l'adattatore di conformità elabora i dati.</span><span class="sxs-lookup"><span data-stu-id="e56cb-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="e56cb-121">È tua responsabilità, come amministratore della chat persistente, gestire correttamente l'output della scheda per evitare perdite di dati.</span><span class="sxs-lookup"><span data-stu-id="e56cb-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="e56cb-122">Per eseguire il failover del server di chat persistente:</span><span class="sxs-lookup"><span data-stu-id="e56cb-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="e56cb-123">Rimuovere il log shipping dal database di log shipping del server di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="e56cb-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="e56cb-124">In SQL Server Management Studio connettersi all'istanza del database in cui si trova il database di backup di MGC del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e56cb-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="e56cb-125">Aprire una finestra di query nel database master.</span><span class="sxs-lookup"><span data-stu-id="e56cb-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="e56cb-126">Usare il comando seguente per eliminare il log shipping:</span><span class="sxs-lookup"><span data-stu-id="e56cb-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="e56cb-127">Copiare i file di backup non copiati dalla condivisione di backup alla cartella di destinazione della copia del server di backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="e56cb-128">Applicare i backup del log delle transazioni non applicati in sequenza al database secondario.</span><span class="sxs-lookup"><span data-stu-id="e56cb-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="e56cb-129">Per informazioni dettagliate, vedere [procedura: applicare un backup del log delle transazioni (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="e56cb-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="e56cb-130">Porta il database di backup MGC online.</span><span class="sxs-lookup"><span data-stu-id="e56cb-130">Bring the backup mgc database online.</span></span> <span data-ttu-id="e56cb-131">Usando la finestra della query visualizzata nel passaggio 1b, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e56cb-131">Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="e56cb-132">Terminare tutte le connessioni al database di MGC, se presenti:</span><span class="sxs-lookup"><span data-stu-id="e56cb-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="e56cb-133">**sp_who2 EXEC** per identificare le connessioni al database di MGC.</span><span class="sxs-lookup"><span data-stu-id="e56cb-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="e56cb-134">\*\*uccidere \<SPID\> \*\* per terminare queste connessioni.</span><span class="sxs-lookup"><span data-stu-id="e56cb-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="e56cb-135">Porta il database online:</span><span class="sxs-lookup"><span data-stu-id="e56cb-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="e56cb-136">**ripristinare il database di MGC con il ripristino**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="e56cb-137">In Skype for Business Server Management Shell usare il comando **Set-CsPersistentChatState-Identity "Service: atl-cs-001.litwareinc.com"-PoolState FailedOver** per eseguire il failover nel database di backup di MGC.</span><span class="sxs-lookup"><span data-stu-id="e56cb-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="e56cb-138">Assicurarsi di sostituire il nome di dominio completo del pool di chat persistente per atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e56cb-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="e56cb-139">Il database di backup di MGC ora funge da database primario.</span><span class="sxs-lookup"><span data-stu-id="e56cb-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="e56cb-140">In Skype for Business Server Management Shell usare il cmdlet **Install-CsMirrorDatabase** per stabilire un mirror di disponibilità elevata per il database di backup che ora funge da database primario.</span><span class="sxs-lookup"><span data-stu-id="e56cb-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="e56cb-141">Usa l'istanza del database di backup come database principale e l'istanza del database mirror di backup come istanza di mirror.</span><span class="sxs-lookup"><span data-stu-id="e56cb-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="e56cb-142">Questo non è lo stesso mirror di quello inizialmente configurato per il database principale durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e56cb-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="e56cb-143">Impostare i server attivi della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e56cb-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="e56cb-144">Da Skype for Business Server Management Shell, usa il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.</span><span class="sxs-lookup"><span data-stu-id="e56cb-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e56cb-145">Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database.</span><span class="sxs-lookup"><span data-stu-id="e56cb-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="e56cb-146">A questo punto, il failover dal database primario del server di chat persistente al database di backup del server di chat persistente viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e56cb-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="e56cb-147">Non ripristinare il server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="e56cb-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="e56cb-148">Questa procedura descrive i passaggi necessari per il ripristino da un errore del server di chat persistente e per ristabilire le operazioni dal centro dati principale.</span><span class="sxs-lookup"><span data-stu-id="e56cb-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="e56cb-149">Durante l'errore del server di chat persistente, il centro dati principale soffre l'interruzione completa e i database primari e mirror diventano non disponibili.</span><span class="sxs-lookup"><span data-stu-id="e56cb-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="e56cb-150">Il data center principale viene superato nel server di backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="e56cb-151">La procedura seguente ripristina il normale funzionamento dopo il backup del data center principale e i server sono stati ricompilati.</span><span class="sxs-lookup"><span data-stu-id="e56cb-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="e56cb-152">La procedura presuppone che il centro dati principale sia stato recuperato dall'interruzione totale e che il database di MGC e il database di mgccomp siano stati ricostruiti e reinstallati usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e56cb-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="e56cb-153">La procedura presuppone inoltre che non siano stati distribuiti nuovi mirror e server di backup durante il periodo di failover e che l'unico server distribuito sia il server di backup e il relativo server mirror, come definito in precedenza in fail over Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="e56cb-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="e56cb-154">Questi passaggi sono progettati per recuperare la configurazione come esisteva prima del disastro, causando il failover dal server primario al server di backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="e56cb-155">Cancellare tutti i server dall'elenco Active server Chat persistente usando il cmdlet **Set-CsPersistentChatActiveServer** di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e56cb-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e56cb-156">In questo articolo vengono arrestati tutti i server di chat persistenti che si connettono al database mgc e mgccomp durante il failback.</span><span class="sxs-lookup"><span data-stu-id="e56cb-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e56cb-157">L'agente SQL Server nel server di chat secondario persistente deve essere in uso in un account con privilegi.</span><span class="sxs-lookup"><span data-stu-id="e56cb-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="e56cb-158">In particolare, l'account deve includere:</span><span class="sxs-lookup"><span data-stu-id="e56cb-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="e56cb-159">Accesso in lettura alla condivisione di rete in cui vengono inseriti i backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="e56cb-160">Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="e56cb-161">Disabilitare il mirroring nel database di backup MGC:</span><span class="sxs-lookup"><span data-stu-id="e56cb-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="e56cb-162">Con SQL Server Management Studio connettersi all'istanza di backup MGC.</span><span class="sxs-lookup"><span data-stu-id="e56cb-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="e56cb-163">Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **Specchia**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="e56cb-164">Fare clic su **Rimuovi mirroring**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="e56cb-165">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="e56cb-166">Eseguire gli stessi passaggi con il database mgccomp.</span><span class="sxs-lookup"><span data-stu-id="e56cb-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="e56cb-167">Eseguire il backup del database di MGC in modo che possa essere ripristinato nel nuovo database primario:</span><span class="sxs-lookup"><span data-stu-id="e56cb-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="e56cb-168">Con SQL Server Management Studio connettersi all'istanza di backup MGC.</span><span class="sxs-lookup"><span data-stu-id="e56cb-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="e56cb-169">Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **backup**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-169">Right-click the mgc database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="e56cb-170">Verrà visualizzata la finestra di dialogo **backup database** .</span><span class="sxs-lookup"><span data-stu-id="e56cb-170">The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="e56cb-171">In **tipo di backup**selezionare **completo**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="e56cb-172">Per il **componente backup**fare clic su **database**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="e56cb-173">Accettare il nome predefinito del set di backup consigliato in **nome**o immettere un nome diverso per il set di backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="e56cb-174">\* \<Facoltativo\> \*  In **Descrizione**immettere una descrizione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="e56cb-175">Rimuovere la posizione di backup predefinita dall'elenco di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e56cb-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="e56cb-176">Aggiungere un file all'elenco usando il percorso della posizione di condivisione stabilita per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="e56cb-176">Add a file to the list by using the path to the share location that you established for log shipping.</span></span> <span data-ttu-id="e56cb-177">Questo percorso è disponibile per il database principale e per il database di backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-177">This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="e56cb-178">Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="e56cb-179">Ripristinare il database principale usando il database di backup creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e56cb-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="e56cb-180">Con SQL Server Management Studio, connettersi all'istanza di MGC primaria.</span><span class="sxs-lookup"><span data-stu-id="e56cb-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="e56cb-181">Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**, scegliere **Ripristina**e quindi fare clic su **database**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-181">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span> <span data-ttu-id="e56cb-182">Verrà visualizzata la finestra di dialogo **Ripristina database** .</span><span class="sxs-lookup"><span data-stu-id="e56cb-182">The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="e56cb-183">Selezionare **da dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="e56cb-184">Fare clic sul pulsante Sfoglia, che apre la finestra di dialogo **specifica backup** .</span><span class="sxs-lookup"><span data-stu-id="e56cb-184">Click the browse button, which opens the **Specify Backup** dialog box.</span></span> <span data-ttu-id="e56cb-185">In **supporto di backup**selezionare **file**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-185">In **Backup media**, select **File**.</span></span> <span data-ttu-id="e56cb-186">Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-186">Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="e56cb-187">In **selezionare i set di backup da ripristinare**selezionare il backup.</span><span class="sxs-lookup"><span data-stu-id="e56cb-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="e56cb-188">Fare clic su **Opzioni** nel riquadro **Seleziona pagina** .</span><span class="sxs-lookup"><span data-stu-id="e56cb-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="e56cb-189">In **Opzioni di ripristino**selezionare **sovrascrivere il database esistente**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="e56cb-190">In **stato di ripristino**selezionare **lascia il database pronto per l'uso**.</span><span class="sxs-lookup"><span data-stu-id="e56cb-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="e56cb-191">Fare clic su **OK** per avviare il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="e56cb-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="e56cb-192">Configurare la distribuzione del log di SQL Server per il database principale.</span><span class="sxs-lookup"><span data-stu-id="e56cb-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="e56cb-193">Seguire le procedure descritte in [configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) per stabilire la distribuzione del log per il database mgc principale.</span><span class="sxs-lookup"><span data-stu-id="e56cb-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="e56cb-194">Impostare i server attivi della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e56cb-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="e56cb-195">Da Skype for Business Server Management Shell, usa il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.</span><span class="sxs-lookup"><span data-stu-id="e56cb-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e56cb-196">Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database.</span><span class="sxs-lookup"><span data-stu-id="e56cb-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="e56cb-197">Per ripristinare lo stato normale del pool, eseguire il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="e56cb-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="e56cb-198">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e56cb-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

