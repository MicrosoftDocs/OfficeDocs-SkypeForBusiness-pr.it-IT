---
title: 'Lync Server 2013: Appendice B: gestione di un Survivable Branch Appliance'
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
ms.openlocfilehash: 27975119b9e54b96ba7472ce1e60d64a51671c5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="15d4c-102">Appendice B: gestione di un Survivable Branch Appliance in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d4c-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15d4c-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="15d4c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="15d4c-104">In questo argomento vengono descritte le procedure per la gestione di un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="15d4c-105">In particolare, come sostituire e rinominare un Survivable Branch Appliance e come modificare il pool Lync Server 2013 front end a cui è associato il Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="15d4c-106">Per sostituire un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="15d4c-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="15d4c-107">Arrestare tutti i servizi di Lync Server 2013 nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="15d4c-108">A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="15d4c-109">Consigliato Rimuovere il Survivable Branch Appliance dal dominio.</span><span class="sxs-lookup"><span data-stu-id="15d4c-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="15d4c-110">Eliminare l'oggetto computer Survivable Branch Appliance in servizi di dominio Active Directory attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="15d4c-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="15d4c-111">Eseguire l'accesso a un server membro come membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="15d4c-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="15d4c-112">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="15d4c-113">Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="15d4c-114">Aggiungere di nuovo l'oggetto computer Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="15d4c-115">Per ulteriori informazioni, vedere [aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).</span><span class="sxs-lookup"><span data-stu-id="15d4c-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="15d4c-116">Attendere che venga eseguita la replica di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="15d4c-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="15d4c-117">Aprire Lync Server Management Shell e digitare **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="15d4c-118">Connettere il nuovo Survivable Branch Appliance alla rete e seguire i passaggi illustrati in [Deploying a Survivable Branch Appliance or Server with Lync server 2013-Central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="15d4c-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="15d4c-119">Per rinominare un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="15d4c-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="15d4c-120">Spostare gli utenti nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="15d4c-120">Move users to the central site.</span></span> <span data-ttu-id="15d4c-121">Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="15d4c-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="15d4c-122">Arrestare tutti i servizi di Lync Server 2013 nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="15d4c-123">A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="15d4c-124">Rimuovere il Survivable Branch Appliance dalla topologia, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="15d4c-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="15d4c-125">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="15d4c-126">Nell'albero della console espandere **siti di succursale**, fare clic sul Survivable Branch Appliance, quindi fare clic su **Elimina** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="15d4c-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="15d4c-127">Rimuovere il Survivable Branch Appliance dal dominio.</span><span class="sxs-lookup"><span data-stu-id="15d4c-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="15d4c-128">Eliminare l'oggetto computer Survivable Branch Appliance in Active Directory, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="15d4c-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="15d4c-129">Eseguire l'accesso a un controller di dominio come membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="15d4c-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="15d4c-130">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="15d4c-131">Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="15d4c-132">Ripristinare il Survivable Branch Appliance in Factory Defaults.</span><span class="sxs-lookup"><span data-stu-id="15d4c-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="15d4c-133">A tale scopo, vedere la documentazione del fornitore del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="15d4c-134">Seguire la procedura illustrata in [Deploying a Survivable Branch Appliance or Server with Lync server 2013-Central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="15d4c-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="15d4c-135">Spostare gli utenti nel Survivable Branch Appliance rinominato.</span><span class="sxs-lookup"><span data-stu-id="15d4c-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="15d4c-136">Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="15d4c-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="15d4c-137">Per cambiare il pool Front End di Lync Server a cui è associato il Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="15d4c-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="15d4c-138">Spostare gli utenti dal Survivable Branch Appliance al pool Front End di Lync Server nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="15d4c-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="15d4c-139">Per informazioni dettagliate, vedere [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="15d4c-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="15d4c-140">Arrestare tutti i servizi di Lync Server nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="15d4c-141">(Vedere la documentazione del fornitore di Survivable Branch Appliance).</span><span class="sxs-lookup"><span data-stu-id="15d4c-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="15d4c-142">Aggiornare il pool Front End di Lync Server a cui è associato il Survivable Branch Appliance, attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="15d4c-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="15d4c-143">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server** e quindi **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="15d4c-144">Espandere **Siti di succursale**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="15d4c-145">Fare clic con il pulsante destro del mouse sull'oggetto Survivable Branch Appliance da modificare e quindi scegliere **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="15d4c-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="15d4c-146">In resilienza selezionare il nuovo pool Front end a cui deve essere associato il Survivable Branch Appliance, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="15d4c-147">Nell'albero della console fare clic con il pulsante destro del mouse sul nuovo Survivable Branch Appliance, scegliere **topologia**e quindi fare clic su **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="15d4c-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="15d4c-148">Riavviare tutti i servizi di Lync Server nel Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="15d4c-149">Testare il Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="15d4c-150">Per informazioni dettagliate, vedere [Home Users on a Survivable Branch Appliance or server in Lync server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="15d4c-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="15d4c-151">Spostare gli utenti dal pool Front End di Lync Server nel sito centrale a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="15d4c-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

