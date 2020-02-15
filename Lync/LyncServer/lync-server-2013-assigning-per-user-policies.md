---
title: 'Lync Server 2013: assegnazione di criteri per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e9b5780b17ad2ed7a057979f77e504fb1fca0db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="5a1e7-102">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a1e7-103">_**Ultimo argomento modificato:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="5a1e7-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="5a1e7-p101">È possibile assegnare alcuni criteri a un utente o a un gruppo di utenti per definire impostazioni specifiche che deviano dalle impostazioni definite nei criteri assegnati ad altri utenti, ad esempio i criteri globali. Questi criteri sono denominati criteri per utente.</span><span class="sxs-lookup"><span data-stu-id="5a1e7-p101">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies. These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a1e7-106">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="5a1e7-106">In This Section</span></span>

  - [<span data-ttu-id="5a1e7-107">Assegnazione di un criterio di conferenza per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="5a1e7-108">Assegnare criteri di versione client per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="5a1e7-109">Assegnare un criterio PIN per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="5a1e7-110">Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="5a1e7-111">Assegnare criteri di archiviazione per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="5a1e7-112">Assegnare un criterio percorso per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="5a1e7-113">Assegnare un criterio per dispositivi mobili per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="5a1e7-114">Assegnazione di criteri di chat persistente per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="5a1e7-115">Assegnare un criterio di dial plan per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="5a1e7-116">Assegnare un criterio vocale per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a1e7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a1e7-117">See Also</span></span>


[<span data-ttu-id="5a1e7-118">Gestione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a1e7-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

