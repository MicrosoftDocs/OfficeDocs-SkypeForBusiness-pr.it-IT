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
ms.openlocfilehash: 91254ecffa70944f867f3df3b69290b52d041305
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="b9720-102">Eliminazione di un messaggio o eliminazione di messaggi obsoleti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9720-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9720-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="b9720-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b9720-104">Un amministratore di chat persistente può eliminare un messaggio da una chat room persistente (e, facoltativamente, può sostituirlo con un altro messaggio).</span><span class="sxs-lookup"><span data-stu-id="b9720-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="b9720-105">Gli amministratori possono inoltre eliminare i messaggi durante le operazioni di manutenzione in modo da ridurre l'aumento delle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="b9720-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="b9720-106">Ad esempio, il comando di Windows PowerShell rimuove tutti i messaggi dalla chat room di room ITChatRoom che sono stati pubblicati dall'utente kenmyer@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b9720-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="b9720-107">In questo esempio vengono sostituiti tutti i messaggi rimossi con la nota che il messaggio non è più disponibile:</span><span class="sxs-lookup"><span data-stu-id="b9720-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="b9720-108">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .</span><span class="sxs-lookup"><span data-stu-id="b9720-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

