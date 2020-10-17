---
title: Considerazioni sulla coesistenza
description: Considerazioni sulla coesistenza.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd1f9525b37bdee3249e0e47352fdea1bc7f012f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547032"
---
# <a name="coexistence-considerations"></a><span data-ttu-id="a29f1-103">Considerazioni sulla coesistenza</span><span class="sxs-lookup"><span data-stu-id="a29f1-103">Coexistence considerations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a29f1-104">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a29f1-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a29f1-105">Dopo la migrazione, esisterà solo un pool di server Chat persistente di Lync Server 2013 ed è possibile rimuovere le autorizzazioni della distribuzione legacy.</span><span class="sxs-lookup"><span data-stu-id="a29f1-105">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="a29f1-106">Prima del completamento della migrazione e prima di rimuovere completamente la distribuzione di Group Chat Server corrente, è possibile che si disponga di una delle distribuzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a29f1-106">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="a29f1-107">Lync Server 2013, pool di server Chat persistente, che deve essere ospitato in un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a29f1-107">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="a29f1-108">Lync Server 2010, pool di chat di gruppo, che deve essere ospitato in un pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a29f1-108">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="a29f1-109">Pool di chat di gruppo di Office Communications Server 2007 R2, che deve essere ospitato in un pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a29f1-109">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="a29f1-110">Queste distribuzioni possono esistere fianco a fianco.</span><span class="sxs-lookup"><span data-stu-id="a29f1-110">These deployments can exist side by side.</span></span> <span data-ttu-id="a29f1-111">Tuttavia, le categorie, le sale e i componenti aggiuntivi in una distribuzione non interagiscono con quelli nella distribuzione di accompagnamento.</span><span class="sxs-lookup"><span data-stu-id="a29f1-111">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="a29f1-112">Se si utilizza la configurazione manuale, un client legacy (client Group Chat) può connettersi a un pool alla volta per Office Communications Server 2007 R2, Lync Server 2010, Group Chat o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a29f1-112">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="a29f1-113">Lync 2013 (client) è in grado di interagire solo con Lync Server 2013, il pool di server Chat persistente, non con i pool di server di chat di gruppo legacy.</span><span class="sxs-lookup"><span data-stu-id="a29f1-113">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="a29f1-114">Per utilizzare la chat persistente in un Lync 2013 (client), è necessario che l'utente sia ospitato in Lync 2013 e sia abilitato dal criterio.</span><span class="sxs-lookup"><span data-stu-id="a29f1-114">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

