---
title: 'Lync Server 2013: Considerazioni sulla migrazione e la coesistenza per IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5785b270aa3070c2b1592112ab4d5ae582e52bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="f83b4-102">Considerazioni sulla migrazione e la coesistenza per IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f83b4-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f83b4-103">_**Argomento Ultima modifica:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="f83b4-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="f83b4-104">IP versione 6 (IPv6) non è supportato in Lync Server 2010 o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="f83b4-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="f83b4-105">Per scopi di pilotaggio, è possibile testare la coesistenza di Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f83b4-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="f83b4-106">È consigliabile che tutti i pool per un sito centrale specifico vengano aggiornati a Lync Server 2013 prima di abilitare IPv6 (rete dual-stack) per uno dei pool.</span><span class="sxs-lookup"><span data-stu-id="f83b4-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="f83b4-107">Se è necessario configurare solo un pool per IPv6, è consigliabile configurare un pool solo IPv6 nell'ambiente lab per i test.</span><span class="sxs-lookup"><span data-stu-id="f83b4-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="f83b4-108">Gli scenari seguenti sono supportati durante la migrazione e la coesistenza:</span><span class="sxs-lookup"><span data-stu-id="f83b4-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="f83b4-109">Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2 pool in modalità IPv4, che coesiste con Lync Server 2013 in modalità a doppio stack.</span><span class="sxs-lookup"><span data-stu-id="f83b4-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="f83b4-110">Pool di Lync Server 2013 in modalità solo IPv6, se il pool solo IPv6 è siloed.</span><span class="sxs-lookup"><span data-stu-id="f83b4-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

