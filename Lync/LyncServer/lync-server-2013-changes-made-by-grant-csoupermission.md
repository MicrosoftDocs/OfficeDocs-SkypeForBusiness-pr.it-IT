---
title: 'Lync Server 2013: modifiche apportate da Grant-CsOUPermission'
description: 'Lync Server 2013: modifiche apportate da Grant-CsOUPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543612"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="3b361-103">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b361-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b361-104">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="3b361-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="3b361-105">Per delegare l'amministrazione di Lync Server 2013, è possibile aggiungere autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="3b361-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="3b361-106">Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata, come indicato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="3b361-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="3b361-107">Concessione di autorizzazioni per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="3b361-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="3b361-108">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente di un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3b361-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="3b361-109">Autorizzazioni concesse per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="3b361-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b361-110">Gruppo</span><span class="sxs-lookup"><span data-stu-id="3b361-110">Group</span></span></th>
<th><span data-ttu-id="3b361-111">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3b361-111">Permission</span></span></th>
<th><span data-ttu-id="3b361-112">Si applica a</span><span class="sxs-lookup"><span data-stu-id="3b361-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b361-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3b361-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3b361-114">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="3b361-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3b361-115">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-117">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-117">List contents</span></span></p>
<p><span data-ttu-id="3b361-118">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-118">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-119">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-120">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-122">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-122">List contents</span></span></p>
<p><span data-ttu-id="3b361-123">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-123">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-124">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-125">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-127">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-128">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-129">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-130">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="3b361-131">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-131">Read General-Information</span></span></p>
<p><span data-ttu-id="3b361-132">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="3b361-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3b361-133">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="3b361-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b361-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3b361-135">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-136">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3b361-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="3b361-137">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-138">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-139">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3b361-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3b361-140">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="3b361-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="3b361-141">Concessione di autorizzazioni per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="3b361-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="3b361-142">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3b361-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="3b361-143">Autorizzazioni concesse per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="3b361-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b361-144">Gruppo</span><span class="sxs-lookup"><span data-stu-id="3b361-144">Group</span></span></th>
<th><span data-ttu-id="3b361-145">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3b361-145">Permission</span></span></th>
<th><span data-ttu-id="3b361-146">Si applica a</span><span class="sxs-lookup"><span data-stu-id="3b361-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b361-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3b361-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3b361-148">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="3b361-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3b361-149">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-151">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-151">List contents</span></span></p>
<p><span data-ttu-id="3b361-152">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-152">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-153">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-154">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-156">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-156">List contents</span></span></p>
<p><span data-ttu-id="3b361-157">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-157">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-158">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-159">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-161">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="3b361-162">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="3b361-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="3b361-163">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b361-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3b361-165">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="3b361-166">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="3b361-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="3b361-167">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="3b361-168">Concessione di autorizzazioni per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="3b361-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="3b361-169">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti contatto o gli oggetti AppContact su un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3b361-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="3b361-170">Autorizzazioni concesse per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="3b361-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b361-171">Gruppo</span><span class="sxs-lookup"><span data-stu-id="3b361-171">Group</span></span></th>
<th><span data-ttu-id="3b361-172">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3b361-172">Permission</span></span></th>
<th><span data-ttu-id="3b361-173">Si applica a</span><span class="sxs-lookup"><span data-stu-id="3b361-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b361-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3b361-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3b361-175">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="3b361-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3b361-176">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-178">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-178">List contents</span></span></p>
<p><span data-ttu-id="3b361-179">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-179">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-180">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-181">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-183">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-183">List contents</span></span></p>
<p><span data-ttu-id="3b361-184">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-184">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-185">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-186">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-188">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-189">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-190">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-191">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="3b361-192">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-192">Read General-Information</span></span></p>
<p><span data-ttu-id="3b361-193">Leggere Personal-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="3b361-194">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="3b361-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3b361-195">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b361-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3b361-197">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-198">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="3b361-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="3b361-199">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="3b361-199">Write displayName</span></span></p>
<p><span data-ttu-id="3b361-200">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="3b361-200">Write description</span></span></p>
<p><span data-ttu-id="3b361-201">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3b361-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="3b361-202">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3b361-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="3b361-203">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-204">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-205">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3b361-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3b361-206">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="3b361-207">Concessione di autorizzazioni per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="3b361-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="3b361-208">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3b361-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="3b361-209">Autorizzazioni concesse per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="3b361-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b361-210">Gruppo</span><span class="sxs-lookup"><span data-stu-id="3b361-210">Group</span></span></th>
<th><span data-ttu-id="3b361-211">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3b361-211">Permission</span></span></th>
<th><span data-ttu-id="3b361-212">Si applica a</span><span class="sxs-lookup"><span data-stu-id="3b361-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b361-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3b361-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3b361-214">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="3b361-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3b361-215">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-217">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-217">List contents</span></span></p>
<p><span data-ttu-id="3b361-218">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-218">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-219">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-220">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-222">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-222">List contents</span></span></p>
<p><span data-ttu-id="3b361-223">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-223">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-224">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-225">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-227">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-228">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-229">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-230">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="3b361-231">Leggere Personal-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="3b361-232">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-232">Read General-Information</span></span></p>
<p><span data-ttu-id="3b361-233">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="3b361-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3b361-234">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b361-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3b361-236">Crea elemento figlio</span><span class="sxs-lookup"><span data-stu-id="3b361-236">Create child</span></span></p>
<p><span data-ttu-id="3b361-237">Elimina elemento figlio</span><span class="sxs-lookup"><span data-stu-id="3b361-237">Delete child</span></span></p>
<p><span data-ttu-id="3b361-238">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="3b361-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="3b361-239">Contatto</span><span class="sxs-lookup"><span data-stu-id="3b361-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b361-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3b361-241">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="3b361-241">Write displayName</span></span></p>
<p><span data-ttu-id="3b361-242">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="3b361-242">Write description</span></span></p>
<p><span data-ttu-id="3b361-243">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3b361-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="3b361-244">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="3b361-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b361-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3b361-246">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-247">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="3b361-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="3b361-248">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="3b361-248">Write displayName</span></span></p>
<p><span data-ttu-id="3b361-249">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="3b361-249">Write description</span></span></p>
<p><span data-ttu-id="3b361-250">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3b361-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="3b361-251">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3b361-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="3b361-252">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-253">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-254">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3b361-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3b361-255">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="3b361-256">Concessione di autorizzazioni per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="3b361-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="3b361-257">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3b361-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="3b361-258">Autorizzazioni concesse per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="3b361-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b361-259">Gruppo</span><span class="sxs-lookup"><span data-stu-id="3b361-259">Group</span></span></th>
<th><span data-ttu-id="3b361-260">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3b361-260">Permission</span></span></th>
<th><span data-ttu-id="3b361-261">Si applica a</span><span class="sxs-lookup"><span data-stu-id="3b361-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b361-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3b361-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="3b361-263">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="3b361-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="3b361-264">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-266">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-266">List contents</span></span></p>
<p><span data-ttu-id="3b361-267">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-267">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-268">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-269">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-271">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="3b361-271">List contents</span></span></p>
<p><span data-ttu-id="3b361-272">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="3b361-272">Read all properties</span></span></p>
<p><span data-ttu-id="3b361-273">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="3b361-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="3b361-274">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="3b361-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b361-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="3b361-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="3b361-276">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-277">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-278">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-279">Leggere Personal-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="3b361-280">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="3b361-281">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="3b361-281">Read General-Information</span></span></p>
<p><span data-ttu-id="3b361-282">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="3b361-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3b361-283">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b361-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b361-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3b361-285">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="3b361-286">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="3b361-287">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3b361-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="3b361-288">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3b361-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3b361-289">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="3b361-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

