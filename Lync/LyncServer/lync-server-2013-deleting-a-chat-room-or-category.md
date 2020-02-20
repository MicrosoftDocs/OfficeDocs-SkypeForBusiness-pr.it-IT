---
title: 'Lync Server 2013: eliminazione di una chat room o una categoria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4e346d33e44a9365d9cf4924374c2a28b8b908
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="41654-102">Eliminazione di una chat room o di una categoria in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41654-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41654-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="41654-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="41654-104">È possibile eliminare le chat room permanenti.</span><span class="sxs-lookup"><span data-stu-id="41654-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="41654-105">Se una chat room non viene più utilizzata, è possibile disabilitarla.</span><span class="sxs-lookup"><span data-stu-id="41654-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="41654-106">Per informazioni dettagliate, vedere [disattivazione o abilitazione di una chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="41654-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="41654-107">Un amministratore di chat persistente può eseguire query per le chat room disabilitate e può periodicamente eliminare e cancellare definitivamente le chat room utilizzando il cmdlet di Windows PowerShell **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="41654-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="41654-108">Le categorie possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="41654-108">Categories can be deleted.</span></span> <span data-ttu-id="41654-109">Tuttavia, per eliminare una categoria, è prima necessario eliminare tutte le chat room che appartengono a essa oppure spostare le chat room in una nuova categoria, lasciando una categoria vuota per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="41654-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="41654-110">Il server Chat persistente non consente di eliminare una categoria contenente chat room.</span><span class="sxs-lookup"><span data-stu-id="41654-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="41654-111">Per informazioni dettagliate, vedere [spostamento di una chat room da una categoria all'altra in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="41654-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="41654-112">Per informazioni dettagliate sull'eliminazione di categorie vuote tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione relativa alla gestione delle chat room in [Configuring Persistent chatroom server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="41654-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="41654-113">Per informazioni dettagliate sulle chat room e sulle categorie, vedere [Configure rooms in Lync server 2013](lync-server-2013-configure-rooms.md) e [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="41654-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

