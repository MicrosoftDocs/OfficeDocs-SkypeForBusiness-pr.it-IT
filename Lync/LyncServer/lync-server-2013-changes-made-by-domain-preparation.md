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
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="32842-102">Modifiche apportate dalla preparazione del dominio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32842-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32842-103">_**Ultimo argomento modificato:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="32842-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="32842-p101">Nella tabella riportata di seguito vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nella radice del dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="32842-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="32842-106">Voci di controllo di accesso aggiunte alla radice del dominio</span><span class="sxs-lookup"><span data-stu-id="32842-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="32842-107">ACE</span><span class="sxs-lookup"><span data-stu-id="32842-107">ACE</span></span></th>
<th><span data-ttu-id="32842-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="32842-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="32842-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="32842-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="32842-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="32842-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="32842-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="32842-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="32842-112">Utenti autenticati</span><span class="sxs-lookup"><span data-stu-id="32842-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32842-113">Read Container (not inherited)</span><span class="sxs-lookup"><span data-stu-id="32842-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="32842-114"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-115"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-116">No</span><span class="sxs-lookup"><span data-stu-id="32842-116">No</span></span></p></td>
<td><p><span data-ttu-id="32842-117">No</span><span class="sxs-lookup"><span data-stu-id="32842-117">No</span></span></p></td>
<td><p><span data-ttu-id="32842-118">No</span><span class="sxs-lookup"><span data-stu-id="32842-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32842-119">Read User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="32842-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="32842-120"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-121">No</span><span class="sxs-lookup"><span data-stu-id="32842-121">No</span></span></p></td>
<td><p><span data-ttu-id="32842-122">No</span><span class="sxs-lookup"><span data-stu-id="32842-122">No</span></span></p></td>
<td><p><span data-ttu-id="32842-123">No</span><span class="sxs-lookup"><span data-stu-id="32842-123">No</span></span></p></td>
<td><p><span data-ttu-id="32842-124">No</span><span class="sxs-lookup"><span data-stu-id="32842-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32842-125">Read User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="32842-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="32842-126"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-127">No</span><span class="sxs-lookup"><span data-stu-id="32842-127">No</span></span></p></td>
<td><p><span data-ttu-id="32842-128">No</span><span class="sxs-lookup"><span data-stu-id="32842-128">No</span></span></p></td>
<td><p><span data-ttu-id="32842-129">No</span><span class="sxs-lookup"><span data-stu-id="32842-129">No</span></span></p></td>
<td><p><span data-ttu-id="32842-130">No</span><span class="sxs-lookup"><span data-stu-id="32842-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32842-131">Read User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="32842-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="32842-132"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-133">No</span><span class="sxs-lookup"><span data-stu-id="32842-133">No</span></span></p></td>
<td><p><span data-ttu-id="32842-134">No</span><span class="sxs-lookup"><span data-stu-id="32842-134">No</span></span></p></td>
<td><p><span data-ttu-id="32842-135">No</span><span class="sxs-lookup"><span data-stu-id="32842-135">No</span></span></p></td>
<td><p><span data-ttu-id="32842-136">No</span><span class="sxs-lookup"><span data-stu-id="32842-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32842-137">Read User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="32842-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="32842-138"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-139">No</span><span class="sxs-lookup"><span data-stu-id="32842-139">No</span></span></p></td>
<td><p><span data-ttu-id="32842-140">No</span><span class="sxs-lookup"><span data-stu-id="32842-140">No</span></span></p></td>
<td><p><span data-ttu-id="32842-141">No</span><span class="sxs-lookup"><span data-stu-id="32842-141">No</span></span></p></td>
<td><p><span data-ttu-id="32842-142">No</span><span class="sxs-lookup"><span data-stu-id="32842-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32842-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="32842-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="32842-144"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-145">No</span><span class="sxs-lookup"><span data-stu-id="32842-145">No</span></span></p></td>
<td><p><span data-ttu-id="32842-146">No</span><span class="sxs-lookup"><span data-stu-id="32842-146">No</span></span></p></td>
<td><p><span data-ttu-id="32842-147">No</span><span class="sxs-lookup"><span data-stu-id="32842-147">No</span></span></p></td>
<td><p><span data-ttu-id="32842-148"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32842-149">Read User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="32842-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="32842-150"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-151">No</span><span class="sxs-lookup"><span data-stu-id="32842-151">No</span></span></p></td>
<td><p><span data-ttu-id="32842-152">No</span><span class="sxs-lookup"><span data-stu-id="32842-152">No</span></span></p></td>
<td><p><span data-ttu-id="32842-153">No</span><span class="sxs-lookup"><span data-stu-id="32842-153">No</span></span></p></td>
<td><p><span data-ttu-id="32842-154">No</span><span class="sxs-lookup"><span data-stu-id="32842-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32842-155">Write User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="32842-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="32842-156">No</span><span class="sxs-lookup"><span data-stu-id="32842-156">No</span></span></p></td>
<td><p><span data-ttu-id="32842-157">No</span><span class="sxs-lookup"><span data-stu-id="32842-157">No</span></span></p></td>
<td><p><span data-ttu-id="32842-158"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-159">No</span><span class="sxs-lookup"><span data-stu-id="32842-159">No</span></span></p></td>
<td><p><span data-ttu-id="32842-160">No</span><span class="sxs-lookup"><span data-stu-id="32842-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32842-161">Write User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="32842-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="32842-162">No</span><span class="sxs-lookup"><span data-stu-id="32842-162">No</span></span></p></td>
<td><p><span data-ttu-id="32842-163">No</span><span class="sxs-lookup"><span data-stu-id="32842-163">No</span></span></p></td>
<td><p><span data-ttu-id="32842-164"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-165">No</span><span class="sxs-lookup"><span data-stu-id="32842-165">No</span></span></p></td>
<td><p><span data-ttu-id="32842-166">No</span><span class="sxs-lookup"><span data-stu-id="32842-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32842-167">Write User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="32842-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="32842-168">No</span><span class="sxs-lookup"><span data-stu-id="32842-168">No</span></span></p></td>
<td><p><span data-ttu-id="32842-169">No</span><span class="sxs-lookup"><span data-stu-id="32842-169">No</span></span></p></td>
<td><p><span data-ttu-id="32842-170"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-171">No</span><span class="sxs-lookup"><span data-stu-id="32842-171">No</span></span></p></td>
<td><p><span data-ttu-id="32842-172">No</span><span class="sxs-lookup"><span data-stu-id="32842-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32842-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span><span class="sxs-lookup"><span data-stu-id="32842-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="32842-174">No</span><span class="sxs-lookup"><span data-stu-id="32842-174">No</span></span></p></td>
<td><p><span data-ttu-id="32842-175">No</span><span class="sxs-lookup"><span data-stu-id="32842-175">No</span></span></p></td>
<td><p><span data-ttu-id="32842-176">No</span><span class="sxs-lookup"><span data-stu-id="32842-176">No</span></span></p></td>
<td><p><span data-ttu-id="32842-177"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-178">No</span><span class="sxs-lookup"><span data-stu-id="32842-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32842-p102">Nella tabella seguente vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nei tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.</span><span class="sxs-lookup"><span data-stu-id="32842-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="32842-181">Voci di controllo di accesso aggiunte ai contenitori predefiniti</span><span class="sxs-lookup"><span data-stu-id="32842-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32842-182">ACE</span><span class="sxs-lookup"><span data-stu-id="32842-182">ACE</span></span></th>
<th><span data-ttu-id="32842-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="32842-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="32842-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="32842-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32842-185">Read Container (non ereditata)</span><span class="sxs-lookup"><span data-stu-id="32842-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="32842-186"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="32842-187"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="32842-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

