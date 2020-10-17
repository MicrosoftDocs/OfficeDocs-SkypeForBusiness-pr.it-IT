---
title: 'Lync Server 2013: modifiche apportate dalla preparazione del dominio'
description: 'Lync Server 2013: modifiche apportate dalla preparazione del dominio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543692"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="c793a-103">Modifiche apportate dalla preparazione del dominio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c793a-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c793a-104">_**Ultimo argomento modificato:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="c793a-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="c793a-p101">Nella tabella riportata di seguito vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nella radice del dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="c793a-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="c793a-107">Voci di controllo di accesso aggiunte alla radice del dominio</span><span class="sxs-lookup"><span data-stu-id="c793a-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c793a-108">ACE</span><span class="sxs-lookup"><span data-stu-id="c793a-108">ACE</span></span></th>
<th><span data-ttu-id="c793a-109">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c793a-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c793a-110">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c793a-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="c793a-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="c793a-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="c793a-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="c793a-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="c793a-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="c793a-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c793a-114">Read Container (not inherited)</span><span class="sxs-lookup"><span data-stu-id="c793a-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c793a-115"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-116"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-117">No</span><span class="sxs-lookup"><span data-stu-id="c793a-117">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-118">No</span><span class="sxs-lookup"><span data-stu-id="c793a-118">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-119">No</span><span class="sxs-lookup"><span data-stu-id="c793a-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c793a-120">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="c793a-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c793a-121"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-122">No</span><span class="sxs-lookup"><span data-stu-id="c793a-122">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-123">No</span><span class="sxs-lookup"><span data-stu-id="c793a-123">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-124">No</span><span class="sxs-lookup"><span data-stu-id="c793a-124">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-125">No</span><span class="sxs-lookup"><span data-stu-id="c793a-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c793a-126">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="c793a-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="c793a-127"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-128">No</span><span class="sxs-lookup"><span data-stu-id="c793a-128">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-129">No</span><span class="sxs-lookup"><span data-stu-id="c793a-129">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-130">No</span><span class="sxs-lookup"><span data-stu-id="c793a-130">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-131">No</span><span class="sxs-lookup"><span data-stu-id="c793a-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c793a-132">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="c793a-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="c793a-133"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-134">No</span><span class="sxs-lookup"><span data-stu-id="c793a-134">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-135">No</span><span class="sxs-lookup"><span data-stu-id="c793a-135">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-136">No</span><span class="sxs-lookup"><span data-stu-id="c793a-136">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-137">No</span><span class="sxs-lookup"><span data-stu-id="c793a-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c793a-138">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="c793a-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="c793a-139"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-140">No</span><span class="sxs-lookup"><span data-stu-id="c793a-140">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-141">No</span><span class="sxs-lookup"><span data-stu-id="c793a-141">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-142">No</span><span class="sxs-lookup"><span data-stu-id="c793a-142">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-143">No</span><span class="sxs-lookup"><span data-stu-id="c793a-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c793a-144">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="c793a-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c793a-145"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-146">No</span><span class="sxs-lookup"><span data-stu-id="c793a-146">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-147">No</span><span class="sxs-lookup"><span data-stu-id="c793a-147">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-148">No</span><span class="sxs-lookup"><span data-stu-id="c793a-148">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-149"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c793a-150">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c793a-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c793a-151"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-152">No</span><span class="sxs-lookup"><span data-stu-id="c793a-152">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-153">No</span><span class="sxs-lookup"><span data-stu-id="c793a-153">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-154">No</span><span class="sxs-lookup"><span data-stu-id="c793a-154">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-155">No</span><span class="sxs-lookup"><span data-stu-id="c793a-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c793a-156">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="c793a-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="c793a-157">No</span><span class="sxs-lookup"><span data-stu-id="c793a-157">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-158">No</span><span class="sxs-lookup"><span data-stu-id="c793a-158">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-159"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-160">No</span><span class="sxs-lookup"><span data-stu-id="c793a-160">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-161">No</span><span class="sxs-lookup"><span data-stu-id="c793a-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c793a-162">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="c793a-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c793a-163">No</span><span class="sxs-lookup"><span data-stu-id="c793a-163">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-164">No</span><span class="sxs-lookup"><span data-stu-id="c793a-164">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-165"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-166">No</span><span class="sxs-lookup"><span data-stu-id="c793a-166">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-167">No</span><span class="sxs-lookup"><span data-stu-id="c793a-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c793a-168">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c793a-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c793a-169">No</span><span class="sxs-lookup"><span data-stu-id="c793a-169">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-170">No</span><span class="sxs-lookup"><span data-stu-id="c793a-170">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-171"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-172">No</span><span class="sxs-lookup"><span data-stu-id="c793a-172">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-173">No</span><span class="sxs-lookup"><span data-stu-id="c793a-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c793a-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span><span class="sxs-lookup"><span data-stu-id="c793a-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="c793a-175">No</span><span class="sxs-lookup"><span data-stu-id="c793a-175">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-176">No</span><span class="sxs-lookup"><span data-stu-id="c793a-176">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-177">No</span><span class="sxs-lookup"><span data-stu-id="c793a-177">No</span></span></p></td>
<td><p><span data-ttu-id="c793a-178"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-179">No</span><span class="sxs-lookup"><span data-stu-id="c793a-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c793a-p102">Nella tabella seguente vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nei tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="c793a-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="c793a-182">Voci di controllo di accesso aggiunte ai contenitori predefiniti</span><span class="sxs-lookup"><span data-stu-id="c793a-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c793a-183">ACE</span><span class="sxs-lookup"><span data-stu-id="c793a-183">ACE</span></span></th>
<th><span data-ttu-id="c793a-184">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c793a-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c793a-185">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c793a-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c793a-186">Read Container (non ereditata)</span><span class="sxs-lookup"><span data-stu-id="c793a-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c793a-187"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c793a-188"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="c793a-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

