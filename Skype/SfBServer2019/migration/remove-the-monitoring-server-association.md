---
title: Rimuovere l'associazione del server di monitoraggio
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
description: Per rimuovere il Monitoring Server, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati. È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, si riceve una notifica che indica che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753418"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="7b976-105">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="7b976-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="7b976-106">Per rimuovere il Monitoring Server, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati.</span><span class="sxs-lookup"><span data-stu-id="7b976-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="7b976-107">È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="7b976-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="7b976-108">Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, si riceve una notifica che indica che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7b976-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="7b976-109">Per rimuovere l'associazione del Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="7b976-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="7b976-110">Nel Front End Server di Skype for Business Server 2019 aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7b976-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="7b976-111">Passare al nodo delle installazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="7b976-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="7b976-112">In Generatore di topologie espandere Pool **Enterprise Edition Front End,** **Standard Edition Front End Server** o siti di succursale, a seconda della posizione in cui è definito il Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="7b976-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="7b976-113">Se è associato un Survivable Branch Server, espandere Siti di succursale, espandere il nome del sito di succursale e quindi **espandere Survivable Branch Appliance.**</span><span class="sxs-lookup"><span data-stu-id="7b976-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7b976-114">**I Survivable Branch Appliance nell'interfaccia** utente si applicano sia al Survivable Branch Server che al Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="7b976-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="7b976-115">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al Monitoring Server e quindi scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="7b976-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="7b976-116">In **Modifica proprietà,** in **Associazioni**  >  **generali,** deselezionare la **casella di** controllo Associa Monitoring Server e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="7b976-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="7b976-117">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="7b976-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="7b976-118">Fare clic con il pulsante destro del mouse sul Monitoring Server e quindi scegliere **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="7b976-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="7b976-119">In **Elimina archivi dipendenti** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b976-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="7b976-120">Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata di Skype for Business Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7b976-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

