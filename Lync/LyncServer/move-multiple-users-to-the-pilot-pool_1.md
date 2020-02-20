---
title: Spostare più utenti nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf1f33a47a9a311a9e4b09c7c50190c2c864452
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="1c212-102">Spostare più utenti nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="1c212-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c212-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1c212-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1c212-104">È possibile spostare più utenti dal pool di Office Communications Server 2007 R2 al pool pilota di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1c212-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="1c212-105">Per spostare più utenti utilizzando il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c212-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="1c212-106">Aprire il **Pannello di controllo di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1c212-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="1c212-107">Nella scheda **Ricerca utenti** fare clic sul pulsante **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="1c212-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="1c212-108">Fare quindi clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="1c212-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="1c212-109">Creare un filtro in cui **l'utente di Office Communications Server** corrisponde a **True**.</span><span class="sxs-lookup"><span data-stu-id="1c212-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="1c212-110">Fare clic su **trova** per cercare gli utenti legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1c212-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="1c212-111">Selezionare due utenti che si desidera spostare nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c212-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="1c212-112">In questo esempio spostiamo gli utenti Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="1c212-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="1c212-113">![Elenco utenti visualizzato dalla ricerca di utenti OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Elenco utenti visualizzato dalla ricerca di utenti OCS")</span><span class="sxs-lookup"><span data-stu-id="1c212-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="1c212-114">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="1c212-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="1c212-115">Nell'elenco a discesa selezionare il pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c212-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="1c212-116">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="1c212-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="1c212-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="1c212-117">Click OK.</span></span>
    
    <span data-ttu-id="1c212-118">![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Finestra di dialogo Sposta utenti, pool di registrazione di destinazione")</span><span class="sxs-lookup"><span data-stu-id="1c212-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="1c212-119">Verificare che la colonna **pool di registrazione** per gli utenti contenga ora il pool Lync Server 2013, che indica che gli utenti sono stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1c212-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="1c212-120">Per spostare più utenti utilizzando Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="1c212-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="1c212-121">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1c212-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="1c212-122">Nella riga di comando digitare quanto segue e sostituire **User1** e **User2** con nomi utente specifici che si desidera spostare e sostituire **FQDN del\_pool** con il nome del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1c212-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="1c212-123">In questo esempio spostiamo gli utenti Hao Chen e Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="1c212-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="1c212-124">![Cmdlet di esempio per spostare un utente legacy](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Cmdlet di esempio per spostare un utente legacy")</span><span class="sxs-lookup"><span data-stu-id="1c212-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="1c212-125">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1c212-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="1c212-126">L'identità del **pool di registrazione** deve ora puntare al pool specificato come **FQDN\_del pool** nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1c212-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="1c212-127">La presenza di questa identità conferma che l'utente è stato correttamente spostato.</span><span class="sxs-lookup"><span data-stu-id="1c212-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="1c212-128">Ripetere il passaggio per verificare che **User2** sia stato spostato.</span><span class="sxs-lookup"><span data-stu-id="1c212-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="1c212-129">![Output del cmdlet Get-UsUser-Identity di PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output del cmdlet Get-UsUser-Identity di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="1c212-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="1c212-130">Per spostare tutti gli utenti contemporaneamente utilizzando Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="1c212-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="1c212-131">In questo esempio, tutti gli utenti sono stati restituiti al pool di Office Communications Server 2007 R2 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="1c212-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="1c212-132">Se si utilizza Lync Server 2013 Management Shell, tutti gli utenti verranno spostati contemporaneamente sul pool Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="1c212-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="1c212-133">Aprire **Lync Server 2013 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1c212-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="1c212-134">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1c212-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="1c212-135">![Cmdlet di esempio per spostare tutti gli utenti legacy in un pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Cmdlet di esempio per spostare tutti gli utenti legacy in un pool")</span><span class="sxs-lookup"><span data-stu-id="1c212-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="1c212-136">Eseguire quindi **Get-CsUser** per uno degli utenti pilota.</span><span class="sxs-lookup"><span data-stu-id="1c212-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="1c212-137">L'identità del **pool di registrazione** per ogni utente ora punta al pool specificato come "FQDN\_del pool" nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="1c212-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="1c212-138">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="1c212-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="1c212-139">Inoltre, è possibile visualizzare l'elenco di utenti nel pannello di controllo di Lync Server 2013 e verificare che il valore del pool di registrazione punti ora al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c212-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="1c212-140">![Elenco utenti del pannello di controllo di Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Elenco utenti del pannello di controllo di Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="1c212-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

