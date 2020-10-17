---
title: 'Lync Server 2013: assegnare i numeri di prelievo delle chiamate di gruppo agli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3de74542edc65de68ab5f803934aa671575cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499483"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Assegnare numeri di prelievo delle chiamate di gruppo agli utenti in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Dopo aver aggiunto i numeri del gruppo di prelievo delle chiamate di gruppo alla tabella orbit del parcheggio di chiamata, è possibile assegnare i gruppi agli utenti. Utilizzare lo strumento Resource Kit di attivazione delle funzionalità di SEFAUtil (Secondary Extension feature Activation) per assegnare i gruppi di prelievo delle chiamate agli utenti.

<div>


> [!NOTE]  
> In una distribuzione ibrida, non assegnare un gruppo di prelievo di chiamata di gruppo agli utenti ospitati online. Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo. Vale a fare che le chiamate non possono rispondere ad altri utenti e che non rispondono alle chiamate ad altri utenti.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Per assegnare un gruppo di prelievo di chiamata di gruppo a un utente

1.  Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2.  Nella riga di comando digitare il comando seguente:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Ad esempio:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Abilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Disabilitare il prelievo delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

