---
title: Gestire le chat room
description: Gestire le chat room.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be093e14a68639fdde73b58936e1b2f5cf4424cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544592"
---
# <a name="manage-rooms"></a><span data-ttu-id="5216d-103">Gestire le chat room</span><span class="sxs-lookup"><span data-stu-id="5216d-103">Manage rooms</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5216d-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5216d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5216d-105">Per creare una nuova sala del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="5216d-105">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5216d-106">-PersistentChatPoolFqdn non è necessario se si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5216d-106">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="5216d-107">È presente un solo pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5216d-107">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="5216d-108">Si specifica l'FQDN di un pool per la categoria.</span><span class="sxs-lookup"><span data-stu-id="5216d-108">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="5216d-109">Si specifica l'FQDN di un pool per l'aggiunta della chat room.</span><span class="sxs-lookup"><span data-stu-id="5216d-109">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5216d-110">Per apportare modifiche a una stanza del server Chat persistente esistente</span><span class="sxs-lookup"><span data-stu-id="5216d-110">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="5216d-111">Windows PowerShell: i membri, i Manager e i relatori possono essere impostati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="5216d-111">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="5216d-112">Dovrebbero corrispondere tutti al sottoinsieme di AllowedMembers meno DeniedMembers della categoria (Category) host.</span><span class="sxs-lookup"><span data-stu-id="5216d-112">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="5216d-113">Una chat room definita come type=normal non può includere relatori (Presenters).</span><span class="sxs-lookup"><span data-stu-id="5216d-113">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="5216d-114">Creare, ottenere, impostare, cancellare o rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="5216d-114">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="5216d-115">Per creare una nuova chat room</span><span class="sxs-lookup"><span data-stu-id="5216d-115">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="5216d-116">Per impostare una chat room</span><span class="sxs-lookup"><span data-stu-id="5216d-116">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="5216d-117">Per ottenere una chat room</span><span class="sxs-lookup"><span data-stu-id="5216d-117">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="5216d-118">oppure</span><span class="sxs-lookup"><span data-stu-id="5216d-118">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="5216d-119">dove –filter supporta solo Name e Description e consente di trovare chat room in cui Name/Description corrisponde alla stringa della parola chiave.</span><span class="sxs-lookup"><span data-stu-id="5216d-119">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="5216d-120">PoolFqdn esegue la ricerca in un pool di server Chat persistente specificato.</span><span class="sxs-lookup"><span data-stu-id="5216d-120">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="5216d-121">Per cancellare una chat room e per cancellare i messaggi di una chat room</span><span class="sxs-lookup"><span data-stu-id="5216d-121">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="5216d-122">oppure</span><span class="sxs-lookup"><span data-stu-id="5216d-122">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="5216d-123">Per rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="5216d-123">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="5216d-124">oppure</span><span class="sxs-lookup"><span data-stu-id="5216d-124">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

