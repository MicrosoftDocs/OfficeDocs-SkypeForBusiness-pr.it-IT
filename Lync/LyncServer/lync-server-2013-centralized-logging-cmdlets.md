---
title: 'Lync Server 2013: cmdlet di registrazione centralizzata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Centralized Logging cmdlets
ms:assetid: 8ba5bcae-8b99-489c-9355-6e77d4ad9100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205064(v=OCS.15)
ms:contentKeyID: 48184743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05bdedc57fca4c51351bcee351c7774c471cc821
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6b0f4-102">Cmdlet di registrazione centralizzati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b0f4-102">Centralized Logging cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b0f4-103">_**Argomento Ultima modifica:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="6b0f4-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="6b0f4-104">I cmdlet di registrazione centralizzati consentono agli amministratori di gestire e configurare le funzionalità di registrazione centralizzate introdotte in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-104">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6b0f4-105">La registrazione centralizzata consente agli amministratori di abilitare o disabilitare contemporaneamente la traccia degli eventi in più computer.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-105">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="6b0f4-106">Cmdlet di registrazione centralizzata</span><span class="sxs-lookup"><span data-stu-id="6b0f4-106">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="6b0f4-107">I cmdlet di registrazione centralizzati consentono di gestire il servizio di registrazione centralizzato introdotto in Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6b0f4-107">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="6b0f4-108">**Cmdlet di registrazione centralizzata**</span><span class="sxs-lookup"><span data-stu-id="6b0f4-108">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="6b0f4-109">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-109">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-110">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-110">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-111">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-111">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-112">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-112">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b0f4-113">[Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-113">[Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-114">[Mostra-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-114">[Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-115">[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-115">[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-116">[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-116">[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-117">[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-117">[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-118">[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-118">[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b0f4-119">[New-CsClsProvider](https://technet.microsoft.com/en-us/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-119">[New-CsClsProvider](https://technet.microsoft.com/en-us/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b0f4-120">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-120">[Get-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-121">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-121">[New-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-122">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-122">[Remove-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-123">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-123">[Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b0f4-124">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-124">[Get-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-125">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-125">[New-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-126">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-126">[Remove-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-127">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-127">[Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b0f4-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b0f4-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-131">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-131">[New-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="6b0f4-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b0f4-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

