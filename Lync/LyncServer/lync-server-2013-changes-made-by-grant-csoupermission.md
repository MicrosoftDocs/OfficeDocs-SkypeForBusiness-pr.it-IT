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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="30c2a-102">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30c2a-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30c2a-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="30c2a-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="30c2a-104">Per delegare l'amministrazione di Lync Server 2013, è possibile aggiungere autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="30c2a-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="30c2a-105">Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata, come indicato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="30c2a-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="30c2a-106">Concessione di autorizzazioni per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="30c2a-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="30c2a-107">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente di un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="30c2a-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="30c2a-108">Autorizzazioni concesse per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="30c2a-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30c2a-109">Gruppo</span><span class="sxs-lookup"><span data-stu-id="30c2a-109">Group</span></span></th>
<th><span data-ttu-id="30c2a-110">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30c2a-110">Permission</span></span></th>
<th><span data-ttu-id="30c2a-111">Si applica a</span><span class="sxs-lookup"><span data-stu-id="30c2a-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="30c2a-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="30c2a-113">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="30c2a-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="30c2a-114">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-116">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-116">List contents</span></span></p>
<p><span data-ttu-id="30c2a-117">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-117">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-118">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-119">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-121">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-121">List contents</span></span></p>
<p><span data-ttu-id="30c2a-122">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-122">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-123">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-124">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-126">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-127">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-128">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-129">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="30c2a-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="30c2a-130">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="30c2a-130">Read General-Information</span></span></p>
<p><span data-ttu-id="30c2a-131">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="30c2a-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-132">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="30c2a-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30c2a-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30c2a-134">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-135">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="30c2a-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="30c2a-136">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-137">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-138">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="30c2a-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="30c2a-139">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="30c2a-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="30c2a-140">Concessione di autorizzazioni per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="30c2a-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="30c2a-141">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="30c2a-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="30c2a-142">Autorizzazioni concesse per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="30c2a-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30c2a-143">Gruppo</span><span class="sxs-lookup"><span data-stu-id="30c2a-143">Group</span></span></th>
<th><span data-ttu-id="30c2a-144">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30c2a-144">Permission</span></span></th>
<th><span data-ttu-id="30c2a-145">Si applica a</span><span class="sxs-lookup"><span data-stu-id="30c2a-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="30c2a-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="30c2a-147">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="30c2a-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="30c2a-148">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-150">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-150">List contents</span></span></p>
<p><span data-ttu-id="30c2a-151">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-151">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-152">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-153">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-155">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-155">List contents</span></span></p>
<p><span data-ttu-id="30c2a-156">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-156">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-157">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-158">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-160">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="30c2a-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="30c2a-161">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="30c2a-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="30c2a-162">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30c2a-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30c2a-164">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="30c2a-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="30c2a-165">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="30c2a-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="30c2a-166">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="30c2a-167">Concessione di autorizzazioni per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="30c2a-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="30c2a-168">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti contatto o gli oggetti AppContact su un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="30c2a-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="30c2a-169">Autorizzazioni concesse per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="30c2a-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30c2a-170">Gruppo</span><span class="sxs-lookup"><span data-stu-id="30c2a-170">Group</span></span></th>
<th><span data-ttu-id="30c2a-171">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30c2a-171">Permission</span></span></th>
<th><span data-ttu-id="30c2a-172">Si applica a</span><span class="sxs-lookup"><span data-stu-id="30c2a-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="30c2a-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="30c2a-174">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="30c2a-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="30c2a-175">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-177">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-177">List contents</span></span></p>
<p><span data-ttu-id="30c2a-178">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-178">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-179">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-180">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-182">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-182">List contents</span></span></p>
<p><span data-ttu-id="30c2a-183">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-183">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-184">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-185">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-187">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-188">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-189">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-190">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="30c2a-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="30c2a-191">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="30c2a-191">Read General-Information</span></span></p>
<p><span data-ttu-id="30c2a-192">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="30c2a-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="30c2a-193">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="30c2a-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-194">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30c2a-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30c2a-196">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-197">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="30c2a-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="30c2a-198">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="30c2a-198">Write displayName</span></span></p>
<p><span data-ttu-id="30c2a-199">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="30c2a-199">Write description</span></span></p>
<p><span data-ttu-id="30c2a-200">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="30c2a-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="30c2a-201">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="30c2a-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="30c2a-202">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-203">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-204">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="30c2a-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="30c2a-205">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="30c2a-206">Concessione di autorizzazioni per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="30c2a-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="30c2a-207">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="30c2a-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="30c2a-208">Autorizzazioni concesse per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="30c2a-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30c2a-209">Gruppo</span><span class="sxs-lookup"><span data-stu-id="30c2a-209">Group</span></span></th>
<th><span data-ttu-id="30c2a-210">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30c2a-210">Permission</span></span></th>
<th><span data-ttu-id="30c2a-211">Si applica a</span><span class="sxs-lookup"><span data-stu-id="30c2a-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="30c2a-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="30c2a-213">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="30c2a-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="30c2a-214">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-216">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-216">List contents</span></span></p>
<p><span data-ttu-id="30c2a-217">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-217">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-218">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-219">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-221">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-221">List contents</span></span></p>
<p><span data-ttu-id="30c2a-222">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-222">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-223">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-224">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-226">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-227">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-228">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-229">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="30c2a-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="30c2a-230">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="30c2a-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="30c2a-231">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="30c2a-231">Read General-Information</span></span></p>
<p><span data-ttu-id="30c2a-232">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="30c2a-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-233">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30c2a-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30c2a-235">Crea elemento figlio</span><span class="sxs-lookup"><span data-stu-id="30c2a-235">Create child</span></span></p>
<p><span data-ttu-id="30c2a-236">Elimina elemento figlio</span><span class="sxs-lookup"><span data-stu-id="30c2a-236">Delete child</span></span></p>
<p><span data-ttu-id="30c2a-237">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="30c2a-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="30c2a-238">Contatto</span><span class="sxs-lookup"><span data-stu-id="30c2a-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30c2a-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30c2a-240">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="30c2a-240">Write displayName</span></span></p>
<p><span data-ttu-id="30c2a-241">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="30c2a-241">Write description</span></span></p>
<p><span data-ttu-id="30c2a-242">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="30c2a-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="30c2a-243">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="30c2a-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30c2a-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30c2a-245">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-246">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="30c2a-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="30c2a-247">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="30c2a-247">Write displayName</span></span></p>
<p><span data-ttu-id="30c2a-248">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="30c2a-248">Write description</span></span></p>
<p><span data-ttu-id="30c2a-249">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="30c2a-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="30c2a-250">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="30c2a-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="30c2a-251">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-252">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-253">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="30c2a-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="30c2a-254">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="30c2a-255">Concessione di autorizzazioni per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="30c2a-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="30c2a-256">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="30c2a-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="30c2a-257">Autorizzazioni concesse per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="30c2a-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30c2a-258">Gruppo</span><span class="sxs-lookup"><span data-stu-id="30c2a-258">Group</span></span></th>
<th><span data-ttu-id="30c2a-259">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30c2a-259">Permission</span></span></th>
<th><span data-ttu-id="30c2a-260">Si applica a</span><span class="sxs-lookup"><span data-stu-id="30c2a-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="30c2a-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="30c2a-262">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="30c2a-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="30c2a-263">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-265">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-265">List contents</span></span></p>
<p><span data-ttu-id="30c2a-266">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-266">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-267">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-268">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-270">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="30c2a-270">List contents</span></span></p>
<p><span data-ttu-id="30c2a-271">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="30c2a-271">Read all properties</span></span></p>
<p><span data-ttu-id="30c2a-272">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="30c2a-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-273">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="30c2a-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c2a-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="30c2a-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="30c2a-275">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-276">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-277">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-278">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="30c2a-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="30c2a-279">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="30c2a-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="30c2a-280">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="30c2a-280">Read General-Information</span></span></p>
<p><span data-ttu-id="30c2a-281">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="30c2a-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="30c2a-282">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c2a-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="30c2a-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="30c2a-284">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-285">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-286">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="30c2a-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="30c2a-287">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="30c2a-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="30c2a-288">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="30c2a-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

