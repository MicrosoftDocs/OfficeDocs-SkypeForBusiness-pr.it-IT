---
title: 'Lync Server 2013: risoluzione dei problemi relativi ai cmdlet di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Enterprise Voice cmdlets
ms:assetid: 28ec32d2-6d1e-40e6-b2a8-065803288e8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415638(v=OCS.15)
ms:contentKeyID: 48183697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ef88ac7a55480df050719fa1a85a056df8a02ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2a80a-102">Risoluzione dei problemi relativi ai cmdlet di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a80a-102">Troubleshooting Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a80a-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="2a80a-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="2a80a-104">La configurazione di VoIP aziendale come parte dell'implementazione di Microsoft Lync Server 2013 prevede la creazione di route, criteri e regole che devono collaborare tutti per garantire che le chiamate in arrivo e in uscita vengano completate come previsto.</span><span class="sxs-lookup"><span data-stu-id="2a80a-104">Setting up Enterprise Voice as part of your Microsoft Lync Server 2013 implementation involves creating routes, policies and rules that must all work together to ensure incoming and outgoing calls are completed as expected.</span></span> <span data-ttu-id="2a80a-105">Lync Server Management Shell include cmdlet che possono essere utilizzati per testare le connessioni e i percorsi e per risolvere i problemi che possono verificarsi durante l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="2a80a-105">Lync Server Management Shell includes cmdlets that can be used to test connections and paths and to troubleshoot issues that may arise during implementation.</span></span>

<div>

## <a name="troubleshooting-enterprise-voice-cmdlets"></a><span data-ttu-id="2a80a-106">Cmdlet per la risoluzione dei problemi relativi a VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="2a80a-106">Troubleshooting Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="2a80a-107">È possibile utilizzare i cmdlet seguenti per testare le connessioni VoIP aziendale e risolvere i relativi problemi.</span><span class="sxs-lookup"><span data-stu-id="2a80a-107">The following cmdlets can be used to test and troubleshoot Enterprise Voice connections.</span></span>

<span data-ttu-id="2a80a-108">**Cmdlet per la risoluzione dei problemi relativi a VoIP aziendale**</span><span class="sxs-lookup"><span data-stu-id="2a80a-108">**Troubleshooting Enterprise Voice Cmdlets**</span></span>

  - <span></span>  
    <span data-ttu-id="2a80a-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a80a-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a80a-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a80a-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a80a-113">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-113">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a80a-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a80a-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a80a-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a80a-117">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-117">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a80a-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a80a-119">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-119">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a80a-120">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-120">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a80a-121">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a80a-121">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a80a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a80a-122">See Also</span></span>


[<span data-ttu-id="2a80a-123">Cmdlet di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a80a-123">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="2a80a-124">Blog di PowerShell per Lync Server</span><span class="sxs-lookup"><span data-stu-id="2a80a-124">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

