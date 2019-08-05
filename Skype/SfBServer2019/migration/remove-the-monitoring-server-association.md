---
title: Rimuovere l'associazione del server di monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Per rimuovere il server di monitoraggio, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195223"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="87f18-105">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="87f18-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="87f18-106">Per rimuovere il server di monitoraggio, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="87f18-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="87f18-107">Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="87f18-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="87f18-108">Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="87f18-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="87f18-109">Per rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="87f18-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="87f18-110">Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="87f18-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="87f18-111">Passare al nodo installazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="87f18-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="87f18-112">In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti**di succursale, a seconda di dove è definito il server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="87f18-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="87f18-113">Se si ha un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="87f18-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="87f18-114">Gli **elettrodomestici Survivable Branch** nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="87f18-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="87f18-115">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di monitoraggio e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="87f18-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="87f18-116">In **modifica proprietà**, in \*\*\*\* > **associazioni**generali, deselezionare la casella di controllo **Associa server di monitoraggio** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f18-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="87f18-117">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="87f18-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="87f18-118">Fare clic con il pulsante destro del mouse sul server di monitoraggio e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="87f18-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="87f18-119">In **eliminare gli archivi dipendenti**fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="87f18-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="87f18-120">Pubblicare la topologia, controllare lo stato di replica ed eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="87f18-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

