---
title: "Lync Server 2013: Preparazione dell'ambiente per VDI"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a3fb2563e287f24d49c23a468b4a44528707b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="8d4a5-102">Preparazione dell'ambiente di Lync Server 2013 per VDI</span><span class="sxs-lookup"><span data-stu-id="8d4a5-102">Preparing your Lync Server 2013 environment for VDI</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d4a5-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8d4a5-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8d4a5-104">Per preparare l'ambiente per il plug-in di Lync VDI, l'amministratore deve eseguire i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8d4a5-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="8d4a5-105">In Lync Server 2013 verificare che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti VDI.</span><span class="sxs-lookup"><span data-stu-id="8d4a5-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="8d4a5-106">Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e al cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="8d4a5-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="8d4a5-107">Nel computer centro dati installare il client Lync 2013 in tutte le macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="8d4a5-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="8d4a5-108">Nei computer locali installare il plug-in di Lync VDI.</span><span class="sxs-lookup"><span data-stu-id="8d4a5-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

