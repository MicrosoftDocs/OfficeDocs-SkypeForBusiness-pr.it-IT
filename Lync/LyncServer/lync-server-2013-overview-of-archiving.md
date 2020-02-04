---
title: "Lync Server 2013: Panoramica dell'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f718ac939fc665c0464d4986f51279d3afdee8a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="0102f-102">Panoramica dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0102f-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0102f-103">_**Argomento Ultima modifica:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="0102f-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="0102f-104">L'archiviazione in Lync Server 2013 offre la possibilità di archiviare le comunicazioni inviate tramite Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0102f-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="0102f-105">È possibile implementare l'archiviazione come parte della distribuzione iniziale di Lync Server 2013 oppure aggiungerla a una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="0102f-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="0102f-106">Per usare i database di archiviazione di Lync Server 2013 (database di SQL Server) per l'archiviazione dei dati di archiviazione, è possibile usare generatore di topologie per aggiungere i database alla topologia e quindi pubblicare di nuovo la topologia.</span><span class="sxs-lookup"><span data-stu-id="0102f-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="0102f-107">Se tutti gli utenti sono ospitati in Exchange 2013 e le cassette postali vengono posizionate sul posto, non è necessario aggiornare la topologia, ma è sufficiente abilitare l'integrazione di Microsoft Exchange per archiviare i dati archiviati in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0102f-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="0102f-108">Quando si implementa l'archiviazione, è possibile configurarlo per specificare gli elementi archiviati.</span><span class="sxs-lookup"><span data-stu-id="0102f-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="0102f-109">Per impostazione predefinita, non viene archiviato alcun archivio.</span><span class="sxs-lookup"><span data-stu-id="0102f-109">By default, nothing is archived.</span></span> <span data-ttu-id="0102f-110">Configurare e gestire l'archiviazione tramite il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0102f-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="0102f-111">Puoi implementare l'archiviazione per comunicazioni interne, comunicazioni esterne o entrambe.</span><span class="sxs-lookup"><span data-stu-id="0102f-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="0102f-112">È possibile configurare le impostazioni di archiviazione per l'intera organizzazione e, facoltativamente, per siti specifici, specifici pool e specifici utenti e gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="0102f-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="0102f-113">Per informazioni dettagliate sulla determinazione delle opzioni appropriate per l'organizzazione, vedere [definizione dei requisiti per l'archiviazione in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0102f-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="0102f-114">Per informazioni dettagliate sul modo in cui vengono implementati i criteri e le configurazioni di archiviazione e i dettagli sulle informazioni che possono o non possono essere archiviati, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione di distribuzione o nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0102f-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

