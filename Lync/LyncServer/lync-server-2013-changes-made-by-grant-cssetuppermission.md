---
title: 'Lync Server 2013: modifiche apportate da Grant-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="cdd01-102">Modifiche apportate da Grant-CsSetupPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd01-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdd01-103">_**Argomento Ultima modifica:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="cdd01-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="cdd01-104">Per delegare la configurazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per una specifica unità organizzativa di Active Directory, che consente ai membri del gruppo RTCUniversalServerAdmins in tale OU di installare Lync Server 2013 nell'elemento specificato dominio senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="cdd01-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="cdd01-105">Il cmdlet **Grant-CsSetupPermission** concede le autorizzazioni di gruppo RTCUniversalServerAdmins per un'unità organizzativa, come specificato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="cdd01-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="cdd01-106">Autorizzazioni concesse agli oggetti nell'unità organizzativa</span><span class="sxs-lookup"><span data-stu-id="cdd01-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdd01-107">Le autorizzazioni si applicano a:</span><span class="sxs-lookup"><span data-stu-id="cdd01-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="cdd01-108">Le autorizzazioni concesse sono:</span><span class="sxs-lookup"><span data-stu-id="cdd01-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdd01-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cdd01-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="cdd01-110">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-111">Leggere servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="cdd01-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="cdd01-112">Scrivere servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="cdd01-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="cdd01-113">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="cdd01-114">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="cdd01-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd01-115">Oggetti serviceConnectionPoint discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-116">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-117">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="cdd01-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="cdd01-118">Autorizzazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="cdd01-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="cdd01-119">Creare un bambino</span><span class="sxs-lookup"><span data-stu-id="cdd01-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="cdd01-120">Eliminare il bambino</span><span class="sxs-lookup"><span data-stu-id="cdd01-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="cdd01-121">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="cdd01-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="cdd01-122">Proprietà Write</span><span class="sxs-lookup"><span data-stu-id="cdd01-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-123">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-124">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd01-125">Oggetti msRTCSIP-Server discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-126">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-127">Proprietà Write</span><span class="sxs-lookup"><span data-stu-id="cdd01-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-128">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-129">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd01-130">Oggetti msRTCSIP-WebComponents discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-131">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-132">Proprietà Write</span><span class="sxs-lookup"><span data-stu-id="cdd01-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-133">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-134">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd01-135">Oggetti msRTCSIP-MCU discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-136">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-137">Proprietà Write</span><span class="sxs-lookup"><span data-stu-id="cdd01-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-138">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-139">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd01-140">Oggetti msRTCSIP-MediationServer discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-141">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-142">Proprietà Write</span><span class="sxs-lookup"><span data-stu-id="cdd01-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-143">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-144">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd01-145">Oggetti msRTCSIP-ApplicationServer discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-146">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-147">Proprietà Write</span><span class="sxs-lookup"><span data-stu-id="cdd01-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-148">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-149">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd01-150">Oggetti msRTCSIP-ConnectionPoint discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-151">Accesso speciale:</span><span class="sxs-lookup"><span data-stu-id="cdd01-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-152">Proprietà Write</span><span class="sxs-lookup"><span data-stu-id="cdd01-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-153">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="cdd01-154">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd01-155">Oggetti computer discendenti</span><span class="sxs-lookup"><span data-stu-id="cdd01-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="cdd01-156">Accesso speciale per serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="cdd01-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-157">Creare oggetti figlio</span><span class="sxs-lookup"><span data-stu-id="cdd01-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="cdd01-158">Eliminare oggetti figlio</span><span class="sxs-lookup"><span data-stu-id="cdd01-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="cdd01-159">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="cdd01-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="cdd01-160">Accesso speciale per informazioni pubbliche:</span><span class="sxs-lookup"><span data-stu-id="cdd01-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-161">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="cdd01-162">Accesso speciale per il nome host DNS:</span><span class="sxs-lookup"><span data-stu-id="cdd01-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="cdd01-163">Proprietà Read</span><span class="sxs-lookup"><span data-stu-id="cdd01-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

