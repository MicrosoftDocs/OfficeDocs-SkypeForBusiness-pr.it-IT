---
title: 'Lync Server 2013: creare criteri per la posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f420d3b634df79411bbc72cd4c029f9b5d97e19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="fe793-102">Creare criteri di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe793-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe793-103">_**Argomento Ultima modifica:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="fe793-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="fe793-104">Lync Server usa un criterio di posizione per abilitare i client Lync per il E9-1-1 durante la registrazione client.</span><span class="sxs-lookup"><span data-stu-id="fe793-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="fe793-105">Un criterio di posizione contiene le impostazioni che definiscono il modo in cui verrà implementato E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="fe793-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="fe793-106">È possibile modificare i criteri di posizione globale e creare nuovi criteri di posizione contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="fe793-106">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="fe793-107">Un client ottiene un criterio globale quando non si trova all'interno di una subnet con un criterio di posizione associato o quando al client non è stato assegnato direttamente un criterio di posizione.</span><span class="sxs-lookup"><span data-stu-id="fe793-107">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="fe793-108">I criteri contrassegnati vengono assegnati a subnet o utenti.</span><span class="sxs-lookup"><span data-stu-id="fe793-108">Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="fe793-109">Per creare un criterio di posizione, è necessario usare un account che sia membro del gruppo RTCUniversalServerAdmins oppure sia un membro del ruolo amministrativo di CsVoiceAdministrator o disponga di autorizzazioni e diritti di amministratore equivalenti.</span><span class="sxs-lookup"><span data-stu-id="fe793-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="fe793-110">Per una descrizione completa dei criteri di posizione, vedere [definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fe793-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="fe793-111">I cmdlet in questa procedura usano i criteri di posizione definiti con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe793-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe793-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe793-112">Element</span></span></th>
<th><span data-ttu-id="fe793-113">Valore</span><span class="sxs-lookup"><span data-stu-id="fe793-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe793-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="fe793-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="fe793-115"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe793-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="fe793-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="fe793-117"><strong>Dichiarazione di non responsabilità</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe793-118">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="fe793-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="fe793-119">I criteri aziendali richiedono l'impostazione di una posizione.</span><span class="sxs-lookup"><span data-stu-id="fe793-119">Your company policy requires you to set a location.</span></span> <span data-ttu-id="fe793-120">Se non si imposta una posizione, i servizi di emergenza non saranno in grado di individuare l'utente in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="fe793-120">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="fe793-121">Impostare una posizione.</span><span class="sxs-lookup"><span data-stu-id="fe793-121">Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe793-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="fe793-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="fe793-123"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe793-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="fe793-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="fe793-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe793-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="fe793-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="fe793-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe793-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="fe793-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="fe793-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe793-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="fe793-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="fe793-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe793-132">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="fe793-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="fe793-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe793-134">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="fe793-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="fe793-135"><strong>TwoWay</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe793-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="fe793-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="fe793-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="fe793-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fe793-138">Per informazioni dettagliate sull'uso dei criteri di posizione, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe793-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="fe793-139">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="fe793-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="fe793-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="fe793-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="fe793-141">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="fe793-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="fe793-142">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="fe793-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="fe793-143">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="fe793-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="fe793-144">Per creare criteri di posizione</span><span class="sxs-lookup"><span data-stu-id="fe793-144">To create location policies</span></span>

1.  <span data-ttu-id="fe793-145">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="fe793-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe793-146">CsLocationPolicy non riesce se l'impostazione per <STRONG>PstnUsage</STRONG> non è già presente nell'elenco globale di PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="fe793-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="fe793-147">Facoltativamente, eseguire il cmdlet seguente per modificare il criterio della posizione globale:</span><span class="sxs-lookup"><span data-stu-id="fe793-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="fe793-148">Eseguire la procedura seguente per creare criteri di posizione contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="fe793-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="fe793-149">Eseguire il cmdlet seguente per applicare il criterio di posizione con tag creato nel passaggio 3 a un criterio utente.</span><span class="sxs-lookup"><span data-stu-id="fe793-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

