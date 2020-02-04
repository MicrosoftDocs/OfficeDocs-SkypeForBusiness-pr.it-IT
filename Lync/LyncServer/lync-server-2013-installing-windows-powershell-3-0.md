---
title: 'Lync Server 2013: Installazione di Windows PowerShell 3.0'
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
ms.openlocfilehash: 7cd8b4b48f2ff5a50ef7cafc1ec39671f672670f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="78adc-102">Installazione di Windows PowerShell 3.0 per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78adc-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78adc-103">_**Argomento Ultima modifica:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="78adc-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="78adc-104">Per distribuire Lync Server 2013 correttamente, è necessario Windows PowerShell 3,0 in ogni computer che fa parte della topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78adc-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="78adc-105">A questo punto, per i sistemi che eseguono Windows Server 2012 o Windows Server 2012 R2, non è necessario eseguire alcuna operazione e procedere con la fase successiva della distribuzione, perché PowerShell 3,0 è incluso in tali sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="78adc-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78adc-106">Ma per i sistemi che utilizzano Windows Server 2008 R2 SP1, è necessario installare PowerShell 3,0 come prerequisito prima di installare Lync Server 2013 o le cose non funzionano.</span><span class="sxs-lookup"><span data-stu-id="78adc-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="78adc-107">Per installare PowerShell 3,0, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>.</span><span class="sxs-lookup"><span data-stu-id="78adc-107">To install PowerShell 3.0, see <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="78adc-108">Si tratta di un collegamento diretto alla pagina di download di PowerShell 3,0, insieme alle informazioni relative all'installazione con successo.</span><span class="sxs-lookup"><span data-stu-id="78adc-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="78adc-109">Dopo aver eseguito l'installazione o se si vuole semplicemente verificare ed essere sicuri prima di continuare con la distribuzione di Lync Server, verificare che PowerShell 3,0 si trovi in un server sia piuttosto semplice se si esegue questa operazione:</span><span class="sxs-lookup"><span data-stu-id="78adc-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="78adc-110">Nel server che si vuole controllare scegliere **Start**, fare clic su **tutti i programmi**, su **Accessori**, su **Windows PowerShell**e quindi su **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78adc-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="78adc-111">Nella console di Windows PowerShell digitare il comando seguente al prompt dei comandi e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="78adc-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="78adc-112">Se Windows PowerShell 3,0 è installato, verrà visualizzato l'output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="78adc-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

