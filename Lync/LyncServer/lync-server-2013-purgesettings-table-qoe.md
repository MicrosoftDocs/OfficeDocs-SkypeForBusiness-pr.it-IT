---
title: 'Lync Server 2013: tabella PurgeSettings (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cb0a0770136fa5b9d61f80825e49d319f872f32
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="03a80-102">Tabella PurgeSettings (QoE) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03a80-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03a80-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="03a80-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="03a80-104">Nella tabella PurgeSettings sono contenute informazioni che specificano se e quando i record QoE (qualità percepita dagli utenti) obsoleti verranno eliminati automaticamente dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="03a80-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="03a80-105">Si noti che le informazioni relative all'eliminazione possono essere ottenute anche da Microsoft Lync Server 2013 Management Shell eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="03a80-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="03a80-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03a80-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03a80-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="03a80-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="03a80-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="03a80-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03a80-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="03a80-112">int</span><span class="sxs-lookup"><span data-stu-id="03a80-112">int</span></span></p></td>
<td><p><span data-ttu-id="03a80-113">Principale</span><span class="sxs-lookup"><span data-stu-id="03a80-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="03a80-114">Identificatore univoco per la raccolta delle impostazioni di eliminazione QoE.</span><span class="sxs-lookup"><span data-stu-id="03a80-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03a80-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="03a80-116">po'</span><span class="sxs-lookup"><span data-stu-id="03a80-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="03a80-117">Se impostato su true (1) Microsoft Lync Server 2013 eliminerà periodicamente i record obsoleti dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="03a80-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="03a80-118">L'eliminazione verrà eseguita ogni giorno all'ora specificata dall'impostazione PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="03a80-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="03a80-119">Se impostato su False (0), i record non verranno eliminati automaticamente dal database.</span><span class="sxs-lookup"><span data-stu-id="03a80-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="03a80-120">Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="03a80-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03a80-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="03a80-122">int</span><span class="sxs-lookup"><span data-stu-id="03a80-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="03a80-p103">Specifica la giacenza dei record QoE (in giorni) che verranno eliminati dal database. Se l'eliminazione è abilitata, i record QoE precedenti a questo valore verranno rimossi dal database. Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="03a80-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03a80-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="03a80-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="03a80-126">int</span><span class="sxs-lookup"><span data-stu-id="03a80-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="03a80-p104">Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 1 (1 del mattino). Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database. L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera. Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino). Il valore predefinito è 1 (1 del mattino).</span><span class="sxs-lookup"><span data-stu-id="03a80-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

