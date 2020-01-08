---
title: 'Lync Server 2013: tabella CodecDescription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f9c6cbdfd24517308321f5f3838fba56e90f842
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="0f561-102">Tabella CodecDescription in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f561-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f561-103">_**Argomento Ultima modifica:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="0f561-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="0f561-104">La tabella CodecDescription associa identificatori di codec univoci al relativo codec.</span><span class="sxs-lookup"><span data-stu-id="0f561-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="0f561-105">I codec vengono usati per codificare i segnali digitali per la trasmissione e la trasmissione e quindi per decodificare i segnali per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="0f561-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="0f561-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f561-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f561-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="0f561-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0f561-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="0f561-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0f561-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="0f561-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0f561-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="0f561-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f561-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="0f561-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0f561-112">smallint</span><span class="sxs-lookup"><span data-stu-id="0f561-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="0f561-113">Principale</span><span class="sxs-lookup"><span data-stu-id="0f561-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="0f561-114">Identificatore univoco assegnato al codec.</span><span class="sxs-lookup"><span data-stu-id="0f561-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f561-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="0f561-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="0f561-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="0f561-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0f561-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="0f561-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="0f561-118">Descrizione univoca del codec corrispondente a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="0f561-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

