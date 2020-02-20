---
title: 'Lync Server 2013: processo di distribuzione per il parcheggio di chiamata'
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
ms.openlocfilehash: 2ff40921e75eb9b2a48c591f3f5df2ba09891627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="25d89-102">Processo di distribuzione per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25d89-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25d89-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="25d89-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="25d89-104">In questa sezione viene fornita una panoramica dei passaggi necessari per la distribuzione dell'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="25d89-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="25d89-105">Prima di configurare il parcheggio di chiamata, è necessario distribuire Enterprise Edition o Standard Edition con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="25d89-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="25d89-106">I componenti richiesti dal parcheggio di chiamata vengono installati e abilitati quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="25d89-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="25d89-107">Processo di distribuzione di Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="25d89-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25d89-108">Fase</span><span class="sxs-lookup"><span data-stu-id="25d89-108">Phase</span></span></th>
<th><span data-ttu-id="25d89-109">Passaggi</span><span class="sxs-lookup"><span data-stu-id="25d89-109">Steps</span></span></th>
<th><span data-ttu-id="25d89-110">Gruppi e ruoli obbligatori</span><span class="sxs-lookup"><span data-stu-id="25d89-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="25d89-111">Documentazione sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="25d89-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25d89-112">Configurare gli intervalli dei codici orbit di parcheggio di chiamata nella tabella dei codici orbit</span><span class="sxs-lookup"><span data-stu-id="25d89-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="25d89-113">Utilizzare il pannello di controllo di Lync Server o il cmdlet <strong>New-CsCallParkOrbit</strong> per creare gli intervalli di Orbit nella tabella orbit del parcheggio di chiamata e associarli al servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="25d89-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="25d89-p102">Per l'integrazione completa con i dial plan esistenti, gli intervalli dei codici orbit in genere sono configurati come un blocco di estensioni virtuali. L'assegnazione di numeri Direct Inward Dialing (DID) come numeri di codici orbit nella tabella dei codici orbit di parcheggio di chiamata non è supportata.</span><span class="sxs-lookup"><span data-stu-id="25d89-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="25d89-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25d89-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25d89-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="25d89-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="25d89-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="25d89-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25d89-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25d89-121">Configurare le impostazioni del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="25d89-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="25d89-122">Utilizzare il cmdlet <strong>Set-CsCpsConfiguration</strong> per configurare le impostazioni del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="25d89-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="25d89-123">È consigliabile configurare almeno l'opzione <strong>OnTimeoutURI</strong> per configurare la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata. È inoltre possibile configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="25d89-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="25d89-124">(Facoltativo) <strong>EnableMusicOnHold</strong> per abilitare o disabilitare la musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="25d89-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="25d89-125">(Facoltativo) <strong>MaxCallPickupAttempts</strong> per determinare il numero di squilli sul telefono di destinazione di una chiamata parcheggiata prima dell'inoltro all'URI (Uniform Resource Identifier) di fallback.</span><span class="sxs-lookup"><span data-stu-id="25d89-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="25d89-126">(Facoltativo) <strong>CallPickupTimeoutThreshold</strong> per determinare quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta.</span><span class="sxs-lookup"><span data-stu-id="25d89-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="25d89-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25d89-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25d89-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="25d89-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="25d89-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="25d89-131"><a href="lync-server-2013-configure-call-park-settings.md">Configurare le impostazioni del parcheggio di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25d89-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25d89-132">Se lo si desidera, personalizzare la musica di attesa</span><span class="sxs-lookup"><span data-stu-id="25d89-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="25d89-133">Utilizzare il cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> per personalizzare e caricare un file audio, se non si desidera utilizzare la musica di attesa predefinita.</span><span class="sxs-lookup"><span data-stu-id="25d89-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="25d89-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25d89-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25d89-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="25d89-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="25d89-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="25d89-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizzare la musica del parcheggio di chiamata in attesa in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25d89-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25d89-139">Configurare il criterio vocale per abilitare il parcheggio di chiamata per gli utenti</span><span class="sxs-lookup"><span data-stu-id="25d89-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="25d89-140">Utilizzare il pannello di controllo di Lync Server o il cmdlet <strong>Set-CsVoicePolicy</strong> con l'opzione <strong>EnableCallPark</strong> per abilitare il parcheggio di chiamata per gli utenti nel criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="25d89-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="25d89-141">Per impostazione predefinita, il parcheggio di chiamata è disabilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="25d89-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="25d89-142">Se si dispone di più criteri vocali, verificare che la proprietà EnableCallPark sia impostata per ogni criterio vocale e non solo per quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="25d89-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="25d89-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25d89-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25d89-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="25d89-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="25d89-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="25d89-147"><a href="lync-server-2013-enable-call-park-for-users.md">Abilitare il parcheggio di chiamata per gli utenti in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25d89-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25d89-148">Verificare le regole di normalizzazione per il parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="25d89-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="25d89-p104">I codici orbit di Parcheggio di chiamata non devono essere normalizzati. Verificare che le regole di normalizzazione non includano alcun intervallo dei codici orbit. Se necessario, creare regole di normalizzazione aggiuntive per impedire che vengano normalizzati i codici orbit.</span><span class="sxs-lookup"><span data-stu-id="25d89-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="25d89-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="25d89-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="25d89-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="25d89-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="25d89-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="25d89-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="25d89-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verificare le regole di normalizzazione per il parcheggio di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25d89-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25d89-157">Verificare la distribuzione del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="25d89-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="25d89-158">Verifica del parcheggio e del recupero delle chiamate per verificare che la configurazione funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="25d89-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="25d89-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Optional Verificare la distribuzione del parcheggio di chiamata in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="25d89-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

