---
title: 'Lync Server 2013: disabilitazione o abilitazione di una chat room'
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
ms.openlocfilehash: 55d9c706c0ea5afcff4f249a9c00a2355667f221
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="0cdd5-102">Disabilitazione o abilitazione di una chat room in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cdd5-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cdd5-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="0cdd5-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="0cdd5-104">Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitarla.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="0cdd5-105">Quando si disabilita una chat room, tutti i membri vengono disconnessi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="0cdd5-106">Dopo la disabilitazione di una chat room, gli utenti non possono più parteciparvi né trovarla eseguendo ricerche di chat room.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="0cdd5-107">Una chat room disattivata può essere abilitata in un secondo momento da un amministratore di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="0cdd5-108">Se una chat è disabilitata, il relativo elenco dei membri e le altre impostazioni vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="0cdd5-109">In questo modo, se si decide di riabilitarla, non sarà necessario ricreare manualmente le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="0cdd5-p103">Se è configurata la persistenza della cronologia della chat room, il contenuto verrà mantenuto in caso di disabilitazione della chat room. La persistenza della cronologia della chat room è un'impostazione facoltativa di una categoria e viene applicata a tutte le chat room della categoria. Per impostazione predefinita, la persistenza è abilitata, ma è possibile disabilitarla impostando la proprietà **Abilita cronologia chat** della categoria su false. Se si disabilita una chat room, il contenuto tuttavia non verrà visualizzato nelle ricerche per tutto il tempo in cui la chat room resterà disabilitata. Se successivamente si abilita la chat room, gli utenti potranno ricercare messaggi inseriti prima che la chat room venisse disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-p103">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled. However, that content will not appear in searches during the time that the chat room remains in a disabled state. If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="0cdd5-113">Per informazioni dettagliate sulla disattivazione e l'abilitazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione "gestione sala" in [configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="0cdd5-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="0cdd5-114">Per disabilitare una chat room, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0cdd5-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="0cdd5-115">Per abilitare una chat room, impostare la proprietà Disabled su false:</span><span class="sxs-lookup"><span data-stu-id="0cdd5-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="0cdd5-116">Si noti che le chat room non possono essere abilitate o disabilitate utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="0cdd5-117">Per informazioni dettagliate sulla configurazione delle chat room, vedere [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0cdd5-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

