---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb5f6400de1c71b4d11101871b2dadedd232a9ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="e831d-102">tblPrincipalAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e831d-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e831d-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e831d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e831d-104">tblPrincipalAffiliations contiene le principali affiliazioni che descrivono le appartenenze in posizioni, inclusi i gruppi di sicurezza dei servizi di dominio Active Directory, in contenitori di Active Directory in domini.</span><span class="sxs-lookup"><span data-stu-id="e831d-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="e831d-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="e831d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e831d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e831d-106">Column</span></span></th>
<th><span data-ttu-id="e831d-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e831d-107">Type</span></span></th>
<th><span data-ttu-id="e831d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e831d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e831d-109">principalID</span><span class="sxs-lookup"><span data-stu-id="e831d-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="e831d-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e831d-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e831d-111">ID dell'oggetto Principal affiliato.</span><span class="sxs-lookup"><span data-stu-id="e831d-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e831d-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e831d-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="e831d-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="e831d-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e831d-114">ID dell'entità che rappresenta l'affiliazione.</span><span class="sxs-lookup"><span data-stu-id="e831d-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="e831d-115">Ogni entità (ad eccezione di System-User-Types) ha anche una propria affiliazione.</span><span class="sxs-lookup"><span data-stu-id="e831d-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e831d-116">Indice</span><span class="sxs-lookup"><span data-stu-id="e831d-116">index</span></span></p></td>
<td><p><span data-ttu-id="e831d-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="e831d-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e831d-118">Indice.</span><span class="sxs-lookup"><span data-stu-id="e831d-118">Index.</span></span> <span data-ttu-id="e831d-119">Il valore di self-Affiliations è-1 e per le altre affiliazioni aumenta sequenzialmente da 1 all'interno di ogni &lt;PrincipalId, affiliationId&gt; bucket.</span><span class="sxs-lookup"><span data-stu-id="e831d-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e831d-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e831d-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="e831d-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="e831d-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e831d-122">Principal che ha eseguito l'aggiornamento più recente.</span><span class="sxs-lookup"><span data-stu-id="e831d-122">Principal that did the latest update.</span></span> <span data-ttu-id="e831d-123">Si tratta in genere di 1, che indica la sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e831d-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e831d-124">Tasti</span><span class="sxs-lookup"><span data-stu-id="e831d-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e831d-125">Colonne</span><span class="sxs-lookup"><span data-stu-id="e831d-125">Columns</span></span></th>
<th><span data-ttu-id="e831d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e831d-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e831d-127">&lt;principalID, index, affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="e831d-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e831d-128">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="e831d-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e831d-129">principalID</span><span class="sxs-lookup"><span data-stu-id="e831d-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="e831d-130">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="e831d-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e831d-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e831d-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="e831d-132">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="e831d-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

