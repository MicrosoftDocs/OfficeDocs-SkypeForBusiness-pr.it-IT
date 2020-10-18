---
title: Eseguire la migrazione dei numeri di accesso esterno
description: Eseguire la migrazione di numeri di accesso esterno.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c8bd34a30bc4b3f8999144cd84a1eee62e2ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579322"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="3a644-103">Eseguire la migrazione dei numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3a644-103">Migrate dial-in access numbers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a644-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3a644-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3a644-105">La migrazione dei numeri di accesso esterno da Lync Server 2010 a Lync Server 2013 richiede l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="3a644-105">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="3a644-106">Durante il periodo di coesistenza di Lync Server 2010 e Lync Server 2013, i numeri di accesso esterno creati in Lync Server 2013 si comportano in modo analogo ai numeri di accesso esterno che si creano in Lync Server 2010, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3a644-106">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="3a644-107">I numeri di accesso esterno creati in Lync Server 2010 ma spostati in Lync Server 2013 o creati in Lync Server 2013 prima, durante o dopo la migrazione hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a644-107">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="3a644-108">Non sono visualizzati negli inviti alle riunioni di Office Communications Server 2007 R2 e nella pagina del numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3a644-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="3a644-109">Sono visualizzati negli inviti alle riunioni di Lync Server 2010 e nella pagina del numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3a644-109">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="3a644-110">Sono visualizzati negli inviti alle riunioni di Lync Server 2013 e nella pagina del numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3a644-110">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="3a644-111">Possono essere visualizzati e modificati nello strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3a644-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="3a644-112">Possono essere visualizzati e modificati nel Pannello di controllo di Lync Server 2010 e in Lync Server 2010 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3a644-112">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="3a644-113">Possono essere visualizzati e modificati nel Pannello di controllo di Lync Server 2013 e in Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3a644-113">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="3a644-114">Possono essere risequenziati nell'area tramite il cmdlet Set-CsDialinConferencingAccessNumber con il parametro Priority.</span><span class="sxs-lookup"><span data-stu-id="3a644-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="3a644-p102">È necessario completare la migrazione dei numeri di accesso esterno che puntano a un pool di Lync Server 2010 prima di rimuovere il pool di Lync Server 2010. Se non si completa la migrazione come descritto nella procedura seguente, le chiamate in arrivo ai numeri di accesso avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3a644-p102">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool. If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3a644-117">È necessario eseguire questa procedura prima di rimuovere il pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3a644-117">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3a644-118">È consigliabile spostare i numeri di accesso esterno quando l'utilizzo della rete è ridotto, nel caso si verifichi una breve interruzione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3a644-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="3a644-119">**Per identificare e spostare i numeri di accesso esterno**</span><span class="sxs-lookup"><span data-stu-id="3a644-119">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="3a644-120">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3a644-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3a644-121">Per spostare ogni numero di accesso esterno in un pool ospitato in Lync Server 2013, dalla riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="3a644-121">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="3a644-122">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a644-122">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="3a644-123">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="3a644-123">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="3a644-124">Fare clic sulla scheda **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="3a644-124">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="3a644-125">Verificare che non rimangano numeri di accesso esterno per il pool di Lync Server 2010 da cui si esegue la migrazione.</span><span class="sxs-lookup"><span data-stu-id="3a644-125">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a644-126">Quando tutti i numeri di accesso esterno puntano al pool di Lync Server 2013, è possibile rimuovere il pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3a644-126">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="3a644-127">**Verificare la migrazione dei numeri di accesso esterno tramite il Pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3a644-127">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3a644-128">Da un account utente assegnato al ruolo **CsUserAdministrator** o al ruolo **CsAdministrator** accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3a644-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a644-129">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a644-129">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3a644-130">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="3a644-130">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="3a644-131">Fare clic sulla scheda **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="3a644-131">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="3a644-132">Verificare che tutti i numeri di accesso esterno vengano migrati nel pool ospitato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a644-132">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="3a644-133">**Verificare la migrazione dei numeri di accesso esterno tramite Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="3a644-133">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="3a644-134">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3a644-134">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3a644-135">Per ottenere un elenco di tutti i numeri di accesso a conferenze telefoniche con accesso esterno di cui è stata eseguita la migrazione, dalla riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="3a644-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="3a644-136">Verificare che tutti i numeri di accesso esterno vengano migrati nel pool ospitato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a644-136">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

