---
title: 'Lync Server 2013: requisiti software per gli strumenti di amministrazione'
description: 'Lync Server 2013: requisiti software per gli strumenti di amministrazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c723d56cbda0c171fab206e3bcd3b2da0cc5b4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552962"
---
# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="dd2dd-103">Requisiti software per gli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd2dd-103">Administrative tools software requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd2dd-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="dd2dd-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="dd2dd-105">In questo argomento viene descritto il software necessario per installare e utilizzare gli strumenti di amministrazione di Lync Server 2013 oltre ai requisiti del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-105">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="dd2dd-106">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="dd2dd-106">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="dd2dd-107">Per Lync Server 2013 è necessaria l'edizione a 64 bit di Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-107">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="dd2dd-108">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="dd2dd-108">Windows PowerShell 3.0</span></span>

<span data-ttu-id="dd2dd-109">Windows PowerShell 3,0 è necessario per l'esecuzione di qualsiasi componente di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-109">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="dd2dd-110">Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="dd2dd-110">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="dd2dd-111">Windows Installer versione 4.5</span><span class="sxs-lookup"><span data-stu-id="dd2dd-111">Windows Installer Version 4.5</span></span>

<span data-ttu-id="dd2dd-112">Lync Server 2013 utilizza la tecnologia Windows Installer per installare, disinstallare e gestire diversi ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-112">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="dd2dd-113">Windows Installer versione 4.5 è disponibile come componente ridistribuibile per il sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-113">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="dd2dd-114">Windows Installer 4,5 viene fornito con Windows Server 2012 R2, Windows Server 2012 e Windows Server 2008 R2 e questo significa che non è necessario scaricare l'utilità per tutti i computer che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-114">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="dd2dd-115">(Lync Server 2013 può essere installato solo nei computer che eseguono Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="dd2dd-115">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="dd2dd-116">Tuttavia, se si desidera installare Lync Server Management Shell o il generatore di topologie di Lync Server in una workstation amministratore, potrebbe essere necessario scaricare Windows Installer 4,5.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-116">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="dd2dd-117">Tale utilità viene fornita con Windows 7 e Windows 2008 R2, ma non con le versioni precedenti del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-117">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="dd2dd-118">È possibile scaricare Windows Installer 4,5 dall'area download Microsoft all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=197395> .</span><span class="sxs-lookup"><span data-stu-id="dd2dd-118">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="dd2dd-119">Plug-in del browser Microsoft Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="dd2dd-119">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="dd2dd-120">Il pannello di controllo di Lync Server 2013 è uno strumento basato sul Web e richiede l'installazione della versione più recente del plug-in per il browser Microsoft Silverlight 5.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-120">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="dd2dd-121">Quando si avvia il pannello di controllo di Lync Server 2013, se il software non è installato o se è installata una versione precedente, il pannello di controllo di Lync Server 2013 richiede l'installazione della versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="dd2dd-121">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd2dd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd2dd-122">See Also</span></span>


[<span data-ttu-id="dd2dd-123">Supporto del sistema operativo per server e strumenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd2dd-123">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="dd2dd-124">Requisiti dell'infrastruttura degli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd2dd-124">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="dd2dd-125">Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd2dd-125">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

