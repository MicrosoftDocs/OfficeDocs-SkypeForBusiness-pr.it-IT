---
title: 'Lync Server 2013: configurazione di VoIP aziendale'
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
ms.openlocfilehash: 76105b9bee5ce35801196b5a4cd20b2a1feed3e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="e52c2-102">Configurazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e52c2-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e52c2-103">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="e52c2-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e52c2-104">Per distribuire VoIP aziendale, è necessario configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e52c2-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="e52c2-105">Creare un trunk</span><span class="sxs-lookup"><span data-stu-id="e52c2-105">Create a Trunk</span></span>

  - <span data-ttu-id="e52c2-106">Definire un criterio vocale</span><span class="sxs-lookup"><span data-stu-id="e52c2-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="e52c2-107">Definire una route vocale</span><span class="sxs-lookup"><span data-stu-id="e52c2-107">Define a Voice Route</span></span>

  - <span data-ttu-id="e52c2-108">Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="e52c2-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="e52c2-109">Creare un trunk</span><span class="sxs-lookup"><span data-stu-id="e52c2-109">Create a Trunk</span></span>

<span data-ttu-id="e52c2-110">È necessario definire trunk nella distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e52c2-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="e52c2-111">Per il routing in base alla posizione, è necessario creare una configurazione trunk per trunk.</span><span class="sxs-lookup"><span data-stu-id="e52c2-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="e52c2-112">Utilizzare il generatore di topologie di Lync Server per definire i trunk e utilizzare il comando di Windows PowerShell di Lync Server, New-CsTrunkConfiguration o il pannello di controllo di Lync Server per definire le configurazioni trunk corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e52c2-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="e52c2-113">Ulteriori informazioni su come abilitare il routing basato sulla posizione sulle configurazioni trunk sono disponibili nella sezione abilitare il routing in base alla posizione ai trunk, nell'argomento, per abilitare il [routing in base alla posizione in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e52c2-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="e52c2-114">In questo esempio, nella tabella seguente vengono illustrati i trunk utilizzati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e52c2-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="e52c2-115">Per ulteriori informazioni, vedere [definire ulteriori trunk in Generatore di topologie in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e52c2-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="e52c2-116">Nome trunk</span><span class="sxs-lookup"><span data-stu-id="e52c2-116">Trunk name</span></span></th>
<th><span data-ttu-id="e52c2-117">Tipo di sistema</span><span class="sxs-lookup"><span data-stu-id="e52c2-117">System type</span></span></th>
<th><span data-ttu-id="e52c2-118">Nome</span><span class="sxs-lookup"><span data-stu-id="e52c2-118">Name</span></span></th>
<th><span data-ttu-id="e52c2-119">Posizione</span><span class="sxs-lookup"><span data-stu-id="e52c2-119">Location</span></span></th>
<th><span data-ttu-id="e52c2-120">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e52c2-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52c2-121">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="e52c2-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="e52c2-122">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="e52c2-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="e52c2-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="e52c2-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="e52c2-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="e52c2-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="e52c2-125">MS1</span><span class="sxs-lookup"><span data-stu-id="e52c2-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c2-126">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="e52c2-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="e52c2-127">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="e52c2-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="e52c2-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="e52c2-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="e52c2-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e52c2-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="e52c2-130">MS1</span><span class="sxs-lookup"><span data-stu-id="e52c2-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c2-131">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="e52c2-132">PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="e52c2-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="e52c2-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="e52c2-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="e52c2-135">MS1</span><span class="sxs-lookup"><span data-stu-id="e52c2-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c2-136">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="e52c2-137">PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="e52c2-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="e52c2-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e52c2-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="e52c2-140">MS1</span><span class="sxs-lookup"><span data-stu-id="e52c2-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="e52c2-141">Definisce i criteri vocali</span><span class="sxs-lookup"><span data-stu-id="e52c2-141">Defines Voice Policies</span></span>

<span data-ttu-id="e52c2-142">È necessario definire i criteri vocali per la distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e52c2-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="e52c2-143">Definire un criterio vocale per applicare restrizioni di routing basate sul percorso a un sottoinsieme di utenti se solo un sottoinsieme di essi è necessario per l'utilizzo del routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="e52c2-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="e52c2-144">In questo esempio, nella tabella seguente sono illustrati i criteri vocali utilizzati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e52c2-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="e52c2-145">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="e52c2-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="e52c2-146">Per ulteriori informazioni, vedere [configurazione di criteri vocali e record utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="e52c2-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e52c2-147">Criterio vocale 1</span><span class="sxs-lookup"><span data-stu-id="e52c2-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="e52c2-148">Criterio vocale 2</span><span class="sxs-lookup"><span data-stu-id="e52c2-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52c2-149">ID criterio vocale</span><span class="sxs-lookup"><span data-stu-id="e52c2-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="e52c2-150">Criteri vocali Delhi</span><span class="sxs-lookup"><span data-stu-id="e52c2-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="e52c2-151">Criteri vocali di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e52c2-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c2-152">Utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="e52c2-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="e52c2-153">Utilizzo di Delhi, utilizzo del sistema PBX del PBX, utilizzo del sistema idraulico HYD</span><span class="sxs-lookup"><span data-stu-id="e52c2-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="e52c2-154">Utilizzo di Hyderabad, utilizzo del PBX HYD, utilizzo del sistema PBX del</span><span class="sxs-lookup"><span data-stu-id="e52c2-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c2-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="e52c2-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="e52c2-156">False</span><span class="sxs-lookup"><span data-stu-id="e52c2-156">False</span></span></p></td>
<td><p><span data-ttu-id="e52c2-157">False</span><span class="sxs-lookup"><span data-stu-id="e52c2-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="e52c2-158">Definire le route vocali</span><span class="sxs-lookup"><span data-stu-id="e52c2-158">Define Voice Routes</span></span>

<span data-ttu-id="e52c2-159">È necessario definire le route vocali per la distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e52c2-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="e52c2-160">In questo esempio, nella tabella seguente vengono illustrate le route vocali utilizzate in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e52c2-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="e52c2-161">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="e52c2-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="e52c2-162">Per ulteriori informazioni, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="e52c2-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="e52c2-163">Route vocale 1</span><span class="sxs-lookup"><span data-stu-id="e52c2-163">Voice route 1</span></span></th>
<th><span data-ttu-id="e52c2-164">Route vocale 2</span><span class="sxs-lookup"><span data-stu-id="e52c2-164">Voice route 2</span></span></th>
<th><span data-ttu-id="e52c2-165">Route vocale 3</span><span class="sxs-lookup"><span data-stu-id="e52c2-165">Voice route 3</span></span></th>
<th><span data-ttu-id="e52c2-166">Route vocale 4</span><span class="sxs-lookup"><span data-stu-id="e52c2-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52c2-167">Nome</span><span class="sxs-lookup"><span data-stu-id="e52c2-167">Name</span></span></p></td>
<td><p><span data-ttu-id="e52c2-168">Route Delhi</span><span class="sxs-lookup"><span data-stu-id="e52c2-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="e52c2-169">Route Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e52c2-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="e52c2-170">PBX del Route</span><span class="sxs-lookup"><span data-stu-id="e52c2-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="e52c2-171">Route HYD PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c2-172">Utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="e52c2-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="e52c2-173">Utilizzo Delhi</span><span class="sxs-lookup"><span data-stu-id="e52c2-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="e52c2-174">Utilizzo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e52c2-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="e52c2-175">Utilizzo del sistema PBX del</span><span class="sxs-lookup"><span data-stu-id="e52c2-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="e52c2-176">Utilizzo di HYD PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52c2-177">Trunk</span><span class="sxs-lookup"><span data-stu-id="e52c2-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="e52c2-178">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="e52c2-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="e52c2-179">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="e52c2-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="e52c2-180">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="e52c2-181">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="e52c2-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="e52c2-182">Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="e52c2-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="e52c2-183">Abilitare gli utenti per VoIP aziendale e assegnargli un criterio vocale precedentemente definito.</span><span class="sxs-lookup"><span data-stu-id="e52c2-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="e52c2-184">In questo esempio, nella tabella seguente viene illustrata l'assegnazione utilizzata in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="e52c2-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="e52c2-185">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="e52c2-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="e52c2-186">Per ulteriori informazioni, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="e52c2-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="e52c2-187">Utenti che si trovano a Delhi</span><span class="sxs-lookup"><span data-stu-id="e52c2-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="e52c2-188">Utenti che si trovano in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e52c2-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52c2-189">Criteri vocali associati</span><span class="sxs-lookup"><span data-stu-id="e52c2-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="e52c2-190">Criteri vocali Delhi</span><span class="sxs-lookup"><span data-stu-id="e52c2-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="e52c2-191">Criteri vocali di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e52c2-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52c2-192">Utenti di esempio</span><span class="sxs-lookup"><span data-stu-id="e52c2-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="e52c2-193">CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="e52c2-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="e52c2-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="e52c2-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e52c2-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e52c2-195">See Also</span></span>


[<span data-ttu-id="e52c2-196">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e52c2-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

