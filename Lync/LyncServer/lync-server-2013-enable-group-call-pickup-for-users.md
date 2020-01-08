---
title: 'Lync Server 2013: abilitare il ritiro delle chiamate di gruppo per gli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54abf04c7c0d892e5cc58938866592f96cc1776
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Usare lo strumento SEFAUtil Resource Kit per abilitare il ritiro delle chiamate di gruppo per gli utenti. Agli utenti deve essere assegnato un numero di gruppo con il tipo GroupPickup nella tabella Orbit di Call Park in cui è abilitato il pick-up delle chiamate di gruppo. Si assegna un numero di gruppo di prelievo delle chiamate e si Abilita la raccolta chiamate di gruppo contemporaneamente usando il parametro/enablegrouppickup quando si esegue SEFAUtil. exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Per abilitare il ritiro delle chiamate di gruppo per un utente

1.  Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2.  Nella riga di comando eseguire:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Ad esempio:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Assegnare numeri di raccolta chiamate di gruppo agli utenti in Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Disabilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

