---
title: 'Lync Server 2013: cmdlet per la gestione degli utenti'
description: 'Lync Server 2013: cmdlet per la gestione degli utenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94f2b48017fd29fa7a5a814da8a3c80d8f57968
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569782"
---
# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e6de8-103">Cmdlet per la gestione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6de8-103">User management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6de8-104">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e6de8-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e6de8-105">I cmdlet per la gestione degli utenti inclusi in Microsoft Lync Server 2013 consentono di abilitare, disabilitare e modificare gli account utente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6de8-105">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="e6de8-106">Cmdlet per la gestione degli utenti</span><span class="sxs-lookup"><span data-stu-id="e6de8-106">User Management Cmdlets</span></span>

<span data-ttu-id="e6de8-107">La maggior parte delle attività di gestione che si applicano agli utenti e agli account utente può essere eseguita dal pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6de8-107">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="e6de8-108">Le principali eccezioni sono i cmdlet relativi ai provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e6de8-108">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="e6de8-109">Le attività di gestione degli utenti possono essere eseguite utilizzando i cmdlet di Lync Server Management Shell o da uno script.</span><span class="sxs-lookup"><span data-stu-id="e6de8-109">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="e6de8-110">L'utilizzo di uno script consente di automatizzare particolari attività.</span><span class="sxs-lookup"><span data-stu-id="e6de8-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="e6de8-111">Di seguito è riportato un elenco di cmdlet direttamente correlati alla gestione di utenti e account utente:</span><span class="sxs-lookup"><span data-stu-id="e6de8-111">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="e6de8-112">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="e6de8-112">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="e6de8-113">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="e6de8-113">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="e6de8-114">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="e6de8-114">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="e6de8-115">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="e6de8-115">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="e6de8-116">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="e6de8-116">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="e6de8-117">Debug-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="e6de8-117">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="e6de8-118">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="e6de8-118">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="e6de8-119">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="e6de8-119">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="e6de8-120">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="e6de8-120">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="e6de8-121">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="e6de8-121">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="e6de8-122">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="e6de8-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="e6de8-123">Set-CsUser</span><span class="sxs-lookup"><span data-stu-id="e6de8-123">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="e6de8-124">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="e6de8-124">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="e6de8-125">Remove-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="e6de8-125">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="e6de8-126">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="e6de8-126">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="e6de8-127">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="e6de8-127">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="e6de8-128">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="e6de8-128">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="e6de8-129">Get-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="e6de8-129">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="e6de8-130">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="e6de8-130">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="e6de8-131">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="e6de8-131">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="e6de8-132">Remove-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="e6de8-132">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="e6de8-133">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="e6de8-133">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6de8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6de8-134">See Also</span></span>


[<span data-ttu-id="e6de8-135">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="e6de8-135">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

