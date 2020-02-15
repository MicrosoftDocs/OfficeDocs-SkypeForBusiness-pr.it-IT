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
ms.openlocfilehash: 1f733397483693ad4c18418f3e82b9f99cfa640f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="25984-102">tblADCookie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25984-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25984-103">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="25984-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="25984-104">tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.</span><span class="sxs-lookup"><span data-stu-id="25984-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="25984-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="25984-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25984-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="25984-106">Column</span></span></th>
<th><span data-ttu-id="25984-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="25984-107">Type</span></span></th>
<th><span data-ttu-id="25984-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25984-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25984-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="25984-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="25984-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="25984-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="25984-111">GUID entità del dominio da monitorare.</span><span class="sxs-lookup"><span data-stu-id="25984-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25984-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="25984-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="25984-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="25984-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="25984-114">Nome di dominio completo (FQDN) del controller di dominio corrente utilizzato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.</span><span class="sxs-lookup"><span data-stu-id="25984-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25984-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="25984-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="25984-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="25984-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="25984-117">Cookie di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="25984-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25984-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="25984-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="25984-119">datetime</span><span class="sxs-lookup"><span data-stu-id="25984-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="25984-120">Timestamp con data e ora di aggiornamento della riga</span><span class="sxs-lookup"><span data-stu-id="25984-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25984-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="25984-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="25984-122">datetime</span><span class="sxs-lookup"><span data-stu-id="25984-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="25984-p101">Data e ora fino a cui la riga è bloccata in modo da impedire eventuali modifiche. Fa parte di un meccanismo di blocco software che garantisce che un solo servizio chat alla volta esegua la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="25984-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="25984-125">Chiavi</span><span class="sxs-lookup"><span data-stu-id="25984-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25984-126">Colonne</span><span class="sxs-lookup"><span data-stu-id="25984-126">Column(s)</span></span></th>
<th><span data-ttu-id="25984-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25984-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25984-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="25984-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="25984-129">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="25984-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25984-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="25984-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="25984-131">Chiave esterna con ricerca nella tabella Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="25984-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

