---
title: 'Lync Server 2013: Visualizzazione UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb9e70635fc4c54448f6fe3f549d3d6853612070
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530123"
---
# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="14965-102">Visualizzazione UserAgent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14965-102">UserAgent view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14965-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="14965-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="14965-104">Nella visualizzazione UserAgent vengono archiviate le informazioni relative agli agenti utente coinvolti in sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="14965-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="14965-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14965-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14965-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="14965-106">Column</span></span></th>
<th><span data-ttu-id="14965-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="14965-107">Data Type</span></span></th>
<th><span data-ttu-id="14965-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="14965-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14965-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="14965-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="14965-110">int</span><span class="sxs-lookup"><span data-stu-id="14965-110">int</span></span></p></td>
<td><p><span data-ttu-id="14965-111">Numero univoco che identifica l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="14965-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14965-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="14965-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="14965-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14965-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="14965-114">Stringa dell'agente utente.</span><span class="sxs-lookup"><span data-stu-id="14965-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14965-115">UAType</span><span class="sxs-lookup"><span data-stu-id="14965-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="14965-116">smallint</span><span class="sxs-lookup"><span data-stu-id="14965-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="14965-117">Tipo di agente utente.</span><span class="sxs-lookup"><span data-stu-id="14965-117">Type of user agent.</span></span> <span data-ttu-id="14965-118">Per ulteriori informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="14965-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14965-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="14965-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="14965-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="14965-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="14965-p103">Categoria a cui appartiene l'agente utente. Ad esempio, l'agente utente Conferencing_Attendant_1.0 appartiene alla categoria (UACategory) CAA.</span><span class="sxs-lookup"><span data-stu-id="14965-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

