---
title: 'Lync Server 2013: visualizzazione ConferenceMessageCount'
description: 'Lync Server 2013: visualizzazione ConferenceMessageCount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561612"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="c6bb3-103">Visualizzazione ConferenceMessageCount in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6bb3-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6bb3-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c6bb3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c6bb3-105">La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c6bb3-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="c6bb3-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6bb3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6bb3-107">La visualizzazione ConferenceMessageCount contiene tutte le colonne della <A href="lync-server-2013-conferencesessiondetails-view.md">visualizzazione ConferenceSessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="c6bb3-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6bb3-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="c6bb3-108">Column</span></span></th>
<th><span data-ttu-id="c6bb3-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c6bb3-109">Data Type</span></span></th>
<th><span data-ttu-id="c6bb3-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c6bb3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6bb3-111"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c6bb3-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c6bb3-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c6bb3-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c6bb3-113">URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="c6bb3-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6bb3-114"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c6bb3-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c6bb3-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c6bb3-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c6bb3-116">Tipo di URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="c6bb3-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="c6bb3-117">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6bb3-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6bb3-118"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c6bb3-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c6bb3-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c6bb3-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c6bb3-120">Tenant dell'utente che ha inviato i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c6bb3-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="c6bb3-121">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6bb3-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6bb3-122"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c6bb3-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c6bb3-123">smallint</span><span class="sxs-lookup"><span data-stu-id="c6bb3-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="c6bb3-124">Numero di messaggi inviati dall'utente durante la sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c6bb3-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

