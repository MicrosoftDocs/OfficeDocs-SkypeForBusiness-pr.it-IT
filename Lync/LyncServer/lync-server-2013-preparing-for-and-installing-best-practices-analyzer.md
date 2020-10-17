---
title: 'Lync Server 2013: preparazione e installazione di Best Practices Analyzer'
description: 'Lync Server 2013: preparazione e installazione di Best Practices Analyzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 005c5ac372a3564e74af549832830ebae899e9d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549932"
---
# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="733dd-103">Preparazione e installazione di Best Practices Analyzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="733dd-103">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="733dd-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="733dd-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="733dd-105">Per eseguire le attività descritte in questo argomento è necessario accedere con un account membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="733dd-105">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="733dd-106">Requisiti di sistema per l'installazione di Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="733dd-106">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="733dd-107">Per eseguire Lync Server 2013, Best Practices Analyzer per analizzare l'ambiente in uso, è necessario che il computer esegua un'edizione a 64 bit di uno dei sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="733dd-107">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="733dd-108">Sistema operativo Windows Server 2008 R2 con Service Pack 1 (SP1) standard</span><span class="sxs-lookup"><span data-stu-id="733dd-108">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="733dd-109">Sistema operativo Windows Server 2008 R2 con SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="733dd-109">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="733dd-110">Sistema operativo Windows Server 2008 R2 con SP1 Datacenter</span><span class="sxs-lookup"><span data-stu-id="733dd-110">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="733dd-111">Sistema operativo Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="733dd-111">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="733dd-112">Sistema operativo Windows Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="733dd-112">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="733dd-113">Sistema operativo Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="733dd-113">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="733dd-114">Sistema operativo Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="733dd-114">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="733dd-115">Sistema operativo Windows Server 2012 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="733dd-115">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="733dd-116">Sistema operativo Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="733dd-116">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="733dd-117">Sistema operativo Windows 8</span><span class="sxs-lookup"><span data-stu-id="733dd-117">Windows 8 operating system</span></span>

  - <span data-ttu-id="733dd-118">Sistema operativo Windows 7</span><span class="sxs-lookup"><span data-stu-id="733dd-118">Windows 7 operating system</span></span>

<span data-ttu-id="733dd-119">Nel computer deve inoltre essere in esecuzione il software seguente:</span><span class="sxs-lookup"><span data-stu-id="733dd-119">The computer must also be running the following:</span></span>

  - <span data-ttu-id="733dd-120">Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="733dd-120">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="733dd-121">Per Lync Server 2013, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 sul server prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="733dd-121">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="733dd-122">Lync Server 2013, componenti di base.</span><span class="sxs-lookup"><span data-stu-id="733dd-122">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="733dd-123">Pacchetto di compatibilità con le versioni precedenti di Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="733dd-123">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="733dd-124">Per ulteriori informazioni, vedere Installare il pacchetto di compatibilità con le [versioni precedenti di WMI](install-wmi-backward-compatibility-package.md) nella documentazione relativa alla migrazione.</span><span class="sxs-lookup"><span data-stu-id="733dd-124">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="733dd-125">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="733dd-125">Windows PowerShell 3.0.</span></span> <span data-ttu-id="733dd-126">Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="733dd-126">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="733dd-127">È possibile installare Best Practices Analyzer nei computer con un sistema operativo supportato che non esegue Lync Server 2013, componenti di base o un pacchetto di compatibilità con le versioni precedenti di WMI, ma è possibile utilizzare Best Practices Analyzer nei computer solo per visualizzare i report, non per eseguire le analisi.</span><span class="sxs-lookup"><span data-stu-id="733dd-127">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="733dd-128">Scelta del computer per l'installazione</span><span class="sxs-lookup"><span data-stu-id="733dd-128">Choosing a Computer for Installation</span></span>

<span data-ttu-id="733dd-129">È consigliabile installare Lync Server 2013, Best Practices Analyzer su un computer dedicato alla gestione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="733dd-129">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="733dd-130">È possibile installare lo strumento su un server che esegue Lync Server 2013 o un computer amministrativo che esegue gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="733dd-130">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="733dd-131">Se si installa lo strumento su un server che esegue Lync Server, è consigliabile utilizzare lo strumento per analizzare solo quel server.</span><span class="sxs-lookup"><span data-stu-id="733dd-131">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="733dd-132">Installazione di Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="733dd-132">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="733dd-133">È possibile scaricare l'Analizzatore procedure consigliate per Lync Server 2013 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539) .</span><span class="sxs-lookup"><span data-stu-id="733dd-133">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="733dd-134">Per installare Best Practices Analyzer, avviare il file di Microsoft Installer RtcBPA.msi nel computer in cui si vuole installare lo strumento e quindi seguire le istruzioni sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="733dd-134">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="733dd-135">Il percorso predefinito per l'installazione dei file di programma è \<system drive\> \\ file di programma \\ Lync Server 2013 \\ BPA.</span><span class="sxs-lookup"><span data-stu-id="733dd-135">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

