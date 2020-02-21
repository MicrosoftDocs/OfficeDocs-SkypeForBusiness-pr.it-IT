---
title: "Lync Server 2013: spostamento di una chat room da una categoria all'altra"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27ca186fa31b1207238c3a7d254bbd6066cc1d89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="3e47f-102">Spostamento di una chat room da una categoria all'altra in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e47f-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e47f-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3e47f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3e47f-104">Si consiglia di non modificare la categoria di una chat room persistente dopo la creazione della chat room.</span><span class="sxs-lookup"><span data-stu-id="3e47f-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="3e47f-105">Tuttavia, se il responsabile della chat room ha privilegi di **creatore** in un'altra categoria, può spostare la sala da una categoria all'altra.</span><span class="sxs-lookup"><span data-stu-id="3e47f-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="3e47f-106">La sala non viene eliminata e ricreata.</span><span class="sxs-lookup"><span data-stu-id="3e47f-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="3e47f-107">Si tratta di un cambiamento di associazione all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="3e47f-107">It is a change of association within the database.</span></span>

<span data-ttu-id="3e47f-p102">La modifica della categoria di una chat room deve essere un'operazione eseguita raramente. Una categoria determina i membri a cui è consentito accedere alla chat room; se questa viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso del sistema (SACL) non supportati dalla nuova categoria vengono eliminati. Ad esempio, se un utente membro di una chat room non è più un **AllowedMember** nella nuova categoria, l'appartenenza alla chat risulterà modificata, e l'utente non avrà più accesso alla chat room.</span><span class="sxs-lookup"><span data-stu-id="3e47f-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="3e47f-111">Per informazioni dettagliate sullo spostamento di una chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione relativa alla gestione delle chat room in [Configuring Persistent chatroom server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="3e47f-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="3e47f-112">Per informazioni dettagliate sulla configurazione delle chat room, vedere [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3e47f-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

