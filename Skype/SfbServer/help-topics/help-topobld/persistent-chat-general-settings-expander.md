---
title: Espansione delle impostazioni generali di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'È possibile modificare le impostazioni generali per il server di chat persistente o il pool di server di chat persistente configurando o definendo queste proprietà:'
ms.openlocfilehash: 184ee58f5b79547434281e073cf99a30d72b7bbc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684489"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="7a4d4-103">Espansione delle impostazioni generali di Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="7a4d4-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="7a4d4-104">È possibile modificare le impostazioni **generali** per il server di chat persistente o il pool di server di chat persistente configurando o definendo queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="7a4d4-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="7a4d4-105">**Generale**</span><span class="sxs-lookup"><span data-stu-id="7a4d4-105">**General**</span></span>
  
- <span data-ttu-id="7a4d4-106">**FQDN**: modificare questa impostazione per definire il nome di dominio completo del server di chat persistente o del pool di server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="7a4d4-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="7a4d4-107">**Nome visualizzato del pool di Chat persistente**: definire questa impostazione del server o del pool specificando un nome facile da leggere e comprendere per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="7a4d4-108">Questa impostazione rende più facile per gli utenti associare un server di chat persistente o un pool di server di chat persistente in base al nome visualizzato invece di un nome di dominio completo più difficile da comprendere.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="7a4d4-109">**Porta di Chat persistente**: specificare la porta da usare per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="7a4d4-110">È possibile modificare le impostazioni delle **associazioni** per il server di chat persistente o il pool di server di chat persistente configurando o definendo queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="7a4d4-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="7a4d4-111">**Associazioni**</span><span class="sxs-lookup"><span data-stu-id="7a4d4-111">**Associations**</span></span>
  
- <span data-ttu-id="7a4d4-112">**Archivio SQL Server**: selezionare l'archivio SQL Server e l'istanza denominata facoltativa nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="7a4d4-113">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-114">Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per l'archivio principale di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="7a4d4-115">Se si è scelto di abilitare il mirroring di SQL Server Store, selezionare lo Store e l'istanza dall'elenco **mirroring di SQL Server Store**.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="7a4d4-116">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-117">Selezionare la casella **di controllo Usa verifica mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico dell'archivio principale di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="7a4d4-118">Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7a4d4-119">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7a4d4-120">Selezionare la casella **di controllo Usa gli archivi di SQL Server di backup per abilitare il ripristino di emergenza** se si vuole abilitare l'uso del ripristino di emergenza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a4d4-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="7a4d4-121">Se si è scelto di abilitare il ripristino di emergenza, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server backup**.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="7a4d4-122">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-123">Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per l'archivio di mirroring di SQL Server di backup.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="7a4d4-124">Se si è scelto di abilitare il mirroring di SQL Server Store di backup, selezionare lo Store e l'istanza dal mirror di backup dell'elenco di **SQL Server Store**.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7a4d4-125">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-126">Selezionare la casella **di controllo Usa verifica mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico dell'archivio di SQL Server di backup.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="7a4d4-127">Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7a4d4-128">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7a4d4-129">Selezionare la casella di controllo **Abilita conformità** per consentire l'uso di un database di conformità.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="7a4d4-130">Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità**.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="7a4d4-131">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-132">Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per la conformità a SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7a4d4-133">Se si è scelto di abilitare il mirroring di SQL Server Store Compliance, selezionare lo Store e l'istanza dal **mirror di SQL Server Store Compliance**List.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7a4d4-134">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-135">Selezionare la casella **di controllo Usa verifica mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico della conformità di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7a4d4-136">Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7a4d4-137">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7a4d4-138">Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità backup**.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="7a4d4-139">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-140">Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per la conformità a SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7a4d4-141">Se si è scelto di abilitare il mirroring di SQL Server Store Compliance, selezionare lo Store e l'istanza dal **mirror di SQL Server Store Compliance list backup**.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="7a4d4-142">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="7a4d4-143">Selezionare la casella **di controllo Usa il witness di mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico dell'archivio di SQL server Compliance backup.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="7a4d4-144">Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="7a4d4-145">Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="7a4d4-146">**Archivio file** Selezionare una posizione di archivio file nell'elenco oppure fare clic su **nuovo** per creare un nuovo archivio di file.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="7a4d4-147">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="7a4d4-148">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="7a4d4-149">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="7a4d4-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a4d4-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a4d4-150">See also</span></span>

[<span data-ttu-id="7a4d4-151">Pianificare il server Chat persistente in Skype per Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7a4d4-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7a4d4-152">Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7a4d4-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="7a4d4-153">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7a4d4-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
