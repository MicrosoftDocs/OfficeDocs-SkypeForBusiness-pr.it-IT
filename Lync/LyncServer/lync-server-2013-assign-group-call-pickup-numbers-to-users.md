---
title: 'Lync Server 2013: assegnare numeri di raccolta chiamate di gruppo agli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e919b1fb4ee225eba1c5317ff1f3049791075bcc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Assegnare numeri di raccolta chiamate di gruppo agli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Dopo aver aggiunto i numeri dei gruppi di prelievo delle chiamate di gruppo alla tabella Orbit di Call Park, è possibile assegnare i gruppi agli utenti. Usare lo strumento Resource Kit di attivazione delle funzionalità di estensione secondaria (SEFAUtil) per assegnare gruppi di prelievo delle chiamate agli utenti.

<div>


> [!NOTE]  
> In una distribuzione ibrida non assegnare un gruppo di raccolta chiamate di gruppo agli utenti ospitati online. Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo. Ossia, non è possibile rispondere alle chiamate di altri utenti, e non possono ricevere risposte ad altri utenti.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Per assegnare un gruppo di raccolta chiamate di gruppo a un utente

1.  Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2.  Nella riga di comando eseguire:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Ad esempio:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Disabilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

