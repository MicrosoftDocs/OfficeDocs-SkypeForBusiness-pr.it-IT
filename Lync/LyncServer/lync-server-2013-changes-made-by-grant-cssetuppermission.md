---
title: 'Lync Server 2013: modifiche apportate da Grant-CsSetupPermission'
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="343d5-102">Modifiche apportate da Grant-CsSetupPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="343d5-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="343d5-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="343d5-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="343d5-104">Per delegare l'installazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per un'unità organizzativa di Active Directory specifica, consentendo ai membri del gruppo RTCUniversalServerAdmins nell'unità organizzativa di installare Lync Server 2013 nell'oggetto dominio senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="343d5-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="343d5-105">Il cmdlet **Grant-CsSetupPermission** concede al gruppo RTCUniversalServerAdmins le autorizzazioni per un'unità organizzativa, come specificato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="343d5-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="343d5-106">Autorizzazioni concesse a oggetti nell'unità organizzativa</span><span class="sxs-lookup"><span data-stu-id="343d5-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="343d5-107">Le autorizzazioni si applicano a:</span><span class="sxs-lookup"><span data-stu-id="343d5-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="343d5-108">Autorizzazioni concesse:</span><span class="sxs-lookup"><span data-stu-id="343d5-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="343d5-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="343d5-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="343d5-110">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-111">Leggi servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="343d5-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="343d5-112">Scrivi in servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="343d5-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="343d5-113">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="343d5-114">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="343d5-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343d5-115">Oggetti serviceConnectionPoint discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-116">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-117">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="343d5-118">Autorizzazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="343d5-119">Crea elemento figlio</span><span class="sxs-lookup"><span data-stu-id="343d5-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="343d5-120">Elimina elemento figlio</span><span class="sxs-lookup"><span data-stu-id="343d5-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="343d5-121">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="343d5-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="343d5-122">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="343d5-123">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="343d5-124">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343d5-125">Oggetti msRTCSIP-Server discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-126">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-127">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="343d5-128">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="343d5-129">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343d5-130">Oggetti msRTCSIP-WebComponents discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-131">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-132">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="343d5-133">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="343d5-134">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343d5-135">Oggetti msRTCSIP-MCU discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-136">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-137">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="343d5-138">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="343d5-139">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343d5-140">Oggetti msRTCSIP-MediationServer discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-141">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-142">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="343d5-143">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="343d5-144">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343d5-145">Oggetti msRTCSIP-ApplicationServer discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-146">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-147">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="343d5-148">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="343d5-149">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343d5-150">Oggetti msRTCSIP-ConnectionPoint discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-151">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="343d5-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-152">Proprietà di scrittura</span><span class="sxs-lookup"><span data-stu-id="343d5-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="343d5-153">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="343d5-154">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343d5-155">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="343d5-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="343d5-156">Accesso speciale per serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="343d5-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-157">Crea oggetti figli</span><span class="sxs-lookup"><span data-stu-id="343d5-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="343d5-158">Elimina oggetti figli</span><span class="sxs-lookup"><span data-stu-id="343d5-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="343d5-159">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="343d5-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="343d5-160">Accesso speciale per informazioni pubbliche:</span><span class="sxs-lookup"><span data-stu-id="343d5-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-161">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="343d5-162">Accesso speciale per il nome host DNS:</span><span class="sxs-lookup"><span data-stu-id="343d5-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="343d5-163">Proprietà di lettura</span><span class="sxs-lookup"><span data-stu-id="343d5-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

