---
title: 'Lync Server 2013: tblADCookie'
description: 'Lync Server 2013: tblADCookie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573722"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="3d644-103">tblADCookie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d644-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d644-104">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="3d644-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="3d644-105">tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="3d644-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="3d644-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="3d644-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d644-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="3d644-107">Column</span></span></th>
<th><span data-ttu-id="3d644-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d644-108">Type</span></span></th>
<th><span data-ttu-id="3d644-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d644-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d644-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3d644-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="3d644-111">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="3d644-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="3d644-112">GUID entità del dominio da monitorare.</span><span class="sxs-lookup"><span data-stu-id="3d644-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d644-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="3d644-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="3d644-114">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="3d644-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="3d644-115">Nome di dominio completo (FQDN) del controller di dominio corrente utilizzato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.</span><span class="sxs-lookup"><span data-stu-id="3d644-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d644-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="3d644-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="3d644-117">image (binary)</span><span class="sxs-lookup"><span data-stu-id="3d644-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="3d644-118">Cookie di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d644-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d644-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="3d644-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="3d644-120">datetime</span><span class="sxs-lookup"><span data-stu-id="3d644-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="3d644-121">Timestamp con data e ora di aggiornamento della riga</span><span class="sxs-lookup"><span data-stu-id="3d644-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d644-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="3d644-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="3d644-123">datetime</span><span class="sxs-lookup"><span data-stu-id="3d644-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="3d644-p101">Data e ora fino a cui la riga è bloccata in modo da impedire eventuali modifiche. Fa parte di un meccanismo di blocco software che garantisce che un solo servizio chat alla volta esegua la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d644-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3d644-126">Chiavi</span><span class="sxs-lookup"><span data-stu-id="3d644-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d644-127">Colonne</span><span class="sxs-lookup"><span data-stu-id="3d644-127">Column(s)</span></span></th>
<th><span data-ttu-id="3d644-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d644-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d644-129">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3d644-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="3d644-130">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3d644-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d644-131">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3d644-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="3d644-132">Chiave esterna con ricerca nella tabella Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="3d644-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

