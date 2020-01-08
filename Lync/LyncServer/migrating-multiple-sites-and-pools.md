---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7759c52051dfe4ca4a46e105e6a33f3284f334e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="1e6f7-102">Migrazione di più siti e pool</span><span class="sxs-lookup"><span data-stu-id="1e6f7-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e6f7-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1e6f7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1e6f7-104">Lync Server 2013 supporta distribuzioni multisito e multipool.</span><span class="sxs-lookup"><span data-stu-id="1e6f7-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="1e6f7-105">Il processo di migrazione di più pool da Lync Server 2010 a Lync Server 2013 richiede le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e6f7-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="1e6f7-106">Dopo aver distribuito un pool di piloti di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1e6f7-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="1e6f7-107">Dopo aver spostato un utente nel pool pilota, ad esempio, verificare che i criteri di conferenza dell'utente siano stati spostati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6f7-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="1e6f7-108">Dopo la distribuzione di un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6f7-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="1e6f7-109">Dopo aver eseguito la transizione dalle route federate da Lync Server 2010 Edge Server ai server pilota Lync Server 2013 Edge, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6f7-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="1e6f7-110">Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Lync Server 2010 sia vuoto.</span><span class="sxs-lookup"><span data-stu-id="1e6f7-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="1e6f7-111">Dopo aver verificato che il pool di Lync Server 2010 sia vuoto, è possibile disattivare il pool.</span><span class="sxs-lookup"><span data-stu-id="1e6f7-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="1e6f7-112">Per informazioni dettagliate su come disattivare il pool e i server legacy di Lync Server 2010, vedere la [fase 8: rimuovere i pool legacy](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="1e6f7-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

