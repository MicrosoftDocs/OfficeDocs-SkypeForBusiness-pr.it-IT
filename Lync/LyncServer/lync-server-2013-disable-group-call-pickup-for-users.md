---
title: 'Lync Server 2013: disabilitare il prelievo delle chiamate di gruppo per gli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c03242cf0b3521dada944ccaba30946306c1ff24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Disabilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Per disabilitare il prelievo delle chiamate di gruppo per un utente, eseguire la procedura seguente.

<div>


> [!NOTE]  
> Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero del gruppo di prelievo delle chiamate assegnato all'utente non viene mantenuto. Se successivamente si desidera riabilitare il prelievo delle chiamate di gruppo per tale utente, è necessario assegnare di nuovo il numero del gruppo di prelievo delle chiamate con il parametro/enablegrouppickup.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>Per disabilitare il prelievo delle chiamate di gruppo per un utente

1.  Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2.  Nella riga di comando digitare il comando seguente:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Ad esempio:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Assegnare numeri di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Abilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

