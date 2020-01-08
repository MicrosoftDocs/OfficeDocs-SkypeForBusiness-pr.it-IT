---
title: 'Lync Server 2013: configurazione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e46bd64efd8aa2eb6e1aead17083aa8593c8544
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="1efa8-102">Configurazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1efa8-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1efa8-103">_**Argomento Ultima modifica:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="1efa8-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="1efa8-104">Per distribuire Enterprise Voice, è necessario configurare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1efa8-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="1efa8-105">Creare un trunk</span><span class="sxs-lookup"><span data-stu-id="1efa8-105">Create a Trunk</span></span>

  - <span data-ttu-id="1efa8-106">Definire un criterio vocale</span><span class="sxs-lookup"><span data-stu-id="1efa8-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="1efa8-107">Definire una route vocale</span><span class="sxs-lookup"><span data-stu-id="1efa8-107">Define a Voice Route</span></span>

  - <span data-ttu-id="1efa8-108">Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="1efa8-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="1efa8-109">Creare un trunk</span><span class="sxs-lookup"><span data-stu-id="1efa8-109">Create a Trunk</span></span>

<span data-ttu-id="1efa8-110">È necessario definire Trunks nella distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="1efa8-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="1efa8-111">Per il routing basato sulla posizione, devi creare una configurazione trunk per tronco.</span><span class="sxs-lookup"><span data-stu-id="1efa8-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="1efa8-112">Usare il generatore di topologia di Lync Server per definire i trunk e usare il comando Lync Server di Windows PowerShell, New-CsTrunkConfiguration o il pannello di controllo di Lync Server per definire le configurazioni trunk corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1efa8-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="1efa8-113">Altre informazioni su come abilitare il routing basato sulla posizione sulle configurazioni trunk sono disponibili nella sezione abilitare il routing basato sulla posizione ai trunk, nell'argomento abilitare il [routing basato sulla posizione in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1efa8-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="1efa8-114">Per questo esempio, la tabella seguente illustra i trunk usati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="1efa8-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="1efa8-115">Per altre informazioni, vedere [definire trunk aggiuntivi in Generatore di topologia in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1efa8-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="1efa8-116">Nome trunk</span><span class="sxs-lookup"><span data-stu-id="1efa8-116">Trunk name</span></span></th>
<th><span data-ttu-id="1efa8-117">Tipo di sistema</span><span class="sxs-lookup"><span data-stu-id="1efa8-117">System type</span></span></th>
<th><span data-ttu-id="1efa8-118">Nome</span><span class="sxs-lookup"><span data-stu-id="1efa8-118">Name</span></span></th>
<th><span data-ttu-id="1efa8-119">Posizione</span><span class="sxs-lookup"><span data-stu-id="1efa8-119">Location</span></span></th>
<th><span data-ttu-id="1efa8-120">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="1efa8-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1efa8-121">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="1efa8-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="1efa8-122">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="1efa8-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="1efa8-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="1efa8-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="1efa8-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="1efa8-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="1efa8-125">MS1</span><span class="sxs-lookup"><span data-stu-id="1efa8-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1efa8-126">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="1efa8-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="1efa8-127">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="1efa8-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="1efa8-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="1efa8-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="1efa8-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efa8-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="1efa8-130">MS1</span><span class="sxs-lookup"><span data-stu-id="1efa8-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1efa8-131">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="1efa8-132">PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="1efa8-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="1efa8-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="1efa8-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="1efa8-135">MS1</span><span class="sxs-lookup"><span data-stu-id="1efa8-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1efa8-136">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="1efa8-137">PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="1efa8-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="1efa8-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efa8-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="1efa8-140">MS1</span><span class="sxs-lookup"><span data-stu-id="1efa8-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="1efa8-141">Definisce i criteri vocali</span><span class="sxs-lookup"><span data-stu-id="1efa8-141">Defines Voice Policies</span></span>

<span data-ttu-id="1efa8-142">È necessario definire i criteri vocali per la distribuzione vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="1efa8-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="1efa8-143">Definire un criterio vocale per applicare restrizioni di routing basate sul percorso a un sottoinsieme di utenti, se è necessario solo un sottoinsieme per l'uso del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1efa8-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="1efa8-144">Per questo esempio, la tabella seguente illustra i criteri vocali usati in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="1efa8-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="1efa8-145">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1efa8-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="1efa8-146">Per altre informazioni, vedere [configurazione di criteri vocali e record di utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="1efa8-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="1efa8-147">Criterio vocale 1</span><span class="sxs-lookup"><span data-stu-id="1efa8-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="1efa8-148">Criterio vocale 2</span><span class="sxs-lookup"><span data-stu-id="1efa8-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1efa8-149">ID criterio vocale</span><span class="sxs-lookup"><span data-stu-id="1efa8-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="1efa8-150">Politica vocale di Delhi</span><span class="sxs-lookup"><span data-stu-id="1efa8-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="1efa8-151">Politica vocale di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efa8-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1efa8-152">Usi PSTN</span><span class="sxs-lookup"><span data-stu-id="1efa8-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="1efa8-153">Uso di Delhi, uso del PBX, uso di HYD PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="1efa8-154">Uso di Hyderabad, uso del PBX HYD, uso del PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1efa8-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="1efa8-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="1efa8-156">False</span><span class="sxs-lookup"><span data-stu-id="1efa8-156">False</span></span></p></td>
<td><p><span data-ttu-id="1efa8-157">False</span><span class="sxs-lookup"><span data-stu-id="1efa8-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="1efa8-158">Definire le route vocali</span><span class="sxs-lookup"><span data-stu-id="1efa8-158">Define Voice Routes</span></span>

<span data-ttu-id="1efa8-159">È necessario definire le route vocali per la distribuzione vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="1efa8-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="1efa8-160">Per questo esempio, la tabella seguente illustra le route vocali usate in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="1efa8-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="1efa8-161">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1efa8-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="1efa8-162">Per altre informazioni, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="1efa8-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="1efa8-163">Route vocale 1</span><span class="sxs-lookup"><span data-stu-id="1efa8-163">Voice route 1</span></span></th>
<th><span data-ttu-id="1efa8-164">Route vocale 2</span><span class="sxs-lookup"><span data-stu-id="1efa8-164">Voice route 2</span></span></th>
<th><span data-ttu-id="1efa8-165">Route vocale 3</span><span class="sxs-lookup"><span data-stu-id="1efa8-165">Voice route 3</span></span></th>
<th><span data-ttu-id="1efa8-166">Route vocale 4</span><span class="sxs-lookup"><span data-stu-id="1efa8-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1efa8-167">Nome</span><span class="sxs-lookup"><span data-stu-id="1efa8-167">Name</span></span></p></td>
<td><p><span data-ttu-id="1efa8-168">Itinerario Delhi</span><span class="sxs-lookup"><span data-stu-id="1efa8-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="1efa8-169">Itinerario di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efa8-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="1efa8-170">PBX del Route</span><span class="sxs-lookup"><span data-stu-id="1efa8-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="1efa8-171">Route HYD PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1efa8-172">Usi PSTN</span><span class="sxs-lookup"><span data-stu-id="1efa8-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="1efa8-173">Uso di Delhi</span><span class="sxs-lookup"><span data-stu-id="1efa8-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="1efa8-174">Uso di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efa8-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="1efa8-175">Utilizzo di PBX del</span><span class="sxs-lookup"><span data-stu-id="1efa8-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="1efa8-176">Uso di HYD PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1efa8-177">Tronco</span><span class="sxs-lookup"><span data-stu-id="1efa8-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="1efa8-178">Trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="1efa8-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="1efa8-179">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="1efa8-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="1efa8-180">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="1efa8-181">Trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="1efa8-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="1efa8-182">Abilitare gli utenti per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="1efa8-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="1efa8-183">Consente agli utenti di VoIP aziendale di assegnare loro un criterio vocale già definito.</span><span class="sxs-lookup"><span data-stu-id="1efa8-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="1efa8-184">Per questo esempio, la tabella seguente illustra l'assegnazione usata in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="1efa8-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="1efa8-185">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="1efa8-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="1efa8-186">Per altre informazioni, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="1efa8-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="1efa8-187">Utenti ubicati in Delhi</span><span class="sxs-lookup"><span data-stu-id="1efa8-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="1efa8-188">Utenti ubicati in Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efa8-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1efa8-189">Criterio vocale associato</span><span class="sxs-lookup"><span data-stu-id="1efa8-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="1efa8-190">Politica vocale di Delhi</span><span class="sxs-lookup"><span data-stu-id="1efa8-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="1efa8-191">Politica vocale di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="1efa8-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1efa8-192">Utenti di esempio</span><span class="sxs-lookup"><span data-stu-id="1efa8-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="1efa8-193">CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="1efa8-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="1efa8-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="1efa8-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1efa8-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1efa8-195">See Also</span></span>


[<span data-ttu-id="1efa8-196">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1efa8-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

