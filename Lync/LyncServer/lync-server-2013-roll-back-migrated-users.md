---
title: 'Lync Server 2013: eseguire il rollback degli utenti migrati'
description: 'Lync Server 2013: eseguire il rollback degli utenti migrati.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5993bfd530c84307d3ee5be627b3ed33814be73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559542"
---
# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="6c065-103">Eseguire il rollback degli utenti migrati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c065-103">Roll back migrated users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c065-104">_**Ultimo argomento modificato:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="6c065-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="6c065-105">Se è necessario eseguire il rollback della caratteristica archivio contatti unificato, eseguire il rollback dei contatti solo se l'utente viene spostato di nuovo in Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6c065-105">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="6c065-106">Per eseguire il rollback, disabilitare il criterio per l'utente e quindi eseguire il cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="6c065-106">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="6c065-107">La sola esecuzione di **Invoke-CsUcsRollback** non è sufficiente ad assicurare un rollback permanente, in quanto la migrazione dell'archivio contatti unificato verrà avviata di nuovo se il criterio non viene disabilitato.</span><span class="sxs-lookup"><span data-stu-id="6c065-107">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="6c065-108">Ad esempio, se un utente viene eseguito il rollback perché Exchange 2013 viene ripristinato in Exchange 2010 e quindi la cassetta postale dell'utente viene spostata in Exchange 2013, la migrazione dell'archivio contatti unificato verrà avviata di nuovo sette giorni dopo il rollback, purché l'archivio contatti unificato sia ancora abilitato per l'utente nei criteri servizi utente.</span><span class="sxs-lookup"><span data-stu-id="6c065-108">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c065-109">Il cmdlet <STRONG>Move-CsUser</STRONG> esegue automaticamente il rollback dell'archivio contatti dell'utente da Exchange 2013 a Lync Server 2013 nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c065-109">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6c065-110">Quando gli utenti vengono spostati da Lync Server 2013 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6c065-110">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="6c065-111">Quando gli utenti eseguono la migrazione di spazi incrociati, ad esempio quando un utente viene spostato da Lync Online a Lync Server 2013 in locale o viceversa.</span><span class="sxs-lookup"><span data-stu-id="6c065-111">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c065-p102">L'importazione dei dati dell'archivio contatti unificato da un database di backup può danneggiare i dati dell'archivio e degli utenti se la modalità dell'archivio stesso è cambiata tra l'esportazione e l'importazione. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6c065-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6c065-114">Se si esportano gli elenchi di contatti prima della migrazione dei contatti degli utenti a Exchange 2013 e successivamente, dopo la migrazione, vengono importati gli stessi dati, i dati degli archivi dei contatti unificati e gli elenchi di contatti verranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="6c065-114">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="6c065-115">Se si esporta UserData dopo aver eseguito la migrazione degli utenti a Exchange 2013, eseguire il rollback della migrazione e quindi, per qualche motivo, i dati vengono importati dopo la migrazione, i dati dell'archivio contatti unificato e gli elenchi di contatti verranno danneggiati.</span><span class="sxs-lookup"><span data-stu-id="6c065-115">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c065-116">Prima di spostare una cassetta postale di Exchange da Exchange 2013 a Exchange 2010, l'amministratore di Exchange deve verificare che l'amministratore di Lync Server abbia prima eseguito il rollback dei contatti utente di Lync Server da Exchange 2013 a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c065-116">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="6c065-117">Per eseguire il rollback dei contatti dell'archivio contatti unificato in Lync Server, vedere la procedura "per eseguire il rollback degli archivi di contatti unificati da Exchange 2013 a Lync Server 2013" più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="6c065-117">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="6c065-118">Nella procedura seguente viene illustrato come eseguire il rollback dei contatti degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6c065-118">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="6c065-119">Se si utilizza il cmdlet **Move-CsUser** per spostare gli utenti tra lync Server 2013 e lync Server 2010, è possibile ignorare questi passaggi perché il cmdlet **Move-CsUser** esegue automaticamente il rollback dell'archivio contatti di unifed quando sposta gli utenti da Lync Server 2013 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6c065-119">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="6c065-120">**Move-CsUser** non disattiva il criterio dell'archivio contatti unificato, quindi la migrazione all'archivio contatti unificato si ripeterà se l'utente viene spostato di nuovo su Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c065-120">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="6c065-121">Per eseguire il rollback dei contatti utente da Lync Server 2013 a Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6c065-121">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="6c065-122">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6c065-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6c065-p105">Disabilitare l'archivio contatti unificato per gli utenti di cui è necessario eseguire il rollback in modo che, dopo il rollback, non ne venga ripetuta la migrazione. Eseguire questo passaggio solo se si desidera essere certi che gli utenti non vengano ritrasferiti in futuro. Per disabilitare l'archivio contatti unificato per i singoli utenti, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6c065-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="6c065-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6c065-125">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="6c065-126">Prima di spostare un utente da Lync Server 2013 a Lync Server 2010, eseguire il rollback dell'elenco contatti per gli utenti specificati in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c065-126">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6c065-127">Se si ignora questo passaggio, l'elenco contatti andrà perso.</span><span class="sxs-lookup"><span data-stu-id="6c065-127">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="6c065-p106">Eseguire il rollback degli utenti specificati. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6c065-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="6c065-130">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6c065-130">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6c065-p107">Non è consigliabile utilizzare l'opzione –Force per forzare il rollback. Se si utilizza tale opzione, i contatti degli utenti andranno persi.</span><span class="sxs-lookup"><span data-stu-id="6c065-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="6c065-133">Per eseguire il rollback dei contatti dell'archivio contatti unificato da Exchange 2013 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c065-133">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="6c065-134">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6c065-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6c065-p108">Disabilitare l'archivio contatti unificato per gli utenti di cui è necessario eseguire il rollback in modo che, dopo il rollback, non ne venga ripetuta la migrazione. Per disabilitare l'archivio contatti unificato per i singoli utenti, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6c065-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="6c065-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6c065-137">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="6c065-p109">Eseguire il rollback degli utenti specificati. Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6c065-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="6c065-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6c065-140">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6c065-141">È necessario innanzitutto eseguire il rollback dell'utente di Lync Server e quindi spostare la cassetta postale di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6c065-141">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="6c065-142">L'amministratore di Exchange è bloccato dal rollback di Exchange fino al completamento del ripristino di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c065-142">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="6c065-143">Non è consigliabile utilizzare l'opzione –Force per forzare il rollback.</span><span class="sxs-lookup"><span data-stu-id="6c065-143">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="6c065-144">Se si utilizza tale opzione, i contatti degli utenti andranno persi.</span><span class="sxs-lookup"><span data-stu-id="6c065-144">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="6c065-145">Dopo aver eseguito il rollback dell'utente a Lync Server, l'amministratore di Exchange può eseguire il rollback dell'utente di Exchange da Exchange 2013 a Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="6c065-145">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

