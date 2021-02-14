---
title: Rimuovere l'associazione del server di archiviazione
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
description: Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati. È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, viene notificato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752138"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="05f14-105">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05f14-105">Remove the Archiving server association</span></span>

<span data-ttu-id="05f14-106">Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front End, dal Front End Server, dal Survivable Branch Appliance e dal Survivable Branch Server associati.</span><span class="sxs-lookup"><span data-stu-id="05f14-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="05f14-107">È possibile modificare le proprietà del pool Front End, del Front End Server, del Survivable Branch Appliance e del Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="05f14-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="05f14-108">Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, si riceve una notifica che indica che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="05f14-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="05f14-109">Per rimuovere un'associazione a un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="05f14-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="05f14-110">Nel Front End Server di Skype for Business Server 2019 aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="05f14-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="05f14-111">Passare al nodo di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="05f14-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="05f14-112">In Generatore di topologie espandere Pool **Enterprise Edition Front End,** **Standard Edition Front End Server** o siti di succursale, a seconda della posizione in cui è definito il server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="05f14-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="05f14-113">Se è associato un Survivable Branch Server, espandere Siti di succursale, espandere il nome del sito di succursale e quindi **espandere Survivable Branch Appliance.**</span><span class="sxs-lookup"><span data-stu-id="05f14-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="05f14-114">**I Survivable Branch Appliance nell'interfaccia** utente si applicano sia al Survivable Branch Server che al Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="05f14-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="05f14-115">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione e quindi scegliere **Modifica proprietà.**</span><span class="sxs-lookup"><span data-stu-id="05f14-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="05f14-116">In **Modifica proprietà,** in **Associazioni generali,** deselezionare la casella di controllo Associa server  >   **di** archiviazione e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="05f14-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="05f14-117">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="05f14-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="05f14-118">Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="05f14-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="05f14-119">In **Elimina archivi dipendenti** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="05f14-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="05f14-120">Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata di Skype for Business Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="05f14-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

