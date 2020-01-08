---
title: 'Lync Server 2013: abilitare il ritiro delle chiamate di gruppo per gli utenti e assegnare un numero di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9523a76eb9cd23dd4c8ee531520341aaf82f508
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Abilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013 e assegnare un numero di gruppo

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Dopo aver aggiunto numeri di gruppo di prelievo chiamate alla tabella Orbit di Call Park, assegnare i numeri di gruppo agli utenti e abilitare il ritiro delle chiamate di gruppo. Usare lo strumento Resource Kit di attivazione delle funzionalità di estensione secondaria (SEFAUtil) per assegnare numeri di gruppo e consentire il prelievo delle chiamate di gruppo.

<div>


> [!NOTE]  
> In una distribuzione ibrida non assegnare un gruppo di raccolta chiamate di gruppo agli utenti ospitati online. Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo. Ossia, non è possibile rispondere alle chiamate di altri utenti, e non possono ricevere risposte ad altri utenti.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Per assegnare un numero di gruppo e abilitare il ritiro delle chiamate di gruppo per un utente

1.  Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2.  Nella riga di comando eseguire:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Ad esempio, per assegnare un numero di gruppo 199 a un utente:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Disabilitare il ritiro delle chiamate di gruppo per gli utenti in Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

