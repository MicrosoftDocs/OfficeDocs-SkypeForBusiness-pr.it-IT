---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="bcd48-102">tblComplianceParticipant in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bcd48-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcd48-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bcd48-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bcd48-104">tblComplianceParticipant contiene i partecipanti correnti per canale e per server.</span><span class="sxs-lookup"><span data-stu-id="bcd48-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="bcd48-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="bcd48-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcd48-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="bcd48-106">Column</span></span></th>
<th><span data-ttu-id="bcd48-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="bcd48-107">Type</span></span></th>
<th><span data-ttu-id="bcd48-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcd48-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcd48-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="bcd48-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="bcd48-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="bcd48-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="bcd48-111">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="bcd48-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd48-112">userId</span><span class="sxs-lookup"><span data-stu-id="bcd48-112">userId</span></span></p></td>
<td><p><span data-ttu-id="bcd48-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="bcd48-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bcd48-114">ID principale del partecipante (corrispondente alla tabella tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="bcd48-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd48-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="bcd48-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="bcd48-116">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="bcd48-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bcd48-117">Indicatore di data e ora dell'evento Joining.</span><span class="sxs-lookup"><span data-stu-id="bcd48-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd48-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="bcd48-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="bcd48-119">bigint</span><span class="sxs-lookup"><span data-stu-id="bcd48-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="bcd48-120">Null se i partecipanti sono ancora Uniti.</span><span class="sxs-lookup"><span data-stu-id="bcd48-120">Null if participant is still joined.</span></span> <span data-ttu-id="bcd48-121">L'indicatore di data e ora del canale che lascia l'evento se non è null.</span><span class="sxs-lookup"><span data-stu-id="bcd48-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="bcd48-122">Queste voci vengono infine rimosse quando tutti i traduttori elaborano l'evento.</span><span class="sxs-lookup"><span data-stu-id="bcd48-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd48-123">userUri</span><span class="sxs-lookup"><span data-stu-id="bcd48-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="bcd48-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="bcd48-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="bcd48-125">URI utente.</span><span class="sxs-lookup"><span data-stu-id="bcd48-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcd48-126">serverID</span><span class="sxs-lookup"><span data-stu-id="bcd48-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="bcd48-127">int</span><span class="sxs-lookup"><span data-stu-id="bcd48-127">int</span></span></p></td>
<td><p><span data-ttu-id="bcd48-128">Identità del server (come nella tabella tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="bcd48-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcd48-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="bcd48-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="bcd48-130">bigint</span><span class="sxs-lookup"><span data-stu-id="bcd48-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="bcd48-131">Sessione del server.</span><span class="sxs-lookup"><span data-stu-id="bcd48-131">Server session.</span></span> <span data-ttu-id="bcd48-132">Si tratta di un numero casuale generato ogni volta che viene avviato un servizio chat.</span><span class="sxs-lookup"><span data-stu-id="bcd48-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="bcd48-133">Viene usato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.</span><span class="sxs-lookup"><span data-stu-id="bcd48-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bcd48-134">Chiave</span><span class="sxs-lookup"><span data-stu-id="bcd48-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcd48-135">Colonna</span><span class="sxs-lookup"><span data-stu-id="bcd48-135">Column</span></span></th>
<th><span data-ttu-id="bcd48-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcd48-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcd48-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="bcd48-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="bcd48-138">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="bcd48-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

