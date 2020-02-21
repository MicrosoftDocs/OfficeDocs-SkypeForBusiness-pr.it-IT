---
title: 'Lync Server 2013: tabella CodecDescription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c45300800ad83bbeee0d71abd1a38879f41c903d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="6ddcf-102">Tabella CodecDescription in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ddcf-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ddcf-103">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="6ddcf-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="6ddcf-104">La tabella CodecDescription associa identificatori codec univoci al codec corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6ddcf-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="6ddcf-105">I codec vengono usati per codificare i segnali digitali per la trasmissione, quindi per decodificare tali segnali per la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="6ddcf-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="6ddcf-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ddcf-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ddcf-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="6ddcf-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6ddcf-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="6ddcf-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6ddcf-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="6ddcf-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6ddcf-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="6ddcf-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ddcf-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="6ddcf-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddcf-112">smallint</span><span class="sxs-lookup"><span data-stu-id="6ddcf-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="6ddcf-113">Principale</span><span class="sxs-lookup"><span data-stu-id="6ddcf-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6ddcf-114">Identificatore univoco assegnato al codec.</span><span class="sxs-lookup"><span data-stu-id="6ddcf-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddcf-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="6ddcf-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddcf-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6ddcf-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6ddcf-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="6ddcf-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="6ddcf-118">Descrizione univoca del codec corrispondente a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="6ddcf-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

