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

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="f7beb-102">Backup di database di chat persistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7beb-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7beb-103">_**Argomento Ultima modifica:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f7beb-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f7beb-104">Il contenuto della chat room persistente viene archiviato nel database della chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="f7beb-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="f7beb-105">Si tratta di dati business-critical di cui eseguire il backup regolarmente.</span><span class="sxs-lookup"><span data-stu-id="f7beb-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="f7beb-106">Oltre al contenuto della chat room, il database della chat persistente memorizza anche informazioni sulle entità (ad esempio utenti e gruppi utente) e sui ruoli e l'accesso necessari per la chat room e la sala chat.</span><span class="sxs-lookup"><span data-stu-id="f7beb-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="f7beb-107">Esistono due modi per eseguire il backup dei dati della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f7beb-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="f7beb-108">Backup di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f7beb-108">SQL Server Backup</span></span>

  - <span data-ttu-id="f7beb-109">Il `Export-CsPersistentChatData` cmdlet, che esporta i dati della chat persistente come file</span><span class="sxs-lookup"><span data-stu-id="f7beb-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="f7beb-110">I dati creati con SQL Server backup richiedono molto più spazio su disco, possibilmente 20 volte di più rispetto a quello creato `Export-CsPersistentChatData`da, ma è più probabile che SQL Server backup sia una procedura che gli amministratori hanno familiarità con.</span><span class="sxs-lookup"><span data-stu-id="f7beb-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

