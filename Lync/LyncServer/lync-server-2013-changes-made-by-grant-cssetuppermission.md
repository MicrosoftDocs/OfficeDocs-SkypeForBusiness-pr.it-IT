---
title: 'Lync Server 2013: modifiche apportate da Grant-CsSetupPermission'
description: 'Lync Server 2013: modifiche apportate da Grant-CsSetupPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543602"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="7d3d7-103">Modifiche apportate da Grant-CsSetupPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d3d7-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d3d7-104">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="7d3d7-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="7d3d7-105">Per delegare l'installazione, è possibile concedere le autorizzazioni al gruppo universale RTCUniversalServerAdmins per un'unità organizzativa di Active Directory specifica, consentendo ai membri del gruppo RTCUniversalServerAdmins nell'unità organizzativa di installare Lync Server 2013 nel dominio specificato senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="7d3d7-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="7d3d7-106">Il cmdlet **Grant-CsSetupPermission** concede al gruppo RTCUniversalServerAdmins le autorizzazioni per un'unità organizzativa, come specificato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="7d3d7-107">Autorizzazioni concesse a oggetti nell'unità organizzativa</span><span class="sxs-lookup"><span data-stu-id="7d3d7-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d3d7-108">Le autorizzazioni si applicano a:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="7d3d7-109">Autorizzazioni concesse:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d3d7-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7d3d7-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-111">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-112">Leggi servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="7d3d7-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-113">Scrivi in servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="7d3d7-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-114">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-115">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="7d3d7-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d3d7-116">Oggetti serviceConnectionPoint discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-117">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-118">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-119">Autorizzazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-120">Crea elemento figlio</span><span class="sxs-lookup"><span data-stu-id="7d3d7-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-121">Elimina elemento figlio</span><span class="sxs-lookup"><span data-stu-id="7d3d7-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-122">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="7d3d7-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-123">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-124">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-125">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d3d7-126">Oggetti msRTCSIP-Server discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-127">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-128">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-129">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-130">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d3d7-131">Oggetti msRTCSIP-WebComponents discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-132">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-133">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-134">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-135">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d3d7-136">Oggetti msRTCSIP-MCU discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-137">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-138">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-139">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-140">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d3d7-141">Oggetti msRTCSIP-MediationServer discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-142">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-143">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-144">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-145">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d3d7-146">Oggetti msRTCSIP-ApplicationServer discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-147">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-148">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-149">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-150">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d3d7-151">Oggetti msRTCSIP-ConnectionPoint discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-152">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-153">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-154">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-155">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d3d7-156">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="7d3d7-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="7d3d7-157">Accesso speciale per serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-158">Crea oggetti figli</span><span class="sxs-lookup"><span data-stu-id="7d3d7-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-159">Elimina oggetti figli</span><span class="sxs-lookup"><span data-stu-id="7d3d7-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="7d3d7-160">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="7d3d7-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="7d3d7-161">Accesso speciale per informazioni pubbliche:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-162">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="7d3d7-163">Accesso speciale per il nome host DNS:</span><span class="sxs-lookup"><span data-stu-id="7d3d7-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d3d7-164">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="7d3d7-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

