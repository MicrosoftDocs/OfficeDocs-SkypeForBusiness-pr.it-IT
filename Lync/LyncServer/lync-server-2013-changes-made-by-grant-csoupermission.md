---
title: 'Lync Server 2013: modifiche apportate da Grant-CsOUPermission'
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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529433"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="12a54-102">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12a54-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12a54-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="12a54-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="12a54-104">Per delegare l'amministrazione di Lync Server 2013, è possibile aggiungere autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="12a54-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="12a54-105">Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata, come indicato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="12a54-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="12a54-106">Concessione di autorizzazioni per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="12a54-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="12a54-107">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente di un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="12a54-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="12a54-108">Autorizzazioni concesse per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="12a54-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12a54-109">Gruppo</span><span class="sxs-lookup"><span data-stu-id="12a54-109">Group</span></span></th>
<th><span data-ttu-id="12a54-110">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="12a54-110">Permission</span></span></th>
<th><span data-ttu-id="12a54-111">Si applica a</span><span class="sxs-lookup"><span data-stu-id="12a54-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a54-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12a54-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12a54-113">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="12a54-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12a54-114">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-116">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-116">List contents</span></span></p>
<p><span data-ttu-id="12a54-117">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-117">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-118">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-119">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-121">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-121">List contents</span></span></p>
<p><span data-ttu-id="12a54-122">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-122">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-123">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-124">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-126">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-127">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-128">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-129">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="12a54-130">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-130">Read General-Information</span></span></p>
<p><span data-ttu-id="12a54-131">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="12a54-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12a54-132">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="12a54-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12a54-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12a54-134">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-135">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="12a54-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="12a54-136">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-137">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-138">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="12a54-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12a54-139">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="12a54-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="12a54-140">Concessione di autorizzazioni per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="12a54-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="12a54-141">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="12a54-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="12a54-142">Autorizzazioni concesse per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="12a54-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12a54-143">Gruppo</span><span class="sxs-lookup"><span data-stu-id="12a54-143">Group</span></span></th>
<th><span data-ttu-id="12a54-144">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="12a54-144">Permission</span></span></th>
<th><span data-ttu-id="12a54-145">Si applica a</span><span class="sxs-lookup"><span data-stu-id="12a54-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a54-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12a54-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12a54-147">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="12a54-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12a54-148">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-150">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-150">List contents</span></span></p>
<p><span data-ttu-id="12a54-151">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-151">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-152">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-153">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-155">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-155">List contents</span></span></p>
<p><span data-ttu-id="12a54-156">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-156">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-157">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-158">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-160">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="12a54-161">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="12a54-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="12a54-162">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12a54-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12a54-164">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="12a54-165">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="12a54-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="12a54-166">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="12a54-167">Concessione di autorizzazioni per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="12a54-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="12a54-168">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti contatto o gli oggetti AppContact su un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="12a54-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="12a54-169">Autorizzazioni concesse per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="12a54-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12a54-170">Gruppo</span><span class="sxs-lookup"><span data-stu-id="12a54-170">Group</span></span></th>
<th><span data-ttu-id="12a54-171">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="12a54-171">Permission</span></span></th>
<th><span data-ttu-id="12a54-172">Si applica a</span><span class="sxs-lookup"><span data-stu-id="12a54-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a54-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12a54-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12a54-174">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="12a54-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12a54-175">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-177">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-177">List contents</span></span></p>
<p><span data-ttu-id="12a54-178">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-178">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-179">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-180">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-182">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-182">List contents</span></span></p>
<p><span data-ttu-id="12a54-183">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-183">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-184">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-185">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-187">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-188">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-189">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-190">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="12a54-191">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-191">Read General-Information</span></span></p>
<p><span data-ttu-id="12a54-192">Leggere Personal-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="12a54-193">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="12a54-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12a54-194">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12a54-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12a54-196">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-197">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="12a54-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="12a54-198">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="12a54-198">Write displayName</span></span></p>
<p><span data-ttu-id="12a54-199">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="12a54-199">Write description</span></span></p>
<p><span data-ttu-id="12a54-200">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="12a54-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="12a54-201">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="12a54-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="12a54-202">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-203">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-204">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="12a54-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12a54-205">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="12a54-206">Concessione di autorizzazioni per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="12a54-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="12a54-207">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="12a54-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="12a54-208">Autorizzazioni concesse per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="12a54-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12a54-209">Gruppo</span><span class="sxs-lookup"><span data-stu-id="12a54-209">Group</span></span></th>
<th><span data-ttu-id="12a54-210">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="12a54-210">Permission</span></span></th>
<th><span data-ttu-id="12a54-211">Si applica a</span><span class="sxs-lookup"><span data-stu-id="12a54-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a54-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12a54-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12a54-213">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="12a54-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12a54-214">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-216">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-216">List contents</span></span></p>
<p><span data-ttu-id="12a54-217">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-217">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-218">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-219">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-221">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-221">List contents</span></span></p>
<p><span data-ttu-id="12a54-222">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-222">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-223">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-224">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-226">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-227">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-228">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-229">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="12a54-230">Leggere Personal-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="12a54-231">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-231">Read General-Information</span></span></p>
<p><span data-ttu-id="12a54-232">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="12a54-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12a54-233">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12a54-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12a54-235">Crea elemento figlio</span><span class="sxs-lookup"><span data-stu-id="12a54-235">Create child</span></span></p>
<p><span data-ttu-id="12a54-236">Elimina elemento figlio</span><span class="sxs-lookup"><span data-stu-id="12a54-236">Delete child</span></span></p>
<p><span data-ttu-id="12a54-237">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="12a54-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="12a54-238">Contatto</span><span class="sxs-lookup"><span data-stu-id="12a54-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12a54-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12a54-240">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="12a54-240">Write displayName</span></span></p>
<p><span data-ttu-id="12a54-241">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="12a54-241">Write description</span></span></p>
<p><span data-ttu-id="12a54-242">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="12a54-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="12a54-243">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="12a54-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12a54-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12a54-245">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-246">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="12a54-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="12a54-247">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="12a54-247">Write displayName</span></span></p>
<p><span data-ttu-id="12a54-248">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="12a54-248">Write description</span></span></p>
<p><span data-ttu-id="12a54-249">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="12a54-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="12a54-250">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="12a54-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="12a54-251">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-252">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-253">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="12a54-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12a54-254">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="12a54-255">Concessione di autorizzazioni per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="12a54-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="12a54-256">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="12a54-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="12a54-257">Autorizzazioni concesse per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="12a54-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12a54-258">Gruppo</span><span class="sxs-lookup"><span data-stu-id="12a54-258">Group</span></span></th>
<th><span data-ttu-id="12a54-259">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="12a54-259">Permission</span></span></th>
<th><span data-ttu-id="12a54-260">Si applica a</span><span class="sxs-lookup"><span data-stu-id="12a54-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a54-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="12a54-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="12a54-262">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="12a54-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="12a54-263">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-265">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-265">List contents</span></span></p>
<p><span data-ttu-id="12a54-266">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-266">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-267">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-268">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-270">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="12a54-270">List contents</span></span></p>
<p><span data-ttu-id="12a54-271">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="12a54-271">Read all properties</span></span></p>
<p><span data-ttu-id="12a54-272">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="12a54-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="12a54-273">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="12a54-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a54-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="12a54-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="12a54-275">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-276">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-277">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-278">Leggere Personal-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="12a54-279">Leggere Public-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="12a54-280">Leggere General-Information</span><span class="sxs-lookup"><span data-stu-id="12a54-280">Read General-Information</span></span></p>
<p><span data-ttu-id="12a54-281">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="12a54-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12a54-282">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a54-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="12a54-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="12a54-284">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="12a54-285">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="12a54-286">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="12a54-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="12a54-287">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="12a54-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="12a54-288">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="12a54-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

