---
title: 'Lync Server 2013: Tabella ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96e8f035dbc0005bb331a188a308f456992f091
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="c23fa-102">Tabella ClientVersions in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c23fa-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c23fa-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c23fa-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c23fa-p101">La tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei diversi tipi di client e delle versioni che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta una versione client.</span><span class="sxs-lookup"><span data-stu-id="c23fa-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c23fa-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="c23fa-106">Column</span></span></th>
<th><span data-ttu-id="c23fa-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c23fa-107">Data Type</span></span></th>
<th><span data-ttu-id="c23fa-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="c23fa-108">Key/Index</span></span></th>
<th><span data-ttu-id="c23fa-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c23fa-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c23fa-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="c23fa-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="c23fa-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="c23fa-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="c23fa-112">Principale</span><span class="sxs-lookup"><span data-stu-id="c23fa-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c23fa-113">Numero univoco che identifica il tipo di client e la versione.</span><span class="sxs-lookup"><span data-stu-id="c23fa-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c23fa-114"><strong>Versione</strong></span><span class="sxs-lookup"><span data-stu-id="c23fa-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="c23fa-115"><strong>nvarchar (256)</strong></span><span class="sxs-lookup"><span data-stu-id="c23fa-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c23fa-116">Nome della versione.</span><span class="sxs-lookup"><span data-stu-id="c23fa-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c23fa-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c23fa-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c23fa-118">int</span><span class="sxs-lookup"><span data-stu-id="c23fa-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c23fa-119">Specifica il tipo di client usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="c23fa-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="c23fa-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c23fa-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c23fa-121">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c23fa-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

