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
ms.openlocfilehash: 6143310797c7372a30665cd380d7fb07340ebaf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="b6b30-102">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6b30-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6b30-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b6b30-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b6b30-104">Per delegare l'amministrazione di Lync Server 2013, è possibile aggiungere autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="b6b30-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="b6b30-105">Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata, come indicato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="b6b30-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="b6b30-106">Concessione di autorizzazioni per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="b6b30-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="b6b30-107">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente di un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6b30-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="b6b30-108">Autorizzazioni concesse per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="b6b30-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6b30-109">Gruppo</span><span class="sxs-lookup"><span data-stu-id="b6b30-109">Group</span></span></th>
<th><span data-ttu-id="b6b30-110">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b6b30-110">Permission</span></span></th>
<th><span data-ttu-id="b6b30-111">Si applica a</span><span class="sxs-lookup"><span data-stu-id="b6b30-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b6b30-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b6b30-113">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="b6b30-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="b6b30-114">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-116">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-116">List contents</span></span></p>
<p><span data-ttu-id="b6b30-117">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-117">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-118">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-119">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-121">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-121">List contents</span></span></p>
<p><span data-ttu-id="b6b30-122">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-122">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-123">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-124">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-126">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-127">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-128">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-129">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="b6b30-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="b6b30-130">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="b6b30-130">Read General-Information</span></span></p>
<p><span data-ttu-id="b6b30-131">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="b6b30-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-132">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="b6b30-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b6b30-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b6b30-134">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-135">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="b6b30-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="b6b30-136">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-137">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-138">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b6b30-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="b6b30-139">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="b6b30-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="b6b30-140">Concessione di autorizzazioni per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="b6b30-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="b6b30-141">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6b30-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="b6b30-142">Autorizzazioni concesse per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="b6b30-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6b30-143">Gruppo</span><span class="sxs-lookup"><span data-stu-id="b6b30-143">Group</span></span></th>
<th><span data-ttu-id="b6b30-144">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b6b30-144">Permission</span></span></th>
<th><span data-ttu-id="b6b30-145">Si applica a</span><span class="sxs-lookup"><span data-stu-id="b6b30-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b6b30-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b6b30-147">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="b6b30-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="b6b30-148">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-150">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-150">List contents</span></span></p>
<p><span data-ttu-id="b6b30-151">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-151">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-152">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-153">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-155">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-155">List contents</span></span></p>
<p><span data-ttu-id="b6b30-156">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-156">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-157">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-158">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-160">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="b6b30-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="b6b30-161">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="b6b30-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="b6b30-162">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b6b30-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b6b30-164">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="b6b30-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="b6b30-165">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="b6b30-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="b6b30-166">Oggetti Computer discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="b6b30-167">Concessione di autorizzazioni per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="b6b30-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="b6b30-168">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti contatto o gli oggetti AppContact su un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6b30-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="b6b30-169">Autorizzazioni concesse per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="b6b30-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6b30-170">Gruppo</span><span class="sxs-lookup"><span data-stu-id="b6b30-170">Group</span></span></th>
<th><span data-ttu-id="b6b30-171">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b6b30-171">Permission</span></span></th>
<th><span data-ttu-id="b6b30-172">Si applica a</span><span class="sxs-lookup"><span data-stu-id="b6b30-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b6b30-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b6b30-174">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="b6b30-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="b6b30-175">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-177">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-177">List contents</span></span></p>
<p><span data-ttu-id="b6b30-178">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-178">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-179">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-180">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-182">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-182">List contents</span></span></p>
<p><span data-ttu-id="b6b30-183">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-183">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-184">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-185">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-187">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-188">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-189">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-190">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="b6b30-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="b6b30-191">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="b6b30-191">Read General-Information</span></span></p>
<p><span data-ttu-id="b6b30-192">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="b6b30-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="b6b30-193">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="b6b30-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-194">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b6b30-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b6b30-196">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-197">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="b6b30-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="b6b30-198">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="b6b30-198">Write displayName</span></span></p>
<p><span data-ttu-id="b6b30-199">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="b6b30-199">Write description</span></span></p>
<p><span data-ttu-id="b6b30-200">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="b6b30-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="b6b30-201">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="b6b30-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="b6b30-202">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-203">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-204">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b6b30-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="b6b30-205">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="b6b30-206">Concessione di autorizzazioni per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="b6b30-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="b6b30-207">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6b30-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="b6b30-208">Autorizzazioni concesse per gli oggetti Device</span><span class="sxs-lookup"><span data-stu-id="b6b30-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6b30-209">Gruppo</span><span class="sxs-lookup"><span data-stu-id="b6b30-209">Group</span></span></th>
<th><span data-ttu-id="b6b30-210">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b6b30-210">Permission</span></span></th>
<th><span data-ttu-id="b6b30-211">Si applica a</span><span class="sxs-lookup"><span data-stu-id="b6b30-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b6b30-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b6b30-213">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="b6b30-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="b6b30-214">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-216">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-216">List contents</span></span></p>
<p><span data-ttu-id="b6b30-217">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-217">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-218">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-219">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-221">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-221">List contents</span></span></p>
<p><span data-ttu-id="b6b30-222">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-222">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-223">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-224">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-226">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-227">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-228">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-229">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="b6b30-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="b6b30-230">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="b6b30-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="b6b30-231">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="b6b30-231">Read General-Information</span></span></p>
<p><span data-ttu-id="b6b30-232">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="b6b30-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-233">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b6b30-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b6b30-235">Crea elemento figlio</span><span class="sxs-lookup"><span data-stu-id="b6b30-235">Create child</span></span></p>
<p><span data-ttu-id="b6b30-236">Elimina elemento figlio</span><span class="sxs-lookup"><span data-stu-id="b6b30-236">Delete child</span></span></p>
<p><span data-ttu-id="b6b30-237">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="b6b30-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="b6b30-238">Contatto</span><span class="sxs-lookup"><span data-stu-id="b6b30-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b6b30-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b6b30-240">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="b6b30-240">Write displayName</span></span></p>
<p><span data-ttu-id="b6b30-241">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="b6b30-241">Write description</span></span></p>
<p><span data-ttu-id="b6b30-242">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="b6b30-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="b6b30-243">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="b6b30-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b6b30-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b6b30-245">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-246">Scrittura otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="b6b30-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="b6b30-247">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="b6b30-247">Write displayName</span></span></p>
<p><span data-ttu-id="b6b30-248">Descrizione di scrittura</span><span class="sxs-lookup"><span data-stu-id="b6b30-248">Write description</span></span></p>
<p><span data-ttu-id="b6b30-249">Scrittura telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="b6b30-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="b6b30-250">Scrittura msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="b6b30-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="b6b30-251">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-252">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-253">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b6b30-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="b6b30-254">Oggetti contatto discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="b6b30-255">Concessione di autorizzazioni per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="b6b30-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="b6b30-256">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b6b30-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="b6b30-257">Autorizzazioni concesse per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="b6b30-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6b30-258">Gruppo</span><span class="sxs-lookup"><span data-stu-id="b6b30-258">Group</span></span></th>
<th><span data-ttu-id="b6b30-259">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b6b30-259">Permission</span></span></th>
<th><span data-ttu-id="b6b30-260">Si applica a</span><span class="sxs-lookup"><span data-stu-id="b6b30-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="b6b30-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="b6b30-262">Replica modifiche directory</span><span class="sxs-lookup"><span data-stu-id="b6b30-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="b6b30-263">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-265">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-265">List contents</span></span></p>
<p><span data-ttu-id="b6b30-266">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-266">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-267">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-268">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-270">Elenca contenuto</span><span class="sxs-lookup"><span data-stu-id="b6b30-270">List contents</span></span></p>
<p><span data-ttu-id="b6b30-271">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="b6b30-271">Read all properties</span></span></p>
<p><span data-ttu-id="b6b30-272">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="b6b30-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-273">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="b6b30-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6b30-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="b6b30-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="b6b30-275">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-276">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-277">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-278">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="b6b30-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="b6b30-279">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="b6b30-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="b6b30-280">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="b6b30-280">Read General-Information</span></span></p>
<p><span data-ttu-id="b6b30-281">Leggere le restrizioni degli account utente</span><span class="sxs-lookup"><span data-stu-id="b6b30-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="b6b30-282">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6b30-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b6b30-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b6b30-284">Scrittura RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-285">Scrittura RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-286">Scrittura RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="b6b30-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="b6b30-287">Scrittura proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b6b30-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="b6b30-288">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="b6b30-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

