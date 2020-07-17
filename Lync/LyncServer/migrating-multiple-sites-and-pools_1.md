---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6efbad7107109096a5f17d82912353e6f8a1a14a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="dbebe-102">Migrazione di più siti e pool</span><span class="sxs-lookup"><span data-stu-id="dbebe-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbebe-103">_**Ultimo argomento modificato:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="dbebe-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="dbebe-104">Lync Server 2013 supporta distribuzioni multisito e multi-pool.</span><span class="sxs-lookup"><span data-stu-id="dbebe-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="dbebe-105">Il processo di migrazione di più pool da Office Communications Server 2007 R2 a Lync Server 2013 richiede le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbebe-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="dbebe-106">Dopo aver distribuito un pool pilota di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="dbebe-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="dbebe-107">Dopo aver distribuito un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbebe-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="dbebe-108">Dopo aver eseguito la transizione dalle route federate dai server perimetrali di Office Communications Server 2007 R2 ai server perimetrali di Lync Server 2013 pilota, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbebe-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="dbebe-109">Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Office Communications Server 2007 R2 sia vuoto.</span><span class="sxs-lookup"><span data-stu-id="dbebe-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="dbebe-110">Dopo aver verificato che il pool di Office Communications Server 2007 R2 è vuoto, sarà possibile disattivare il pool.</span><span class="sxs-lookup"><span data-stu-id="dbebe-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="dbebe-111">Per informazioni dettagliate su come disattivare i server e il pool di Office Communications Server 2007 R2 legacy, vedere [Phase 10: decommission legacy Site](phase-10-decommission-legacy-site.md).</span><span class="sxs-lookup"><span data-stu-id="dbebe-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

