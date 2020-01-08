---
title: Gestire le chat room
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f611b3cb6d54711557c8a172b1213127696c9b3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="7f77f-102">Gestire le chat room</span><span class="sxs-lookup"><span data-stu-id="7f77f-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f77f-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7f77f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7f77f-104">Per creare una nuova sala server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="7f77f-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f77f-105">-PersistentChatPoolFqdn non è necessario se una delle opzioni seguenti è vera:</span><span class="sxs-lookup"><span data-stu-id="7f77f-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="7f77f-106">Esiste un solo pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7f77f-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="7f77f-107">Fornisci un nome di dominio completo del pool alla categoria.</span><span class="sxs-lookup"><span data-stu-id="7f77f-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="7f77f-108">Puoi specificare un nome di dominio completo del pool per l'aggiunta della chat room.</span><span class="sxs-lookup"><span data-stu-id="7f77f-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="7f77f-109">Per apportare modifiche a una sala del server di chat persistente esistente</span><span class="sxs-lookup"><span data-stu-id="7f77f-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="7f77f-110">Windows PowerShell: i membri, i Manager e i relatori possono essere impostati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="7f77f-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="7f77f-111">Tutti devono essere il sottoinsieme di AllowedMembers meno DeniedMembers della categoria host.</span><span class="sxs-lookup"><span data-stu-id="7f77f-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="7f77f-112">Una sala di tipo = normale non può includere relatori.</span><span class="sxs-lookup"><span data-stu-id="7f77f-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="7f77f-113">Creare, ottenere, impostare, cancellare o rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="7f77f-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="7f77f-114">Per creare una nuova sala</span><span class="sxs-lookup"><span data-stu-id="7f77f-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="7f77f-115">Per impostare una sala</span><span class="sxs-lookup"><span data-stu-id="7f77f-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="7f77f-116">Per ottenere una chat room</span><span class="sxs-lookup"><span data-stu-id="7f77f-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="7f77f-117">o</span><span class="sxs-lookup"><span data-stu-id="7f77f-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="7f77f-118">Where: Filter supporta solo il nome e la descrizione e consente di trovare le camere il cui nome/descrizione corrisponde alla stringa della parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7f77f-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="7f77f-119">PoolFqdn Cerca in un pool di server di chat persistente specifico.</span><span class="sxs-lookup"><span data-stu-id="7f77f-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="7f77f-120">Per cancellare una chat room e cancellare i messaggi da una chat room</span><span class="sxs-lookup"><span data-stu-id="7f77f-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="7f77f-121">o</span><span class="sxs-lookup"><span data-stu-id="7f77f-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="7f77f-122">Per rimuovere una chat room</span><span class="sxs-lookup"><span data-stu-id="7f77f-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="7f77f-123">o</span><span class="sxs-lookup"><span data-stu-id="7f77f-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

