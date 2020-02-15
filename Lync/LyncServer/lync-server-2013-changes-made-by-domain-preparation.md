---
title: 'Lync Server 2013: modifiche apportate dalla preparazione del dominio'
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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="73670-102">Modifiche apportate dalla preparazione del dominio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73670-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73670-103">_**Ultimo argomento modificato:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="73670-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="73670-p101">Nella tabella riportata di seguito vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nella radice del dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="73670-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="73670-106">Voci di controllo di accesso aggiunte alla radice del dominio</span><span class="sxs-lookup"><span data-stu-id="73670-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="73670-107">ACE</span><span class="sxs-lookup"><span data-stu-id="73670-107">ACE</span></span></th>
<th><span data-ttu-id="73670-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="73670-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="73670-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="73670-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="73670-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="73670-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="73670-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="73670-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="73670-112">Utenti autenticati</span><span class="sxs-lookup"><span data-stu-id="73670-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73670-113">Read Container (not inherited)</span><span class="sxs-lookup"><span data-stu-id="73670-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="73670-114"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-115"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-116">No</span><span class="sxs-lookup"><span data-stu-id="73670-116">No</span></span></p></td>
<td><p><span data-ttu-id="73670-117">No</span><span class="sxs-lookup"><span data-stu-id="73670-117">No</span></span></p></td>
<td><p><span data-ttu-id="73670-118">No</span><span class="sxs-lookup"><span data-stu-id="73670-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73670-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="73670-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="73670-120"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-121">No</span><span class="sxs-lookup"><span data-stu-id="73670-121">No</span></span></p></td>
<td><p><span data-ttu-id="73670-122">No</span><span class="sxs-lookup"><span data-stu-id="73670-122">No</span></span></p></td>
<td><p><span data-ttu-id="73670-123">No</span><span class="sxs-lookup"><span data-stu-id="73670-123">No</span></span></p></td>
<td><p><span data-ttu-id="73670-124">No</span><span class="sxs-lookup"><span data-stu-id="73670-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73670-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="73670-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="73670-126"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-127">No</span><span class="sxs-lookup"><span data-stu-id="73670-127">No</span></span></p></td>
<td><p><span data-ttu-id="73670-128">No</span><span class="sxs-lookup"><span data-stu-id="73670-128">No</span></span></p></td>
<td><p><span data-ttu-id="73670-129">No</span><span class="sxs-lookup"><span data-stu-id="73670-129">No</span></span></p></td>
<td><p><span data-ttu-id="73670-130">No</span><span class="sxs-lookup"><span data-stu-id="73670-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73670-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="73670-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="73670-132"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-133">No</span><span class="sxs-lookup"><span data-stu-id="73670-133">No</span></span></p></td>
<td><p><span data-ttu-id="73670-134">No</span><span class="sxs-lookup"><span data-stu-id="73670-134">No</span></span></p></td>
<td><p><span data-ttu-id="73670-135">No</span><span class="sxs-lookup"><span data-stu-id="73670-135">No</span></span></p></td>
<td><p><span data-ttu-id="73670-136">No</span><span class="sxs-lookup"><span data-stu-id="73670-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73670-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="73670-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="73670-138"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-139">No</span><span class="sxs-lookup"><span data-stu-id="73670-139">No</span></span></p></td>
<td><p><span data-ttu-id="73670-140">No</span><span class="sxs-lookup"><span data-stu-id="73670-140">No</span></span></p></td>
<td><p><span data-ttu-id="73670-141">No</span><span class="sxs-lookup"><span data-stu-id="73670-141">No</span></span></p></td>
<td><p><span data-ttu-id="73670-142">No</span><span class="sxs-lookup"><span data-stu-id="73670-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73670-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="73670-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="73670-144"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-145">No</span><span class="sxs-lookup"><span data-stu-id="73670-145">No</span></span></p></td>
<td><p><span data-ttu-id="73670-146">No</span><span class="sxs-lookup"><span data-stu-id="73670-146">No</span></span></p></td>
<td><p><span data-ttu-id="73670-147">No</span><span class="sxs-lookup"><span data-stu-id="73670-147">No</span></span></p></td>
<td><p><span data-ttu-id="73670-148"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73670-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="73670-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="73670-150"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-151">No</span><span class="sxs-lookup"><span data-stu-id="73670-151">No</span></span></p></td>
<td><p><span data-ttu-id="73670-152">No</span><span class="sxs-lookup"><span data-stu-id="73670-152">No</span></span></p></td>
<td><p><span data-ttu-id="73670-153">No</span><span class="sxs-lookup"><span data-stu-id="73670-153">No</span></span></p></td>
<td><p><span data-ttu-id="73670-154">No</span><span class="sxs-lookup"><span data-stu-id="73670-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73670-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="73670-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="73670-156">No</span><span class="sxs-lookup"><span data-stu-id="73670-156">No</span></span></p></td>
<td><p><span data-ttu-id="73670-157">No</span><span class="sxs-lookup"><span data-stu-id="73670-157">No</span></span></p></td>
<td><p><span data-ttu-id="73670-158"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-159">No</span><span class="sxs-lookup"><span data-stu-id="73670-159">No</span></span></p></td>
<td><p><span data-ttu-id="73670-160">No</span><span class="sxs-lookup"><span data-stu-id="73670-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73670-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="73670-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="73670-162">No</span><span class="sxs-lookup"><span data-stu-id="73670-162">No</span></span></p></td>
<td><p><span data-ttu-id="73670-163">No</span><span class="sxs-lookup"><span data-stu-id="73670-163">No</span></span></p></td>
<td><p><span data-ttu-id="73670-164"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-165">No</span><span class="sxs-lookup"><span data-stu-id="73670-165">No</span></span></p></td>
<td><p><span data-ttu-id="73670-166">No</span><span class="sxs-lookup"><span data-stu-id="73670-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73670-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="73670-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="73670-168">No</span><span class="sxs-lookup"><span data-stu-id="73670-168">No</span></span></p></td>
<td><p><span data-ttu-id="73670-169">No</span><span class="sxs-lookup"><span data-stu-id="73670-169">No</span></span></p></td>
<td><p><span data-ttu-id="73670-170"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-171">No</span><span class="sxs-lookup"><span data-stu-id="73670-171">No</span></span></p></td>
<td><p><span data-ttu-id="73670-172">No</span><span class="sxs-lookup"><span data-stu-id="73670-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73670-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span><span class="sxs-lookup"><span data-stu-id="73670-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="73670-174">No</span><span class="sxs-lookup"><span data-stu-id="73670-174">No</span></span></p></td>
<td><p><span data-ttu-id="73670-175">No</span><span class="sxs-lookup"><span data-stu-id="73670-175">No</span></span></p></td>
<td><p><span data-ttu-id="73670-176">No</span><span class="sxs-lookup"><span data-stu-id="73670-176">No</span></span></p></td>
<td><p><span data-ttu-id="73670-177"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-178">No</span><span class="sxs-lookup"><span data-stu-id="73670-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="73670-p102">Nella tabella seguente vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nei tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="73670-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="73670-181">Voci di controllo di accesso aggiunte ai contenitori predefiniti</span><span class="sxs-lookup"><span data-stu-id="73670-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73670-182">ACE</span><span class="sxs-lookup"><span data-stu-id="73670-182">ACE</span></span></th>
<th><span data-ttu-id="73670-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="73670-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="73670-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="73670-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73670-185">Read Container (non ereditata)</span><span class="sxs-lookup"><span data-stu-id="73670-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="73670-186"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="73670-187"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="73670-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

