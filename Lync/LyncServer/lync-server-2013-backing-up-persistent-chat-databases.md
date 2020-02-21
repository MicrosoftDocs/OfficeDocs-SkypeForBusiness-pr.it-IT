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
ms.openlocfilehash: 218c011d2acc970028bfd0be529d89542d684758
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="f84a1-102">Backup dei database di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f84a1-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f84a1-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f84a1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f84a1-104">Il contenuto della chat persistente viene archiviato nel database di Persistent Chat (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="f84a1-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="f84a1-105">Si tratta di dati critici per le aziende di cui è necessario eseguire regolarmente il backup.</span><span class="sxs-lookup"><span data-stu-id="f84a1-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="f84a1-106">Oltre al contenuto delle chat room, il database di Persistent Chat memorizza anche informazioni sulle entità (ad esempio, utenti e gruppi utenti) e sui ruoli e l'accesso necessari per le chat room e la chat.</span><span class="sxs-lookup"><span data-stu-id="f84a1-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="f84a1-107">Sono disponibili due modi per eseguire il backup dei dati di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="f84a1-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="f84a1-108">Backup di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f84a1-108">SQL Server Backup</span></span>

  - <span data-ttu-id="f84a1-109">Il `Export-CsPersistentChatData` cmdlet, che esporta i dati della chat persistente come file</span><span class="sxs-lookup"><span data-stu-id="f84a1-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="f84a1-110">I dati creati utilizzando il backup di SQL Server richiedono molto più spazio su disco, possibilmente 20 volte di più, rispetto `Export-CsPersistentChatData`a quello creato da, ma il backup di SQL Server è più probabile che sia una procedura che gli amministratori hanno familiarità con.</span><span class="sxs-lookup"><span data-stu-id="f84a1-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

