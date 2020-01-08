---
title: Considerazioni sulla coesistenza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc2889a11f6cc0afaecd7adf35bc16075011fef9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40975782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="88688-102">Considerazioni sulla coesistenza</span><span class="sxs-lookup"><span data-stu-id="88688-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88688-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="88688-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="88688-104">Dopo la migrazione, esisterà solo un Lync Server 2013, il pool di server di chat persistente e sarà possibile rimuovere la Commissione dalla distribuzione legacy.</span><span class="sxs-lookup"><span data-stu-id="88688-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="88688-105">Prima che la migrazione venga completata e prima di aver disattivato completamente la distribuzione del server di chat di gruppo corrente, è possibile che si disponga di una delle distribuzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88688-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="88688-106">Lync Server 2013, pool di server di chat persistente, che deve essere ospitato in un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88688-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="88688-107">Lync Server 2010, pool di chat di gruppo, che deve essere ospitato in un pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="88688-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="88688-108">Pool di chat di gruppo di Office Communications Server 2007 R2, che deve essere ospitato in un pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="88688-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="88688-109">Queste distribuzioni possono essere affiancate.</span><span class="sxs-lookup"><span data-stu-id="88688-109">These deployments can exist side by side.</span></span> <span data-ttu-id="88688-110">Tuttavia, le categorie, le sale e i componenti aggiuntivi di una distribuzione non interagiscono con quelli della distribuzione che lo accompagna.</span><span class="sxs-lookup"><span data-stu-id="88688-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="88688-111">Usando la configurazione manuale, un client legacy (client di chat di gruppo) può connettersi a un pool alla volta per Office Communications Server 2007 R2, Lync Server 2010, Group Chat o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88688-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="88688-112">Lync 2013 (client) può interagire solo con Lync Server 2013, il pool di server di chat persistente, non con i pool di server di chat di gruppo legacy.</span><span class="sxs-lookup"><span data-stu-id="88688-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="88688-113">Per usare la chat persistente in un Lync 2013 (client), l'utente deve essere ospitato in Lync 2013 e abilitato per criteri.</span><span class="sxs-lookup"><span data-stu-id="88688-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

