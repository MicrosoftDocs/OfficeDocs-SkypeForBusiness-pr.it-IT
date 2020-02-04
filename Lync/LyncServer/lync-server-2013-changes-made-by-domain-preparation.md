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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="7cd15-102">Modifiche apportate dalla preparazione del dominio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cd15-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cd15-103">_**Argomento Ultima modifica:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="7cd15-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="7cd15-104">Nella tabella seguente sono elencate le voci di controllo di accesso (ACE) create dalla preparazione del dominio nella radice del dominio.</span><span class="sxs-lookup"><span data-stu-id="7cd15-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="7cd15-105">Tutte le voci ACE vengono ereditate se non diversamente specificato.</span><span class="sxs-lookup"><span data-stu-id="7cd15-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="7cd15-106">Voci ACE aggiunte alla radice del dominio</span><span class="sxs-lookup"><span data-stu-id="7cd15-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="7cd15-107">ACE</span><span class="sxs-lookup"><span data-stu-id="7cd15-107">ACE</span></span></th>
<th><span data-ttu-id="7cd15-108">RTCUniversal-UserReadOnly-gruppo</span><span class="sxs-lookup"><span data-stu-id="7cd15-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="7cd15-109">RTCUniversal-ServerReadOnly-gruppo</span><span class="sxs-lookup"><span data-stu-id="7cd15-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="7cd15-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="7cd15-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="7cd15-111">RTCHSUniversal-servizi</span><span class="sxs-lookup"><span data-stu-id="7cd15-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="7cd15-112">Utenti autenticati</span><span class="sxs-lookup"><span data-stu-id="7cd15-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cd15-113">Contenitore di lettura (non ereditato)</span><span class="sxs-lookup"><span data-stu-id="7cd15-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="7cd15-114"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-115"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-116">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-116">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-117">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-117">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-118">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd15-119">Leggere l'utente di PropertySet user-account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="7cd15-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7cd15-120"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-121">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-121">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-122">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-122">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-123">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-123">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-124">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd15-125">Leggere l'utente PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="7cd15-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="7cd15-126"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-127">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-127">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-128">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-128">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-129">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-129">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-130">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd15-131">Leggere l'utente PropertySet generale-informazioni</span><span class="sxs-lookup"><span data-stu-id="7cd15-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="7cd15-132"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-133">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-133">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-134">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-134">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-135">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-135">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-136">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd15-137">Leggere l'utente PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="7cd15-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="7cd15-138"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-139">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-139">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-140">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-140">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-141">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-141">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-142">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd15-143">Leggi utente PropertySet RTCUserSearchProperty-set</span><span class="sxs-lookup"><span data-stu-id="7cd15-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="7cd15-144"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-145">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-145">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-146">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-146">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-147">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-147">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-148"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd15-149">Leggere l'utente PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7cd15-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="7cd15-150"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-151">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-151">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-152">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-152">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-153">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-153">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-154">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd15-155">Scrivere gli indirizzi proxy della proprietà utente</span><span class="sxs-lookup"><span data-stu-id="7cd15-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="7cd15-156">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-156">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-157">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-157">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-158"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-159">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-159">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-160">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd15-161">Scrivere l'utente PropertySet RTCUserSearchProperty-set</span><span class="sxs-lookup"><span data-stu-id="7cd15-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="7cd15-162">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-162">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-163">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-163">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-164"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-165">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-165">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-166">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd15-167">Scrivere l'utente PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="7cd15-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="7cd15-168">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-168">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-169">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-169">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-170"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-171">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-171">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-172">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd15-173">Leggere PropertySet DS-replica-Get-modifiche di tutti gli oggetti di Active Directory</span><span class="sxs-lookup"><span data-stu-id="7cd15-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="7cd15-174">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-174">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-175">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-175">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-176">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-176">No</span></span></p></td>
<td><p><span data-ttu-id="7cd15-177"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-178">No</span><span class="sxs-lookup"><span data-stu-id="7cd15-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7cd15-179">Nella tabella seguente sono elencate le voci ACE create dalla preparazione del dominio nei tre contenitori predefiniti: utenti, computer e controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="7cd15-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="7cd15-180">Tutte le voci ACE vengono ereditate se non diversamente specificato.</span><span class="sxs-lookup"><span data-stu-id="7cd15-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="7cd15-181">Voci ACE aggiunte ai contenitori predefiniti</span><span class="sxs-lookup"><span data-stu-id="7cd15-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cd15-182">ACE</span><span class="sxs-lookup"><span data-stu-id="7cd15-182">ACE</span></span></th>
<th><span data-ttu-id="7cd15-183">RTCUniversal-UserReadOnly-gruppo</span><span class="sxs-lookup"><span data-stu-id="7cd15-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="7cd15-184">RTCUniversal-ServerReadOnly-gruppo</span><span class="sxs-lookup"><span data-stu-id="7cd15-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cd15-185">Contenitore di lettura (non ereditato)</span><span class="sxs-lookup"><span data-stu-id="7cd15-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="7cd15-186"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7cd15-187"><strong>Sì</strong></span><span class="sxs-lookup"><span data-stu-id="7cd15-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

