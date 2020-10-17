---
title: 'Lync Server 2013: tblComplianceParticipant'
description: 'Lync Server 2013: tblComplianceParticipant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569072"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="7bdf4-103">tblComplianceParticipant in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bdf4-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bdf4-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7bdf4-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7bdf4-105">In tblComplianceParticipant sono inclusi i partecipanti correnti per canale e per server.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="7bdf4-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="7bdf4-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bdf4-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="7bdf4-107">Column</span></span></th>
<th><span data-ttu-id="7bdf4-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="7bdf4-108">Type</span></span></th>
<th><span data-ttu-id="7bdf4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bdf4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bdf4-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="7bdf4-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-111">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7bdf4-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-112">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf4-113">userId</span><span class="sxs-lookup"><span data-stu-id="7bdf4-113">userId</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="7bdf4-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-115">ID dell'entità del partecipante (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="7bdf4-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf4-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="7bdf4-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-117">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="7bdf4-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-118">Timestamp dell'evento di partecipazione.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf4-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="7bdf4-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-120">bigint</span><span class="sxs-lookup"><span data-stu-id="7bdf4-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-p101">Null se il partecipante sta ancora partecipando. Timestamp dell'evento di uscita dal canale, se not null.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="7bdf4-123">Queste voci vengono rimosse alle fine quando tutti i convertitori hanno elaborato l'evento.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf4-124">userUri</span><span class="sxs-lookup"><span data-stu-id="7bdf4-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-125">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7bdf4-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-126">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bdf4-127">serverID</span><span class="sxs-lookup"><span data-stu-id="7bdf4-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-128">int</span><span class="sxs-lookup"><span data-stu-id="7bdf4-128">int</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-129">Identità del server (come nella tabella tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="7bdf4-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bdf4-130">sessionId</span><span class="sxs-lookup"><span data-stu-id="7bdf4-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-131">bigint</span><span class="sxs-lookup"><span data-stu-id="7bdf4-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-p102">Sessione del server. Numero casuale generato a ogni avvio di un servizio chat, utilizzato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7bdf4-135">Chiave</span><span class="sxs-lookup"><span data-stu-id="7bdf4-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bdf4-136">Colonna</span><span class="sxs-lookup"><span data-stu-id="7bdf4-136">Column</span></span></th>
<th><span data-ttu-id="7bdf4-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bdf4-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bdf4-138">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="7bdf4-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="7bdf4-139">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

