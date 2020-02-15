---
title: 'Lync Server 2013: eliminazione di un messaggio o eliminazione di messaggi obsoleti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb0c960140ebe7474ac7b4b5322f7b42d611af5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>Eliminazione di un messaggio o eliminazione di messaggi obsoleti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Un amministratore di chat persistente può eliminare un messaggio da una chat room persistente (e, facoltativamente, può sostituirlo con un altro messaggio). Gli amministratori possono inoltre eliminare i messaggi durante le operazioni di manutenzione in modo da ridurre l'aumento delle dimensioni del database. Ad esempio, il comando di Windows PowerShell rimuove tutti i messaggi dalla chat room di room ITChatRoom che sono stati pubblicati dall'utente kenmyer@litwareinc.com:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

In questo esempio vengono sostituiti tutti i messaggi rimossi con la nota che il messaggio non è più disponibile:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .

</div>

<span> </span>

</div>

</div>

</div>

