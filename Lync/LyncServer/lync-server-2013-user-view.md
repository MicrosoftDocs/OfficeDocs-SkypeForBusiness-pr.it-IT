---
title: 'Lync Server 2013: visualizzazione utente'
description: 'Lync Server 2013: visualizzazione utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558912"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="fe51d-103">Visualizzazione utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe51d-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe51d-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fe51d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fe51d-105">Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="fe51d-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="fe51d-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe51d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe51d-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="fe51d-107">Column</span></span></th>
<th><span data-ttu-id="fe51d-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="fe51d-108">Data Type</span></span></th>
<th><span data-ttu-id="fe51d-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fe51d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe51d-110">UserId</span><span class="sxs-lookup"><span data-stu-id="fe51d-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="fe51d-111">int</span><span class="sxs-lookup"><span data-stu-id="fe51d-111">int</span></span></p></td>
<td><p><span data-ttu-id="fe51d-112">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="fe51d-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe51d-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="fe51d-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="fe51d-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe51d-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe51d-115">Uri dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fe51d-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe51d-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="fe51d-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="fe51d-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="fe51d-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fe51d-118">Tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fe51d-118">Tenant of user.</span></span> <span data-ttu-id="fe51d-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe51d-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe51d-120">UriType</span><span class="sxs-lookup"><span data-stu-id="fe51d-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="fe51d-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe51d-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe51d-122">Tipo dell'URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fe51d-122">Type of user URI.</span></span> <span data-ttu-id="fe51d-123">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe51d-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

