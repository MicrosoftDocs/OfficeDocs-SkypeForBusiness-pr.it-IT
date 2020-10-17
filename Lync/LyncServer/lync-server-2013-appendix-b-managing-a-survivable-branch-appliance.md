---
title: 'Lync Server 2013: Appendice B: gestione di un Survivable Branch Appliance'
description: 'Lync Server 2013: Appendice B: gestione di un Survivable Branch Appliance.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e66d97f538ee751d7bf12b0d0f70ff3a3f5576b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561832"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="6a74a-103">Appendice B: gestione di un Survivable Branch Appliance in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a74a-103">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a74a-104">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6a74a-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6a74a-105">In questo argomento vengono descritte le procedure per la gestione di un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-105">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="6a74a-106">In particolare, come sostituire e rinominare un Survivable Branch Appliance e come modificare il pool Lync Server 2013 front end a cui è associato il Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-106">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="6a74a-107">Per sostituire un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="6a74a-107">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="6a74a-108">Arrestare tutti i servizi di Lync Server 2013 nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-108">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="6a74a-109">A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-109">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="6a74a-110">Consigliato Rimuovere il Survivable Branch Appliance dal dominio.</span><span class="sxs-lookup"><span data-stu-id="6a74a-110">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="6a74a-111">Eliminare l'oggetto computer Survivable Branch Appliance in servizi di dominio Active Directory attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="6a74a-111">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="6a74a-112">Eseguire l'accesso a un server membro come membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="6a74a-112">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="6a74a-113">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-113">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="6a74a-114">Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-114">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="6a74a-115">Aggiungere di nuovo l'oggetto computer Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-115">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="6a74a-116">Per ulteriori informazioni, vedere [aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).</span><span class="sxs-lookup"><span data-stu-id="6a74a-116">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="6a74a-117">Attendere che venga eseguita la replica di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a74a-117">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="6a74a-118">Aprire Lync Server Management Shell e digitare **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-118">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="6a74a-119">Connettere il nuovo Survivable Branch Appliance alla rete e seguire i passaggi illustrati in [Deploying a Survivable Branch Appliance or Server with Lync server 2013-Central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="6a74a-119">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="6a74a-120">Per rinominare un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="6a74a-120">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="6a74a-121">Spostare gli utenti nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="6a74a-121">Move users to the central site.</span></span> <span data-ttu-id="6a74a-122">Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="6a74a-122">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="6a74a-123">Arrestare tutti i servizi di Lync Server 2013 nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-123">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="6a74a-124">A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-124">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="6a74a-125">Rimuovere il Survivable Branch Appliance dalla topologia, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="6a74a-125">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="6a74a-126">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="6a74a-127">Nell'albero della console espandere **siti di succursale**, fare clic sul Survivable Branch Appliance, quindi fare clic su **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="6a74a-127">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="6a74a-128">Rimuovere il Survivable Branch Appliance dal dominio.</span><span class="sxs-lookup"><span data-stu-id="6a74a-128">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="6a74a-129">Eliminare l'oggetto computer Survivable Branch Appliance in Active Directory, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="6a74a-129">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="6a74a-130">Eseguire l'accesso a un controller di dominio come membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="6a74a-130">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="6a74a-131">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-131">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="6a74a-132">Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-132">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="6a74a-133">Ripristinare il Survivable Branch Appliance in Factory Defaults.</span><span class="sxs-lookup"><span data-stu-id="6a74a-133">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="6a74a-134">A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-134">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="6a74a-135">Seguire la procedura illustrata in [Deploying a Survivable Branch Appliance or Server with Lync server 2013-Central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="6a74a-135">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="6a74a-136">Spostare gli utenti nel Survivable Branch Appliance rinominato.</span><span class="sxs-lookup"><span data-stu-id="6a74a-136">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="6a74a-137">Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="6a74a-137">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="6a74a-138">Per cambiare il pool Front End di Lync Server a cui è associato il Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="6a74a-138">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="6a74a-139">Spostare gli utenti dal Survivable Branch Appliance al pool Front End di Lync Server nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="6a74a-139">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="6a74a-140">Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="6a74a-140">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="6a74a-141">Arrestare tutti i servizi di Lync Server nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-141">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="6a74a-142">(Vedere la documentazione del fornitore di Survivable Branch Appliance).</span><span class="sxs-lookup"><span data-stu-id="6a74a-142">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="6a74a-143">Aggiornare il pool Front End di Lync Server a cui è associato il Survivable Branch Appliance, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="6a74a-143">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="6a74a-144">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-144">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="6a74a-145">Espandere **Siti di succursale**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-145">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="6a74a-146">Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance da modificare e quindi scegliere **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="6a74a-146">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="6a74a-147">In resilienza selezionare il nuovo pool Front end a cui deve essere associato il Survivable Branch Appliance, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-147">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="6a74a-148">Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo Survivable Branch Appliance, scegliere **topologia**e quindi fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="6a74a-148">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="6a74a-149">Riavviare tutti i servizi di Lync Server nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-149">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="6a74a-150">Testare il Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-150">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="6a74a-151">Per informazioni dettagliate, vedere [Home Users on a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="6a74a-151">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="6a74a-152">Spostare gli utenti dal pool Front End di Lync Server nel sito centrale a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="6a74a-152">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

