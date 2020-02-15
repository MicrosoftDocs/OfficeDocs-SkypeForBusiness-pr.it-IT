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

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="63d32-102">Ripristino dei dati di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63d32-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63d32-103">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="63d32-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="63d32-104">Il contenuto della chat persistente viene archiviato nel database di Persistent Chat (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="63d32-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="63d32-105">Si tratta di dati critici per le aziende di cui è necessario eseguire regolarmente il backup.</span><span class="sxs-lookup"><span data-stu-id="63d32-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="63d32-106">Oltre al contenuto delle chat room, le entità (ad esempio utenti e gruppi) e i ruoli e l'accesso necessari per le chat room e il contenuto delle chat room sono archiviati anche nel database di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="63d32-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="63d32-107">Il modo in cui si ripristinano i dati della chat persistente dipende dal metodo utilizzato per eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="63d32-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="63d32-108">Se sono state utilizzate le procedure di backup di SQL Server, è necessario utilizzare le procedure di ripristino di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="63d32-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="63d32-109">Se è stato utilizzato il cmdlet **Export-CsPersistentChatData** per eseguire il backup dei dati di Persistent Chat, è necessario utilizzare il cmdlet **Import-CsPersistentChatData** per ripristinare i dati.</span><span class="sxs-lookup"><span data-stu-id="63d32-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

