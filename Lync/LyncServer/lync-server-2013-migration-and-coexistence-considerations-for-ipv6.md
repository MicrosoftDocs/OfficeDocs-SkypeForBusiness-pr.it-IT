---
title: 'Lync Server 2013: considerazioni sulla migrazione e la coesistenza per IPv6'
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
ms.openlocfilehash: 3f4a042089c0961eb8ea8313b78bbfcafa72c999
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="24450-102">Considerazioni sulla migrazione e la coesistenza per IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24450-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24450-103">_**Ultimo argomento modificato:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="24450-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="24450-104">IP versione 6 (IPv6) non è supportato in Lync Server 2010 o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="24450-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="24450-105">A scopo di pilotaggio, è possibile testare Lync Server 2010 e Lync Server 2013 dual-stack coesistenza.</span><span class="sxs-lookup"><span data-stu-id="24450-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="24450-106">È consigliabile che tutti i pool di un determinato sito centrale vengano aggiornati a Lync Server 2013 prima di abilitare IPv6 (dual-stack Network) per uno qualsiasi dei pool.</span><span class="sxs-lookup"><span data-stu-id="24450-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="24450-107">Se è necessario configurare un pool solo per IPv6, è consigliabile configurare un pool solo IPv6 nell'ambiente di prova a fini di test.</span><span class="sxs-lookup"><span data-stu-id="24450-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="24450-108">Durante la migrazione e in caso di coesistenza sono supportati gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="24450-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="24450-109">Lync Server 2013, Lync Server 2010 e i pool di Office Communications Server 2007 R2 in modalità IPv4, coesistenti con Lync Server 2013 in modalità dual stack.</span><span class="sxs-lookup"><span data-stu-id="24450-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="24450-110">Pool Lync Server 2013 in modalità solo IPv6, se il pool IPv6 è solo silo.</span><span class="sxs-lookup"><span data-stu-id="24450-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

