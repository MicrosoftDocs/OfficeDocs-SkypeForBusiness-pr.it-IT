---
title: Trasferire più utenti nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="e31eb-102">Trasferire più utenti nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="e31eb-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e31eb-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e31eb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e31eb-104">È possibile trasferire più utenti dal pool di Lync Server 2010 al pool di piloti di Lync Server 2013 usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e31eb-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="e31eb-105">Per trasferire più utenti tramite il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e31eb-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="e31eb-106">Aprire il **Pannello di controllo di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e31eb-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="e31eb-107">Fare clic su **utenti**, fare clic su Cerca e quindi su **trova**.</span><span class="sxs-lookup"><span data-stu-id="e31eb-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="e31eb-108">Selezionare due utenti che si desidera trasferire nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e31eb-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="e31eb-109">In questo esempio verranno spostati gli utenti Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="e31eb-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="e31eb-110">![Trasferire gli utenti in un pool di registri specifico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "per trasferire gli utenti in un pool di registri specifico")</span><span class="sxs-lookup"><span data-stu-id="e31eb-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="e31eb-111">Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="e31eb-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="e31eb-112">Nell'elenco a discesa selezionare il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e31eb-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="e31eb-113">Fare clic su **azione** e quindi su **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="e31eb-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="e31eb-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e31eb-114">Click OK.</span></span>
    
    <span data-ttu-id="e31eb-115">![Trasferire utenti, finestra di dialogo pool di registrar di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ", finestra di dialogo pool Registrar di destinazione")</span><span class="sxs-lookup"><span data-stu-id="e31eb-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="e31eb-116">Verificare che la colonna del **pool di registrar** per gli utenti contenga ora il pool di Lync Server 2013, che indica che gli utenti sono stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="e31eb-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="e31eb-117">Per trasferire più utenti tramite Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="e31eb-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="e31eb-118">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e31eb-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="e31eb-119">Nella riga di comando digitare le opzioni seguenti e sostituire **User1** e **User2** con nomi utente specifici che si desidera trasferire e sostituire il nome di **dominio completo del pool\_** con quello del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e31eb-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="e31eb-120">In questo esempio verranno spostati gli utenti Hao Chen e Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="e31eb-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="e31eb-121">![Esempio di cmdlet PowerShell Get-CsUser](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "esempio di cmdlet PowerShell Get-CsUser")</span><span class="sxs-lookup"><span data-stu-id="e31eb-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="e31eb-122">Nella riga di comando digitare la seguente</span><span class="sxs-lookup"><span data-stu-id="e31eb-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="e31eb-123">L'identità del **pool di registrazione** deve ora puntare al pool specificato come **FQDN\_del pool** nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e31eb-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="e31eb-124">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e31eb-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="e31eb-125">Ripetere il passaggio per verificare che **User2** sia stato spostato.</span><span class="sxs-lookup"><span data-stu-id="e31eb-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="e31eb-126">![Output di PowerShell Get-UsUser-cmdlet Identity]-(images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "output di PowerShell Get-UsUser-cmdlet Identity")</span><span class="sxs-lookup"><span data-stu-id="e31eb-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="e31eb-127">Per trasferire tutti gli utenti contemporaneamente tramite Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="e31eb-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="e31eb-128">In questo esempio tutti gli utenti sono stati restituiti al pool di Lync Server 2010 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="e31eb-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="e31eb-129">Usando Lync Server 2013 Management Shell, sposteremo tutti gli utenti contemporaneamente sul pool di Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="e31eb-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="e31eb-130">Aprire **Lync Server 2013 Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e31eb-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="e31eb-131">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e31eb-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="e31eb-132">![Cmdlet di PowerShell e risultati in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet e risultati in Management Shell")</span><span class="sxs-lookup"><span data-stu-id="e31eb-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="e31eb-133">Esegui quindi **Get-CsUser** per uno degli utenti pilota.</span><span class="sxs-lookup"><span data-stu-id="e31eb-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="e31eb-134">L'identità del **pool di registrar** per ogni utente ora punta al pool specificato come "\_FQDN del pool" nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e31eb-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="e31eb-135">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e31eb-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="e31eb-136">Inoltre, è possibile visualizzare l'elenco degli utenti nel pannello di controllo di Lync Server 2013 e verificare che il valore del pool di registrazione punti ora al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e31eb-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="e31eb-137">![Lync server 2013 elenco utenti del pannello di controllo]di(images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 elenco utenti del pannello di controllo")</span><span class="sxs-lookup"><span data-stu-id="e31eb-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

