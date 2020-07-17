---
title: Spostare più utenti nel pool pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a5a92b0438e72be0ecb5acaa1b8e1886768ad59
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="3e4d4-102">Spostare più utenti nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="3e4d4-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e4d4-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3e4d4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3e4d4-104">È possibile spostare più utenti dal pool Lync Server 2010 al pool pilota di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="3e4d4-105">Per spostare più utenti utilizzando il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e4d4-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="3e4d4-106">Aprire il **Pannello di controllo di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="3e4d4-107">Fare clic su **Utenti**, su Cerca e quindi su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="3e4d4-108">Selezionare due utenti che si desidera spostare nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="3e4d4-109">In questo esempio spostiamo gli utenti Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="3e4d4-110">![Spostare gli utenti in un pool di registri specifico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Spostare gli utenti in un pool di registri specifico")</span><span class="sxs-lookup"><span data-stu-id="3e4d4-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="3e4d4-111">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="3e4d4-112">Nell'elenco a discesa selezionare il pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="3e4d4-113">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="3e4d4-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-114">Click OK.</span></span>
    
    <span data-ttu-id="3e4d4-115">![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Finestra di dialogo Sposta utenti, pool di registrazione di destinazione")</span><span class="sxs-lookup"><span data-stu-id="3e4d4-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="3e4d4-116">Verificare che la colonna **pool di registrazione** per gli utenti contenga ora il pool Lync Server 2013, che indica che gli utenti sono stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="3e4d4-117">Per spostare più utenti utilizzando Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="3e4d4-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="3e4d4-118">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="3e4d4-119">Nella riga di comando digitare quanto segue e sostituire **User1** e **User2** con nomi utente specifici che si desidera spostare e sostituire \*\* \_ FQDN del pool\*\* con il nome del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="3e4d4-120">In questo esempio spostiamo gli utenti Hao Chen e Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="3e4d4-121">![Esempio di cmdlet Get-CsUser di PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Esempio di cmdlet Get-CsUser di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="3e4d4-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="3e4d4-122">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3e4d4-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="3e4d4-123">L'identità del **pool di registrazione** deve ora puntare al pool specificato come \*\* \_ FQDN del pool\*\* nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="3e4d4-124">La presenza di questa identità conferma che l'utente è stato correttamente spostato.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="3e4d4-125">Ripetere il passaggio per verificare che **User2** sia stato spostato.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="3e4d4-126">![Output del cmdlet Get-UsUser-Identity di PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output del cmdlet Get-UsUser-Identity di PowerShell")</span><span class="sxs-lookup"><span data-stu-id="3e4d4-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="3e4d4-127">Per spostare tutti gli utenti contemporaneamente utilizzando Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="3e4d4-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="3e4d4-128">In questo esempio, tutti gli utenti sono stati restituiti al pool di Lync Server 2010 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="3e4d4-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="3e4d4-129">Se si utilizza Lync Server 2013 Management Shell, tutti gli utenti verranno spostati contemporaneamente sul pool Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="3e4d4-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="3e4d4-130">Aprire **Lync Server 2013 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="3e4d4-131">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e4d4-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="3e4d4-132">![Cmdlet di PowerShell e risultati in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet di PowerShell e risultati in Management Shell")</span><span class="sxs-lookup"><span data-stu-id="3e4d4-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="3e4d4-133">Eseguire quindi **Get-CsUser** per uno degli utenti pilota.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="3e4d4-134">L'identità del **pool di registrazione** per ogni utente ora punta al pool specificato come "FQDN del pool \_ " nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="3e4d4-135">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="3e4d4-136">Inoltre, è possibile visualizzare l'elenco di utenti nel pannello di controllo di Lync Server 2013 e verificare che il valore del pool di registrazione punti ora al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e4d4-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="3e4d4-137">![Elenco utenti del pannello di controllo di Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Elenco utenti del pannello di controllo di Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="3e4d4-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

