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
ms.openlocfilehash: ef15dec14266d4813ecc11624caa4c11906e7329
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500513"
---
# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a><span data-ttu-id="5095e-102">Spostare un dispositivo per conferenze in un nuovo pool di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5095e-102">Move a conferencing device to a new Registrar pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5095e-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5095e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5095e-104">Spostare un dispositivo per conferenze da un pool di registrazione a un altro utilizzando il cmdlet **Move-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="5095e-104">Move a conferencing device from one Registrar pool to another by using the **Move-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="5095e-105">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5095e-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5095e-106">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="5095e-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a><span data-ttu-id="5095e-107">Spostamento di un dispositivo per conferenze in un nuovo pool di registrazione</span><span class="sxs-lookup"><span data-stu-id="5095e-107">Moving a Conferencing Device to a New Registrar Pool</span></span>

  - <span data-ttu-id="5095e-108">Per spostare un dispositivo per conferenze, è necessario specificare l'identità della sala da spostare e quindi impostare il parametro target sul nome di dominio completo (FQDN) del pool di registrazione in cui verrà spostato il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5095e-108">To move a conferencing device, you must specify the identity of the room to be moved, and then set the Target parameter to the fully qualified domain name (FQDN) of the Registrar pool the device will be moved to.</span></span> <span data-ttu-id="5095e-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5095e-109">For example:</span></span>
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

<span data-ttu-id="5095e-110">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="5095e-110">For details, see the Help topic for the [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

