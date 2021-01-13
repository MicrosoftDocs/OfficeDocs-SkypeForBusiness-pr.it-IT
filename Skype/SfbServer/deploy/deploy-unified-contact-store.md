---
title: "Distribuire l'archivio contatti unificato in Skype for Business Server "
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: "Riepilogo: abilitare l'archivio contatti unificato in Skype for Business Server."
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812556"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="d507b-103">Distribuire l'archivio contatti unificato in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d507b-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="d507b-104">**Riepilogo:** Abilitare l'archivio contatti unificato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d507b-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="d507b-105">L'abilitazione dell'archivio contatti unificato in Skype for Business Server non richiede impostazioni di topologia.</span><span class="sxs-lookup"><span data-stu-id="d507b-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="d507b-106">Per abilitare l'archivio contatti unificato per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="d507b-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="d507b-107">I criteri dell'archivio contatto unificati sono abilitati (abilitati per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="d507b-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="d507b-108">Gli utenti accedono con Skype for business almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="d507b-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="d507b-109">Dopo la migrazione dei contatti di un utente, che avviene automaticamente quando un utente esegue l'accesso con Skype for business, l'utente può accedere e gestire i propri contatti Skype for business da Skype for business, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="d507b-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="d507b-110">L'utente non deve aver eseguito l'accesso a Skype for business per gestire i propri contatti da Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="d507b-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d507b-111">Se un utente esegue l'accesso da Skype for business dopo la migrazione, i contatti e i gruppi sono disponibili e aggiornati, ma l'utente non è in grado di gestire (ovvero, aggiungere, eliminare, spostare, contrassegnare, UNTAG o modificare) tali contatti.</span><span class="sxs-lookup"><span data-stu-id="d507b-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="d507b-112">Abilitare gli utenti per l'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="d507b-112">Enable users for unified contact store</span></span>

<span data-ttu-id="d507b-113">Quando si distribuisce Skype for Business Server e si pubblica la topologia, l'archivio contatti unificato è abilitato per tutti gli utenti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d507b-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="d507b-114">Non è necessario eseguire ulteriori operazioni per abilitare l'archivio contatti unificato dopo la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d507b-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="d507b-115">Tuttavia, è possibile utilizzare il cmdlet **Set-CsUserServicesPolicy** per decidere a quali utenti rendere l'archivio unificato per i contatti disponibile.</span><span class="sxs-lookup"><span data-stu-id="d507b-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="d507b-116">È possibile abilitare questa caratteristica a livello globale, di sito, tenant, o per utenti singoli o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="d507b-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="d507b-117">Per abilitare gli utenti all'archivio unificato contatti</span><span class="sxs-lookup"><span data-stu-id="d507b-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="d507b-118">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d507b-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d507b-119">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d507b-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="d507b-120">Per abilitare l'archivio unificato per i contatti a livello globale per tutti gli utenti di Skype for Business Server, tra i seguenti cmdlet dell'interfaccia della riga di comando di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d507b-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="d507b-121">Per abilitare l'archivio contatti unificato per gli utenti in un sito specifico, al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d507b-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="d507b-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d507b-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="d507b-123">Per abilitare l'archivio contatti unificato dal tenant, al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d507b-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="d507b-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d507b-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="d507b-125">Per abilitare l'archivio contatti unificato per utenti specifici, al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d507b-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="d507b-126">Al posto del nome visualizzato dell'utente, è inoltre possibile utilizzare alias utente o URI SIP.</span><span class="sxs-lookup"><span data-stu-id="d507b-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="d507b-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d507b-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="d507b-128">Nell'esempio precedente, il primo comando crea un nuovo criterio per utente chiamato UCS Enabled Users, con il contrassegno UcsAllowed impostato su True.</span><span class="sxs-lookup"><span data-stu-id="d507b-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="d507b-129">Il secondo comando assegna il criterio all'utente con nome visualizzato Ken Myer, e pertanto Ken Myer è ora abilitato all'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="d507b-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="d507b-130">Eseguire la migrazione degli utenti nell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="d507b-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="d507b-131">I contatti di un utente vengono migrati automaticamente al server Exchange 2013 quando l'utente:</span><span class="sxs-lookup"><span data-stu-id="d507b-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="d507b-132">All'utente sono stati assegnati servizi utente per cui UcsAllowed è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="d507b-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="d507b-133">È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha eseguito l'accesso almeno una volta alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="d507b-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="d507b-134">L'utente effettua l'accesso utilizzando un rich-client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d507b-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="d507b-135">Se l'utente effettua l'accesso con un client Lync o versioni precedenti o se l'utente non è connesso a un server Exchange 2013, i criteri dei servizi utente vengono ignorati e i contatti dell'utente restano in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d507b-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="d507b-136">È possibile stabilire se i contatti di un utente sono stati migrati usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d507b-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="d507b-137">Verificare la chiave del Registro di sistema seguente nel computer client:</span><span class="sxs-lookup"><span data-stu-id="d507b-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="d507b-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<URL SIP \> \UCS</span><span class="sxs-lookup"><span data-stu-id="d507b-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="d507b-139">Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene un valore di InUCSMode con un valore pari a 2165.</span><span class="sxs-lookup"><span data-stu-id="d507b-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="d507b-140">Eseguire il cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="d507b-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="d507b-141">Nella riga di comando di Skype for Business Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d507b-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="d507b-142">Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="d507b-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="d507b-143">Eseguire il rollback degli utenti migrati</span><span class="sxs-lookup"><span data-stu-id="d507b-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="d507b-144">Se è necessario eseguire il rollback della caratteristica archivio contatti unificato, eseguire il rollback dei contatti solo se l'utente viene spostato di nuovo in Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d507b-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="d507b-145">Per eseguire il rollback, disabilitare il criterio per l'utente e quindi eseguire il cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="d507b-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="d507b-146">La sola esecuzione di **Invoke-CsUcsRollback** non è sufficiente ad assicurare un rollback permanente, in quanto la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non viene disabilitato.</span><span class="sxs-lookup"><span data-stu-id="d507b-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="d507b-147">Ad esempio, se un utente viene eseguito il rollback perché Exchange 2013 viene ripristinato in Exchange 2010 e quindi la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato sia ancora abilitato per l'utente nei criteri servizi utente.</span><span class="sxs-lookup"><span data-stu-id="d507b-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="d507b-148">Il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Skype for Business Server nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d507b-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="d507b-149">Quando gli utenti vengono spostati da Skype for Business Server a Microsoft Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d507b-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="d507b-150">Quando gli utenti eseguono la migrazione di spazi incrociati, ad esempio quando un utente viene spostato da Skype for business online a Skype for Business Server locale o viceversa.</span><span class="sxs-lookup"><span data-stu-id="d507b-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="d507b-p107">L'importazione dei dati dell'archivio contatti unificato da un database di backup può danneggiare i dati dell'archivio e degli utenti se la modalità dell'archivio stesso è cambiata tra l'esportazione e l'importazione. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d507b-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="d507b-153">Se si esportano gli elenchi di contatti prima della migrazione dei contatti degli utenti a Exchange 2013 e successivamente, dopo la migrazione, vengono importati gli stessi dati, i dati degli archivi dei contatti unificati e gli elenchi di contatti verranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="d507b-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="d507b-154">Se i dati dell'utente vengono esportati dopo la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, i dati vengono importati dopo la migrazione, i dati dell'archivio contatti unificato e gli elenchi di contatti verranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="d507b-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d507b-155">Prima di spostare una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve accertarsi che l'amministratore di Skype for Business Server abbia prima eseguito il rollback dei contatti utente di Skype for Business Server da Exchange 2013 a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d507b-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="d507b-156">Per eseguire il rollback dei contatti dell'archivio contatti unificato in Skype for Business Server, vedere la procedura "per eseguire il rollback dei contatti dell'archivio contatti unificato da Exchange 2013 a Skype for Business Server" più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d507b-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="d507b-157">**Come eseguire il rollback di contatti utente:** Se si utilizza il cmdlet **Move-CsUser** per spostare gli utenti tra Skype for business server 2015 e lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti unificato quando sposta gli utenti da skype for Business Server 2015 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d507b-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="d507b-158">**Move-CsUser** non disattiva il criterio archivio contatti unificato, quindi la migrazione all'archivio contatti unificato si ripeterà se l'utente viene spostato di nuovo su Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d507b-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

