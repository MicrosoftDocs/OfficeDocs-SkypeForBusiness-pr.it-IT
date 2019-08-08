---
title: Verificare che la replica degli utenti sia stata completata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quando si esegue il cmdlet Move-CsUser, è possibile che si verifichi un errore perché le informazioni degli utenti tra servizi di dominio Active Directory e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta. Il tempo necessario per completare correttamente la sincronizzazione iniziale di Skype for Business Server 2019, dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospitano Skype for business Pool di server 2019. Il processo di sincronizzazione iniziale di Skype for Business Server 2019 viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta. Successivamente, la sincronizzazione si basa sull'intervallo User Replicator. Completare la procedura seguente per verificare che la replica degli utenti sia stata completata prima di eseguire il cmdlet Move-CsUser.
ms.openlocfilehash: 12bb3c29f703287934358f331dc945830e318afb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244028"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="03e6b-107">Verificare che la replica degli utenti sia stata completata</span><span class="sxs-lookup"><span data-stu-id="03e6b-107">Verify user replication has completed</span></span>

<span data-ttu-id="03e6b-108">Quando si esegue il cmdlet **Move-CsUser** , potrebbe verificarsi un errore se le informazioni degli utenti tra servizi di dominio Active Directory e i database di Skype for Business Server 2019 non sono sincronizzate perché la replica iniziale è incompleta.</span><span class="sxs-lookup"><span data-stu-id="03e6b-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="03e6b-109">Il tempo necessario per completare correttamente la sincronizzazione iniziale di Skype for Business Server 2019, dipende dal numero di controller di dominio ospitati nella foresta di Active Directory che ospitano Skype for business Pool di server 2019.</span><span class="sxs-lookup"><span data-stu-id="03e6b-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="03e6b-110">Il processo di sincronizzazione iniziale di Skype for Business Server 2019 viene eseguito quando il server front end di Skype for Business Server 2019 è stato avviato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="03e6b-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="03e6b-111">In seguito, la sincronizzazione si basa sull'intervallo User Replicator.</span><span class="sxs-lookup"><span data-stu-id="03e6b-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="03e6b-112">Completare la procedura seguente per verificare che la replica dell'utente sia stata completata prima di eseguire il cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="03e6b-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="03e6b-113">Per verificare che la replica dell'utente sia stata completata</span><span class="sxs-lookup"><span data-stu-id="03e6b-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="03e6b-114">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="03e6b-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="03e6b-115">Fare clic sul menu **Start** e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="03e6b-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="03e6b-116">Immettere **eventvwr. exe**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03e6b-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="03e6b-117">Nel Visualizzatore eventi fare clic su **registri applicazioni e servizi** per espanderlo e quindi selezionare Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="03e6b-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="03e6b-118">Nel riquadro **azioni** fare clic su **Filtra log corrente**.</span><span class="sxs-lookup"><span data-stu-id="03e6b-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="03e6b-119">Nell'elenco **origini eventi** fare clic su **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="03e6b-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="03e6b-120">In \*\* \<tutti gli ID\>evento\*\*immettere **30024**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03e6b-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="03e6b-121">Nell'elenco eventi filtrati, nella scheda **generale** , cercare una voce che indica che la replica degli utenti è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="03e6b-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

