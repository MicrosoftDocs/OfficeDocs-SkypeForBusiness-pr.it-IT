---
title: Rimuovere l'associazione del server di monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Per rimuovere il server di monitoraggio, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.
ms.openlocfilehash: aed16d60fbdae2413cb7890e38895bf6930cd4fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812864"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="bbd62-105">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="bbd62-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="bbd62-106">Per rimuovere il server di monitoraggio, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="bbd62-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="bbd62-107">Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="bbd62-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="bbd62-108">Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="bbd62-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="bbd62-109">Per rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="bbd62-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="bbd62-110">Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="bbd62-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="bbd62-111">Passare al nodo installazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="bbd62-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="bbd62-112">In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti di succursale**, a seconda di dove è definito il server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="bbd62-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="bbd62-113">Se si ha un Survivable Branch Server associato, espandere **siti di succursale**, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="bbd62-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bbd62-114">Gli **elettrodomestici Survivable Branch** nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="bbd62-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="bbd62-115">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di monitoraggio e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bbd62-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="bbd62-116">In **modifica proprietà**, in \*\*\*\* > **associazioni**generali, deselezionare la casella di controllo **Associa server di monitoraggio** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbd62-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="bbd62-117">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="bbd62-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="bbd62-118">Fare clic con il pulsante destro del mouse sul server di monitoraggio e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="bbd62-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="bbd62-119">In **eliminare gli archivi dipendenti**fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbd62-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="bbd62-120">Pubblicare la topologia, controllare lo stato di replica ed eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="bbd62-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

