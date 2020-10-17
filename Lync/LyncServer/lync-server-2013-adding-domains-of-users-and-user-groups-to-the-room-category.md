---
title: 'Lync Server 2013: aggiunta di domini di utenti e gruppi utente alla categoria della chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f330f05f6b47a147e8b0b8f97948870305a890c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521313"
---
# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="a6a7b-102">Aggiunta di domini di utenti e gruppi utente alla categoria della chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6a7b-102">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6a7b-103">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="a6a7b-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="a6a7b-104">Per aggiungere gruppi di utenti di grandi dimensioni a una chat room, vedere [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) e [Manage Categories](manage-categories.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a6a7b-104">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="a6a7b-105">Ad esempio, questo comando aggiunge tutti gli utenti dall'unità organizzativa NorthAmericaUsers in Active Directory alla chat room di NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="a6a7b-105">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="a6a7b-106">Il comando aggiunge tutti i membri del gruppo di distribuzione Finance alla stessa chat room:</span><span class="sxs-lookup"><span data-stu-id="a6a7b-106">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

