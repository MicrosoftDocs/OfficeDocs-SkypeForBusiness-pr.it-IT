---
title: 'Lync Server 2013: backup dei database di chat persistente'
description: 'Lync Server 2013: backup dei database di chat persistente.'
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
ms.openlocfilehash: 9885eaf0065f5b558922c056fb1f669a5b821460
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563292"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="9d658-103">Backup dei database di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d658-103">Backing up Persistent Chat databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d658-104">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="9d658-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="9d658-105">Il contenuto della chat persistente viene archiviato nel database di Persistent Chat (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="9d658-105">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="9d658-106">Si tratta di dati critici per le aziende di cui è necessario eseguire regolarmente il backup.</span><span class="sxs-lookup"><span data-stu-id="9d658-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="9d658-107">Oltre al contenuto delle chat room, il database di Persistent Chat memorizza anche informazioni sulle entità (ad esempio, utenti e gruppi utenti) e sui ruoli e l'accesso necessari per le chat room e la chat.</span><span class="sxs-lookup"><span data-stu-id="9d658-107">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="9d658-108">Sono disponibili due modi per eseguire il backup dei dati di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="9d658-108">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="9d658-109">Backup di SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d658-109">SQL Server Backup</span></span>

  - <span data-ttu-id="9d658-110">Il `Export-CsPersistentChatData` cmdlet, che esporta i dati della chat persistente come file</span><span class="sxs-lookup"><span data-stu-id="9d658-110">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="9d658-111">I dati creati utilizzando il backup di SQL Server richiedono molto più spazio su disco, possibilmente 20 volte di più, rispetto a quello creato da `Export-CsPersistentChatData` , ma il backup di SQL Server è più probabile che sia una procedura che gli amministratori hanno familiarità con.</span><span class="sxs-lookup"><span data-stu-id="9d658-111">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

