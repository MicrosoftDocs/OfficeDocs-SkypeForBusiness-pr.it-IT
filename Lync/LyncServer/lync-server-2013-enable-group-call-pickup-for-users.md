---
title: 'Lync Server 2013: abilitare il prelievo delle chiamate di gruppo per gli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89d512eea147039a5766193f9ec2a20cf45caaa0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528723"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Abilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Utilizzare lo strumento Resource Kit di SEFAUtil per abilitare il prelievo delle chiamate di gruppo per gli utenti. Agli utenti deve essere assegnato un numero di gruppo con tipo GroupPickup nella tabella orbit del parcheggio di chiamata per abilitare il prelievo delle chiamate di gruppo. È possibile assegnare un numero di gruppo di prelievo di chiamata e attivare il prelievo delle chiamate di gruppo contemporaneamente utilizzando il parametro/enablegrouppickup quando si esegue SEFAUtil.exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Per abilitare il prelievo delle chiamate di gruppo per un utente

1.  Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2.  Nella riga di comando digitare il comando seguente:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Ad esempio:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Assegnare numeri di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Disabilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

