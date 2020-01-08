---
title: 'Lync Server 2013: assegnazione di criteri per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9088326d5d7a11bd186a594327eb083df590849
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="e38ec-102">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e38ec-103">_**Argomento Ultima modifica:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="e38ec-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="e38ec-104">È possibile assegnare determinati criteri a un utente o a un gruppo di utenti per specificare determinate impostazioni che deviano dalle impostazioni definite nei criteri assegnati ad altri utenti, ad esempio i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="e38ec-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="e38ec-105">Questi criteri sono definiti criteri per utente.</span><span class="sxs-lookup"><span data-stu-id="e38ec-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e38ec-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e38ec-106">In This Section</span></span>

  - [<span data-ttu-id="e38ec-107">Assegnare criteri di conferenza per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="e38ec-108">Assegnare criteri di versione client per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="e38ec-109">Assegnare un criterio PIN per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="e38ec-110">Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="e38ec-111">Assegnare criteri di archiviazione per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="e38ec-112">Assegnare criteri di posizione per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="e38ec-113">Assegnare un criterio di mobilità per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="e38ec-114">Assegnare criteri per la chat persistente per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="e38ec-115">Assegnare un criterio di dial plan per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="e38ec-116">Assegnare un criterio vocale per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e38ec-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e38ec-117">See Also</span></span>


[<span data-ttu-id="e38ec-118">Gestione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38ec-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

