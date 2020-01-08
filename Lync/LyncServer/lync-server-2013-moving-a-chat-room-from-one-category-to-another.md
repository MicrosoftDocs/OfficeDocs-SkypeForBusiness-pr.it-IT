---
title: "Lync Server 2013: Spostamento di una chat room da una categoria all'altra"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="d2711-102">Spostamento di una chat room da una categoria all'altra in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2711-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2711-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d2711-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d2711-104">È consigliabile non modificare la categoria di una chat room persistente dopo la creazione della chat room.</span><span class="sxs-lookup"><span data-stu-id="d2711-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="d2711-105">Tuttavia, se il responsabile della chat room ha privilegi di **autore** in un'altra categoria, può trasferire la sala da una categoria a un'altra.</span><span class="sxs-lookup"><span data-stu-id="d2711-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="d2711-106">La sala non viene eliminata e ricreata.</span><span class="sxs-lookup"><span data-stu-id="d2711-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="d2711-107">Si tratta di un cambiamento di associazione all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="d2711-107">It is a change of association within the database.</span></span>

<span data-ttu-id="d2711-108">La modifica di una categoria di chat room deve essere eseguita raramente.</span><span class="sxs-lookup"><span data-stu-id="d2711-108">Changing a chat room category should be done rarely.</span></span> <span data-ttu-id="d2711-109">Una categoria determina l'appartenenza consentita per la chat room, quindi quando una chat room viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso di sistema (SACL) che non sono più supportati dalla nuova categoria vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="d2711-109">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="d2711-110">Ad esempio, se un utente è stato un membro della chat room e non è più un **AllowedMember** nella nuova categoria, l'appartenenza alla sala verrà modificata e l'utente verrà rimosso dalla sala.</span><span class="sxs-lookup"><span data-stu-id="d2711-110">For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="d2711-111">Per informazioni dettagliate sullo spostamento di una chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" in [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="d2711-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="d2711-112">Per informazioni dettagliate sulla configurazione delle chat room, vedere [configurare le sale in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d2711-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

