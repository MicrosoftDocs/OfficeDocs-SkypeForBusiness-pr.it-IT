---
title: 'Lync Server 2013: aggiungere o rimuovere un server front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Aggiungere o rimuovere un server front-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-01-21_

Quando si aggiunge un server front-end a un pool o si rimuove un server front-end da un pool, è necessario riavviare il pool. Per impedire l'interruzione del servizio agli utenti, usare la procedura seguente per aggiungere o rimuovere un server front-end.

<div>


> [!NOTE]  
> Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che si trovino nello stesso livello di aggiornamento cumulativo dei server esistenti nel pool.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Per aggiungere o rimuovere i server front-end

1.  Se si stanno rimuovendo i server front-end, arrestare prima le nuove connessioni a tali server. A questo scopo, puoi usare il cmdlet seguente:
    
        Stop-CsWindowsServices -Graceful

2.  Quando i server rimossi non hanno sessioni correnti, arrestare i servizi di Lync Server.

3.  Aprire Generatore di topologia e aggiungere o rimuovere i server necessari.

4.  Pubblicare la topologia.

5.  Se il pool è stato rimosso da due server front-end a più di due o se è stato superato da più di due server a due, è necessario digitare il cmdlet seguente:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Se il pool include tre o più server, è necessario che almeno tre di questi server vengano eseguiti quando si digita questo cmdlet.

6.  Riavviare tutti i server front-end nel pool, uno alla volta.

</div>

</div>

<span> </span>

</div>

</div>

</div>

