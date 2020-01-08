---
title: 'Lync Server 2013: preparazione e installazione di Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d1d2f86b579bfb0259c8ad3e4b26b051b47a8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="80fc1-102">Preparazione e installazione di Best Practices Analyzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80fc1-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80fc1-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="80fc1-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="80fc1-104">Per eseguire le attività descritte in questo argomento, è necessario avere effettuato l'accesso come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="80fc1-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="80fc1-105">Requisiti di sistema per l'installazione di Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="80fc1-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="80fc1-106">Per eseguire Lync Server 2013, Best Practices Analyzer per analizzare l'ambiente, è necessario che il computer esegua una versione a 64 bit di uno dei sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="80fc1-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="80fc1-107">Windows Server 2008 R2 con il sistema operativo standard Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="80fc1-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="80fc1-108">Sistema operativo Windows Server 2008 R2 con SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80fc1-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="80fc1-109">Sistema operativo Windows Server 2008 R2 con SP1 Datacenter</span><span class="sxs-lookup"><span data-stu-id="80fc1-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="80fc1-110">Sistema operativo Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="80fc1-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="80fc1-111">Sistema operativo standard di Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="80fc1-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="80fc1-112">Sistema operativo Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80fc1-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="80fc1-113">Sistema operativo Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="80fc1-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="80fc1-114">Sistema operativo Windows Server 2012 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="80fc1-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="80fc1-115">Sistema operativo Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80fc1-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="80fc1-116">Sistema operativo Windows 8</span><span class="sxs-lookup"><span data-stu-id="80fc1-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="80fc1-117">Sistema operativo Windows 7</span><span class="sxs-lookup"><span data-stu-id="80fc1-117">Windows 7 operating system</span></span>

<span data-ttu-id="80fc1-118">Il computer deve eseguire anche le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80fc1-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="80fc1-119">Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="80fc1-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="80fc1-120">Per Lync Server 2013 è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 nel server prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80fc1-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="80fc1-121">Lync Server 2013, componenti principali.</span><span class="sxs-lookup"><span data-stu-id="80fc1-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="80fc1-122">Pacchetto compatibilità con le versioni precedenti di WMI.</span><span class="sxs-lookup"><span data-stu-id="80fc1-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="80fc1-123">Per informazioni dettagliate, vedere [installare il pacchetto compatibilità con le versioni precedenti di WMI](install-wmi-backward-compatibility-package.md) nella documentazione relativa alla migrazione.</span><span class="sxs-lookup"><span data-stu-id="80fc1-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="80fc1-124">Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="80fc1-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="80fc1-125">Per informazioni dettagliate, vedere [installazione di Windows PowerShell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="80fc1-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="80fc1-126">È possibile installare Best Practices Analyzer nei computer con un sistema operativo supportato che non esegue Lync Server 2013, componenti principali o un pacchetto di compatibilità con le versioni precedenti di WMI, ma è possibile usare le procedure consigliate in questi computer solo per visualizzare i report e non per eseguire le analisi.</span><span class="sxs-lookup"><span data-stu-id="80fc1-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="80fc1-127">Scelta di un computer per l'installazione</span><span class="sxs-lookup"><span data-stu-id="80fc1-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="80fc1-128">È consigliabile installare Lync Server 2013, Best Practices Analyzer in un computer dedicato a Lync Server 2013 Management.</span><span class="sxs-lookup"><span data-stu-id="80fc1-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="80fc1-129">È possibile installare lo strumento in un server che utilizza Lync Server 2013 o un computer amministrativo che gestisce gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80fc1-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="80fc1-130">Se si installa lo strumento in un server che esegue Lync Server, è consigliabile usare lo strumento per analizzare solo il server.</span><span class="sxs-lookup"><span data-stu-id="80fc1-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="80fc1-131">Installazione di Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="80fc1-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="80fc1-132">È possibile scaricare l'analizzatore delle procedure consigliate per Lync [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80fc1-132">You can download the Best Practices Analyzer for Lync Server 2013 at [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="80fc1-133">Per installare Best Practices Analyzer, avviare il file di Microsoft Installer RtcBPA. msi nel computer in cui si vuole installare lo strumento e quindi seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="80fc1-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="80fc1-134">Il percorso predefinito per l'installazione dei file di \<programma è\>\\System Drive\\Program Files Lync\\Server 2013 BPA.</span><span class="sxs-lookup"><span data-stu-id="80fc1-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

