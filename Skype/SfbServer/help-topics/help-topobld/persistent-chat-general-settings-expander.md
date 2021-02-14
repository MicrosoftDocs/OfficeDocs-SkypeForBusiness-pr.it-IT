---
title: Espansione delle impostazioni generali di Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'È possibile modificare le impostazioni generali per il server Chat persistente o il pool di server Chat persistente configurando o definendo queste proprietà:'
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823855"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="bef32-103">Espansione delle impostazioni generali di Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="bef32-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="bef32-104">È possibile modificare **le impostazioni** generali per il server Chat persistente o il pool di server Chat persistente configurando o definendo queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="bef32-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="bef32-105">**Generale**</span><span class="sxs-lookup"><span data-stu-id="bef32-105">**General**</span></span>
  
- <span data-ttu-id="bef32-106">**FQDN:** modificare questa impostazione per definire il nome di dominio completo del server Chat persistente o del pool di server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="bef32-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="bef32-107">**Nome visualizzato del pool Persistent Chat**: definire questa impostazione del server o del pool specificando un nome facile da leggere e comprendere per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="bef32-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="bef32-108">Questa impostazione agevola l'associazione di un determinato server Chat persistente o pool di server Chat persistente in base al nome visualizzato anziché a un nome di dominio completo più difficile da comprendere.</span><span class="sxs-lookup"><span data-stu-id="bef32-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="bef32-109">**Porta Persistent Chat**: specificare la porta da usare per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bef32-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="bef32-110">È possibile modificare **le impostazioni** delle associazioni per il server Chat persistente o il pool di server Chat persistente configurando o definendo queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="bef32-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="bef32-111">**Associazioni**</span><span class="sxs-lookup"><span data-stu-id="bef32-111">**Associations**</span></span>
  
- <span data-ttu-id="bef32-112">**SQL Server store:** selezionare l'SQL Server store e l'istanza denominata facoltativa dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="bef32-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="bef32-113">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-114">Selezionare la **casella di controllo SQL Server mirroring dell'archivio** se si desidera abilitare il mirroring per l'SQL Server principale.</span><span class="sxs-lookup"><span data-stu-id="bef32-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="bef32-115">Se si è scelto di abilitare SQL Server mirroring dell'archivio, selezionare l'archivio e l'istanza nell'elenco **Mirroring SQL Server store.**</span><span class="sxs-lookup"><span data-stu-id="bef32-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="bef32-116">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-117">Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'SQL Server principale.</span><span class="sxs-lookup"><span data-stu-id="bef32-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="bef32-118">Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bef32-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="bef32-119">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="bef32-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="bef32-120">Selezionare la **casella di controllo Usa archivi SQL Server backup** per abilitare il ripristino di emergenza se si desidera abilitare l'utilizzo SQL Server ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="bef32-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="bef32-121">Se si è scelto di abilitare il ripristino di emergenza, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server backup**.</span><span class="sxs-lookup"><span data-stu-id="bef32-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="bef32-122">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-123">Selezionare la **casella di SQL Server di mirroring** dell'archivio se si desidera abilitare il mirroring per l'SQL Server di mirroring di backup.</span><span class="sxs-lookup"><span data-stu-id="bef32-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="bef32-124">Se si è scelto di abilitare il mirroring dell SQL Server di archiviazione, selezionare l'archivio e l'istanza nell'elenco **Backup SQL Server mirror dell'archivio.**</span><span class="sxs-lookup"><span data-stu-id="bef32-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="bef32-125">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-126">Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'archivio SQL Server backup.</span><span class="sxs-lookup"><span data-stu-id="bef32-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="bef32-127">Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bef32-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="bef32-128">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="bef32-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="bef32-129">Selezionare la casella di controllo **Abilita conformità** per consentire l'uso di un database di conformità.</span><span class="sxs-lookup"><span data-stu-id="bef32-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="bef32-130">Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità**.</span><span class="sxs-lookup"><span data-stu-id="bef32-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="bef32-131">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-132">Selezionare la **casella di controllo SQL Server mirroring dell'archivio** se si desidera abilitare il mirroring per l'archivio SQL Server conformità.</span><span class="sxs-lookup"><span data-stu-id="bef32-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="bef32-133">Se si è scelto di abilitare il mirroring SQL Server store, selezionare l'archivio e l'istanza nell'elenco **SQL Server mirror dell'archivio.**</span><span class="sxs-lookup"><span data-stu-id="bef32-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="bef32-134">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-135">Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'archivio SQL Server conformità.</span><span class="sxs-lookup"><span data-stu-id="bef32-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="bef32-136">Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bef32-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="bef32-137">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="bef32-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="bef32-138">Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità backup**.</span><span class="sxs-lookup"><span data-stu-id="bef32-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="bef32-139">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-140">Selezionare la **casella di controllo SQL Server mirroring dell'archivio** se si desidera abilitare il mirroring per l'archivio SQL Server conformità.</span><span class="sxs-lookup"><span data-stu-id="bef32-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="bef32-141">Se si è scelto di abilitare il mirroring SQL Server dell'archivio, selezionare l'archivio e l'istanza nell'elenco **Backup SQL Server mirror dell'archivio.**</span><span class="sxs-lookup"><span data-stu-id="bef32-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="bef32-142">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bef32-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="bef32-143">Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'archivio di conformità SQL Server backup.</span><span class="sxs-lookup"><span data-stu-id="bef32-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="bef32-144">Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bef32-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="bef32-145">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="bef32-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="bef32-146">**Archivio file** Selezionare un percorso di archivio file nell'elenco oppure fare clic su **Nuovo** per creare un nuovo archivio file.</span><span class="sxs-lookup"><span data-stu-id="bef32-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="bef32-147">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="bef32-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="bef32-148">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="bef32-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="bef32-149">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="bef32-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bef32-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bef32-150">See also</span></span>

[<span data-ttu-id="bef32-151">Pianificare il server Chat persistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bef32-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="bef32-152">Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bef32-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="bef32-153">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bef32-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
