---
title: 'Lync Server 2013: Record utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="62563-102">Record utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62563-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62563-103">_**Argomento Ultima modifica:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="62563-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="62563-104">La pianificazione dei record di utilizzo PSTN consiste principalmente nell'elencare tutte le autorizzazioni di chiamata attualmente in vigore nell'organizzazione, dall'amministratore delegato a lavoratori temporanei, consulenti e personale contingente.</span><span class="sxs-lookup"><span data-stu-id="62563-104">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="62563-105">Questo processo offre anche l'opportunità di riesaminare le autorizzazioni di chiamata esistenti e di modificarle.</span><span class="sxs-lookup"><span data-stu-id="62563-105">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="62563-106">È possibile creare record di utilizzo PSTN solo per le autorizzazioni di chiamata applicabili agli utenti di VoIP aziendale previsti, ma una soluzione migliore a lungo raggio può essere quella di creare record di utilizzo PSTN per tutte le autorizzazioni di chiamata, indipendentemente dal fatto che alcuni potrebbero non essere attualmente si applicano al gruppo di utenti che deve essere abilitato per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="62563-106">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="62563-107">Se le autorizzazioni di chiamata cambiano o vengono aggiunti nuovi utenti con autorizzazioni di chiamata diverse, saranno già stati creati i record di utilizzo PSTN necessari.</span><span class="sxs-lookup"><span data-stu-id="62563-107">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="62563-108">La tabella seguente mostra una tipica tabella di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="62563-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="62563-109">Record utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="62563-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62563-110">Attributo Phone</span><span class="sxs-lookup"><span data-stu-id="62563-110">Phone attribute</span></span></th>
<th><span data-ttu-id="62563-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62563-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62563-112">Locale</span><span class="sxs-lookup"><span data-stu-id="62563-112">Local</span></span></p></td>
<td><p><span data-ttu-id="62563-113">Chiamate locali</span><span class="sxs-lookup"><span data-stu-id="62563-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62563-114">Lunga distanza</span><span class="sxs-lookup"><span data-stu-id="62563-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="62563-115">Chiamate interurbane</span><span class="sxs-lookup"><span data-stu-id="62563-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62563-116">Internazionale</span><span class="sxs-lookup"><span data-stu-id="62563-116">International</span></span></p></td>
<td><p><span data-ttu-id="62563-117">Chiamate internazionali</span><span class="sxs-lookup"><span data-stu-id="62563-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62563-118">Delhi</span><span class="sxs-lookup"><span data-stu-id="62563-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="62563-119">Dipendenti a tempo pieno di Delhi</span><span class="sxs-lookup"><span data-stu-id="62563-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62563-120">Redmond</span><span class="sxs-lookup"><span data-stu-id="62563-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="62563-121">Dipendenti a tempo pieno Redmond</span><span class="sxs-lookup"><span data-stu-id="62563-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62563-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="62563-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="62563-123">Dipendenti temporanei Redmond</span><span class="sxs-lookup"><span data-stu-id="62563-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62563-124">Zurigo</span><span class="sxs-lookup"><span data-stu-id="62563-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="62563-125">Dipendenti a tempo pieno di Zurigo</span><span class="sxs-lookup"><span data-stu-id="62563-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="62563-126">Da solo, i record di utilizzo PSTN non eseguono alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="62563-126">By themselves, PSTN usage records do not do anything.</span></span> <span data-ttu-id="62563-127">Affinché funzioni, è necessario associarle con le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62563-127">For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="62563-128">Criteri vocali, assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="62563-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="62563-129">Route, assegnate ai numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="62563-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="62563-130">Per informazioni dettagliate sui criteri vocali e le route, vedere [criteri vocali in Lync server 2013](lync-server-2013-voice-policies.md) e [route vocali in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="62563-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="62563-131">Per informazioni dettagliate su come crearle e configurarle, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="62563-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

