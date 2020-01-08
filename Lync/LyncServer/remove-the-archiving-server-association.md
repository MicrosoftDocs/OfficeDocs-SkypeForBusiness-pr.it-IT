---
title: Rimuovere l'associazione del server di archiviazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="5956e-102">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5956e-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5956e-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="5956e-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="5956e-104">Per rimuovere un server di archiviazione, è necessario modificare o deselezionare la dipendenza dal pool Front-end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="5956e-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="5956e-105">Si modificano le proprietà del pool Front-End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="5956e-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="5956e-106">Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologia, viene visualizzato un avviso che l'oggetto archivio di database associato in Generatore di topologia verrà eliminata.</span><span class="sxs-lookup"><span data-stu-id="5956e-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="5956e-107">Per rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5956e-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="5956e-108">Aprire il server front-end di Lync Server 2013, aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="5956e-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="5956e-109">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5956e-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="5956e-110">In Generatore di topologie espandere i **pool Front End di Enterprise Edition**, i **server front-end Standard Edition**o i **siti di succursale**in base alla posizione in cui è definito il server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5956e-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="5956e-111">Se si ha un Survivable Branch Server associato, espandere **siti di succursale**, espandere il nome del sito della filiale e quindi espandere **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="5956e-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5956e-112">Gli <STRONG>elettrodomestici Survivable Branch</STRONG> nell'interfaccia utente si applicano sia a Survivable Branch Server che Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5956e-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="5956e-113">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5956e-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="5956e-114">In **modifica proprietà**, in **generale**, in **associazioni**deselezionare la casella di controllo **Associa server di archiviazione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5956e-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="5956e-115">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="5956e-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="5956e-116">Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="5956e-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="5956e-117">In **eliminare gli archivi dipendenti**fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5956e-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="5956e-118">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5956e-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

