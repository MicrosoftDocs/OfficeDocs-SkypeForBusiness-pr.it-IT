---
title: Gestire i componenti aggiuntivi
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 964716509feb0bf1101181693e5ab777de6736ab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a><span data-ttu-id="e7862-102">Gestire i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="e7862-102">Manage add-ins</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7862-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e7862-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e7862-104">Per creare un nuovo componente aggiuntivo di Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="e7862-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="e7862-105">Creare, ottenere, impostare o rimuovere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e7862-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="e7862-106">Per creare un nuovo componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e7862-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7862-107">&lt;La stringa PersistentChatPoolFqdn &gt; è obbligatoria solo se è presente più di un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e7862-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="e7862-108">Per ottenere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e7862-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="e7862-109">oppure</span><span class="sxs-lookup"><span data-stu-id="e7862-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="e7862-110">Per impostare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e7862-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="e7862-111">oppure</span><span class="sxs-lookup"><span data-stu-id="e7862-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="e7862-112">Per rimuovere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="e7862-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="e7862-113">oppure</span><span class="sxs-lookup"><span data-stu-id="e7862-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

