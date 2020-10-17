---
title: 'Lync Server 2013: tabella PurgeSettings'
description: 'Lync Server 2013: tabella PurgeSettings.'
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
ms.openlocfilehash: 1ec2d1508d8362988bddbab2fe7303a23a8ee2d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559182"
---
# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="a625d-103">Tabella PurgeSettings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a625d-103">PurgeSettings table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a625d-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a625d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a625d-105">La tabella PurgeSettings contiene informazioni che specificano se (e quando) i record dettagli chiamata obsoleti verranno eliminati automaticamente dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="a625d-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="a625d-106">Si noti che le informazioni relative all'eliminazione possono essere ottenute anche da Microsoft Lync Server 2013 Management Shell eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a625d-106">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="a625d-107">Gli amministratori devono considerare la tabella PurgeSettings come di sola lettura: le modifiche apportate alle impostazioni di eliminazione dei dettagli delle chiamate devono essere effettuate solo utilizzando i cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) o [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a625d-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="a625d-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a625d-108">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a625d-109">Colonna</span><span class="sxs-lookup"><span data-stu-id="a625d-109">Column</span></span></th>
<th><span data-ttu-id="a625d-110">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a625d-110">Data Type</span></span></th>
<th><span data-ttu-id="a625d-111">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="a625d-111">Key/Index</span></span></th>
<th><span data-ttu-id="a625d-112">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a625d-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a625d-113"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="a625d-113"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="a625d-114">int</span><span class="sxs-lookup"><span data-stu-id="a625d-114">int</span></span></p></td>
<td><p><span data-ttu-id="a625d-115">Principale</span><span class="sxs-lookup"><span data-stu-id="a625d-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="a625d-116">Identificatore univoco per la raccolta di impostazioni di eliminazione di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="a625d-116">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a625d-117"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="a625d-117"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="a625d-118">po'</span><span class="sxs-lookup"><span data-stu-id="a625d-118">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a625d-119">Se impostato su true (1) Microsoft Lync Server 2013 eliminerà periodicamente i record obsoleti dal database di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="a625d-119">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="a625d-120">L'eliminazione verrà eseguita ogni giorno all'ora specificata dall'impostazione PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="a625d-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="a625d-121">Se impostato su False (0), i record non verranno eliminati automaticamente dal database.</span><span class="sxs-lookup"><span data-stu-id="a625d-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="a625d-122">Il valore predefinito è True.</span><span class="sxs-lookup"><span data-stu-id="a625d-122">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a625d-123"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="a625d-123"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="a625d-124">int</span><span class="sxs-lookup"><span data-stu-id="a625d-124">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a625d-125">Specifica l'età dei record di registrazione dettagli chiamata (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record CDR precedenti al valore verranno rimossi dal database.</span><span class="sxs-lookup"><span data-stu-id="a625d-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="a625d-126">Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="a625d-126">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a625d-127"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="a625d-127"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="a625d-128">int</span><span class="sxs-lookup"><span data-stu-id="a625d-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a625d-129">Specifica l'età dei record di rapporto di errore (in giorni) che verranno eliminati dal database: se l'eliminazione è abilitata, i record del rapporto errori precedenti al valore verranno rimossi dal database.</span><span class="sxs-lookup"><span data-stu-id="a625d-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="a625d-130">Il valore predefinito è 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="a625d-130">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a625d-131"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="a625d-131"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="a625d-132">int</span><span class="sxs-lookup"><span data-stu-id="a625d-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a625d-133">Specifica l'ora locale del giorno in cui verrà eseguita l'eliminazione dei dati del database.</span><span class="sxs-lookup"><span data-stu-id="a625d-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="a625d-134">L'ora del giorno viene specificata nel formato 24 ore; 0 rappresenta la mezzanotte e 23 rappresenta le 11 di sera.</span><span class="sxs-lookup"><span data-stu-id="a625d-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="a625d-135">Tenere presente che è possibile specificare solo l'ora del giorno: il valore 10 (a indicare le 10 del mattino) è consentito, mentre non lo è il valore 10,5 (a indicare le 10.30 del mattino).</span><span class="sxs-lookup"><span data-stu-id="a625d-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="a625d-136">Il valore predefinito è 2 (2.00).</span><span class="sxs-lookup"><span data-stu-id="a625d-136">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

