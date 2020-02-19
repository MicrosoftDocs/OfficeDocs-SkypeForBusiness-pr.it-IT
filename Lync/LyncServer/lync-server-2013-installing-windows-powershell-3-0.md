---
title: 'Lync Server 2013: installazione di Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce694fe34451d6465f1fff31119ecf40c13e82d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="f9513-102">Installazione di Windows PowerShell 3,0 per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9513-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9513-103">_**Ultimo argomento modificato:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="f9513-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="f9513-104">Per distribuire Lync Server 2013 con esito positivo, è necessario utilizzare Windows PowerShell 3,0 su ogni computer che fa parte della topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9513-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="f9513-105">A questo punto, per i sistemi che eseguono Windows Server 2012 o Windows Server 2012 R2, non è necessario eseguire alcuna operazione e procedere alla fase successiva della distribuzione, poiché PowerShell 3,0 è incluso in tali sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="f9513-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9513-106">Tuttavia, per i sistemi che eseguono Windows Server 2008 R2 SP1, è necessario installare PowerShell 3,0 come prerequisito prima di installare Lync Server 2013 o le cose non funzionano.</span><span class="sxs-lookup"><span data-stu-id="f9513-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="f9513-107">Per installare PowerShell 3,0, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="f9513-107">To install PowerShell 3.0, see <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="f9513-108">Si tratta di un collegamento diretto alla pagina di download di PowerShell 3,0, insieme a informazioni relative all'installazione con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f9513-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="f9513-109">Dopo aver effettuato l'installazione, o se si desidera controllare e assicurarsi che prima di continuare con la distribuzione di Lync Server, confermando che PowerShell 3,0 è su un server è piuttosto semplice se si esegue questa operazione:</span><span class="sxs-lookup"><span data-stu-id="f9513-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="f9513-110">Nel server che si desidera controllare, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, **Windows PowerShell**e quindi fare clic su **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f9513-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="f9513-111">Nella console di Windows PowerShell, digitare il comando seguente al prompt dei comandi e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="f9513-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="f9513-112">Se Windows PowerShell 3,0 è installato, verrà visualizzato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f9513-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

