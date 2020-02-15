---
title: 'Lync Server 2013: visualizzazione utente'
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
ms.openlocfilehash: 3ddc05e2ee7e96ec10c6d3dbf691f7b094a10983
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="32ba2-102">Visualizzazione utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ba2-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32ba2-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="32ba2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="32ba2-104">Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database.</span><span class="sxs-lookup"><span data-stu-id="32ba2-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="32ba2-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32ba2-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32ba2-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="32ba2-106">Column</span></span></th>
<th><span data-ttu-id="32ba2-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="32ba2-107">Data Type</span></span></th>
<th><span data-ttu-id="32ba2-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="32ba2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32ba2-109">UserId</span><span class="sxs-lookup"><span data-stu-id="32ba2-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="32ba2-110">int</span><span class="sxs-lookup"><span data-stu-id="32ba2-110">int</span></span></p></td>
<td><p><span data-ttu-id="32ba2-111">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="32ba2-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32ba2-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="32ba2-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="32ba2-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32ba2-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="32ba2-114">Uri dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32ba2-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32ba2-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="32ba2-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="32ba2-116">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="32ba2-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="32ba2-117">Tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32ba2-117">Tenant of user.</span></span> <span data-ttu-id="32ba2-118">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32ba2-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32ba2-119">UriType</span><span class="sxs-lookup"><span data-stu-id="32ba2-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="32ba2-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="32ba2-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="32ba2-121">Tipo dell'URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32ba2-121">Type of user URI.</span></span> <span data-ttu-id="32ba2-122">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="32ba2-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

