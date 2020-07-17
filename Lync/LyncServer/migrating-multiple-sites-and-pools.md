---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bee98cdc88a836be8b629d76b5bed57af402a3ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="2514e-102">Migrazione di più siti e pool</span><span class="sxs-lookup"><span data-stu-id="2514e-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2514e-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2514e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2514e-104">Lync Server 2013 supporta distribuzioni multisito e multi-pool.</span><span class="sxs-lookup"><span data-stu-id="2514e-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="2514e-105">Il processo di migrazione di più pool da Lync Server 2010 a Lync Server 2013 richiede le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2514e-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="2514e-106">Dopo aver distribuito un pool pilota di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2514e-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="2514e-107">Ad esempio, dopo lo spostamento di un utente nel pool pilota, verificare che i criteri di conferenza dell'utente siano stati spostati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2514e-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="2514e-108">Dopo aver distribuito un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2514e-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="2514e-109">Dopo la transizione delle route federate dai server perimetrali di Lync Server 2010 ai server perimetrali di Lync Server 2013 pilota, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2514e-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="2514e-110">Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Lync Server 2010 sia vuoto.</span><span class="sxs-lookup"><span data-stu-id="2514e-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="2514e-111">Dopo aver verificato che il pool di Lync Server 2010 sia vuoto, è possibile disattivare il pool.</span><span class="sxs-lookup"><span data-stu-id="2514e-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="2514e-112">Per informazioni dettagliate su come disattivare i server e il pool legacy di Lync Server 2010, vedere [Phase 8: decommission legacy pools](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="2514e-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

