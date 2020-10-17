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
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529503"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="e73f3-102">Modifiche apportate dalla preparazione del dominio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e73f3-102">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e73f3-103">_**Ultimo argomento modificato:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="e73f3-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="e73f3-p101">Nella tabella riportata di seguito vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nella radice del dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="e73f3-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="e73f3-106">Voci di controllo di accesso aggiunte alla radice del dominio</span><span class="sxs-lookup"><span data-stu-id="e73f3-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="e73f3-107">ACE</span><span class="sxs-lookup"><span data-stu-id="e73f3-107">ACE</span></span></th>
<th><span data-ttu-id="e73f3-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="e73f3-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="e73f3-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="e73f3-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="e73f3-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="e73f3-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="e73f3-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="e73f3-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="e73f3-112">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="e73f3-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e73f3-113">Read Container (not inherited)</span><span class="sxs-lookup"><span data-stu-id="e73f3-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="e73f3-114"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-115"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-116">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-116">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-117">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-117">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-118">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e73f3-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="e73f3-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e73f3-120"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-121">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-121">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-122">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-122">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-123">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-123">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-124">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e73f3-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="e73f3-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="e73f3-126"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-127">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-127">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-128">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-128">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-129">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-129">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-130">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e73f3-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="e73f3-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="e73f3-132"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-133">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-133">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-134">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-134">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-135">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-135">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-136">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e73f3-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="e73f3-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="e73f3-138"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-139">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-139">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-140">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-140">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-141">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-141">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-142">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e73f3-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="e73f3-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="e73f3-144"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-145">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-145">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-146">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-146">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-147">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-147">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-148"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e73f3-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e73f3-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="e73f3-150"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-151">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-151">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-152">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-152">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-153">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-153">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-154">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e73f3-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="e73f3-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="e73f3-156">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-156">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-157">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-157">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-158"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-159">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-159">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-160">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e73f3-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="e73f3-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="e73f3-162">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-162">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-163">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-163">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-164"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-165">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-165">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-166">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e73f3-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e73f3-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="e73f3-168">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-168">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-169">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-169">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-170"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-171">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-171">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-172">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e73f3-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span><span class="sxs-lookup"><span data-stu-id="e73f3-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="e73f3-174">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-174">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-175">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-175">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-176">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-176">No</span></span></p></td>
<td><p><span data-ttu-id="e73f3-177"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-178">No</span><span class="sxs-lookup"><span data-stu-id="e73f3-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e73f3-p102">Nella tabella seguente vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nei tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="e73f3-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="e73f3-181">Voci di controllo di accesso aggiunte ai contenitori predefiniti</span><span class="sxs-lookup"><span data-stu-id="e73f3-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e73f3-182">ACE</span><span class="sxs-lookup"><span data-stu-id="e73f3-182">ACE</span></span></th>
<th><span data-ttu-id="e73f3-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="e73f3-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="e73f3-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="e73f3-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e73f3-185">Read Container (non ereditata)</span><span class="sxs-lookup"><span data-stu-id="e73f3-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="e73f3-186"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="e73f3-187"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="e73f3-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

