---
title: 'Lync Server 2013: spostare un dispositivo per conferenze in un nuovo pool di registrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebeb81c97e92cc305c3f1bec78f6c59aeb62d978
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a><span data-ttu-id="f7a60-102">Spostare un dispositivo per conferenze in un nuovo pool di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7a60-102">Move a conferencing device to a new Registrar pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a60-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f7a60-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f7a60-104">Spostare un dispositivo per conferenze da un pool di registrazione a un altro utilizzando il cmdlet **Move-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="f7a60-104">Move a conferencing device from one Registrar pool to another by using the **Move-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="f7a60-105">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7a60-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7a60-106">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="f7a60-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a><span data-ttu-id="f7a60-107">Spostamento di un dispositivo per conferenze in un nuovo pool di registrazione</span><span class="sxs-lookup"><span data-stu-id="f7a60-107">Moving a Conferencing Device to a New Registrar Pool</span></span>

  - <span data-ttu-id="f7a60-108">Per spostare un dispositivo per conferenze, è necessario specificare l'identità della sala da spostare e quindi impostare il parametro target sul nome di dominio completo (FQDN) del pool di registrazione in cui verrà spostato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7a60-108">To move a conferencing device, you must specify the identity of the room to be moved, and then set the Target parameter to the fully qualified domain name (FQDN) of the Registrar pool the device will be moved to.</span></span> <span data-ttu-id="f7a60-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f7a60-109">For example:</span></span>
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

<span data-ttu-id="f7a60-110">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="f7a60-110">For details, see the Help topic for the [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

