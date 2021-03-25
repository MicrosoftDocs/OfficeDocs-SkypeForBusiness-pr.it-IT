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
description: Ogni Survivable Branch Appliance (SBA) è associato a un pool Front End che funge da registrar di backup per l'SBA. Quando il pool Front End viene migrato a Skype for Business Server 2019, l'SBA deve essere disassociato dal pool Front End durante l'aggiornamento del pool, Dopo aver eseguito la migrazione del pool a Skype for Business Server 2019, l'SBA può essere nuovamente associato al pool Front End aggiornato. Ciò implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e quindi l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019. Gli utenti ospitati nell'SBA legacy devono prima essere spostati in un altro pool Front End prima di rimuovere l'SBA dalla topologia. Dopo aver aggiunto l'SBA alla topologia di Skype for Business Server 2019, questi utenti possono essere spostati di nuovo nell'SBA. La procedura è sintetizzata sotto.
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113342"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="dd605-108">Connettere un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="dd605-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="dd605-109">Ogni Survivable Branch Appliance (SBA) è associato a un pool Front End che funge da registrar di backup per l'SBA.</span><span class="sxs-lookup"><span data-stu-id="dd605-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="dd605-110">Quando il pool Front End viene migrato a Skype for Business Server 2019, l'SBA deve essere disassociato dal pool Front End durante l'aggiornamento del pool.</span><span class="sxs-lookup"><span data-stu-id="dd605-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="dd605-111">Dopo la migrazione del pool a Skype for Business Server 2019, l'SBA può essere nuovamente associato al pool Front End aggiornato.</span><span class="sxs-lookup"><span data-stu-id="dd605-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="dd605-112">Ciò implica l'eliminazione dell'SBA dalla topologia legacy in Generatore di topologie e quindi l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dd605-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="dd605-113">Gli utenti ospitati nell'SBA legacy devono prima essere spostati in un altro pool Front End prima di rimuovere l'SBA dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="dd605-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="dd605-114">Dopo l'aggiunta dell'SBA alla topologia di Skype for Business Server 2019, tali utenti possono essere spostati di nuovo nell'SBA.</span><span class="sxs-lookup"><span data-stu-id="dd605-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="dd605-115">La procedura è sintetizzata sotto.</span><span class="sxs-lookup"><span data-stu-id="dd605-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="dd605-116">Spostare gli utenti di succursale ospitati nell'SBA legacy in un altro pool Front End.</span><span class="sxs-lookup"><span data-stu-id="dd605-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="dd605-117">Rimuovere SBA dalla topologia legacy per disconnettere il pool Front End esistente come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="dd605-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="dd605-118">Aggiungere SBA alla topologia di Skype for Business Server 2019 e configurare questo nuovo pool Front End come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="dd605-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="dd605-119">Spostare gli utenti di succursale nel nuovo Skype for Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="dd605-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="dd605-120">Aggiungere un sito di succursale SBA legacy alla topologia</span><span class="sxs-lookup"><span data-stu-id="dd605-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="dd605-121">Aprire **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="dd605-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="dd605-122">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **Siti di succursale** e quindi scegliere **Nuovo sito di succursale.**</span><span class="sxs-lookup"><span data-stu-id="dd605-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="dd605-123">Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="dd605-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="dd605-124">(Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="dd605-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="dd605-125">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="dd605-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="dd605-126">(Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd605-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="dd605-127">Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="dd605-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="dd605-128">Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="dd605-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="dd605-129">Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="dd605-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="dd605-130">Fare **clic** su Avanti e quindi, se si utilizza un Survivable Branch Appliance o un Server in questo sito, deselezionare la casella di controllo Apri il Nuovo **Survivable Wizard** alla chiusura della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="dd605-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="dd605-131">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="dd605-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="dd605-132">Per associare l'SBA legacy al pool Front End di Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="dd605-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="dd605-133">Espandere il sito di succursale che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="dd605-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="dd605-134">Fare clic con il pulsante destro del mouse sulla versione legacy e quindi scegliere **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="dd605-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="dd605-135">Fare **clic su Survivable Branch Appliance.**</span><span class="sxs-lookup"><span data-stu-id="dd605-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="dd605-136">Seguire le istruzioni nella procedura guidata visualizzata.</span><span class="sxs-lookup"><span data-stu-id="dd605-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="dd605-137">Per informazioni sugli elementi della procedura guidata, vedere</span><span class="sxs-lookup"><span data-stu-id="dd605-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="dd605-138">Un Survivable Branch Appliance può essere associato solo a un archivio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="dd605-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="dd605-139">Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="dd605-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="dd605-140">Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="dd605-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
