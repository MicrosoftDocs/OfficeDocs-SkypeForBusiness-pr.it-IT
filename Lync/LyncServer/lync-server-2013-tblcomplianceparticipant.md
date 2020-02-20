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
ms.openlocfilehash: fbadec18ba7054c7b58522129fca01da7d015e7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="daa24-102">tblComplianceParticipant in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa24-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daa24-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="daa24-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="daa24-104">In tblComplianceParticipant sono inclusi i partecipanti correnti per canale e per server.</span><span class="sxs-lookup"><span data-stu-id="daa24-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="daa24-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="daa24-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa24-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="daa24-106">Column</span></span></th>
<th><span data-ttu-id="daa24-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="daa24-107">Type</span></span></th>
<th><span data-ttu-id="daa24-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daa24-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa24-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="daa24-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="daa24-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="daa24-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="daa24-111">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="daa24-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa24-112">userId</span><span class="sxs-lookup"><span data-stu-id="daa24-112">userId</span></span></p></td>
<td><p><span data-ttu-id="daa24-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="daa24-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="daa24-114">ID dell'entità del partecipante (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="daa24-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa24-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="daa24-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="daa24-116">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="daa24-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="daa24-117">Timestamp dell'evento di partecipazione.</span><span class="sxs-lookup"><span data-stu-id="daa24-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa24-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="daa24-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="daa24-119">bigint</span><span class="sxs-lookup"><span data-stu-id="daa24-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="daa24-p101">Null se il partecipante sta ancora partecipando. Timestamp dell'evento di uscita dal canale, se not null.</span><span class="sxs-lookup"><span data-stu-id="daa24-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="daa24-122">Queste voci vengono rimosse alle fine quando tutti i convertitori hanno elaborato l'evento.</span><span class="sxs-lookup"><span data-stu-id="daa24-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa24-123">userUri</span><span class="sxs-lookup"><span data-stu-id="daa24-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="daa24-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="daa24-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="daa24-125">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="daa24-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa24-126">serverID</span><span class="sxs-lookup"><span data-stu-id="daa24-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="daa24-127">int</span><span class="sxs-lookup"><span data-stu-id="daa24-127">int</span></span></p></td>
<td><p><span data-ttu-id="daa24-128">Identità del server (come nella tabella tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="daa24-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa24-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="daa24-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="daa24-130">bigint</span><span class="sxs-lookup"><span data-stu-id="daa24-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="daa24-p102">Sessione del server. Numero casuale generato a ogni avvio di un servizio chat, utilizzato per distinguere le sessioni allo scopo di identificare i partecipanti orfani.</span><span class="sxs-lookup"><span data-stu-id="daa24-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="daa24-134">Chiave</span><span class="sxs-lookup"><span data-stu-id="daa24-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa24-135">Colonna</span><span class="sxs-lookup"><span data-stu-id="daa24-135">Column</span></span></th>
<th><span data-ttu-id="daa24-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daa24-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa24-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="daa24-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="daa24-138">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="daa24-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

