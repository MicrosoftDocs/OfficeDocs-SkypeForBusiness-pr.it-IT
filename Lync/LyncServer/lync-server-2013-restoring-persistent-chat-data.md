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

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="e867f-102">Ripristino dei dati della chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e867f-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e867f-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e867f-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e867f-104">Il contenuto della chat room persistente viene archiviato nel database della chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="e867f-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="e867f-105">Si tratta di dati business-critical di cui eseguire il backup regolarmente.</span><span class="sxs-lookup"><span data-stu-id="e867f-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="e867f-106">Oltre al contenuto della chat room, anche le entità (ad esempio utenti e gruppi) e i ruoli e l'accesso che devono eseguire per la chat room e il contenuto della chat room vengono archiviati nel database della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e867f-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="e867f-107">Il modo in cui ripristinare i dati della chat persistente dipende dal metodo usato per eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="e867f-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="e867f-108">Se sono state usate le procedure di backup di SQL Server, è necessario usare le procedure di ripristino di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e867f-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="e867f-109">Se è stato usato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati della chat persistente, è necessario usare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati.</span><span class="sxs-lookup"><span data-stu-id="e867f-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

