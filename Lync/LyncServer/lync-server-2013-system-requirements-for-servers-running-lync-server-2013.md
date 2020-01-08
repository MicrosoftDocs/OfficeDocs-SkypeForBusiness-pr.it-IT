---
title: 'Lync Server 2013: Requisiti di sistema per i server Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="b8977-102">Requisiti di sistema per i server Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8977-102">System requirements for servers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8977-103">_**Argomento Ultima modifica:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="b8977-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8977-104">Per informazioni dettagliate sui requisiti hardware, vedere <A href="lync-server-2013-server-hardware-platforms.md">piattaforme hardware server per Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8977-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b8977-105">I server Standard Edition e Enterprise Edition condividono gli stessi requisiti software.</span><span class="sxs-lookup"><span data-stu-id="b8977-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="b8977-106">I server che usano Lync Server 2013 Enterprise Edition sono destinati alle organizzazioni di grandi dimensioni come principale distribuzione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8977-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="b8977-107">Enterprise Edition Server è progettato per scalare fino a circa 80.000 utenti ospitati per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="b8977-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="b8977-108">I server che usano Lync Server 2013, Standard Edition sono destinati a organizzazioni più piccole e a posizioni remote dalla distribuzione principale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8977-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="b8977-109">Una coppia di server Standard Edition può supportare fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="b8977-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="b8977-110">Per informazioni dettagliate sulle differenze tra i server Standard Edition e i server Enterprise Edition, vedere [Panoramica della distribuzione per Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b8977-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="b8977-111">Installazione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="b8977-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8977-112">Lync Server 2013 è disponibile solo in una versione a 64 bit, che richiede hardware a 64 bit e un'edizione a 64 bit del sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b8977-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="b8977-113">Una versione di 32 bit di Lync Server 2013 non è disponibile con questo rilascio.</span><span class="sxs-lookup"><span data-stu-id="b8977-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="b8977-114">Standard Edition e Enterprise Edition Server possono usare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8977-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="b8977-115">Windows Server 2008 R2 SP1 o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="b8977-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="b8977-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b8977-116">Windows Server 2012</span></span>

  - <span data-ttu-id="b8977-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b8977-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="b8977-118">Installare il software del sistema operativo nel server Standard Edition o nel front-end di Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b8977-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="b8977-119">Applica tutti gli aggiornamenti per riportare il sistema operativo all'aggiornamento più recente e al livello di aggiornamento richiesto coerente con gli standard dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8977-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="b8977-120">Per altre informazioni sui requisiti operativi, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="b8977-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8977-121">Per Lync Server 2013 per l'utilizzo in Windows Server 2012 R2, potrebbe essere necessario modificare il valore di una chiave del registro di sistema in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b8977-121">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="b8977-122">Questa modifica può essere necessaria affinché i certificati funzionino correttamente e i client vengano registrati con Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="b8977-122">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="b8977-123">Per altre informazioni, vedere <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span><span class="sxs-lookup"><span data-stu-id="b8977-123">For more information, see <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="b8977-124">Software aggiuntivo per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8977-124">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="b8977-125">Oltre agli aggiornamenti necessari per il sistema operativo, Lync Server 2013 richiede l'uso di ruoli, funzionalità e software del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b8977-125">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="b8977-126">Per informazioni dettagliate sul software aggiuntivo che deve essere installato prima di pubblicare la topologia e installare Lync Server 2013, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b8977-126">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="b8977-127">Software aggiuntivo necessario per tutti i ruoli del server</span><span class="sxs-lookup"><span data-stu-id="b8977-127">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="b8977-128">In tutti i ruoli del server devi anche verificare che l'interfaccia della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 siano installati.</span><span class="sxs-lookup"><span data-stu-id="b8977-128">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="b8977-129">Inoltre, le interfacce della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 sono necessarie in qualsiasi computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8977-129">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="b8977-130">Windows PowerShell 3,0</span><span class="sxs-lookup"><span data-stu-id="b8977-130">Windows PowerShell 3.0</span></span>

<span data-ttu-id="b8977-131">Lync Server 2013 richiede l'installazione di Windows PowerShell 3,0 in ogni computer che prenderà parte alla topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8977-131">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="b8977-132">Per informazioni dettagliate sull'installazione di Windows PowerShell 3,0, vedere [installazione di Windows powershell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="b8977-132">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8977-133">In Windows Server&nbsp;2008&nbsp;R2 con SP1 l'interfaccia della riga di comando di Windows PowerShell 3,0 non può essere installata prima di installare Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="b8977-133">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="b8977-134">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="b8977-134">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="b8977-135">Quando si installa Microsoft .NET Framework 4,5 nei server in cui viene eseguito Lync Server 2013 in Windows Server 2012 o Windows Server 2012 R2, è necessario eseguire un ulteriore passaggio.</span><span class="sxs-lookup"><span data-stu-id="b8977-135">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="b8977-136">Dopo l'installazione di .NET Framework 4,5, usare Server Manager per installare l'attivazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="b8977-136">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="b8977-137">**Per installare l'attivazione HTTP di .NET 4,5 in Windows Server 2012 o Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="b8977-137">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="b8977-138">Nel menu **Start** fare clic su **programmi**, quindi su **strumenti di amministrazione**e quindi su **Gestione server**.</span><span class="sxs-lookup"><span data-stu-id="b8977-138">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="b8977-139">In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="b8977-139">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="b8977-140">Espandere **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="b8977-140">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="b8977-141">Selezionare l' **attivazione di WCF** se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="b8977-141">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="b8977-142">Quindi seleziona **attivazione http**.</span><span class="sxs-lookup"><span data-stu-id="b8977-142">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="b8977-143">Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b8977-143">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

