---
title: 'Lync Server 2013: Eliminazione di una chat room o una categoria'
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
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="bf2d1-102">Eliminazione di una chat room o una categoria in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2d1-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf2d1-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf2d1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf2d1-104">Le chat room permanenti possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="bf2d1-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="bf2d1-105">Se si ha una chat room che non viene più usata, è possibile disabilitarla.</span><span class="sxs-lookup"><span data-stu-id="bf2d1-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="bf2d1-106">Per informazioni dettagliate, vedere [disabilitazione o abilitazione di una chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="bf2d1-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="bf2d1-107">Un amministratore della chat persistente può eseguire query per le chat room disattivate e può periodicamente eliminare e cancellare definitivamente le chat room usando il cmdlet di Windows PowerShell **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="bf2d1-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="bf2d1-108">Le categorie possono essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="bf2d1-108">Categories can be deleted.</span></span> <span data-ttu-id="bf2d1-109">Tuttavia, per eliminare una categoria, è prima necessario eliminare tutte le chat room o spostarle in una nuova categoria, lasciando una categoria vuota per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="bf2d1-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="bf2d1-110">Il server di chat persistente non consente di eliminare una categoria che contiene chat room.</span><span class="sxs-lookup"><span data-stu-id="bf2d1-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="bf2d1-111">Per informazioni dettagliate, vedere [spostamento di una chat room da una categoria a un'altra in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="bf2d1-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="bf2d1-112">Per informazioni dettagliate sull'eliminazione di categorie vuote tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="bf2d1-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="bf2d1-113">Per informazioni dettagliate sulle chat room e le categorie, vedere [configurare le camere in Lync server 2013](lync-server-2013-configure-rooms.md) e [configurare le categorie in Lync Server 2013](lync-server-2013-configure-categories.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bf2d1-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

