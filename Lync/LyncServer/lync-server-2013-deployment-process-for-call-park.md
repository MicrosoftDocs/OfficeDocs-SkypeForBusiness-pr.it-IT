---
title: 'Lync Server 2013: processo di distribuzione per Call Park'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="c68ce-102">Processo di distribuzione per Call Park in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c68ce-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c68ce-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c68ce-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c68ce-104">Questa sezione fornisce una panoramica dei passaggi necessari per la distribuzione dell'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="c68ce-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="c68ce-105">È necessario distribuire Enterprise Edition o Standard Edition con Enterprise Voice prima di configurare Call Park.</span><span class="sxs-lookup"><span data-stu-id="c68ce-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="c68ce-106">I componenti necessari per il parcheggio delle chiamate vengono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c68ce-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="c68ce-107">Processo di distribuzione di Call Park</span><span class="sxs-lookup"><span data-stu-id="c68ce-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c68ce-108">Fase</span><span class="sxs-lookup"><span data-stu-id="c68ce-108">Phase</span></span></th>
<th><span data-ttu-id="c68ce-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="c68ce-109">Steps</span></span></th>
<th><span data-ttu-id="c68ce-110">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="c68ce-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="c68ce-111">Documentazione di distribuzione</span><span class="sxs-lookup"><span data-stu-id="c68ce-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c68ce-112">Configurare gli intervalli di orbit del parcheggio delle chiamate nella tabella Orbit</span><span class="sxs-lookup"><span data-stu-id="c68ce-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="c68ce-113">Usa il pannello di controllo di Lync Server o il cmdlet <strong>New-CsCallParkOrbit</strong> per creare gli intervalli di Orbit nella tabella Orbit di Call Park e associarli al servizio applicazione che ospita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c68ce-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c68ce-114">Per una perfetta integrazione con i dial plan esistenti, gli intervalli orbit sono in genere configurati come blocco di estensioni virtuali.</span><span class="sxs-lookup"><span data-stu-id="c68ce-114">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="c68ce-115">L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di orbita nella tabella Orbit di parcheggio delle chiamate non è supportata.</span><span class="sxs-lookup"><span data-stu-id="c68ce-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="c68ce-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c68ce-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c68ce-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c68ce-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Creare o modificare un intervallo orbit di Call Park in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c68ce-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c68ce-121">Configurare le impostazioni di Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="c68ce-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="c68ce-122">Usa il cmdlet <strong>Set-CsCpsConfiguration</strong> per configurare le impostazioni di Call Park.</span><span class="sxs-lookup"><span data-stu-id="c68ce-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="c68ce-123">Come minimo, ti consigliamo di configurare l'opzione <strong>OnTimeoutURI</strong> per configurare la destinazione di fallback da usare in caso di timeout di una chiamata parcheggiata. È anche possibile configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c68ce-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="c68ce-124">Opzionale <strong>EnableMusicOnHold</strong> per abilitare o disabilitare la musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="c68ce-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="c68ce-125">Opzionale <strong>MaxCallPickupAttempts</strong> per determinare il numero di squilli di una chiamata parcheggiata di nuovo al telefono che risponde prima di inoltrare la chiamata all'URI (Uniform Resource Identifier) di fallback.</span><span class="sxs-lookup"><span data-stu-id="c68ce-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="c68ce-126">Opzionale <strong>CallPickupTimeoutThreshold</strong> per determinare la quantità di tempo che trascorre dopo il parcheggio di una chiamata prima che ritorni al telefono in cui è stata risolta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c68ce-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c68ce-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c68ce-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c68ce-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c68ce-131"><a href="lync-server-2013-configure-call-park-settings.md">Configurare le impostazioni di Call Park in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c68ce-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c68ce-132">Facoltativamente, personalizzare la musica in attesa</span><span class="sxs-lookup"><span data-stu-id="c68ce-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="c68ce-133">Usare il cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> per personalizzare e caricare un file audio, se non si vuole usare la musica predefinita in attesa.</span><span class="sxs-lookup"><span data-stu-id="c68ce-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="c68ce-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c68ce-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c68ce-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c68ce-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizzare la musica di Call Park in attesa in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c68ce-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c68ce-139">Configurare i criteri vocali per abilitare il parcheggio delle chiamate per gli utenti</span><span class="sxs-lookup"><span data-stu-id="c68ce-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="c68ce-140">Utilizzare il pannello di controllo di Lync Server o il cmdlet <strong>Set-CsVoicePolicy</strong> con l'opzione <strong>EnableCallPark</strong> per abilitare il parcheggio di chiamata per gli utenti nel criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="c68ce-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c68ce-141">Per impostazione predefinita, il parcheggio delle chiamate è disabilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c68ce-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="c68ce-142">Se si hanno più criteri vocali, verificare che la proprietà EnableCallPark sia impostata per ogni criterio vocale, non solo per i criteri predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c68ce-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="c68ce-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c68ce-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c68ce-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c68ce-147"><a href="lync-server-2013-enable-call-park-for-users.md">Abilitare il parcheggio delle chiamate per gli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c68ce-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c68ce-148">Verificare le regole di normalizzazione per il parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="c68ce-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="c68ce-149">Le orbite del parcheggio delle chiamate non devono essere normalizzate.</span><span class="sxs-lookup"><span data-stu-id="c68ce-149">Call park orbits must not be normalized.</span></span> <span data-ttu-id="c68ce-150">Verificare che le regole di normalizzazione non includano alcuno degli intervalli di orbita.</span><span class="sxs-lookup"><span data-stu-id="c68ce-150">Verify that your normalization rules do not include any of your orbit ranges.</span></span> <span data-ttu-id="c68ce-151">Se necessario, creare regole di normalizzazione aggiuntive per impedire la normalizzazione delle orbite.</span><span class="sxs-lookup"><span data-stu-id="c68ce-151">If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="c68ce-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c68ce-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c68ce-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="c68ce-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c68ce-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c68ce-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verificare le regole di normalizzazione per Call Park in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c68ce-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c68ce-157">Verificare la distribuzione di Call Park</span><span class="sxs-lookup"><span data-stu-id="c68ce-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="c68ce-158">Verificare il parcheggio e il recupero delle chiamate per verificare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="c68ce-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c68ce-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Opzionale Verificare la distribuzione di Call Park in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c68ce-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

