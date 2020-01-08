---
title: 'Lync Server 2013: Eseguire il rollback degli utenti migrati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57462cee6c4996f0beb51290f8382a1736d3e635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="59b3d-102">Eseguire il rollback degli utenti migrati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59b3d-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59b3d-103">_**Argomento Ultima modifica:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="59b3d-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="59b3d-104">Se è necessario eseguire il rollback della funzionalità archivio contatti unificato, ripristinare i contatti solo se l'utente viene spostato di nuovo in Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59b3d-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="59b3d-105">Per eseguire il rollback, disabilitare il criterio per l'utente e quindi il cmdlet **Invoke-CsUcsRollback** .</span><span class="sxs-lookup"><span data-stu-id="59b3d-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="59b3d-106">Solo l'uso di **Invoke-CsUcsRollback** da solo non è sufficiente per garantire un rollback permanente, perché la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="59b3d-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="59b3d-107">Se ad esempio viene eseguito il rollback di un utente perché Exchange 2013 viene eseguito il rollback in Exchange 2010 e la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato è ancora abilitato per l'utente nei criteri servizi utente.</span><span class="sxs-lookup"><span data-stu-id="59b3d-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59b3d-108">Il cmdlet <STRONG>Move-CsUser</STRONG> esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Lync Server 2013 nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="59b3d-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="59b3d-109">Quando gli utenti vengono spostati da Lync Server 2013 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59b3d-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="59b3d-110">Quando gli utenti vengono migrati, ad esempio quando un utente viene spostato da Lync Online a Lync Server 2013 locale o viceversa.</span><span class="sxs-lookup"><span data-stu-id="59b3d-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59b3d-111">L'importazione di dati dell'archivio contatti unificati da un database di backup può causare il danneggiamento dei dati dell'archivio contatti unificati se la modalità archivio contatti unificata è cambiata tra l'esportazione e l'importazione.</span><span class="sxs-lookup"><span data-stu-id="59b3d-111">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="59b3d-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="59b3d-112">For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="59b3d-113">Se si esportano elenchi di contatti prima che i contatti degli utenti vengano migrati a Exchange 2013 e quindi, dopo la migrazione, importino gli stessi dati, i dati dell'archivio contatti unificato e gli elenchi di contatti saranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="59b3d-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="59b3d-114">Se si esporta UserData dopo la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, importare i dati dopo la migrazione, i dati dell'archivio contatti unificati e gli elenchi di contatti saranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="59b3d-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59b3d-115">Prima di trasferire una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve verificare che l'amministratore di Lync Server abbia prima eseguito il rollback dei contatti utente di Lync Server da Exchange 2013 a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59b3d-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="59b3d-116">Per ripristinare i contatti degli archivi di contatti unificati in Lync Server, vedere procedura "per ripristinare i contatti dell'archivio contatti unificati da Exchange 2013 a Lync Server 2013" più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="59b3d-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="59b3d-117">La procedura seguente descrive come eseguire il rollback dei contatti utente.</span><span class="sxs-lookup"><span data-stu-id="59b3d-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="59b3d-118">Se si usa il cmdlet **Move-CsUser** per spostare gli utenti tra lync Server 2013 e lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti di unifed quando sposta gli utenti da Lync Server 2013 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59b3d-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="59b3d-119">**Move-CsUser** non Disabilita i criteri archivio contatti unificati, quindi la migrazione all'archivio contatti unificato si ripresenta se l'utente viene spostato di nuovo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59b3d-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="59b3d-120">Per ripristinare i contatti utente da Lync Server 2013 a Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="59b3d-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="59b3d-121">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="59b3d-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="59b3d-122">Disabilitare l'archivio contatti unificato per consentire agli utenti di eseguire il rollback in modo che non vengano rimigrati dopo il rollback.</span><span class="sxs-lookup"><span data-stu-id="59b3d-122">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="59b3d-123">Eseguire questo passaggio solo se si vuole verificare che gli utenti non vengano rimigrati in futuro. Per disabilitare l'archivio contatti unificato per singoli utenti, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="59b3d-123">(Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="59b3d-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="59b3d-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="59b3d-125">Prima di spostare un utente da Lync Server 2013 a Lync Server 2010, eseguire il rollback dell'elenco contatti per gli utenti specificati in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59b3d-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59b3d-126">Se questo passaggio viene omesso, l'elenco contatti verrà perso.</span><span class="sxs-lookup"><span data-stu-id="59b3d-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="59b3d-127">Eseguire il rollback degli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="59b3d-127">Roll back the specified users.</span></span> <span data-ttu-id="59b3d-128">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="59b3d-128">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="59b3d-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="59b3d-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59b3d-130">Non è consigliabile usare l'opzione – Force per forzare il rollback.</span><span class="sxs-lookup"><span data-stu-id="59b3d-130">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="59b3d-131">Se si usa questa opzione, i contatti degli utenti andranno perduti.</span><span class="sxs-lookup"><span data-stu-id="59b3d-131">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="59b3d-132">Per eseguire il rollback dei contatti dell'archivio contatti unificati da Exchange 2013 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59b3d-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="59b3d-133">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="59b3d-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="59b3d-134">Disabilitare l'archivio contatti unificato per consentire agli utenti di eseguire il rollback in modo che non vengano rimigrati dopo il rollback.</span><span class="sxs-lookup"><span data-stu-id="59b3d-134">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="59b3d-135">Per disabilitare l'archivio contatti unificato per singoli utenti, nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="59b3d-135">To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="59b3d-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="59b3d-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="59b3d-137">Eseguire il rollback degli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="59b3d-137">Roll back the specified users.</span></span> <span data-ttu-id="59b3d-138">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="59b3d-138">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="59b3d-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="59b3d-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="59b3d-140">Prima di tutto, è necessario eseguire il rollback dell'utente di Lync Server e quindi la cassetta postale di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="59b3d-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="59b3d-141">L'amministratore di Exchange viene bloccato dal rollback di Exchange fino al completamento del ripristino di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59b3d-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="59b3d-142">Non è consigliabile usare l'opzione – Force per forzare il rollback.</span><span class="sxs-lookup"><span data-stu-id="59b3d-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="59b3d-143">Se si usa questa opzione, i contatti degli utenti andranno perduti.</span><span class="sxs-lookup"><span data-stu-id="59b3d-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="59b3d-144">Dopo aver eseguito il rollback dell'utente a Lync Server, l'amministratore di Exchange può eseguire il rollback dell'utente di Exchange da Exchange 2013 a Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="59b3d-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

