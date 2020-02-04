---
title: 'Lync Server 2013: tblADCookie'
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
ms.openlocfilehash: 8b1b5096c087661bf5afadd2668d6d1bb7ac8330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="d7460-102">tblADCookie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7460-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7460-103">_**Argomento Ultima modifica:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d7460-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d7460-104">tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="d7460-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="d7460-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="d7460-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7460-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="d7460-106">Column</span></span></th>
<th><span data-ttu-id="d7460-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d7460-107">Type</span></span></th>
<th><span data-ttu-id="d7460-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7460-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7460-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d7460-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="d7460-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="d7460-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d7460-111">GUID principale del dominio da monitorare.</span><span class="sxs-lookup"><span data-stu-id="d7460-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7460-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="d7460-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="d7460-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="d7460-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="d7460-114">Nome di dominio completo (FQDN) del controller di dominio corrente usato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.</span><span class="sxs-lookup"><span data-stu-id="d7460-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7460-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="d7460-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="d7460-116">immagine (binario)</span><span class="sxs-lookup"><span data-stu-id="d7460-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="d7460-117">Cookie di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d7460-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7460-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="d7460-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="d7460-119">DateTime</span><span class="sxs-lookup"><span data-stu-id="d7460-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7460-120">Indicatore di data e ora con il tempo di aggiornamento delle righe.</span><span class="sxs-lookup"><span data-stu-id="d7460-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7460-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="d7460-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="d7460-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="d7460-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="d7460-123">Ora fino a quando la riga non viene bloccata per le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d7460-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="d7460-124">Questo fa parte di un meccanismo di blocco software che garantisce che solo uno dei servizi di chat esegue la sincronizzazione di Active Directory alla volta.</span><span class="sxs-lookup"><span data-stu-id="d7460-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d7460-125">Tasti</span><span class="sxs-lookup"><span data-stu-id="d7460-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7460-126">Colonne</span><span class="sxs-lookup"><span data-stu-id="d7460-126">Column(s)</span></span></th>
<th><span data-ttu-id="d7460-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7460-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7460-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d7460-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="d7460-129">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="d7460-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7460-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d7460-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="d7460-131">Chiave esterna con ricerca nella tabella Principal. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="d7460-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

