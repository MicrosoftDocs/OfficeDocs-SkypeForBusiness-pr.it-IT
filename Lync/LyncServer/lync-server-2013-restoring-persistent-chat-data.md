---
title: 'Lync Server 2013: ripristino dei dati di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78d43cedaec50adac895b143a3643a6a1a1a8a48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Ripristino dei dati di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-18_

Il contenuto della chat persistente viene archiviato nel database di Persistent Chat (MGC. MDF). Si tratta di dati critici per le aziende di cui è necessario eseguire regolarmente il backup. Oltre al contenuto delle chat room, le entità (ad esempio utenti e gruppi) e i ruoli e l'accesso necessari per le chat room e il contenuto delle chat room sono archiviati anche nel database di Persistent Chat.

Il modo in cui si ripristinano i dati della chat persistente dipende dal metodo utilizzato per eseguire il backup.

  - Se sono state utilizzate le procedure di backup di SQL Server, è necessario utilizzare le procedure di ripristino di SQL Server.

  - Se è stato utilizzato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati di Persistent Chat, è necessario utilizzare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati.

</div>

<span> </span>

</div>

</div>

</div>

