---
title: 'Lync Server 2013: informazioni sulla visualizzazione dei dati QoE'
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
ms.openlocfilehash: 9f6d2b30654272baf0ce8db712461acb3e4f13a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="8ac52-102">Dettagli della visualizzazione QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ac52-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ac52-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8ac52-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8ac52-104">Le viste disponibili soddisfano gli scenari più comuni per la restituzione di dati dal database di SQL Server QoE.</span><span class="sxs-lookup"><span data-stu-id="8ac52-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="8ac52-105">È consigliabile utilizzare le viste per la creazione di report personalizzati, anziché accedere direttamente alle tabelle del database, perché è più probabile che le viste rimangano compatibili con le versioni precedenti anche nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="8ac52-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ac52-106">Nome della vista</span><span class="sxs-lookup"><span data-stu-id="8ac52-106">View Name</span></span></th>
<th><span data-ttu-id="8ac52-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ac52-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ac52-108"><a href="lync-server-2013-audiostreamdetail-view.md">Visualizzazione AudioStreamDetail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8ac52-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8ac52-109">Archivia informazioni su ogni flusso audio nel database.</span><span class="sxs-lookup"><span data-stu-id="8ac52-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac52-110"><a href="lync-server-2013-medialine-view.md">Visualizzazione MediaLine in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8ac52-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8ac52-111">Archivia informazioni su ogni linea multimediale nel database.</span><span class="sxs-lookup"><span data-stu-id="8ac52-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="8ac52-112">Una sessione audio in genere contiene una linea multimediale audio.</span><span class="sxs-lookup"><span data-stu-id="8ac52-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="8ac52-113">Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta.</span><span class="sxs-lookup"><span data-stu-id="8ac52-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac52-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Visualizzazione NetworkConfigurationSettings in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8ac52-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8ac52-115">Archivia informazioni sulla configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="8ac52-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac52-116"><a href="lync-server-2013-session-view.md">Visualizzazione sessione in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8ac52-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8ac52-117">Archivia informazioni sulle sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="8ac52-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac52-118"><a href="lync-server-2013-useragent-view.md">Visualizzazione UserAgent in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8ac52-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8ac52-119">Archivia informazioni sugli agenti utenti coinvolti nelle sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="8ac52-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac52-120"><a href="lync-server-2013-videostreamdetail-view.md">Visualizzazione VideoStreamDetail in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8ac52-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="8ac52-121">Archivia informazioni su ogni flusso video nel database.</span><span class="sxs-lookup"><span data-stu-id="8ac52-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

