---
title: Rimuovere l'associazione del server di archiviazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Per rimuovere un server di archiviazione, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server. Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza. Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene visualizzato un avviso che l'oggetto archivio di database associato in Generatore di topologia verrà eliminata.
ms.openlocfilehash: d6d7b7f53f9997b17893db079090e1837ce77f4d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244428"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="cf578-105">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="cf578-105">Remove the Archiving server association</span></span>

<span data-ttu-id="cf578-106">Per rimuovere un server di archiviazione, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="cf578-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="cf578-107">Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="cf578-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="cf578-108">Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene segnalato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="cf578-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="cf578-109">Per rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="cf578-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="cf578-110">Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="cf578-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="cf578-111">Passare al nodo di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="cf578-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="cf578-112">In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti**di succursale, a seconda della posizione in cui è definito il server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cf578-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="cf578-113">Se si ha un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="cf578-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cf578-114">Gli **elettrodomestici Survivable Branch** nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="cf578-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="cf578-115">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cf578-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="cf578-116">In **modifica proprietà**, in \*\*\*\* > **associazioni**generali, deselezionare la casella di controllo **Associa server di archiviazione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf578-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="cf578-117">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="cf578-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="cf578-118">Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="cf578-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="cf578-119">In **eliminare gli archivi dipendenti**fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf578-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="cf578-120">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="cf578-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

