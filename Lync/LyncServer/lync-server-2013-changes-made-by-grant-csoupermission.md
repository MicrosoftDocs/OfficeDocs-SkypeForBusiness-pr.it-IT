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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="c9bc3-102">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9bc3-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9bc3-103">_**Argomento Ultima modifica:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="c9bc3-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="c9bc3-104">Per delegare l'amministrazione di Lync Server 2013, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi di RTC universale creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="c9bc3-105">Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni per gli oggetti nell'UO specificata, come specificato nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="c9bc3-106">Concessione dell'autorizzazione per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="c9bc3-107">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="c9bc3-108">Autorizzazioni concesse per gli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9bc3-109">Gruppo</span><span class="sxs-lookup"><span data-stu-id="c9bc3-109">Group</span></span></th>
<th><span data-ttu-id="c9bc3-110">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9bc3-110">Permission</span></span></th>
<th><span data-ttu-id="c9bc3-111">Si applica a</span><span class="sxs-lookup"><span data-stu-id="c9bc3-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c9bc3-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-113">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="c9bc3-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-114">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-116">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-116">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-117">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-117">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-118">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-119">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-121">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-121">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-122">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-122">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-123">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-124">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-126">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-127">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-128">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-129">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="c9bc3-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="c9bc3-130">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="c9bc3-130">Read General-Information</span></span></p>
<p><span data-ttu-id="c9bc3-131">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="c9bc3-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-132">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c9bc3-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-134">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-135">Scrivere msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="c9bc3-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="c9bc3-136">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-137">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-138">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c9bc3-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-139">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="c9bc3-140">Concessione dell'autorizzazione per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="c9bc3-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="c9bc3-141">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="c9bc3-142">Autorizzazioni concesse per gli oggetti computer</span><span class="sxs-lookup"><span data-stu-id="c9bc3-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9bc3-143">Gruppo</span><span class="sxs-lookup"><span data-stu-id="c9bc3-143">Group</span></span></th>
<th><span data-ttu-id="c9bc3-144">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9bc3-144">Permission</span></span></th>
<th><span data-ttu-id="c9bc3-145">Si applica a</span><span class="sxs-lookup"><span data-stu-id="c9bc3-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c9bc3-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-147">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="c9bc3-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-148">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-150">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-150">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-151">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-151">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-152">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-153">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-155">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-155">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-156">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-156">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-157">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-158">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-160">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="c9bc3-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="c9bc3-161">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="c9bc3-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-162">Oggetti computer discendenti</span><span class="sxs-lookup"><span data-stu-id="c9bc3-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c9bc3-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-164">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="c9bc3-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="c9bc3-165">Lettura convalidata-DNS-host-name</span><span class="sxs-lookup"><span data-stu-id="c9bc3-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-166">Oggetti computer discendenti</span><span class="sxs-lookup"><span data-stu-id="c9bc3-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="c9bc3-167">Concessione dell'autorizzazione per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="c9bc3-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="c9bc3-168">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Contact o gli oggetti AppContact in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="c9bc3-169">Autorizzazioni concesse per gli oggetti Contact o AppContact</span><span class="sxs-lookup"><span data-stu-id="c9bc3-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9bc3-170">Gruppo</span><span class="sxs-lookup"><span data-stu-id="c9bc3-170">Group</span></span></th>
<th><span data-ttu-id="c9bc3-171">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9bc3-171">Permission</span></span></th>
<th><span data-ttu-id="c9bc3-172">Si applica a</span><span class="sxs-lookup"><span data-stu-id="c9bc3-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c9bc3-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-174">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="c9bc3-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-175">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-177">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-177">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-178">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-178">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-179">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-180">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-182">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-182">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-183">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-183">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-184">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-185">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-187">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-188">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-189">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-190">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="c9bc3-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="c9bc3-191">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="c9bc3-191">Read General-Information</span></span></p>
<p><span data-ttu-id="c9bc3-192">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="c9bc3-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="c9bc3-193">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="c9bc3-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-194">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c9bc3-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-196">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-197">Scrivere otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="c9bc3-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="c9bc3-198">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="c9bc3-198">Write displayName</span></span></p>
<p><span data-ttu-id="c9bc3-199">Descrizione della scrittura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-199">Write description</span></span></p>
<p><span data-ttu-id="c9bc3-200">Scrivere telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="c9bc3-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="c9bc3-201">Scrivere msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="c9bc3-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="c9bc3-202">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-203">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-204">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c9bc3-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-205">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="c9bc3-206">Concessione dell'autorizzazione per gli oggetti dispositivo</span><span class="sxs-lookup"><span data-stu-id="c9bc3-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="c9bc3-207">Quando si esegue il cmdlet **Grant-CsOUPermission** per oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="c9bc3-208">Autorizzazioni concesse per gli oggetti dispositivo</span><span class="sxs-lookup"><span data-stu-id="c9bc3-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9bc3-209">Gruppo</span><span class="sxs-lookup"><span data-stu-id="c9bc3-209">Group</span></span></th>
<th><span data-ttu-id="c9bc3-210">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9bc3-210">Permission</span></span></th>
<th><span data-ttu-id="c9bc3-211">Si applica a</span><span class="sxs-lookup"><span data-stu-id="c9bc3-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c9bc3-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-213">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="c9bc3-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-214">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-216">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-216">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-217">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-217">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-218">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-219">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-221">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-221">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-222">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-222">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-223">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-224">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-226">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-227">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-228">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-229">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="c9bc3-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="c9bc3-230">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="c9bc3-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="c9bc3-231">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="c9bc3-231">Read General-Information</span></span></p>
<p><span data-ttu-id="c9bc3-232">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="c9bc3-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-233">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c9bc3-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-235">Creare un bambino</span><span class="sxs-lookup"><span data-stu-id="c9bc3-235">Create child</span></span></p>
<p><span data-ttu-id="c9bc3-236">Eliminare il bambino</span><span class="sxs-lookup"><span data-stu-id="c9bc3-236">Delete child</span></span></p>
<p><span data-ttu-id="c9bc3-237">Elimina albero</span><span class="sxs-lookup"><span data-stu-id="c9bc3-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-238">Contatto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c9bc3-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-240">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="c9bc3-240">Write displayName</span></span></p>
<p><span data-ttu-id="c9bc3-241">Descrizione della scrittura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-241">Write description</span></span></p>
<p><span data-ttu-id="c9bc3-242">Scrivere telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="c9bc3-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-243">Oggetti utente discendente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c9bc3-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-245">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-246">Scrivere otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="c9bc3-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="c9bc3-247">Scrittura di displayName</span><span class="sxs-lookup"><span data-stu-id="c9bc3-247">Write displayName</span></span></p>
<p><span data-ttu-id="c9bc3-248">Descrizione della scrittura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-248">Write description</span></span></p>
<p><span data-ttu-id="c9bc3-249">Scrivere telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="c9bc3-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="c9bc3-250">Scrivere msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="c9bc3-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="c9bc3-251">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-252">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-253">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c9bc3-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-254">Oggetti contatto discendente</span><span class="sxs-lookup"><span data-stu-id="c9bc3-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="c9bc3-255">Concessione dell'autorizzazione per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="c9bc3-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="c9bc3-256">Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="c9bc3-257">Autorizzazioni concesse per gli oggetti InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="c9bc3-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9bc3-258">Gruppo</span><span class="sxs-lookup"><span data-stu-id="c9bc3-258">Group</span></span></th>
<th><span data-ttu-id="c9bc3-259">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c9bc3-259">Permission</span></span></th>
<th><span data-ttu-id="c9bc3-260">Si applica a</span><span class="sxs-lookup"><span data-stu-id="c9bc3-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c9bc3-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-262">Replica delle modifiche della directory</span><span class="sxs-lookup"><span data-stu-id="c9bc3-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-263">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-265">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-265">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-266">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-266">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-267">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-268">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-270">Contenuto dell'elenco</span><span class="sxs-lookup"><span data-stu-id="c9bc3-270">List contents</span></span></p>
<p><span data-ttu-id="c9bc3-271">Leggere tutte le proprietà</span><span class="sxs-lookup"><span data-stu-id="c9bc3-271">Read all properties</span></span></p>
<p><span data-ttu-id="c9bc3-272">Autorizzazioni di lettura</span><span class="sxs-lookup"><span data-stu-id="c9bc3-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-273">Solo questo oggetto</span><span class="sxs-lookup"><span data-stu-id="c9bc3-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9bc3-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c9bc3-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-275">Leggere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-276">Leggere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-277">Leggere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-278">Leggere le informazioni personali</span><span class="sxs-lookup"><span data-stu-id="c9bc3-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="c9bc3-279">Leggere le informazioni pubbliche</span><span class="sxs-lookup"><span data-stu-id="c9bc3-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="c9bc3-280">Leggere informazioni generali</span><span class="sxs-lookup"><span data-stu-id="c9bc3-280">Read General-Information</span></span></p>
<p><span data-ttu-id="c9bc3-281">Leggi utente-account-restrizioni</span><span class="sxs-lookup"><span data-stu-id="c9bc3-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-282">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="c9bc3-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9bc3-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c9bc3-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-284">Scrivere RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-285">Scrivere RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-286">Scrivere RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c9bc3-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="c9bc3-287">Scrivere proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c9bc3-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="c9bc3-288">Oggetti inetOrgPerson discendenti</span><span class="sxs-lookup"><span data-stu-id="c9bc3-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

