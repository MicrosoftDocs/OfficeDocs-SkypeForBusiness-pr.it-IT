---
title: 'Lync Server 2013: disabilitare il ritiro delle chiamate di gruppo per gli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b7e0d17b91accdab0f1590d9fc505dec42f430
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Disabilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Usare la procedura seguente per disabilitare il ritiro delle chiamate di gruppo per un utente.

<div>


> [!NOTE]  
> Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero del gruppo di prelievo delle chiamate assegnato all'utente non viene mantenuto. Se in seguito si vuole riabilitare il ritiro delle chiamate di gruppo per l'utente, è necessario assegnare di nuovo il numero del gruppo di prelievo delle chiamate con il parametro/enablegrouppickup.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>Per disabilitare il ritiro delle chiamate di gruppo per un utente

1.  Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2.  Nella riga di comando eseguire:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Ad esempio:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Assegnare numeri di raccolta chiamate di gruppo agli utenti in Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

