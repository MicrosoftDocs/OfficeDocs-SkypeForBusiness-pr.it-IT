---
title: Gestire le categorie
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87dee81fa0a8b51b3d3834b0ad8cca4e18b321e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506303"
---
# <a name="manage-categories"></a><span data-ttu-id="0cc62-102">Gestire le categorie</span><span class="sxs-lookup"><span data-stu-id="0cc62-102">Manage categories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cc62-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0cc62-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0cc62-104">Per creare una nuova categoria del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="0cc62-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0cc62-105">PersistentChatPoolFqdn è necessario solo se è presente più di un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0cc62-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="0cc62-106">Per apportare modifiche alla categoria del server Chat persistente esistente</span><span class="sxs-lookup"><span data-stu-id="0cc62-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="0cc62-107">Windows PowerShell: AllowedMembers, DeniedMembers e Creator possono essere impostati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0cc62-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="0cc62-108">Creators sarà il sottoinsieme di AllowedMembers meno DeniedMembers.</span><span class="sxs-lookup"><span data-stu-id="0cc62-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="0cc62-109">È inoltre possibile impostare le proprietà di una categoria contemporaneamente ai membri e agli autori.</span><span class="sxs-lookup"><span data-stu-id="0cc62-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="0cc62-110">Creare, ottenere, impostare o rimuovere una categoria</span><span class="sxs-lookup"><span data-stu-id="0cc62-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="0cc62-111">Per creare una nuova categoria</span><span class="sxs-lookup"><span data-stu-id="0cc62-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="0cc62-112">Per ottenere una categoria</span><span class="sxs-lookup"><span data-stu-id="0cc62-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="0cc62-113">oppure</span><span class="sxs-lookup"><span data-stu-id="0cc62-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="0cc62-114">Per impostare una categoria</span><span class="sxs-lookup"><span data-stu-id="0cc62-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="0cc62-115">oppure</span><span class="sxs-lookup"><span data-stu-id="0cc62-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="0cc62-116">Per rimuovere una categoria</span><span class="sxs-lookup"><span data-stu-id="0cc62-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="0cc62-117">oppure</span><span class="sxs-lookup"><span data-stu-id="0cc62-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

