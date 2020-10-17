---
title: 'Lync Server 2013: record di utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74c9f6dda4112325d6a408cc1bbb543373e9de61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512433"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="95fa1-102">Record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95fa1-102">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95fa1-103">_**Ultimo argomento modificato:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="95fa1-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="95fa1-p101">La pianificazione dei record utilizzo PSTN consiste principalmente nell'elencare tutte le autorizzazioni per le chiamate attualmente in vigore nell'organizzazione, dal CEO fino ai dipendenti a tempo determinato, ai consulenti e al personale contingente. Questo processo offre anche la possibilità di riesaminare le autorizzazioni esistenti per le chiamate e modificarle. È possibile creare record utilizzo PSTN solo per le autorizzazioni per le chiamate applicabili agli utenti previsti di VoIP aziendale, ma potrebbe essere una soluzione a lungo termine più efficace creare record utilizzo PSTN per tutte le autorizzazioni per le chiamate, anche se alcune potrebbero non essere al momento applicabili al gruppo di utenti da abilitare per VoIP aziendale. In questo modo, se le autorizzazioni per le chiamate subiscono modifiche o vengono aggiunti nuovi utenti con autorizzazioni diverse per le chiamate, saranno già stati creati i record utilizzo PSTN necessari.</span><span class="sxs-lookup"><span data-stu-id="95fa1-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="95fa1-108">Nella tabella seguente viene illustrata una tipica tabella di record di utilizzo PSTN:</span><span class="sxs-lookup"><span data-stu-id="95fa1-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="95fa1-109">Record utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="95fa1-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95fa1-110">Attributo telefono</span><span class="sxs-lookup"><span data-stu-id="95fa1-110">Phone attribute</span></span></th>
<th><span data-ttu-id="95fa1-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95fa1-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95fa1-112">Locale</span><span class="sxs-lookup"><span data-stu-id="95fa1-112">Local</span></span></p></td>
<td><p><span data-ttu-id="95fa1-113">Chiamate locali</span><span class="sxs-lookup"><span data-stu-id="95fa1-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95fa1-114">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="95fa1-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="95fa1-115">Chiamate interurbane</span><span class="sxs-lookup"><span data-stu-id="95fa1-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95fa1-116">Internazionali</span><span class="sxs-lookup"><span data-stu-id="95fa1-116">International</span></span></p></td>
<td><p><span data-ttu-id="95fa1-117">Chiamate internazionali</span><span class="sxs-lookup"><span data-stu-id="95fa1-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95fa1-118">Delhi</span><span class="sxs-lookup"><span data-stu-id="95fa1-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="95fa1-119">Dipendenti a tempo pieno di Delhi</span><span class="sxs-lookup"><span data-stu-id="95fa1-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95fa1-120">Redmond</span><span class="sxs-lookup"><span data-stu-id="95fa1-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="95fa1-121">Dipendenti a tempo pieno di Redmond</span><span class="sxs-lookup"><span data-stu-id="95fa1-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95fa1-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="95fa1-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="95fa1-123">Dipendenti a tempo determinato di Redmond</span><span class="sxs-lookup"><span data-stu-id="95fa1-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95fa1-124">Zurigo</span><span class="sxs-lookup"><span data-stu-id="95fa1-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="95fa1-125">Dipendenti a tempo pieno di Zurigo</span><span class="sxs-lookup"><span data-stu-id="95fa1-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95fa1-p102">I record di utilizzo PSTN non svolgono di per sé alcuna funzione. Per utilizzarli, è necessario associarli agli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="95fa1-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="95fa1-128">Criteri vocali, assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="95fa1-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="95fa1-129">Route, assegnate ai numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="95fa1-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="95fa1-130">Per informazioni dettagliate sui criteri vocali e le route, vedere [Voice Policies in Lync server 2013](lync-server-2013-voice-policies.md) e [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="95fa1-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="95fa1-131">Per informazioni dettagliate su come crearli e configurarli, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="95fa1-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

