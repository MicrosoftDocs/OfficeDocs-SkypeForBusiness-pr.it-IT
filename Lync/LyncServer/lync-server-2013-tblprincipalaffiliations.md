---
title: 'Lync Server 2013: tblPrincipalAffiliations'
description: 'Lync Server 2013: tblPrincipalAffiliations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547482"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="98206-103">tblPrincipalAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98206-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98206-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="98206-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="98206-105">tblPrincipalAffiliations contiene le affiliazioni principali che descrivono le appartenenze nelle posizioni, inclusi i gruppi di sicurezza di servizi di dominio Active Directory, in contenitori di Active Directory, in domini.</span><span class="sxs-lookup"><span data-stu-id="98206-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="98206-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="98206-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98206-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="98206-107">Column</span></span></th>
<th><span data-ttu-id="98206-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="98206-108">Type</span></span></th>
<th><span data-ttu-id="98206-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98206-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98206-110">principalID</span><span class="sxs-lookup"><span data-stu-id="98206-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="98206-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="98206-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="98206-112">ID dell'entità affiliata.</span><span class="sxs-lookup"><span data-stu-id="98206-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98206-113">affiliationID</span><span class="sxs-lookup"><span data-stu-id="98206-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="98206-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="98206-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="98206-p101">ID dell'entità che rappresenta l'affiliazione. Ogni entità prevede anche un'auto-affiliazione (eccetto system-user-types).</span><span class="sxs-lookup"><span data-stu-id="98206-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98206-117">Indice</span><span class="sxs-lookup"><span data-stu-id="98206-117">index</span></span></p></td>
<td><p><span data-ttu-id="98206-118">int, not null</span><span class="sxs-lookup"><span data-stu-id="98206-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="98206-119">Indice.</span><span class="sxs-lookup"><span data-stu-id="98206-119">Index.</span></span> <span data-ttu-id="98206-120">Il valore per le self-affiliazioni è-1 e per le altre affiliazioni aumenta sequenzialmente da 1 all'interno di ogni &lt; principalID, affiliationId &gt; bucket.</span><span class="sxs-lookup"><span data-stu-id="98206-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98206-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="98206-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="98206-122">int, not null</span><span class="sxs-lookup"><span data-stu-id="98206-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="98206-p103">Entità che ha effettuato l'ultimo aggiornamento. Viene utilizzato in genere il valore 1, che indica la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="98206-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="98206-125">Chiavi</span><span class="sxs-lookup"><span data-stu-id="98206-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98206-126">Colonne</span><span class="sxs-lookup"><span data-stu-id="98206-126">Columns</span></span></th>
<th><span data-ttu-id="98206-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98206-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98206-128">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="98206-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="98206-129">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="98206-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98206-130">principalID</span><span class="sxs-lookup"><span data-stu-id="98206-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="98206-131">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="98206-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98206-132">affiliationID</span><span class="sxs-lookup"><span data-stu-id="98206-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="98206-133">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="98206-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

