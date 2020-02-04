---
title: 'Lync Server 2013: tabella PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="e090d-102">Tabella PurgeSettings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e090d-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e090d-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e090d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e090d-104">La tabella PurgeSettings contiene informazioni che specificano se (e quando) i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="e090d-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="e090d-105">Tieni presente che le informazioni correlate all'eliminazione possono essere ottenute anche da Microsoft Lync Server 2013 Management Shell eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e090d-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="e090d-106">Gli amministratori devono considerare la tabella PurgeSettings come di sola lettura: le modifiche alle impostazioni di eliminazione dei dettagli delle chiamate devono essere effettuate solo usando i cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) o [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e090d-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="e090d-107">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e090d-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e090d-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="e090d-108">Column</span></span></th>
<th><span data-ttu-id="e090d-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e090d-109">Data Type</span></span></th>
<th><span data-ttu-id="e090d-110">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="e090d-110">Key/Index</span></span></th>
<th><span data-ttu-id="e090d-111">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e090d-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e090d-112"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="e090d-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="e090d-113">int</span><span class="sxs-lookup"><span data-stu-id="e090d-113">int</span></span></p></td>
<td><p><span data-ttu-id="e090d-114">Principale</span><span class="sxs-lookup"><span data-stu-id="e090d-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="e090d-115">Identificatore univoco per la raccolta di impostazioni di ripulitura CDR.</span><span class="sxs-lookup"><span data-stu-id="e090d-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e090d-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="e090d-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="e090d-117">po'</span><span class="sxs-lookup"><span data-stu-id="e090d-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e090d-118">Se impostato su true (1) Microsoft Lync Server 2013 eliminerà periodicamente i record obsoleti dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="e090d-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="e090d-119">L'eliminazione verrà applicata ogni giorno al tomo specificato dall'impostazione PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="e090d-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="e090d-120">Se impostato su false (0), i record non verranno eliminati automaticamente dal database.</span><span class="sxs-lookup"><span data-stu-id="e090d-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="e090d-121">Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="e090d-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e090d-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="e090d-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="e090d-123">int</span><span class="sxs-lookup"><span data-stu-id="e090d-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e090d-124">Specifica l'età dei record CDR (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record CDR più vecchi di questo valore verranno rimossi dal database.</span><span class="sxs-lookup"><span data-stu-id="e090d-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="e090d-125">Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="e090d-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e090d-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="e090d-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="e090d-127">int</span><span class="sxs-lookup"><span data-stu-id="e090d-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e090d-128">Specifica l'età dei record di report sugli errori (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record dei report di errore antecedenti al valore verranno rimossi dal database.</span><span class="sxs-lookup"><span data-stu-id="e090d-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="e090d-129">Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="e090d-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e090d-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="e090d-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="e090d-131">int</span><span class="sxs-lookup"><span data-stu-id="e090d-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e090d-132">Specifica l'ora locale del giorno in cui verrà eliminata l'eliminazione del database.</span><span class="sxs-lookup"><span data-stu-id="e090d-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="e090d-133">L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte, 23 rappresenta le 11 di sera.</span><span class="sxs-lookup"><span data-stu-id="e090d-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="e090d-134">Tieni presente che puoi specificare solo l'ora del giorno: il valore 10 (che indica 10:00 AM) è consentito, ma il valore 10:30 di 10,5 (che indica 10:30 AM) non è consentita.</span><span class="sxs-lookup"><span data-stu-id="e090d-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="e090d-135">Il valore predefinito è 2 (2.00).</span><span class="sxs-lookup"><span data-stu-id="e090d-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

