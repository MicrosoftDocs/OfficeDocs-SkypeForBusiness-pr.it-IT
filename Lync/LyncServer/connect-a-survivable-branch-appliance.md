---
title: Connettere un Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77382343fa7736c90ac208f8d13f81bc74969efa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="db23c-102">Connettere un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="db23c-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db23c-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="db23c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="db23c-104">Ogni Survivable Branch Appliance (SBA) è associato a un pool Front end che funge da registrar di backup per la SBA.</span><span class="sxs-lookup"><span data-stu-id="db23c-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="db23c-105">Quando si esegue la migrazione del pool Front end in Lync Server 2013, è necessario che l'SBA sia dissociata dal pool Front end Lync Server 2010 mentre il pool viene aggiornato, una volta che il pool è stato migrato a Lync Server 2013, l'SBA può essere riassociato al pool Front end aggiornato.</span><span class="sxs-lookup"><span data-stu-id="db23c-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="db23c-106">Si tratta di eliminare l'ASB dalla topologia di Lync Server 2010 legacy in Generatore di topologie e quindi di aggiungere l'SBA alla topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db23c-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="db23c-107">Gli utenti ospitati nell'ASB legacy di Lync Server 2010 devono essere prima spostati in un altro pool Front end prima di rimuovere la SBA dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="db23c-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="db23c-108">Dopo aver aggiunto l'SBA alla topologia di Lync Server 2013, gli utenti possono quindi essere spostati di nuovo nell'ASB.</span><span class="sxs-lookup"><span data-stu-id="db23c-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="db23c-109">La procedura è sintetizzata sotto.</span><span class="sxs-lookup"><span data-stu-id="db23c-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="db23c-110">Spostare gli utenti di succursale nell'legacy SBA Lync Server 2010 in un altro pool Front end.</span><span class="sxs-lookup"><span data-stu-id="db23c-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="db23c-111">Rimuovere SBA dalla topologia di Lync Server 2010 legacy per disconnettere il pool Front end esistente come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="db23c-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="db23c-112">Aggiungere SBA alla topologia di Lync Server 2013 e configurare questo nuovo pool Front end come registrazione di backup.</span><span class="sxs-lookup"><span data-stu-id="db23c-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="db23c-113">Spostare gli utenti di succursale nella nuova SBA di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db23c-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="db23c-114">**Aggiungere il sito di succursale del Survivable Branch Appliance di Lync Server 2010 alla topologia**</span><span class="sxs-lookup"><span data-stu-id="db23c-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="db23c-115">Aprire **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="db23c-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="db23c-116">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **Siti di succursale** e quindi fare clic su **Nuovo sito di succursale**.</span><span class="sxs-lookup"><span data-stu-id="db23c-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="db23c-117">Nella finestra di dialogo **Definisci nuovo sito di succursale** fare clic su **Nome** e quindi digitare il nome del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db23c-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="db23c-118">(Facoltativo) Fare clic su **Descrizione** e quindi digitare una descrizione significativa del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db23c-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="db23c-119">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="db23c-119">Click **Next**.</span></span>

6.  <span data-ttu-id="db23c-120">(Facoltativo) Nella successiva finestra di dialogo **Definisci nuovo sito di succursale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db23c-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="db23c-121">Fare clic su **Città** e quindi digitare il nome della città in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db23c-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="db23c-122">Fare clic su **Paese** e quindi digitare il nome del paese in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db23c-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="db23c-123">Fare clic su **Codice paese** e quindi digitare il codice di chiamata in due cifre per il paese/area geografica in cui si trova il sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="db23c-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="db23c-124">Fare clic su **Avanti** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db23c-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="db23c-p102">Se nel sito si utilizza un Survivable Branch Appliance o un Survivable Branch Server di Lync 2010, deselezionare l'opzione **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="db23c-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="db23c-127">Per associare la SBA legacy Lync Server 2010 al pool Front End di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="db23c-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="db23c-128">Espandere il sito di succursale che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="db23c-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="db23c-129">Fare clic con il pulsante destro del mouse su **Lync Server 2010** e quindi scegliere **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="db23c-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="db23c-130">Fare clic su **Survivable Branch Appliance…**</span><span class="sxs-lookup"><span data-stu-id="db23c-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="db23c-131">Seguire le istruzioni nella procedura guidata visualizzata.</span><span class="sxs-lookup"><span data-stu-id="db23c-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="db23c-132">Per informazioni sugli elementi della procedura guidata, vedere [define a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="db23c-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db23c-133">Un Survivable Branch Appliance di Lync Server 2010 può essere associato solo a un archivio di monitoraggio di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="db23c-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="db23c-134">Se nel sito non si utilizza un Survivable Branch Appliance o un Survivable Branch Server, deselezionare la casella di controllo **Aprire la procedura guidata Nuovo Survivable Branch Appliance al termine di questa procedura guidata** e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="db23c-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="db23c-135">Ripetere i passaggi precedenti per ogni sito di succursale che si desidera aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="db23c-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

