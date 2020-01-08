---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7412d0ffb1a5d24c2f30b76b987a16903253bfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="9efff-102">Migrazione di più siti e pool</span><span class="sxs-lookup"><span data-stu-id="9efff-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9efff-103">_**Argomento Ultima modifica:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="9efff-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="9efff-104">Lync Server 2013 supporta distribuzioni multisito e multipool.</span><span class="sxs-lookup"><span data-stu-id="9efff-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="9efff-105">Il processo di migrazione di più pool da Office Communications Server 2007 R2 a Lync Server 2013 richiede le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9efff-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="9efff-106">Dopo aver distribuito un pool di piloti di Lync Server 2013, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Lync Server 2013 e una metodologia per la convalida della funzionalità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9efff-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="9efff-107">Dopo la distribuzione di un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9efff-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="9efff-108">Dopo la transizione delle route federate da Office Communications Server 2007 R2 Edge Servers ai server pilota Lync Server 2013 Edge, è necessario verificare che gli utenti federati possano comunicare con il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9efff-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="9efff-109">Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool di Office Communications Server 2007 R2 sia vuoto.</span><span class="sxs-lookup"><span data-stu-id="9efff-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="9efff-110">Dopo aver verificato che il pool di Office Communications Server 2007 R2 è vuoto, è possibile disattivare il pool.</span><span class="sxs-lookup"><span data-stu-id="9efff-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="9efff-111">Per informazioni dettagliate su come disattivare il pool e i server legacy di Office Communications Server 2007 R2, vedere la [fase 10: rimuovere la Commissione dal sito legacy](phase-10-decommission-legacy-site.md).</span><span class="sxs-lookup"><span data-stu-id="9efff-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

