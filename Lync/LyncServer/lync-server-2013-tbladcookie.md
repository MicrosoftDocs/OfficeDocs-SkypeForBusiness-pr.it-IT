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
ms.openlocfilehash: 02995141dfad6e91089fb80c7e9b09e4ef554edb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="34cd2-102">tblADCookie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34cd2-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34cd2-103">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="34cd2-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="34cd2-104">tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="34cd2-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="34cd2-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="34cd2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34cd2-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="34cd2-106">Column</span></span></th>
<th><span data-ttu-id="34cd2-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="34cd2-107">Type</span></span></th>
<th><span data-ttu-id="34cd2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34cd2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34cd2-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="34cd2-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="34cd2-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="34cd2-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="34cd2-111">GUID entità del dominio da monitorare.</span><span class="sxs-lookup"><span data-stu-id="34cd2-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34cd2-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="34cd2-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="34cd2-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="34cd2-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="34cd2-114">Nome di dominio completo (FQDN) del controller di dominio corrente utilizzato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.</span><span class="sxs-lookup"><span data-stu-id="34cd2-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34cd2-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="34cd2-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="34cd2-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="34cd2-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="34cd2-117">Cookie di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34cd2-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34cd2-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="34cd2-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="34cd2-119">datetime</span><span class="sxs-lookup"><span data-stu-id="34cd2-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="34cd2-120">Timestamp con data e ora di aggiornamento della riga</span><span class="sxs-lookup"><span data-stu-id="34cd2-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34cd2-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="34cd2-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="34cd2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="34cd2-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="34cd2-p101">Data e ora fino a cui la riga è bloccata in modo da impedire eventuali modifiche. Fa parte di un meccanismo di blocco software che garantisce che un solo servizio chat alla volta esegua la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34cd2-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="34cd2-125">Chiavi</span><span class="sxs-lookup"><span data-stu-id="34cd2-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34cd2-126">Colonne</span><span class="sxs-lookup"><span data-stu-id="34cd2-126">Column(s)</span></span></th>
<th><span data-ttu-id="34cd2-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34cd2-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34cd2-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="34cd2-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="34cd2-129">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="34cd2-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34cd2-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="34cd2-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="34cd2-131">Chiave esterna con ricerca nella tabella Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="34cd2-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

