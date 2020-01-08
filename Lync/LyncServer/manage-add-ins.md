---
title: Gestire i componenti aggiuntivi
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef4586d0d84d53173f5e27fc504a9911905f1dd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a><span data-ttu-id="b0c82-102">Gestire i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="b0c82-102">Manage add-ins</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0c82-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b0c82-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b0c82-104">Per creare un nuovo componente aggiuntivo Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="b0c82-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="b0c82-105">Creare, ottenere, impostare o rimuovere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b0c82-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="b0c82-106">Per creare un nuovo componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b0c82-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b0c82-107">La &lt;stringa&gt; PersistentChatPoolFqdn è obbligatoria solo se è presente più di un pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b0c82-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="b0c82-108">Per ottenere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b0c82-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="b0c82-109">o</span><span class="sxs-lookup"><span data-stu-id="b0c82-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="b0c82-110">Per impostare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b0c82-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="b0c82-111">o</span><span class="sxs-lookup"><span data-stu-id="b0c82-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="b0c82-112">Per rimuovere un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b0c82-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="b0c82-113">o</span><span class="sxs-lookup"><span data-stu-id="b0c82-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

