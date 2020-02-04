---
title: Verificare impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="74c37-102">Verificare impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="74c37-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74c37-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="74c37-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="74c37-104">Dopo aver merge la topologia ed eseguito il cmdlet **Import-CsLegacyConfiguration** , verificare che i criteri e le impostazioni di Office Communications Server 2007 R2 siano stati importati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74c37-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="74c37-105">Nella tabella seguente sono elencati i criteri e le impostazioni da verificare.</span><span class="sxs-lookup"><span data-stu-id="74c37-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="74c37-106">Criteri e impostazioni per verificare dopo la migrazione</span><span class="sxs-lookup"><span data-stu-id="74c37-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74c37-107">Se si usa questo carico di lavoro:</span><span class="sxs-lookup"><span data-stu-id="74c37-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="74c37-108">Verificare questi criteri e impostazioni:</span><span class="sxs-lookup"><span data-stu-id="74c37-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74c37-109">Messaggistica istantanea (IM) e servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="74c37-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="74c37-110">Criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="74c37-110">Presence policy</span></span></p>
<p><span data-ttu-id="74c37-111">Criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="74c37-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-112">Chiamate in conferenza</span><span class="sxs-lookup"><span data-stu-id="74c37-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="74c37-113">Numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="74c37-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="74c37-114">Dial plan</span><span class="sxs-lookup"><span data-stu-id="74c37-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c37-115">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="74c37-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="74c37-116">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="74c37-116">Voice policy</span></span></p>
<p><span data-ttu-id="74c37-117">Route vocali</span><span class="sxs-lookup"><span data-stu-id="74c37-117">Voice routes</span></span></p>
<p><span data-ttu-id="74c37-118">Dial plan</span><span class="sxs-lookup"><span data-stu-id="74c37-118">Dial plans</span></span></p>
<p><span data-ttu-id="74c37-119">Impostazioni di utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="74c37-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="74c37-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="74c37-121">URL semplici</span><span class="sxs-lookup"><span data-stu-id="74c37-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c37-122">Utenti esterni</span><span class="sxs-lookup"><span data-stu-id="74c37-122">External users</span></span></p></td>
<td><p><span data-ttu-id="74c37-123">Criteri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="74c37-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-124">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="74c37-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="74c37-125">Criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="74c37-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="74c37-126">Per verificare i criteri e le impostazioni</span><span class="sxs-lookup"><span data-stu-id="74c37-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="74c37-127">Nell'ambiente Office Communications Server 2007 R2 prendere nota dei nomi dei dial plan (in precedenza noti come profili di posizione), numeri di accesso in ingresso (numeri di telefono e aree geografiche di accesso per i servizi di conferenza), route vocali e criteri elencati nell'elenco tabella precedente, oltre agli URL usati per Communicator Web Access.</span><span class="sxs-lookup"><span data-stu-id="74c37-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="74c37-128">Nel server front-end di Lync Server 2013 aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74c37-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="74c37-129">Per verificare i criteri di conferenza importati, nel riquadro sinistro fare clic su servizi di **conferenza**, su **criteri di conferenza**e quindi verificare che tutti i criteri di conferenza nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74c37-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74c37-130">Il criterio della <STRONG>riunione</STRONG> delle versioni precedenti di Office Communications Server è ora noto come criterio di conferenza in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74c37-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="74c37-131">Inoltre, l'impostazione <STRONG>Particpants anonima</STRONG> delle versioni precedenti di Office Communications Server è ora un'impostazione nei criteri di conferenza di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74c37-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74c37-132">In Office Communications Server 2007 R2, se i criteri di conferenza non sono impostati per l' <STRONG>uso per utente</STRONG>, vengono importate solo le impostazioni dei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="74c37-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="74c37-133">In questa situazione non vengono importati altri criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="74c37-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74c37-134">Se <STRONG>i partecipanti anonimi</STRONG> sono impostati per l' <STRONG>applicazione per ogni utente</STRONG> nei criteri di conferenza di Office Communications Server 2007 R2, vengono creati due criteri di conferenza durante la migrazione: uno con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> impostato su <STRONG>true</STRONG> e uno con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> impostato su <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="74c37-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="74c37-135">Per verificare i piani di chiamata importati, fare clic su **routing vocale**, fare clic su **dial plan**e verificare che tutti i dial plan nell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74c37-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74c37-136">In Lync Server 2013 i <STRONG>profili di posizione</STRONG> sono ora indicati come <STRONG>dial-plan</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="74c37-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="74c37-137">Per verificare i criteri vocali importati, fare clic su **routing vocale**, fare clic su **criteri vocali**e verificare che tutti i criteri vocali nell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74c37-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74c37-138">Se il criterio vocale non è impostato per l' <STRONG>uso per utente</STRONG> nell'ambiente Office Communications Server 2007 R2, vengono importate solo le impostazioni dei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="74c37-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="74c37-139">In questa situazione non vengono importati altri criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="74c37-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="74c37-140">Per verificare le route vocali importate, fare clic su **routing vocale**, fare clic su **Route**e verificare che tutte le route vocali nell'ambiente Office Communicator 2007 R2 siano incluse nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74c37-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="74c37-141">Per verificare le impostazioni di utilizzo PSTN importate, fare clic su **routing vocale**, fare clic su **utilizzo PSTN**e verificare che le impostazioni di utilizzo PSTN dell'ambiente Office Communicator 2007 R2 siano incluse nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74c37-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="74c37-142">Per verificare i criteri di accesso esterno importati, fare clic su **Federazione e accesso esterno**, fare clic su **criteri di accesso esterno**e verificare che tutti i criteri di accesso esterno nell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74c37-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="74c37-143">Per verificare i criteri di archiviazione, fare clic su **monitoraggio e archiviazione**, fare clic su **criteri di archiviazione**e verificare che tutti i criteri di archiviazione nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74c37-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="74c37-144">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="74c37-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="74c37-145">Per verificare i criteri di presenza, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="74c37-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="74c37-146">Esaminando il nome nel parametro **Identity** , verificare che siano stati importati tutti i criteri di presenza nell'ambiente Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="74c37-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="74c37-147">Per verificare i criteri e le impostazioni usando i cmdlet</span><span class="sxs-lookup"><span data-stu-id="74c37-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="74c37-148">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="74c37-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="74c37-149">Eseguire i cmdlet nella tabella seguente per verificare i criteri e le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="74c37-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="74c37-150">La sintassi di questi cmdlet è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="74c37-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="74c37-151">Per informazioni dettagliate su questi cmdlet, eseguire:</span><span class="sxs-lookup"><span data-stu-id="74c37-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74c37-152">Per questo criterio o impostazione:</span><span class="sxs-lookup"><span data-stu-id="74c37-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="74c37-153">Utilizzare questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="74c37-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74c37-154">Criteri di presenza</span><span class="sxs-lookup"><span data-stu-id="74c37-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="74c37-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-156">Criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="74c37-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="74c37-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c37-158">Numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="74c37-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="74c37-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-160">Dial plan</span><span class="sxs-lookup"><span data-stu-id="74c37-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="74c37-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c37-162">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="74c37-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="74c37-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-164">Route vocali</span><span class="sxs-lookup"><span data-stu-id="74c37-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="74c37-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c37-166">Utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="74c37-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="74c37-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-168">URL</span><span class="sxs-lookup"><span data-stu-id="74c37-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="74c37-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c37-170">Criteri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="74c37-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="74c37-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c37-172">Criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="74c37-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="74c37-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74c37-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

