---
title: 'Lync Server 2013: requisiti di sistema per i server che eseguono Lync Server 2013'
description: 'Lync Server 2013: requisiti di sistema per i server che eseguono Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562652"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="b5f5e-103">Requisiti di sistema per i server che eseguono Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5f5e-103">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5f5e-104">_**Ultimo argomento modificato:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="b5f5e-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b5f5e-105">Per informazioni dettagliate sui requisiti hardware, vedere <A href="lync-server-2013-server-hardware-platforms.md">server hardware Platforms for Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-105">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b5f5e-106">I server Standard Edition e Enterprise Edition condividono gli stessi requisiti software.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-106">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="b5f5e-107">I server che eseguono Lync Server 2013, Enterprise Edition sono progettati per le organizzazioni di grandi dimensioni come principale distribuzione organizzativa.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-107">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="b5f5e-108">Il Server Enterprise è progettato per consentire la scalabilità di circa 80.000 utenti che risiedono in ogni pool.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-108">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="b5f5e-109">I server che eseguono Lync Server 2013, Standard Edition sono destinati a organizzazioni di piccole dimensioni e a percorsi remoti dalla distribuzione dell'organizzazione principale.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-109">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="b5f5e-110">Una coppia di server Standard Edition è in grado di supportare fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-110">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="b5f5e-111">Per informazioni dettagliate sulle differenze tra i server Standard Edition e i server Enterprise Edition, vedere [Deployment Overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b5f5e-111">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="b5f5e-112">Installazione del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="b5f5e-112">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b5f5e-113">Lync Server 2013 è disponibile solo in un'edizione a 64 bit, che richiede hardware a 64 bit e un'edizione a 64 bit del sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-113">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="b5f5e-114">L'edizione a 32 bit di Lync Server 2013 non è disponibile con questa versione.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-114">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="b5f5e-115">Il server Standard Edition e Enterprise Edition è in grado di utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5f5e-115">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="b5f5e-116">Windows Server 2008 R2 SP1 o Service Pack più recente</span><span class="sxs-lookup"><span data-stu-id="b5f5e-116">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="b5f5e-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b5f5e-117">Windows Server 2012</span></span>

  - <span data-ttu-id="b5f5e-118">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b5f5e-118">Windows Server 2012 R2</span></span>

<span data-ttu-id="b5f5e-119">Installare il software del sistema operativo nel server Standard Edition o Enterprise Edition Front End Server.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-119">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="b5f5e-120">Applicare tutti gli aggiornamenti per portare il sistema operativo al livello di aggiornamento più recente necessario in base agli standard dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-120">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="b5f5e-121">Per ulteriori informazioni sui requisiti operativi, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-121">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="b5f5e-122">L'aggiornamento sul posto del sistema operativo non è supportato con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-122">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="b5f5e-123">È necessario distribuire un pool separato ed eseguire la migrazione degli utenti nel nuovo pool con un sistema operativo diverso.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-123">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b5f5e-124">Affinché Lync Server 2013 funzioni su Windows Server 2012 R2, potrebbe essere necessario modificare il valore di una chiave del registro di sistema in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-124">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="b5f5e-125">Questa modifica potrebbe essere necessaria affinché i certificati funzionino correttamente e i client possano registrarsi con Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-125">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="b5f5e-126">Per ulteriori informazioni, vedere <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .</span><span class="sxs-lookup"><span data-stu-id="b5f5e-126">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="b5f5e-127">Software aggiuntivo per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5f5e-127">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="b5f5e-128">Oltre agli aggiornamenti necessari per il sistema operativo, Lync Server 2013 richiede ruoli del sistema operativo, funzionalità e software per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-128">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="b5f5e-129">Per informazioni dettagliate sul software aggiuntivo che deve essere installato prima di pubblicare la topologia e l'installazione di Lync Server 2013, vedere [requisiti software aggiuntivi per Lync server 2013](lync-server-2013-additional-software-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-129">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="b5f5e-130">Software aggiuntivo necessario per tutti i ruoli del server</span><span class="sxs-lookup"><span data-stu-id="b5f5e-130">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="b5f5e-131">In tutti i ruoli del server, è inoltre necessario verificare che l'interfaccia della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 siano installati.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-131">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="b5f5e-132">Inoltre, l'interfaccia della riga di comando di Windows PowerShell 3,0 e Microsoft .NET Framework 4,5 sono necessari in tutti i computer in cui verranno eseguiti gli strumenti di amministrazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-132">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="b5f5e-133">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="b5f5e-133">Windows PowerShell 3.0</span></span>

<span data-ttu-id="b5f5e-134">Lync Server 2013 richiede l'installazione di Windows PowerShell 3,0 su ogni computer che prenderà parte alla topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-134">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="b5f5e-135">Per informazioni dettagliate sull'installazione di Windows PowerShell 3,0, vedere [Installing Windows powershell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="b5f5e-135">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b5f5e-136">In Windows Server &nbsp; 2008 &nbsp; R2 con SP1, l'interfaccia della riga di comando di windows PowerShell 3,0 non può essere installata prima dell'installazione di Microsoft .net Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-136">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="b5f5e-137">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b5f5e-137">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="b5f5e-138">Quando si installa Microsoft .NET Framework 4,5 nei server che eseguiranno Lync Server 2013 su Windows Server 2012 o Windows Server 2012 R2, è necessario eseguire un ulteriore passaggio.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-138">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="b5f5e-139">Dopo l'installazione di .NET Framework 4,5, utilizzare Server Manager per installare l'attivazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-139">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="b5f5e-140">**Per installare l'attivazione di .NET 4,5 HTTP su Windows Server 2012 o Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="b5f5e-140">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="b5f5e-141">Fare clic sul pulsante **Start** , scegliere **programmi**, quindi **strumenti di amministrazione**e quindi fare clic su **Server Manager**.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-141">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="b5f5e-142">In Server Manager, in **Riepilogo funzionalità**, scegliere **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-142">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="b5f5e-143">Espandere **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-143">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="b5f5e-144">Selezionare **attivazione WCF** se non è già selezionata.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-144">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="b5f5e-145">Quindi selezionare **attivazione http**.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-145">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="b5f5e-146">Fare clic su **Avanti** e seguire le istruzioni per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b5f5e-146">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

