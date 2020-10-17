---
title: 'Lync Server 2013: creare criteri percorso'
description: 'Lync Server 2013: creare criteri percorso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562262"
---
# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="7f517-103">Creare criteri percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f517-103">Create location policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f517-104">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="7f517-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="7f517-105">Lync Server utilizza un criterio percorso per abilitare i client Lync per il servizio E9-1-1 durante la registrazione client.</span><span class="sxs-lookup"><span data-stu-id="7f517-105">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="7f517-106">I criteri percorso contengono le impostazioni che definiscono la modalità di implementazione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7f517-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="7f517-p102">È possibile modificare i criteri percorso globali e creare nuovi criteri percorso contrassegnati. Un client ottiene criteri globali quando non si trova in una subnet con criteri percorso associati oppure quando non è stato assegnato direttamente a criteri percorso. I criteri contrassegnati vengono assegnati a subnet o a utenti.</span><span class="sxs-lookup"><span data-stu-id="7f517-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="7f517-110">Per creare criteri percorso, è necessario utilizzare un account membro del gruppo RTCUniversalServerAdmins o del ruolo amministrativo CsVoiceAdministrator oppure che disponga di equivalenti diritti e autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="7f517-110">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="7f517-111">Per una descrizione completa dei criteri percorso, vedere [define the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="7f517-111">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="7f517-112">I cmdlet di questa procedura utilizzano criteri percorso definiti con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f517-112">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f517-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f517-113">Element</span></span></th>
<th><span data-ttu-id="7f517-114">Valore</span><span class="sxs-lookup"><span data-stu-id="7f517-114">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f517-115">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="7f517-115">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="7f517-116"><strong>Vero</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-116"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f517-117">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="7f517-117">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="7f517-118"><strong>Dichiarazione di non responsabilità</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-118"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f517-119">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="7f517-119">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="7f517-p104">È necessario impostare un percorso per il criterio aziendale. Se non si imposta un percorso, in caso di emergenza non sarà possibile essere individuati dai servizi di emergenza. Impostare un percorso.</span><span class="sxs-lookup"><span data-stu-id="7f517-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f517-123">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="7f517-123">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="7f517-124"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-124"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f517-125">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="7f517-125">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="7f517-126"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-126"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f517-127">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="7f517-127">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="7f517-128"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-128"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f517-129">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="7f517-129">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="7f517-130"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-130"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f517-131">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="7f517-131">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="7f517-132"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-132"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f517-133">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="7f517-133">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="7f517-134"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-134"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f517-135">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="7f517-135">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="7f517-136"><strong>TwoWay</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-136"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f517-137">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="7f517-137">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="7f517-138"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="7f517-138"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7f517-139">Per informazioni dettagliate sull'utilizzo dei criteri percorso, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f517-139">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="7f517-140">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="7f517-140">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="7f517-141">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="7f517-141">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="7f517-142">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="7f517-142">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="7f517-143">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="7f517-143">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="7f517-144">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="7f517-144">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="7f517-145">Per creare criteri percorso</span><span class="sxs-lookup"><span data-stu-id="7f517-145">To create location policies</span></span>

1.  <span data-ttu-id="7f517-146">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7f517-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f517-147">CsLocationPolicy non verrà eseguito correttamente se l'impostazione di <STRONG>PstnUsage</STRONG> non è già stata inserita nell'elenco Global di PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="7f517-147">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="7f517-148">Facoltativamente, eseguire il cmdlet seguente per modificare i criteri percorso globali:</span><span class="sxs-lookup"><span data-stu-id="7f517-148">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="7f517-149">Eseguire il cmdlet seguente per creare criteri percorso contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="7f517-149">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="7f517-150">Eseguire il cmdlet seguente per applicare i criteri percorso creati nel passaggio 3 ai criteri di un utente.</span><span class="sxs-lookup"><span data-stu-id="7f517-150">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

