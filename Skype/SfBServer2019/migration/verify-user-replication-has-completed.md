---
title: Verificare il completamento della replica utente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quando si esegue il cmdlet Move-CsUser, è possibile che si verifichi un errore perché le informazioni utente tra servizi di dominio Active Directory (AD DS) e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio Skype for Business Server 2019 User Replicator dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Skype for Business Server 2019. Il processo di sincronizzazione iniziale di Skype for Business Server 2019 User Replicator viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta. Successivamente la sincronizzazione viene basata sull'intervallo di User Replicator. Eseguire la procedura seguente per verificare che la replica degli utenti sia completata prima di eseguire il cmdlet Move-CsUser.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751648"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="f2818-107">Verificare il completamento della replica utente</span><span class="sxs-lookup"><span data-stu-id="f2818-107">Verify user replication has completed</span></span>

<span data-ttu-id="f2818-108">Quando si esegue il cmdlet **Move-CsUser** , è possibile che si verifichi un errore se le informazioni utente tra servizi di dominio Active Directory (ad DS) e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta.</span><span class="sxs-lookup"><span data-stu-id="f2818-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="f2818-109">Il tempo necessario per il corretto completamento della sincronizzazione iniziale del servizio Skype for Business Server 2019 User Replicator dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospita il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f2818-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f2818-110">Il processo di sincronizzazione iniziale di Skype for Business Server 2019 User Replicator viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="f2818-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="f2818-111">Successivamente, la sincronizzazione si basa sull'intervallo User Replicator.</span><span class="sxs-lookup"><span data-stu-id="f2818-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="f2818-112">Completare la procedura seguente per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="f2818-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="f2818-113">Per verificare che la replica degli utenti sia stata completata</span><span class="sxs-lookup"><span data-stu-id="f2818-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="f2818-114">Accedere al computer in cui è installato il Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f2818-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="f2818-115">Fare clic su **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f2818-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="f2818-116">Immettere **eventvwr.exe** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2818-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="f2818-117">In Visualizzatore eventi fare clic su **registri applicazioni e servizi** per espanderlo e quindi selezionare Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2818-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="f2818-118">Nel riquadro **Azioni** fare clic su **Filtro registro corrente**.</span><span class="sxs-lookup"><span data-stu-id="f2818-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="f2818-119">Nell'elenco **Origini eventi** fare clic su **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="f2818-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="f2818-120">In **\<All Event IDs\>** immettere **30024**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2818-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="f2818-121">Nell'elenco eventi filtrati, nella scheda **generale** , cercare una voce che indica che la replica degli utenti è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f2818-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

