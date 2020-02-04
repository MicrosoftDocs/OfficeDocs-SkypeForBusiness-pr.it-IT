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
ms.openlocfilehash: 6ad833bc84d488221d46822686077cfde2cda0ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="0e8cd-102">Visualizzazione multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e8cd-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e8cd-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0e8cd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0e8cd-104">La visualizzazione multimediale archivia le informazioni su un tipo di elemento multimediale usato in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="0e8cd-105">Una sessione verrebbe rappresentata da più record nella tabella, se viene usato più di un tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="0e8cd-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e8cd-107">La visualizzazione multimediale non deve essere usata per calcolare la durata del supporto per una sessione.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="0e8cd-108">Questa visualizzazione contiene i dettagli di segnalazione dello scambio multimediale in una sessione.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="0e8cd-109">Lo scambio multimediale viene eseguito dalla richiesta di invito e StartTime indica l'ora in cui è stato inviato l'invito. Il tempo di invito non significa necessariamente l'ora di inizio del supporto, perché il supporto viene avviato solo dopo l'accettazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="0e8cd-110">La visualizzazione multimediale contiene tutte le colonne della [Visualizzazione SessionDetails in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in aggiunta a quelle elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e8cd-111">Colonna</span><span class="sxs-lookup"><span data-stu-id="0e8cd-111">Column</span></span></th>
<th><span data-ttu-id="0e8cd-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0e8cd-112">Data Type</span></span></th>
<th><span data-ttu-id="0e8cd-113">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0e8cd-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e8cd-114"><strong>Contenuti multimediali</strong></span><span class="sxs-lookup"><span data-stu-id="0e8cd-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="0e8cd-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0e8cd-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0e8cd-116">Tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-116">Media type.</span></span> <span data-ttu-id="0e8cd-117">Per altre informazioni, vedere la <a href="lync-server-2013-medialist-table.md">tabella degli elementi multimediali in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="0e8cd-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e8cd-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e8cd-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e8cd-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="0e8cd-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e8cd-120">Ora in cui è stata inviata una richiesta multimediale.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e8cd-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e8cd-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e8cd-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="0e8cd-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e8cd-123">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="0e8cd-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

