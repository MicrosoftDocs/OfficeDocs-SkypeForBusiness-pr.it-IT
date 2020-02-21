---
title: 'Lync Server 2013: attivazione o disattivazione di un dispositivo per conferenze'
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
ms.openlocfilehash: 27a5ed5c138d1389f0a3d4882bcdd437b5e7919e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Abilitazione o disabilitazione di un dispositivo per conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

Abilitare e disabilitare un dispositivo per conferenze utilizzando il cmdlet **Enable-CsMeetingRoom** e il cmdlet **Disable-CsMeetingRoom** . Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Abilitazione di un dispositivo per conferenze

  - Per abilitare un dispositivo per i servizi di conferenza, utilizzare il cmdlet **Enable-CsMeetingRoom** . Quando si Abilita un dispositivo per i servizi di conferenza, è necessario includere un'identità del dispositivo per i servizi di conferenza, b) il pool di registrazione in cui verrà ospitato l'account della sala e c) l'indirizzo SIP da assegnare a quell'account.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Disabilitazione di un dispositivo per conferenze

  - Per disabilitare un dispositivo per conferenze, utilizzare il cmdlet **Disable-CsMeetingRoom** . Assicurarsi di specificare l'identità del dispositivo per i servizi di conferenza da disabilitare:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e il cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

