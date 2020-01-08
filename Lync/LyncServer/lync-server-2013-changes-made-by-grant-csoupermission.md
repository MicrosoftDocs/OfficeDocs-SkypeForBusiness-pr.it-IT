---
title: 'Lync Server 2013: modifiche apportate da Grant-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="9ab29-102">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ab29-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ab29-103">_**Argomento Ultima modifica:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="9ab29-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="9ab29-104">Per delegare l'amministrazione di Lync Server 2013, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi di RTC universale creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="9ab29-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="9ab29-105">Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni per gli oggetti nell'UO specificata, come specificato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="9ab29-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="9ab29-106">Concessione dell'autorizzazione per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="9ab29-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="9ab29-107">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9ab29-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="9ab29-108">Autorizzazioni concesse per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="9ab29-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ab29-109">Gruppo</span><span class="sxs-lookup"><span data-stu-id="9ab29-109">Group</span></span></th>
<th><span data-ttu-id="9ab29-110">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9ab29-110">Permission</span></span></th>
<th><span data-ttu-id="9ab29-111">Si applica a</span><span class="sxs-lookup"><span data-stu-id="9ab29-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9ab29-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9ab29-113">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="9ab29-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9ab29-114">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-116">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-116">List contents</span></span></p>
<p><span data-ttu-id="9ab29-117">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-117">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-118">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-119">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-121">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-121">List contents</span></span></p>
<p><span data-ttu-id="9ab29-122">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-122">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-123">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-124">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-126">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-127">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-128">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-129">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="9ab29-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="9ab29-130">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="9ab29-130">Read General-Information</span></span></p>
<p><span data-ttu-id="9ab29-131">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ab29-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-132">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="9ab29-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ab29-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9ab29-134">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-135">Scrivere msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="9ab29-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9ab29-136">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-137">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-138">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9ab29-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9ab29-139">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="9ab29-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="9ab29-140">Concessione dell'autorizzazione per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="9ab29-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="9ab29-141">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9ab29-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="9ab29-142">Autorizzazioni concesse per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="9ab29-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ab29-143">Gruppo</span><span class="sxs-lookup"><span data-stu-id="9ab29-143">Group</span></span></th>
<th><span data-ttu-id="9ab29-144">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9ab29-144">Permission</span></span></th>
<th><span data-ttu-id="9ab29-145">Si applica a</span><span class="sxs-lookup"><span data-stu-id="9ab29-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9ab29-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9ab29-147">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="9ab29-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9ab29-148">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-150">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-150">List contents</span></span></p>
<p><span data-ttu-id="9ab29-151">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-151">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-152">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-153">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-155">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-155">List contents</span></span></p>
<p><span data-ttu-id="9ab29-156">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-156">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-157">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-158">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-160">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="9ab29-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="9ab29-161">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="9ab29-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="9ab29-162">Oggetti computer discendenti</span><span class="sxs-lookup"><span data-stu-id="9ab29-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ab29-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9ab29-164">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="9ab29-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="9ab29-165">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="9ab29-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="9ab29-166">Oggetti computer discendenti</span><span class="sxs-lookup"><span data-stu-id="9ab29-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="9ab29-167">Concessione dell'autorizzazione per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="9ab29-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="9ab29-168">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Contact o gli oggetti AppContact in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9ab29-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="9ab29-169">Autorizzazioni concesse per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="9ab29-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ab29-170">Gruppo</span><span class="sxs-lookup"><span data-stu-id="9ab29-170">Group</span></span></th>
<th><span data-ttu-id="9ab29-171">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9ab29-171">Permission</span></span></th>
<th><span data-ttu-id="9ab29-172">Si applica a</span><span class="sxs-lookup"><span data-stu-id="9ab29-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9ab29-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9ab29-174">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="9ab29-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9ab29-175">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-177">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-177">List contents</span></span></p>
<p><span data-ttu-id="9ab29-178">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-178">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-179">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-180">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-182">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-182">List contents</span></span></p>
<p><span data-ttu-id="9ab29-183">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-183">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-184">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-185">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-187">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-188">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-189">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-190">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="9ab29-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="9ab29-191">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="9ab29-191">Read General-Information</span></span></p>
<p><span data-ttu-id="9ab29-192">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="9ab29-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9ab29-193">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ab29-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-194">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="9ab29-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ab29-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9ab29-196">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-197">Scrivere otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="9ab29-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="9ab29-198">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="9ab29-198">Write displayName</span></span></p>
<p><span data-ttu-id="9ab29-199">Descrizione della scrittura</span><span class="sxs-lookup"><span data-stu-id="9ab29-199">Write description</span></span></p>
<p><span data-ttu-id="9ab29-200">Scrivere telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="9ab29-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="9ab29-201">Scrivere msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="9ab29-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9ab29-202">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-203">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-204">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9ab29-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9ab29-205">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="9ab29-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="9ab29-206">Concessione dell'autorizzazione per gli oggetti dispositivo</span><span class="sxs-lookup"><span data-stu-id="9ab29-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="9ab29-207">Quando si esegue il cmdlet **Grant-CsOUPermission** per oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9ab29-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="9ab29-208">Autorizzazioni concesse per gli oggetti dispositivo</span><span class="sxs-lookup"><span data-stu-id="9ab29-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ab29-209">Gruppo</span><span class="sxs-lookup"><span data-stu-id="9ab29-209">Group</span></span></th>
<th><span data-ttu-id="9ab29-210">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9ab29-210">Permission</span></span></th>
<th><span data-ttu-id="9ab29-211">Si applica a</span><span class="sxs-lookup"><span data-stu-id="9ab29-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9ab29-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9ab29-213">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="9ab29-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9ab29-214">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-216">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-216">List contents</span></span></p>
<p><span data-ttu-id="9ab29-217">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-217">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-218">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-219">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-221">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-221">List contents</span></span></p>
<p><span data-ttu-id="9ab29-222">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-222">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-223">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-224">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-226">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-227">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-228">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-229">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="9ab29-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="9ab29-230">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="9ab29-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9ab29-231">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="9ab29-231">Read General-Information</span></span></p>
<p><span data-ttu-id="9ab29-232">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ab29-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-233">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="9ab29-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ab29-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9ab29-235">Creare un bambino</span><span class="sxs-lookup"><span data-stu-id="9ab29-235">Create child</span></span></p>
<p><span data-ttu-id="9ab29-236">Eliminare il bambino</span><span class="sxs-lookup"><span data-stu-id="9ab29-236">Delete child</span></span></p>
<p><span data-ttu-id="9ab29-237">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="9ab29-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="9ab29-238">Contatto</span><span class="sxs-lookup"><span data-stu-id="9ab29-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ab29-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9ab29-240">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="9ab29-240">Write displayName</span></span></p>
<p><span data-ttu-id="9ab29-241">Descrizione della scrittura</span><span class="sxs-lookup"><span data-stu-id="9ab29-241">Write description</span></span></p>
<p><span data-ttu-id="9ab29-242">Scrivere telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="9ab29-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="9ab29-243">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="9ab29-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ab29-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9ab29-245">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-246">Scrivere otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="9ab29-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="9ab29-247">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="9ab29-247">Write displayName</span></span></p>
<p><span data-ttu-id="9ab29-248">Descrizione della scrittura</span><span class="sxs-lookup"><span data-stu-id="9ab29-248">Write description</span></span></p>
<p><span data-ttu-id="9ab29-249">Scrivere telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="9ab29-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="9ab29-250">Scrivere msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="9ab29-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9ab29-251">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-252">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-253">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9ab29-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9ab29-254">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="9ab29-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="9ab29-255">Concessione dell'autorizzazione per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="9ab29-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="9ab29-256">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9ab29-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="9ab29-257">Autorizzazioni concesse per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="9ab29-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ab29-258">Gruppo</span><span class="sxs-lookup"><span data-stu-id="9ab29-258">Group</span></span></th>
<th><span data-ttu-id="9ab29-259">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9ab29-259">Permission</span></span></th>
<th><span data-ttu-id="9ab29-260">Si applica a</span><span class="sxs-lookup"><span data-stu-id="9ab29-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9ab29-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9ab29-262">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="9ab29-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9ab29-263">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-265">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-265">List contents</span></span></p>
<p><span data-ttu-id="9ab29-266">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-266">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-267">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-268">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-270">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="9ab29-270">List contents</span></span></p>
<p><span data-ttu-id="9ab29-271">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="9ab29-271">Read all properties</span></span></p>
<p><span data-ttu-id="9ab29-272">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="9ab29-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-273">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="9ab29-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab29-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9ab29-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9ab29-275">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-276">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-277">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-278">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="9ab29-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9ab29-279">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="9ab29-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="9ab29-280">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="9ab29-280">Read General-Information</span></span></p>
<p><span data-ttu-id="9ab29-281">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="9ab29-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9ab29-282">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="9ab29-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab29-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ab29-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9ab29-284">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-285">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-286">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ab29-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9ab29-287">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9ab29-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9ab29-288">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="9ab29-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

