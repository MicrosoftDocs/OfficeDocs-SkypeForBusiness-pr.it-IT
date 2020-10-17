---
title: 'Lync Server 2013: configurazione di VoIP aziendale'
description: 'Lync Server 2013: configurazione di VoIP aziendale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548432"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="f7d46-103">Configurazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7d46-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7d46-104">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="f7d46-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="f7d46-105">Per distribuire VoIP aziendale, è necessario configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7d46-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="f7d46-106">Creare un trunk</span><span class="sxs-lookup"><span data-stu-id="f7d46-106">Create a Trunk</span></span>

  - <span data-ttu-id="f7d46-107">Definire un criterio vocale</span><span class="sxs-lookup"><span data-stu-id="f7d46-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="f7d46-108">Definire una route vocale</span><span class="sxs-lookup"><span data-stu-id="f7d46-108">Define a Voice Route</span></span>

  - <span data-ttu-id="f7d46-109">Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="f7d46-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="f7d46-110">Creare un trunk</span><span class="sxs-lookup"><span data-stu-id="f7d46-110">Create a Trunk</span></span>

<span data-ttu-id="f7d46-111">È necessario definire trunk nella distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f7d46-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="f7d46-112">Per Location-Based il routing, è necessario creare una configurazione trunk per trunk.</span><span class="sxs-lookup"><span data-stu-id="f7d46-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="f7d46-113">Utilizzare il generatore di topologie di Lync Server per definire i trunk e utilizzare il comando di Windows PowerShell di Lync Server, New-CsTrunkConfiguration o il pannello di controllo di Lync Server per definire le configurazioni trunk corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f7d46-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="f7d46-114">Per ulteriori informazioni su come abilitare Location-Based routing sulle configurazioni trunk, vedere la sezione abilitare Location-Based routing ai trunk, nell'argomento, abilitando [Location-Based routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f7d46-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="f7d46-115">In questo esempio, nella tabella seguente vengono illustrati i trunk utilizzati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="f7d46-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="f7d46-116">Per ulteriori informazioni, vedere [definire ulteriori trunk in Generatore di topologie in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f7d46-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7d46-117">Nome trunk</span><span class="sxs-lookup"><span data-stu-id="f7d46-117">Trunk name</span></span></th>
<th><span data-ttu-id="f7d46-118">Tipo di sistema</span><span class="sxs-lookup"><span data-stu-id="f7d46-118">System type</span></span></th>
<th><span data-ttu-id="f7d46-119">Nome</span><span class="sxs-lookup"><span data-stu-id="f7d46-119">Name</span></span></th>
<th><span data-ttu-id="f7d46-120">Posizione</span><span class="sxs-lookup"><span data-stu-id="f7d46-120">Location</span></span></th>
<th><span data-ttu-id="f7d46-121">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f7d46-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7d46-122">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f7d46-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f7d46-123">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f7d46-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="f7d46-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f7d46-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f7d46-125">Delhi</span><span class="sxs-lookup"><span data-stu-id="f7d46-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="f7d46-126">MS1</span><span class="sxs-lookup"><span data-stu-id="f7d46-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7d46-127">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="f7d46-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f7d46-128">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f7d46-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="f7d46-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="f7d46-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f7d46-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7d46-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="f7d46-131">MS1</span><span class="sxs-lookup"><span data-stu-id="f7d46-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7d46-132">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f7d46-133">PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="f7d46-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f7d46-135">Delhi</span><span class="sxs-lookup"><span data-stu-id="f7d46-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="f7d46-136">MS1</span><span class="sxs-lookup"><span data-stu-id="f7d46-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7d46-137">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="f7d46-138">PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="f7d46-139">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="f7d46-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7d46-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="f7d46-141">MS1</span><span class="sxs-lookup"><span data-stu-id="f7d46-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="f7d46-142">Definisce i criteri vocali</span><span class="sxs-lookup"><span data-stu-id="f7d46-142">Defines Voice Policies</span></span>

<span data-ttu-id="f7d46-143">È necessario definire i criteri vocali per la distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f7d46-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="f7d46-144">Definire un criterio vocale per applicare Location-Based restrizioni di routing a un sottoinsieme di utenti se solo un sottoinsieme di essi è necessario per l'utilizzo del routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f7d46-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="f7d46-145">In questo esempio, nella tabella seguente sono illustrati i criteri vocali utilizzati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="f7d46-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="f7d46-146">Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="f7d46-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="f7d46-147">Per ulteriori informazioni, vedere [configurazione di criteri vocali e record utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="f7d46-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f7d46-148">Criterio vocale 1</span><span class="sxs-lookup"><span data-stu-id="f7d46-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="f7d46-149">Criterio vocale 2</span><span class="sxs-lookup"><span data-stu-id="f7d46-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7d46-150">ID criterio vocale</span><span class="sxs-lookup"><span data-stu-id="f7d46-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f7d46-151">Criteri vocali Delhi</span><span class="sxs-lookup"><span data-stu-id="f7d46-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="f7d46-152">Criteri vocali di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7d46-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7d46-153">Utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="f7d46-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f7d46-154">Utilizzo di Delhi, utilizzo del sistema PBX del PBX, utilizzo del sistema idraulico HYD</span><span class="sxs-lookup"><span data-stu-id="f7d46-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f7d46-155">Utilizzo di Hyderabad, utilizzo del PBX HYD, utilizzo del sistema PBX del</span><span class="sxs-lookup"><span data-stu-id="f7d46-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7d46-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="f7d46-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="f7d46-157">False</span><span class="sxs-lookup"><span data-stu-id="f7d46-157">False</span></span></p></td>
<td><p><span data-ttu-id="f7d46-158">False</span><span class="sxs-lookup"><span data-stu-id="f7d46-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="f7d46-159">Definire le route vocali</span><span class="sxs-lookup"><span data-stu-id="f7d46-159">Define Voice Routes</span></span>

<span data-ttu-id="f7d46-160">È necessario definire le route vocali per la distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f7d46-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="f7d46-161">In questo esempio, nella tabella seguente vengono illustrate le route vocali utilizzate in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="f7d46-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="f7d46-162">Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="f7d46-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="f7d46-163">Per ulteriori informazioni, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="f7d46-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f7d46-164">Route vocale 1</span><span class="sxs-lookup"><span data-stu-id="f7d46-164">Voice route 1</span></span></th>
<th><span data-ttu-id="f7d46-165">Route vocale 2</span><span class="sxs-lookup"><span data-stu-id="f7d46-165">Voice route 2</span></span></th>
<th><span data-ttu-id="f7d46-166">Route vocale 3</span><span class="sxs-lookup"><span data-stu-id="f7d46-166">Voice route 3</span></span></th>
<th><span data-ttu-id="f7d46-167">Route vocale 4</span><span class="sxs-lookup"><span data-stu-id="f7d46-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7d46-168">Nome</span><span class="sxs-lookup"><span data-stu-id="f7d46-168">Name</span></span></p></td>
<td><p><span data-ttu-id="f7d46-169">Route Delhi</span><span class="sxs-lookup"><span data-stu-id="f7d46-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="f7d46-170">Route Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7d46-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="f7d46-171">PBX del Route</span><span class="sxs-lookup"><span data-stu-id="f7d46-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="f7d46-172">Route HYD PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7d46-173">Utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="f7d46-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f7d46-174">Utilizzo Delhi</span><span class="sxs-lookup"><span data-stu-id="f7d46-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="f7d46-175">Utilizzo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7d46-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="f7d46-176">Utilizzo del sistema PBX del</span><span class="sxs-lookup"><span data-stu-id="f7d46-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="f7d46-177">Utilizzo di HYD PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7d46-178">Trunk</span><span class="sxs-lookup"><span data-stu-id="f7d46-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="f7d46-179">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f7d46-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f7d46-180">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="f7d46-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f7d46-181">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f7d46-182">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="f7d46-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="f7d46-183">Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="f7d46-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="f7d46-184">Abilitare gli utenti per VoIP aziendale e assegnargli un criterio vocale precedentemente definito.</span><span class="sxs-lookup"><span data-stu-id="f7d46-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="f7d46-185">In questo esempio, nella tabella seguente viene illustrata l'assegnazione utilizzata in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="f7d46-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="f7d46-186">Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="f7d46-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="f7d46-187">Per ulteriori informazioni, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="f7d46-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f7d46-188">Utenti che si trovano a Delhi</span><span class="sxs-lookup"><span data-stu-id="f7d46-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="f7d46-189">Utenti che si trovano in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7d46-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7d46-190">Criteri vocali associati</span><span class="sxs-lookup"><span data-stu-id="f7d46-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="f7d46-191">Criteri vocali Delhi</span><span class="sxs-lookup"><span data-stu-id="f7d46-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="f7d46-192">Criteri vocali di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f7d46-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7d46-193">Utenti di esempio</span><span class="sxs-lookup"><span data-stu-id="f7d46-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="f7d46-194">CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="f7d46-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="f7d46-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="f7d46-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7d46-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7d46-196">See Also</span></span>


[<span data-ttu-id="f7d46-197">Configurazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7d46-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

