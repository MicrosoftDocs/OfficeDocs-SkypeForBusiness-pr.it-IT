---
title: "Lync Server 2013: assegnazione dell'ambito dei criteri di posizione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395b8a4271338231b4c2c1927f7e40fb21a1cb14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="158fc-102">Assegnazione dell'ambito dei criteri di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="158fc-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="158fc-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="158fc-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="158fc-104">Come per altri criteri di Lync Server, i criteri di posizione possono essere assegnati a più livelli di ambito: globale, sito e utente.</span><span class="sxs-lookup"><span data-stu-id="158fc-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="158fc-105">Tuttavia, l'ambito dei criteri di posizione a livello di utente si comporta in modo leggermente diverso rispetto a quello di altri criteri di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="158fc-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="158fc-106">Non solo i criteri di posizione per utente possono essere applicati agli oggetti endpoint, ad esempio gli utenti e gli oggetti dei contatti telefonici di area comune, ma possono essere applicati anche ai siti di rete di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="158fc-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="158fc-107">I siti di rete sono raggruppamenti di subnet client associati a una posizione geografica (ma potrebbero non essere necessariamente tutte le subnet di un intero sito centrale o di un sito di succursale).</span><span class="sxs-lookup"><span data-stu-id="158fc-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="158fc-108">Tutti i client connessi alle subnet in un sito di rete prelevano automaticamente i criteri di posizione assegnati al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="158fc-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="158fc-109">Nei casi in cui un criterio di posizione a livello di utente viene assegnato sia a un utente che a un sito di rete, il criterio di posizione basato sul sito di rete sostituisce qualsiasi impostazione di criteri per utente.</span><span class="sxs-lookup"><span data-stu-id="158fc-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="158fc-110">A ogni sito di rete è assegnato un criterio di posizione e ogni criterio avrà diversi usi PSTN, URI di notifica e valori degli URI di conferenza assegnati.</span><span class="sxs-lookup"><span data-stu-id="158fc-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="158fc-111">Il motivo di questo comportamento speciale per l'ambito dei criteri è che quando un utente ospitato in un pool di un sito di Office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate di E9-1-1 appropriate per il sito di rete verranno applicate indipendentemente dal pool o dal sito che si usa viene assegnato a ser.</span><span class="sxs-lookup"><span data-stu-id="158fc-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

