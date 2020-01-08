---
title: 'Lync Server 2013: visualizzazione utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c22bdfbf758545418a821edaba5d8aaf447b87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="c2ce6-102">Visualizzazione utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2ce6-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2ce6-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c2ce6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c2ce6-104">La visualizzazione utente archivia le informazioni sugli utenti che hanno partecipato a chiamate o sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c2ce6-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2ce6-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="c2ce6-106">Column</span></span></th>
<th><span data-ttu-id="c2ce6-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c2ce6-107">Data Type</span></span></th>
<th><span data-ttu-id="c2ce6-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c2ce6-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2ce6-109">UserId</span><span class="sxs-lookup"><span data-stu-id="c2ce6-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-110">int</span><span class="sxs-lookup"><span data-stu-id="c2ce6-110">int</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-111">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2ce6-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="c2ce6-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c2ce6-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-114">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2ce6-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c2ce6-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-116">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c2ce6-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-117">Tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-117">Tenant of user.</span></span> <span data-ttu-id="c2ce6-118">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2ce6-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2ce6-119">UriType</span><span class="sxs-lookup"><span data-stu-id="c2ce6-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2ce6-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2ce6-121">Tipo di URI utente.</span><span class="sxs-lookup"><span data-stu-id="c2ce6-121">Type of user URI.</span></span> <span data-ttu-id="c2ce6-122">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2ce6-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

