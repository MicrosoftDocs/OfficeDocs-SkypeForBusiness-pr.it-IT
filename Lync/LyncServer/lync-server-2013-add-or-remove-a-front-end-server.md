---
title: 'Lync Server 2013: aggiungere o rimuovere un front end server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29c1b3800b05ac4318f853ece95b935c6e65c16c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Aggiungere o rimuovere un front end server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-01-21_

Quando si aggiunge un Front End Server a un pool oppure si rimuove un Front End Server da un pool, è quindi necessario riavviare il pool. Per evitare un'interruzione del servizio per gli utenti, eseguire la procedura seguente quando si aggiunge o si rimuove un Front End Server.

<div>


> [!NOTE]  
> Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che siano allo stesso livello di aggiornamento cumulativo dei server esistenti nel pool.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Per aggiungere o rimuovere front end server

1.  Se si desidera rimuovere uno o più Front End Server, innanzitutto interrompere le nuove connessioni a questi server. A tale scopo, è possibile utilizzare il cmdlet seguente:
    
        Stop-CsWindowsServices -Graceful

2.  Quando nei server da rimuovere non vi sono sessioni correnti, arrestare i servizi di Lync Server in esecuzione su di essi.

3.  Aprire Generatore di topologie e aggiungere o rimuovere i server necessari.

4.  Pubblicare la topologia.

5.  Se il pool è passato dall'avere due front end server a più di due o se è passato da più di due server a due esattamente, è necessario digitare il seguente cmdlet:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Se il pool dispone di tre o più server, almeno tre di questi server devono essere in esecuzione quando si digita questo cmdlet.

6.  Riavviare tutti i Front End Server nel pool, uno alla volta.

</div>

</div>

<span> </span>

</div>

</div>

</div>

