---
title: 'Lync Server 2013: tblComplianceParticipant'
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
ms.openlocfilehash: 38d4a47f3778e2343685a993378d97cc37c827a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="5fb98-102">tblComplianceParticipant in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fb98-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fb98-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5fb98-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5fb98-104">In tblComplianceParticipant sono inclusi i partecipanti correnti per canale e per server.</span><span class="sxs-lookup"><span data-stu-id="5fb98-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="5fb98-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="5fb98-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fb98-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="5fb98-106">Column</span></span></th>
<th><span data-ttu-id="5fb98-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5fb98-107">Type</span></span></th>
<th><span data-ttu-id="5fb98-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5fb98-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fb98-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="5fb98-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="5fb98-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="5fb98-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5fb98-111">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="5fb98-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb98-112">userId</span><span class="sxs-lookup"><span data-stu-id="5fb98-112">userId</span></span></p></td>
<td><p><span data-ttu-id="5fb98-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="5fb98-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fb98-114">ID dell'entità del partecipante (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="5fb98-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb98-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="5fb98-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="5fb98-116">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="5fb98-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5fb98-117">Timestamp dell'evento di partecipazione.</span><span class="sxs-lookup"><span data-stu-id="5fb98-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb98-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="5fb98-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="5fb98-119">bigint</span><span class="sxs-lookup"><span data-stu-id="5fb98-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="5fb98-p101">Null se il partecipante sta ancora partecipando. Timestamp dell'evento di uscita dal canale, se not null.</span><span class="sxs-lookup"><span data-stu-id="5fb98-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="5fb98-122">Queste voci vengono rimosse alle fine quando tutti i convertitori hanno elaborato l'evento.</span><span class="sxs-lookup"><span data-stu-id="5fb98-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb98-123">userUri</span><span class="sxs-lookup"><span data-stu-id="5fb98-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="5fb98-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="5fb98-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="5fb98-125">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5fb98-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb98-126">serverID</span><span class="sxs-lookup"><span data-stu-id="5fb98-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="5fb98-127">int</span><span class="sxs-lookup"><span data-stu-id="5fb98-127">int</span></span></p></td>
<td><p><span data-ttu-id="5fb98-128">Identità del server (come nella tabella tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="5fb98-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb98-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="5fb98-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="5fb98-130">bigint</span><span class="sxs-lookup"><span data-stu-id="5fb98-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="5fb98-p102">Sessione del server. Numero casuale generato a ogni avvio di un servizio chat, utilizzato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.</span><span class="sxs-lookup"><span data-stu-id="5fb98-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5fb98-134">Chiave</span><span class="sxs-lookup"><span data-stu-id="5fb98-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fb98-135">Colonna</span><span class="sxs-lookup"><span data-stu-id="5fb98-135">Column</span></span></th>
<th><span data-ttu-id="5fb98-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5fb98-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fb98-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="5fb98-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="5fb98-138">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="5fb98-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

