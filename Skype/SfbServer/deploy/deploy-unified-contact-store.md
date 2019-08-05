---
title: "Distribuire l'archivio contatti unificato in Skype for Business Server "
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: "Riepilogo: abilitare l'archivio contatti unificato in Skype for Business Server."
ms.openlocfilehash: 737e9dbdd0dc9e4aae54e454cb558c59004719b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195410"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="bf395-103">Distribuire l'archivio contatti unificato in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bf395-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="bf395-104">**Riepilogo:** Abilitare l'archivio contatti unificato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf395-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="bf395-105">L'abilitazione dell'archivio contatti unificato in Skype for Business Server non richiede le impostazioni della topologia.</span><span class="sxs-lookup"><span data-stu-id="bf395-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="bf395-106">Per abilitare l'archivio contatti unificato per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="bf395-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="bf395-107">Il criterio archivio contatti unificato è abilitato (il valore predefinito è abilitato).</span><span class="sxs-lookup"><span data-stu-id="bf395-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="bf395-108">Gli utenti accedono con Skype for business almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="bf395-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="bf395-109">Dopo la migrazione dei contatti di un utente, che avviene automaticamente quando un utente accede con Skype for business, l'utente può accedere e gestire i contatti di Skype for business da Skype for business, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="bf395-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="bf395-110">Non è necessario che l'utente abbia effettuato l'accesso a Skype for business per gestire i propri contatti da Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="bf395-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bf395-111">Se un utente accede da Skype for business dopo la migrazione, i contatti e i gruppi sono disponibili e aggiornati, ma l'utente non può gestire (ovvero aggiungere, eliminare, trasferire, contrassegnare, UNTAG o modificare) i contatti.</span><span class="sxs-lookup"><span data-stu-id="bf395-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="bf395-112">Abilitare gli utenti per l'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="bf395-112">Enable users for unified contact store</span></span>

<span data-ttu-id="bf395-113">Quando si distribuisce Skype for Business Server e si pubblica la topologia, per impostazione predefinita l'archivio contatti unificato è abilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="bf395-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="bf395-114">Non è necessario eseguire altre azioni per abilitare l'archiviazione di contatti unificati dopo la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf395-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="bf395-115">Tuttavia, puoi usare il cmdlet **Set-CsUserServicesPolicy** per personalizzare gli utenti che dispongono di un archivio contatti unificato disponibile.</span><span class="sxs-lookup"><span data-stu-id="bf395-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="bf395-116">Puoi abilitare questa funzionalità a livello globale, per sito, per tenant o per singoli o gruppi di persone.</span><span class="sxs-lookup"><span data-stu-id="bf395-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="bf395-117">Per abilitare gli utenti per l'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="bf395-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="bf395-118">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bf395-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="bf395-119">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf395-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="bf395-120">Per abilitare l'archivio contatti unificato a livello globale per tutti gli utenti di Skype for Business Server, tra i seguenti cmdlet dell'interfaccia della riga di comando di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bf395-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="bf395-121">Per abilitare l'archivio contatti unificato per gli utenti di un sito specifico, al prompt digitare:</span><span class="sxs-lookup"><span data-stu-id="bf395-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="bf395-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf395-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="bf395-123">Per abilitare l'archivio contatti unificato dal tenant, al prompt digitare:</span><span class="sxs-lookup"><span data-stu-id="bf395-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="bf395-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf395-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="bf395-125">Per abilitare l'archivio contatti unificato per utenti specifici, al prompt digitare:</span><span class="sxs-lookup"><span data-stu-id="bf395-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="bf395-126">È anche possibile usare l'alias utente o l'URI SIP anziché il nome visualizzato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bf395-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="bf395-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf395-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="bf395-128">Nell'esempio precedente il primo comando crea un nuovo criterio per utente denominato UCS abilitato agli utenti con il flag UcsAllowed impostato su true.</span><span class="sxs-lookup"><span data-stu-id="bf395-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="bf395-129">Il secondo comando assegna i criteri all'utente con il nome visualizzato Ken di riferimento, il che significa che Ken è ora abilitato per l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="bf395-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="bf395-130">Eseguire la migrazione degli utenti nell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="bf395-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="bf395-131">I contatti di un utente vengono automaticamente migrati nel server di Exchange 2013 quando l'utente:</span><span class="sxs-lookup"><span data-stu-id="bf395-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="bf395-132">È stato assegnato un criterio servizi utente con UcsAllowed impostato su true.</span><span class="sxs-lookup"><span data-stu-id="bf395-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="bf395-133">È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha eseguito l'accesso alla cassetta postale almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="bf395-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="bf395-134">Accede usando un client Rich di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="bf395-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="bf395-135">Se l'utente esegue l'accesso con un client Lync o una versione precedente o se l'utente non è connesso a un server di Exchange 2013, il criterio servizi utente viene ignorato e i contatti dell'utente rimangono in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf395-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="bf395-136">Puoi determinare se i contatti di un utente sono stati migrati usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf395-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="bf395-137">Selezionare la chiave del registro di sistema seguente nel computer client:</span><span class="sxs-lookup"><span data-stu-id="bf395-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="bf395-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<URL\>SIP \UCS</span><span class="sxs-lookup"><span data-stu-id="bf395-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="bf395-139">Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene un valore di InUCSMode con il valore 2165.</span><span class="sxs-lookup"><span data-stu-id="bf395-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="bf395-140">Eseguire il cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="bf395-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="bf395-141">Nella riga di comando di Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="bf395-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="bf395-142">Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati in archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="bf395-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="bf395-143">Eseguire il rollback degli utenti migrati</span><span class="sxs-lookup"><span data-stu-id="bf395-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="bf395-144">Se è necessario eseguire il rollback della funzionalità archivio contatti unificato, ripristinare i contatti solo se l'utente viene spostato di nuovo in Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf395-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="bf395-145">Per eseguire il rollback, disabilitare il criterio per l'utente e quindi il cmdlet **Invoke-CsUcsRollback** .</span><span class="sxs-lookup"><span data-stu-id="bf395-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="bf395-146">Solo l'uso di **Invoke-CsUcsRollback** da solo non è sufficiente per garantire un rollback permanente, perché la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="bf395-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="bf395-147">Se ad esempio viene eseguito il rollback di un utente perché Exchange 2013 viene eseguito il rollback in Exchange 2010 e la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato è ancora abilitato per l'utente nei criteri servizi utente.</span><span class="sxs-lookup"><span data-stu-id="bf395-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="bf395-148">Il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Skype for Business Server nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf395-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="bf395-149">Quando gli utenti vengono spostati da Skype for Business Server a Microsoft Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf395-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="bf395-150">Quando gli utenti vengono migrati, ad esempio quando un utente viene spostato da Skype for business online a Skype for Business Server locale o viceversa.</span><span class="sxs-lookup"><span data-stu-id="bf395-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="bf395-151">L'importazione di dati dell'archivio contatti unificati da un database di backup può causare il danneggiamento dei dati dell'archivio contatti unificati se la modalità archivio contatti unificata è cambiata tra l'esportazione e l'importazione.</span><span class="sxs-lookup"><span data-stu-id="bf395-151">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="bf395-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf395-152">For example:</span></span>
  
- <span data-ttu-id="bf395-153">Se si esportano elenchi di contatti prima che i contatti degli utenti vengano migrati a Exchange 2013 e quindi, dopo la migrazione, importino gli stessi dati, i dati dell'archivio contatti unificato e gli elenchi di contatti saranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="bf395-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="bf395-154">Se si esportano dati utente dopo la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, i dati vengono importati dopo la migrazione, i dati dell'archivio contatti unificati e gli elenchi di contatti saranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="bf395-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="bf395-155">Prima di trasferire una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve verificare che l'amministratore di Skype for Business Server abbia prima eseguito il rollback dei contatti degli utenti di Skype for Business Server da Exchange 2013 a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf395-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="bf395-156">Per ripristinare i contatti degli archivi di contatti unificati in Skype for Business Server, vedere procedura "per ripristinare i contatti dell'archivio contatti unificati da Exchange 2013 a Skype for Business Server" più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="bf395-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="bf395-157">**Come ripristinare i contatti utente:** Se si usa il cmdlet **Move-CsUser** per spostare gli utenti tra Skype for Business Server 2015 e Lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti unificato quando sposta gli utenti da Skype for Business Server 2015 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf395-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="bf395-158">**Move-CsUser** non Disabilita i criteri dell'archivio contatti unificato, quindi la migrazione all'archivio contatti unificato si ripresenta se l'utente viene spostato di nuovo in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bf395-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

