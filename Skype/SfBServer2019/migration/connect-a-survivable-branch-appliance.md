---
title: Connettere un Survivable Branch Appliance
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
description: Ogni Survivable Branch Appliance (SBA) è associato a un pool Front end che funge da registrar di backup per la SBA. Quando si esegue la migrazione del pool Front end su Skype for Business Server 2019, è necessario che l'SBA sia dissociata dal pool Front end quando il pool viene aggiornato, una volta che il pool è stato migrato su Skype for Business Server 2019, l'SBA può essere riassociato al pool Front end aggiornato. Questo implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019. Gli utenti ospitati nell'ASB legacy devono essere prima spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia di Skype for Business Server 2019, gli utenti possono quindi essere spostati di nuovo nell'ASB. La procedura è sintetizzata sotto.
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751548"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="ce29f-108">Connettere un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="ce29f-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="ce29f-109">Ogni Survivable Branch Appliance (SBA) è associato a un pool Front end che funge da registrar di backup per la SBA.</span><span class="sxs-lookup"><span data-stu-id="ce29f-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="ce29f-110">Quando si esegue la migrazione del pool Front end in Skype for Business Server 2019, è necessario che l'SBA sia dissociata dal pool Front end mentre il pool viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ce29f-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="ce29f-111">Dopo la migrazione del pool a Skype for Business Server 2019, l'SBA può essere riassociato al pool Front end aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ce29f-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="ce29f-112">Questo implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ce29f-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="ce29f-113">Gli utenti ospitati nell'ASB legacy devono essere prima spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="ce29f-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="ce29f-114">Dopo aver aggiunto la SBA alla topologia di Skype for Business Server 2019, gli utenti possono essere spostati di nuovo nell'ASB.</span><span class="sxs-lookup"><span data-stu-id="ce29f-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="ce29f-115">La procedura è sintetizzata sotto.</span><span class="sxs-lookup"><span data-stu-id="ce29f-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="ce29f-116">Spostare gli utenti di succursale nell'ASB legacy in un altro pool Front end.</span><span class="sxs-lookup"><span data-stu-id="ce29f-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="ce29f-117">Rimuovere SBA dalla topologia legacy per disconnettere il pool Front end esistente come un servizio di registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="ce29f-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="ce29f-118">Aggiungere SBA alla topologia di Skype for Business Server 2019 e configurare questo nuovo pool Front end come registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="ce29f-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="ce29f-119">Spostare gli utenti di succursale nel nuovo SBA di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ce29f-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="ce29f-120">Aggiungere un sito di succursale SBA legacy alla topologia</span><span class="sxs-lookup"><span data-stu-id="ce29f-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="ce29f-121">Aprire **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="ce29f-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="ce29f-122">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **siti di succursale**e quindi scegliere **nuovo sito di succursale**.</span><span class="sxs-lookup"><span data-stu-id="ce29f-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="ce29f-123">Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="ce29f-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="ce29f-124">(Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="ce29f-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="ce29f-125">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ce29f-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="ce29f-126">(Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce29f-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="ce29f-127">Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="ce29f-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="ce29f-128">Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="ce29f-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="ce29f-129">Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="ce29f-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="ce29f-130">Fare clic su **Avanti**e quindi, se si utilizza un Survivable Branch Appliance o server in questo sito, deselezionare la casella di controllo **aprire la procedura guidata nuovo Survivable Wizard quando la procedura guidata viene chiusa** .</span><span class="sxs-lookup"><span data-stu-id="ce29f-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="ce29f-131">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ce29f-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="ce29f-132">Per associare l'ASB legacy al pool Front End di Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="ce29f-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="ce29f-133">Espandere il sito di succursale che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="ce29f-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="ce29f-134">Fare clic con il pulsante destro del mouse sulla versione legacy e quindi scegliere **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ce29f-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="ce29f-135">Fare clic su **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="ce29f-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="ce29f-136">Seguire le istruzioni nella procedura guidata visualizzata.</span><span class="sxs-lookup"><span data-stu-id="ce29f-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="ce29f-137">Per informazioni sugli elementi della procedura guidata, vedere</span><span class="sxs-lookup"><span data-stu-id="ce29f-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="ce29f-138">Un Survivable Branch Appliance può essere associato solo a un archivio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="ce29f-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="ce29f-139">Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ce29f-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="ce29f-140">Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="ce29f-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

