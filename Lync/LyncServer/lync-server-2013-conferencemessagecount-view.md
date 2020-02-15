---
title: 'Lync Server 2013: visualizzazione ConferenceMessageCount'
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
ms.openlocfilehash: f94e824b18cab71fe1329ffcad1c836df6d46ebd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="e709d-102">Visualizzazione ConferenceMessageCount in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e709d-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e709d-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e709d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e709d-104">La vista ConferenceMessageCount archivia informazioni sul numero di messaggi inviati da un utente a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="e709d-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="e709d-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e709d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e709d-106">La visualizzazione ConferenceMessageCount contiene tutte le colonne della <A href="lync-server-2013-conferencesessiondetails-view.md">visualizzazione ConferenceSessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="e709d-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e709d-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="e709d-107">Column</span></span></th>
<th><span data-ttu-id="e709d-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e709d-108">Data Type</span></span></th>
<th><span data-ttu-id="e709d-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e709d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e709d-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e709d-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e709d-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e709d-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e709d-112">URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e709d-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e709d-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e709d-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e709d-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e709d-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e709d-115">Tipo di URI dell'utente che ha inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e709d-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="e709d-116">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e709d-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e709d-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e709d-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e709d-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e709d-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e709d-119">Tenant dell'utente che ha inviato i messaggi.</span><span class="sxs-lookup"><span data-stu-id="e709d-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="e709d-120">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e709d-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e709d-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e709d-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e709d-122">smallint</span><span class="sxs-lookup"><span data-stu-id="e709d-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="e709d-123">Numero di messaggi inviati dall'utente durante la sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e709d-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

