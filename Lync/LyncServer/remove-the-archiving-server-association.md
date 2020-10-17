---
title: Rimuovere l'associazione del server di archiviazione
description: Rimuovere l'associazione del server di archiviazione.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f6c34e49b0217a8318a83752b3878a7625e5d58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570222"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="1412d-103">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="1412d-103">Remove the Archiving server association</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1412d-104">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1412d-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="1412d-105">Per rimuovere un server di archiviazione, è necessario modificare o cancellare la dipendenza dal pool Front end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="1412d-105">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="1412d-106">È possibile modificare le proprietà del pool Front End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="1412d-106">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="1412d-107">Dopo aver cancellato la dipendenza e aver eliminato il server in Generatore di topologie, viene notificato che verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="1412d-107">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="1412d-108">Per rimuovere un'associazione a un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="1412d-108">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="1412d-109">Aprire Lync Server 2013 front end server, aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="1412d-109">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="1412d-110">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1412d-110">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="1412d-111">In Generatore di topologie espandere **pool Enterprise Edition front end**, **Standard Edition Front End Server**o **siti di succursale**, in base alla posizione in cui è definito il server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1412d-111">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="1412d-112">Se è presente un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito di succursale e quindi espandere **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="1412d-112">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1412d-113"><STRONG>Survivable Branch Appliance</STRONG> nell'interfaccia utente si applica sia a Survivable Branch Server che a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="1412d-113"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="1412d-114">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al server di archiviazione, quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1412d-114">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="1412d-115">In **Modifica proprietà**, **Generale**, **Associazioni** deselezionare la casella di controllo **Associa server di archiviazione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1412d-115">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="1412d-116">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al server di archiviazione che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1412d-116">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="1412d-117">Fare clic con il pulsante destro del mouse sul server di archiviazione e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1412d-117">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="1412d-118">In **Elimina archivi dipendenti** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1412d-118">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="1412d-119">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="1412d-119">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

