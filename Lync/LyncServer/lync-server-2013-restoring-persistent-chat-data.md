---
title: 'Lync Server 2013: ripristino dei dati della chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed69938186de2aebf6268168e663abcb125ad86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Ripristino dei dati della chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-18_

Il contenuto della chat room persistente viene archiviato nel database della chat persistente (MGC. MDF). Si tratta di dati business-critical di cui eseguire il backup regolarmente. Oltre al contenuto della chat room, anche le entità (ad esempio utenti e gruppi) e i ruoli e l'accesso che devono eseguire per la chat room e il contenuto della chat room vengono archiviati nel database della chat persistente.

Il modo in cui ripristinare i dati della chat persistente dipende dal metodo usato per eseguire il backup.

  - Se sono state usate le procedure di backup di SQL Server, è necessario usare le procedure di ripristino di SQL Server.

  - Se è stato usato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati della chat persistente, è necessario usare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati.

</div>

<span> </span>

</div>

</div>

</div>

