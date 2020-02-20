---
title: 'Lync Server 2013: visualizzazione multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a760e3113cf12eceaa9f60c829b4d6a4a714ea25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="43aa1-102">Visualizzazione multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43aa1-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43aa1-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="43aa1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="43aa1-104">Nella visualizzazione Media vengono archiviate le informazioni sul tipo di supporto utilizzato in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="43aa1-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="43aa1-105">Qualora si utilizzino più supporti, nella tabella saranno presenti più record per una sessione.</span><span class="sxs-lookup"><span data-stu-id="43aa1-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="43aa1-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43aa1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43aa1-p102">La visualizzazione Media non deve essere utilizzata per calcolare la durata di utilizzo del supporto in una sessione. Questa visualizzazione contiene i dettagli di segnalazione dello scambio di supporti in una sessione. Lo scambio dei supporti viene effettuato mediante la richiesta INVITE, mentre StartTime indica l'ora in cui la richiesta INVITE è stata inviata. L'ora dell'invito non corrisponde necessariamente all'ora di inizio del supporto poiché questo viene avviato solo dopo che la sessione è stata accettata.</span><span class="sxs-lookup"><span data-stu-id="43aa1-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="43aa1-110">La visualizzazione multimediale contiene tutte le colonne della [Visualizzazione SessionDetails in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in aggiunta a quelle elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="43aa1-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43aa1-111">Colonna</span><span class="sxs-lookup"><span data-stu-id="43aa1-111">Column</span></span></th>
<th><span data-ttu-id="43aa1-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="43aa1-112">Data Type</span></span></th>
<th><span data-ttu-id="43aa1-113">Dettagli</span><span class="sxs-lookup"><span data-stu-id="43aa1-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43aa1-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="43aa1-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="43aa1-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="43aa1-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="43aa1-116">Tipo di supporto.</span><span class="sxs-lookup"><span data-stu-id="43aa1-116">Media type.</span></span> <span data-ttu-id="43aa1-117">Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialist-table.md">tabella degli elementi multimediali in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="43aa1-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43aa1-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="43aa1-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43aa1-119">datetime</span><span class="sxs-lookup"><span data-stu-id="43aa1-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="43aa1-120">Ora di invio di una richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="43aa1-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43aa1-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="43aa1-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43aa1-122">datetime</span><span class="sxs-lookup"><span data-stu-id="43aa1-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="43aa1-123">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="43aa1-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

