---
title: 'Lync Server 2013: informazioni sulla visualizzazione QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47fb90b7ffb9eb0cb7fcd1631a0f00ca249276a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="5f688-102">Dettagli della visualizzazione QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f688-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f688-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5f688-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5f688-104">Le visualizzazioni coprono gli scenari più comuni per la restituzione dei dati dal database SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="5f688-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="5f688-105">Si tratta di visualizzazioni consigliate usate per creare report personalizzati anziché accedere direttamente alle tabelle del database. Questo perché le visualizzazioni hanno più probabilità di mantenere la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="5f688-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f688-106">Nome visualizzazione</span><span class="sxs-lookup"><span data-stu-id="5f688-106">View Name</span></span></th>
<th><span data-ttu-id="5f688-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f688-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f688-108"><a href="lync-server-2013-audiostreamdetail-view.md">Visualizzazione AudioStreamDetail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f688-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5f688-109">Archivia informazioni su ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="5f688-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f688-110"><a href="lync-server-2013-medialine-view.md">Visualizzazione MediaLine in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f688-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5f688-111">Archivia informazioni su ogni riga multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="5f688-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="5f688-112">Una sessione audio in genere contiene una linea media audio.</span><span class="sxs-lookup"><span data-stu-id="5f688-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="5f688-113">Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video; Tuttavia, la sessione può contenere due linee multimediali video se viene usato un dispositivo per i servizi di conferenza o se viene usata la visualizzazione raccolta.</span><span class="sxs-lookup"><span data-stu-id="5f688-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f688-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Visualizzazione NetworkConfigurationSettings in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f688-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5f688-115">Archivia informazioni sulla configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="5f688-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f688-116"><a href="lync-server-2013-session-view.md">Visualizzazione sessione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f688-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5f688-117">Archivia informazioni sulle sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="5f688-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f688-118"><a href="lync-server-2013-useragent-view.md">Visualizzazione UserAgent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f688-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5f688-119">Archivia informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="5f688-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f688-120"><a href="lync-server-2013-videostreamdetail-view.md">Visualizzazione VideoStreamDetail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5f688-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5f688-121">Archivia informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="5f688-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

