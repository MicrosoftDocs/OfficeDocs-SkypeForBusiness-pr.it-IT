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

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Abilitare o disabilitare un dispositivo per conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

Abilita e Disabilita un dispositivo per conferenze usando il cmdlet **Enable-CsMeetingRoom** e il cmdlet **Disable-CsMeetingRoom** . Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Abilitazione di un dispositivo di conferenza

  - Per abilitare un dispositivo per i servizi di conferenza, usare il cmdlet **Enable-CsMeetingRoom** . Quando si Abilita un dispositivo per i servizi di conferenza, è necessario includere l'identità di un dispositivo di conferenza, b) il pool di registrar in cui verrà assegnato l'account della sala e c) l'indirizzo SIP da assegnare all'account.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Disabilitazione di un dispositivo per i servizi di conferenza

  - Per disabilitare un dispositivo per i servizi di conferenza, usare il cmdlet **Disable-CsMeetingRoom** . Assicurarsi di specificare l'identità del dispositivo di conferenza da disabilitare:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e al cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

