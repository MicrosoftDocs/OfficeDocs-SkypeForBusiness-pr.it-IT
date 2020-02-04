---
title: 'Lync Server 2013: abilitare o disabilitare un dispositivo per i servizi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a4a0f582f57d4e096001d508d3983facdded74c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="25ac0-102">Abilitare o disabilitare un dispositivo per conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25ac0-102">Enable or disable a conferencing device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25ac0-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="25ac0-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="25ac0-104">Abilita e Disabilita un dispositivo per conferenze usando il cmdlet **Enable-CsMeetingRoom** e il cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="25ac0-104">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="25ac0-105">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25ac0-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25ac0-106">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="25ac0-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="25ac0-107">Abilitazione di un dispositivo di conferenza</span><span class="sxs-lookup"><span data-stu-id="25ac0-107">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="25ac0-108">Per abilitare un dispositivo per i servizi di conferenza, usare il cmdlet **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="25ac0-108">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="25ac0-109">Quando si Abilita un dispositivo per i servizi di conferenza, è necessario includere l'identità di un dispositivo di conferenza, b) il pool di registrar in cui verrà assegnato l'account della sala e c) l'indirizzo SIP da assegnare all'account.</span><span class="sxs-lookup"><span data-stu-id="25ac0-109">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="25ac0-110">Disabilitazione di un dispositivo per i servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="25ac0-110">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="25ac0-111">Per disabilitare un dispositivo per i servizi di conferenza, usare il cmdlet **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="25ac0-111">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="25ac0-112">Assicurarsi di specificare l'identità del dispositivo di conferenza da disabilitare:</span><span class="sxs-lookup"><span data-stu-id="25ac0-112">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="25ac0-113">Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e al cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="25ac0-113">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

