---
title: 'Lync Server 2013: tabella PurgeSettings (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="3463f-102">Tabella PurgeSettings (QoE) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3463f-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3463f-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3463f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3463f-104">La tabella PurgeSettings contiene informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="3463f-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="3463f-105">Tieni presente che le informazioni correlate all'eliminazione possono essere ottenute anche da Microsoft Lync Server 2013 Management Shell eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3463f-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="3463f-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3463f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3463f-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3463f-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3463f-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3463f-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3463f-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="3463f-112">int</span><span class="sxs-lookup"><span data-stu-id="3463f-112">int</span></span></p></td>
<td><p><span data-ttu-id="3463f-113">Principale</span><span class="sxs-lookup"><span data-stu-id="3463f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3463f-114">Identificatore univoco per la raccolta di impostazioni di ripulitura QoE.</span><span class="sxs-lookup"><span data-stu-id="3463f-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3463f-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="3463f-116">po'</span><span class="sxs-lookup"><span data-stu-id="3463f-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3463f-117">Se impostato su true (1) Microsoft Lync Server 2013 eliminerà periodicamente i record obsoleti dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="3463f-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="3463f-118">L'eliminazione verrà applicata ogni giorno al tomo specificato dall'impostazione PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="3463f-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="3463f-119">Se impostato su false (0), i record non verranno eliminati automaticamente dal database.</span><span class="sxs-lookup"><span data-stu-id="3463f-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="3463f-120">Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="3463f-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3463f-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="3463f-122">int</span><span class="sxs-lookup"><span data-stu-id="3463f-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3463f-123">Specifica l'età dei record QoE (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record QoE antecedenti a questo valore verranno rimossi dal database.</span><span class="sxs-lookup"><span data-stu-id="3463f-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="3463f-124">Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="3463f-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3463f-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="3463f-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="3463f-126">int</span><span class="sxs-lookup"><span data-stu-id="3463f-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3463f-127">Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database.</span><span class="sxs-lookup"><span data-stu-id="3463f-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="3463f-128">L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera.</span><span class="sxs-lookup"><span data-stu-id="3463f-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="3463f-129">Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita.</span><span class="sxs-lookup"><span data-stu-id="3463f-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="3463f-130">Il valore predefinito è 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="3463f-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="3463f-131">Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database.</span><span class="sxs-lookup"><span data-stu-id="3463f-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="3463f-132">L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera.</span><span class="sxs-lookup"><span data-stu-id="3463f-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="3463f-133">Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita.</span><span class="sxs-lookup"><span data-stu-id="3463f-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="3463f-134">Il valore predefinito è 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="3463f-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

