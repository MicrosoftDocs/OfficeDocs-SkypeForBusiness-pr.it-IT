---
title: Rimuovere l'associazione del server di monitoraggio
description: Rimuovere l'associazione di Monitoring Server.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 852ea72f814d33022012bf565af9bc5f73e06956
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545862"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="85302-103">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="85302-103">Remove the Monitoring server association</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85302-104">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="85302-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="85302-105">Per rimuovere il Monitoring Server, è necessario modificare o cancellare la dipendenza dal pool Front end associato, Front End Server, Survivable Branch Appliance e Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="85302-105">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="85302-106">È possibile modificare le proprietà del pool Front End, Front End Server, Survivable Branch Appliance e Survivable Branch Server per rimuovere la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="85302-106">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="85302-107">Dopo aver cancellato la dipendenza ed eliminato il server in Generatore di topologie, verrà eliminato anche l'oggetto archivio database associato in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="85302-107">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="85302-108">Per rimuovere l'associazione del Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="85302-108">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="85302-109">Aprire Lync Server 2013 front end server, aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="85302-109">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="85302-110">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="85302-110">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="85302-111">In Generatore di topologie espandere **pool Enterprise Edition front end**, **Standard Edition Front End Server**o **siti di succursale**, in base alla posizione in cui è definito il Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="85302-111">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="85302-112">Se è presente un Survivable Branch Server associato, espandere **siti**di succursale, espandere il nome del sito di succursale e quindi espandere **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="85302-112">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85302-113"><STRONG>Survivable Branch Appliance</STRONG> nell'interfaccia utente si applica sia a Survivable Branch Server che a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="85302-113"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="85302-114">Fare clic con il pulsante destro del mouse sul pool, sul server o sul dispositivo associato al Monitoring Server e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="85302-114">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="85302-115">In **Modifica proprietà**, in **Generale**, in **Associazioni**, deselezionare la casella di controllo **Associa Monitoring Server** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="85302-115">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="85302-116">Ripetere il passaggio precedente per qualsiasi altro pool, server o dispositivo associato al Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="85302-116">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="85302-117">Fare clic con il pulsante destro del mouse su Monitoring Server e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="85302-117">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="85302-118">In **Elimina archivi dipendenti** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="85302-118">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="85302-119">Pubblicare la topologia, controllare lo stato della replica ed eseguire la distribuzione guidata di Lync Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="85302-119">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

