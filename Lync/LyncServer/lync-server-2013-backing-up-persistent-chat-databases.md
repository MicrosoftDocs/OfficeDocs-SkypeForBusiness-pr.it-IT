---
title: 'Lync Server 2013: backup di database di chat persistenti'
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
ms.openlocfilehash: f186552b9e0d5c78d0f40416cd92e41d5705e93a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Backup di database di chat persistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-17_

Il contenuto della chat room persistente viene archiviato nel database della chat persistente (MGC. MDF). Si tratta di dati business-critical di cui eseguire il backup regolarmente. Oltre al contenuto della chat room, il database della chat persistente memorizza anche informazioni sulle entità (ad esempio utenti e gruppi utente) e sui ruoli e l'accesso necessari per la chat room e la sala chat.

Esistono due modi per eseguire il backup dei dati della chat persistente.

  - Backup di SQL Server

  - Il `Export-CsPersistentChatData` cmdlet, che esporta i dati della chat persistente come file

I dati creati con SQL Server backup richiedono molto più spazio su disco, possibilmente 20 volte di più rispetto a quello creato `Export-CsPersistentChatData`da, ma è più probabile che SQL Server backup sia una procedura che gli amministratori hanno familiarità con.

</div>

<span> </span>

</div>

</div>

</div>

