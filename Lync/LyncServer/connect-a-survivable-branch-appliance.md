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
ms.openlocfilehash: 5ef6294deba25998c5ad16254e464b6f682fa660
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="5189c-102">Connettere un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="5189c-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5189c-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5189c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5189c-104">Ogni Survivable Branch Appliance (SBA) è associato a un pool Front-end che funge da registrar di backup per l'SBA.</span><span class="sxs-lookup"><span data-stu-id="5189c-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="5189c-105">Quando il pool Front-end viene migrato a Lync Server 2013, l'SBA deve essere dissociato dal pool di front end di Lync Server 2010 mentre il pool viene aggiornato, dopo la migrazione del pool a Lync Server 2013, l'SBA può essere riassociato al pool Front-end aggiornato.</span><span class="sxs-lookup"><span data-stu-id="5189c-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="5189c-106">Si tratta di eliminare l'ASB dalla topologia legacy di Lync Server 2010 in Generatore di topologia e quindi aggiungere l'ASB alla topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5189c-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="5189c-107">Gli utenti ospitati nella SBA legacy Lync Server 2010 devono prima essere spostati in un altro pool Front-end prima di rimuovere l'SBA dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="5189c-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="5189c-108">Dopo aver aggiunto l'SBA alla topologia di Lync Server 2013, questi utenti possono quindi essere spostati di nuovo nella SBA.</span><span class="sxs-lookup"><span data-stu-id="5189c-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="5189c-109">Questi passaggi sono riepilogati di seguito:</span><span class="sxs-lookup"><span data-stu-id="5189c-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="5189c-110">Sposta gli utenti di Branch residenti nell'legacy SBA Lync Server 2010 in un altro pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="5189c-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="5189c-111">Rimuovere SBA dalla topologia legacy di Lync Server 2010 per disconnettere il pool Front end esistente come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="5189c-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="5189c-112">Aggiungere SBA alla topologia di Lync Server 2013 e configurare il nuovo pool Front-end come registrar di backup.</span><span class="sxs-lookup"><span data-stu-id="5189c-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="5189c-113">Trasferire gli utenti della filiale nel nuovo SBA di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5189c-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="5189c-114">**Aggiungere il sito della filiale di Lync Server 2010 SBA alla topologia**</span><span class="sxs-lookup"><span data-stu-id="5189c-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="5189c-115">Aprire **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="5189c-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="5189c-116">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **siti di succursale**e quindi scegliere **nuovo sito filiale**.</span><span class="sxs-lookup"><span data-stu-id="5189c-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="5189c-117">Nella finestra di dialogo **Definisci nuovo sito succursale** fare clic su **nome**e quindi digitare il nome del sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5189c-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="5189c-118">Opzionale Fare clic su **Descrizione**e quindi digitare una descrizione significativa per il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5189c-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="5189c-119">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5189c-119">Click **Next**.</span></span>

6.  <span data-ttu-id="5189c-120">Opzionale Nella finestra di dialogo **Definisci nuovo sito della filiale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5189c-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="5189c-121">Fare clic su **città**e quindi digitare il nome della città in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5189c-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="5189c-122">Fare clic su **stato/area geografica**e quindi digitare il nome dello stato o dell'area geografica in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5189c-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="5189c-123">Fare clic su **codice paese**e quindi digitare il codice di chiamata a due cifre per il paese/area geografica in cui si trova il sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="5189c-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="5189c-124">Fare clic su **Avanti**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5189c-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="5189c-125">Se si usa un server o un dispositivo Survivable Branch Lync 2010 in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per la procedura guidata** .</span><span class="sxs-lookup"><span data-stu-id="5189c-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="5189c-126">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="5189c-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="5189c-127">Per associare la SBA legacy di Lync Server 2010 al pool Front End di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="5189c-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="5189c-128">Espandere il sito della filiale che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="5189c-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="5189c-129">Fare clic con il pulsante destro del mouse su **Lync Server 2010** e quindi scegliere **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5189c-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="5189c-130">Fare clic su **Survivable Branch Appliance..** .</span><span class="sxs-lookup"><span data-stu-id="5189c-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="5189c-131">Seguire le indicazioni della procedura guidata visualizzata.</span><span class="sxs-lookup"><span data-stu-id="5189c-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="5189c-132">Per informazioni sugli elementi della procedura guidata, vedere [definire un Survivable Branch Appliance o un server in Lync server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="5189c-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5189c-133">Un Survivable Branch Appliance di Lync Server 2010 può essere associato solo a un archivio di monitoraggio di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5189c-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="5189c-134">Se non si usa un Survivable Branch Appliance o un server in questo sito, deselezionare la casella di controllo **Apri la nuova procedura guidata per** la procedura guidata e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="5189c-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="5189c-135">Ripetere i passaggi precedenti per ogni sito di filiale che si vuole aggiungere alla topologia.</span><span class="sxs-lookup"><span data-stu-id="5189c-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

