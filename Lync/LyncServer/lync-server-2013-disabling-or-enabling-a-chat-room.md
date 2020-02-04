---
title: 'Lync Server 2013: Disabilitazione o abilitazione di una chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3ed23319631dd8ab51131fe9a8d7a9099e35d18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="4d12a-102">Disabilitazione o abilitazione di una chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d12a-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d12a-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4d12a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4d12a-104">Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitando il problema.</span><span class="sxs-lookup"><span data-stu-id="4d12a-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="4d12a-105">Quando una chat room è disabilitata, tutti i membri vengono immediatamente disconnessi dalla sala.</span><span class="sxs-lookup"><span data-stu-id="4d12a-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="4d12a-106">Dopo la disattivazione di una chat room, gli utenti non possono raggiungerla o trovarla nelle ricerche in chat room.</span><span class="sxs-lookup"><span data-stu-id="4d12a-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="4d12a-107">Una chat room disabilitata può essere abilitata in seguito da un amministratore della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4d12a-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="4d12a-108">Se una chat room è disabilitata, viene mantenuta l'elenco di appartenenza e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4d12a-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="4d12a-109">Se si abilita di nuovo la chat room, non è necessario ricreare manualmente le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4d12a-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="4d12a-110">Se la cronologia della chat room persiste (la persistenza della cronologia delle chat room è un'impostazione facoltativa per una categoria che si applica a tutte le camere all'interno della categoria; l'impostazione predefinita è che viene mantenuta, ma può essere disattivata impostando la **cronologia della chat di Enable** della categoria su false), il contenuto viene mantenuto quando la chat room è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4d12a-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="4d12a-111">Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo di permanenza della chat room in uno stato disabilitato.</span><span class="sxs-lookup"><span data-stu-id="4d12a-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="4d12a-112">Se in seguito si Abilita la chat room, gli utenti possono cercare i messaggi inviati prima della disattivazione della chat room.</span><span class="sxs-lookup"><span data-stu-id="4d12a-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="4d12a-113">Per informazioni dettagliate sulla disabilitazione e l'abilitazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="4d12a-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="4d12a-114">Per disabilitare una chat room, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4d12a-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="4d12a-115">Per abilitare una chat room, imposta la proprietà Disabled su false:</span><span class="sxs-lookup"><span data-stu-id="4d12a-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="4d12a-116">Tieni presente che le chat room non possono essere abilitate o disabilitate usando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d12a-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="4d12a-117">Per informazioni dettagliate sulla configurazione delle chat room, vedere [configurare le sale in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d12a-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

