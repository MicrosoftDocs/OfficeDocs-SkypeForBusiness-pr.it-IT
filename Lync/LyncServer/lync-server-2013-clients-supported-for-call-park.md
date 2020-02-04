---
title: 'Lync Server 2013: Client supportati per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52304a0241425a3b88c7f9419afa57f3d768fbb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="ab9a3-102">Client supportati per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab9a3-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab9a3-103">_**Argomento Ultima modifica:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="ab9a3-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="ab9a3-104">Questa sezione identifica i client che possono essere usati per parcheggiare le chiamate e i client che possono essere usati per recuperare le chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="ab9a3-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="ab9a3-105">Client supportati per le chiamate di parcheggio</span><span class="sxs-lookup"><span data-stu-id="ab9a3-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="ab9a3-106">Le chiamate da qualsiasi IP, PBX (Private Branch Exchange), PSTN (Public Switched Telephone Network) o cellulare possono essere parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="ab9a3-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab9a3-107">Solo le chiamate audio possono essere parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="ab9a3-107">Only audio calls can be parked.</span></span> <span data-ttu-id="ab9a3-108">I messaggi istantanei e le conferenze non possono essere parcheggiati.</span><span class="sxs-lookup"><span data-stu-id="ab9a3-108">Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="ab9a3-109">I client seguenti possono usare Call Park per parcheggiare le chiamate:</span><span class="sxs-lookup"><span data-stu-id="ab9a3-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="ab9a3-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ab9a3-110">Lync 2013</span></span>

  - <span data-ttu-id="ab9a3-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ab9a3-111">Lync 2010</span></span>

  - <span data-ttu-id="ab9a3-112">Assistente di Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ab9a3-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="ab9a3-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ab9a3-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab9a3-114">I telefoni cellulari non possono usare Call Park per parcheggiare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="ab9a3-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="ab9a3-115">Client supportati per il recupero delle chiamate</span><span class="sxs-lookup"><span data-stu-id="ab9a3-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="ab9a3-116">Gli intervalli di Orbit sono configurati come blocchi di estensioni virtuali (estensioni senza un utente o un telefono assegnato).</span><span class="sxs-lookup"><span data-stu-id="ab9a3-116">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone).</span></span> <span data-ttu-id="ab9a3-117">Quando si configurano le orbite come estensioni virtuali, i telefoni cellulari e i telefoni PSTN non possono recuperare chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="ab9a3-117">When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="ab9a3-118">Gli utenti federati non possono recuperare chiamate parcheggiate.</span><span class="sxs-lookup"><span data-stu-id="ab9a3-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="ab9a3-119">I client seguenti possono recuperare le chiamate parcheggiate su Call Park:</span><span class="sxs-lookup"><span data-stu-id="ab9a3-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="ab9a3-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ab9a3-120">Lync 2013</span></span>

  - <span data-ttu-id="ab9a3-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ab9a3-121">Lync 2010</span></span>

  - <span data-ttu-id="ab9a3-122">Assistente di Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ab9a3-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="ab9a3-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ab9a3-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="ab9a3-124">Telefoni di area comune IP</span><span class="sxs-lookup"><span data-stu-id="ab9a3-124">IP common area phones</span></span>

  - <span data-ttu-id="ab9a3-125">Telefoni non IP connessi all'infrastruttura di Lync Server 2013, inclusi i telefoni delle aree comuni e i telefoni PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="ab9a3-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

