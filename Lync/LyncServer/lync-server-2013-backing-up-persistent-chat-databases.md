---
title: 'Lync Server 2013: backup dei database di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dc1f448c248f80bfcc636c900b6601fda4aa200
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Backup dei database di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-17_

Il contenuto della chat persistente viene archiviato nel database di Persistent Chat (MGC. MDF). Si tratta di dati critici per le aziende di cui è necessario eseguire regolarmente il backup. Oltre al contenuto delle chat room, il database di Persistent Chat memorizza anche informazioni sulle entità (ad esempio, utenti e gruppi utenti) e sui ruoli e l'accesso necessari per le chat room e la chat.

Sono disponibili due modi per eseguire il backup dei dati di Persistent Chat.

  - Backup di SQL Server

  - Il `Export-CsPersistentChatData` cmdlet, che esporta i dati della chat persistente come file

I dati creati utilizzando il backup di SQL Server richiedono molto più spazio su disco, possibilmente 20 volte di più, rispetto `Export-CsPersistentChatData`a quello creato da, ma il backup di SQL Server è più probabile che sia una procedura che gli amministratori hanno familiarità con.

</div>

<span> </span>

</div>

</div>

</div>

