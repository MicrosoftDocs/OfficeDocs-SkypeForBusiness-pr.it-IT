---
title: Creare criteri percorso in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leggere questo argomento per informazioni su come configurare i criteri percorso del servizio di emergenza avanzato (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: cee02204a9c5b3708a83e9433f6a88c70230fd64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093144"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="3c12c-103">Creare criteri percorso in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3c12c-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="3c12c-104">Leggere questo argomento per informazioni su come configurare i criteri percorso del servizio di emergenza avanzato (E9-1-1) in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3c12c-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="3c12c-105">Skype for Business Server usa un criterio percorso per abilitare i client Skype for Business per E9-1-1 durante la registrazione del client.</span><span class="sxs-lookup"><span data-stu-id="3c12c-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="3c12c-106">I criteri percorso contengono le impostazioni che definiscono la modalità di implementazione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="3c12c-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="3c12c-107">Per ulteriori informazioni, vedere [Plan location policies for Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3c12c-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="3c12c-108">È possibile definire i criteri percorso utilizzando il Pannello di controllo di Skype for Business o il cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3c12c-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3c12c-109">Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client.</span><span class="sxs-lookup"><span data-stu-id="3c12c-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="3c12c-110">Se si desidera configurare più numeri di emergenza, è necessario seguire le informazioni in Pianificare più numeri di emergenza [in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) e Configurare più numeri di emergenza in Skype for [Business.](configure-multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="3c12c-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="3c12c-p103">È possibile modificare i criteri percorso globali e creare nuovi criteri percorso contrassegnati. Un client ottiene criteri globali quando non si trova in una subnet con criteri percorso associati oppure quando non è stato assegnato direttamente a criteri percorso. I criteri contrassegnati vengono assegnati a subnet o a utenti.</span><span class="sxs-lookup"><span data-stu-id="3c12c-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="3c12c-114">Per creare criteri percorso, è necessario utilizzare un account membro del gruppo RTCUniversalServerAdmins o del ruolo amministrativo CsVoiceAdministrator oppure che disponga di equivalenti diritti e autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3c12c-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="3c12c-115">Per ulteriori informazioni, vedere [Plan location policies for Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3c12c-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="3c12c-116">I cmdlet di questa procedura utilizzano un criterio percorso definito utilizzando i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="3c12c-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="3c12c-117">Per una descrizione completa dei parametri e dei valori dei cmdlet, [vedere New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3c12c-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="3c12c-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3c12c-118">**Element**</span></span>                               | <span data-ttu-id="3c12c-119">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3c12c-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3c12c-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="3c12c-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="3c12c-121">**True**</span><span class="sxs-lookup"><span data-stu-id="3c12c-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="3c12c-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="3c12c-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="3c12c-123">**Dichiarazione di non responsabilità**</span><span class="sxs-lookup"><span data-stu-id="3c12c-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="3c12c-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="3c12c-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="3c12c-p105">È necessario impostare un percorso per il criterio aziendale. Se non si imposta un percorso, in caso di emergenza non sarà possibile essere individuati dai servizi di emergenza. Impostare un percorso.</span><span class="sxs-lookup"><span data-stu-id="3c12c-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
| <span data-ttu-id="3c12c-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="3c12c-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="3c12c-129">**False**</span><span class="sxs-lookup"><span data-stu-id="3c12c-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="3c12c-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="3c12c-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="3c12c-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="3c12c-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="3c12c-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="3c12c-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="3c12c-133">**911**</span><span class="sxs-lookup"><span data-stu-id="3c12c-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="3c12c-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="3c12c-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="3c12c-135">**112**</span><span class="sxs-lookup"><span data-stu-id="3c12c-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="3c12c-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="3c12c-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="3c12c-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3c12c-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="3c12c-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="3c12c-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="3c12c-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3c12c-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="3c12c-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="3c12c-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="3c12c-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="3c12c-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="3c12c-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="3c12c-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="3c12c-143">**2**</span><span class="sxs-lookup"><span data-stu-id="3c12c-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="3c12c-144">Per creare criteri percorso</span><span class="sxs-lookup"><span data-stu-id="3c12c-144">To create location policies</span></span>

1. <span data-ttu-id="3c12c-145">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="3c12c-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3c12c-146">CsLocationPolicy non verrà eseguito correttamente se l'impostazione di **PstnUsage** non è già stata inserita nell'elenco Global di PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="3c12c-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="3c12c-147">Facoltativamente, eseguire il cmdlet seguente per modificare i criteri percorso globali:</span><span class="sxs-lookup"><span data-stu-id="3c12c-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="3c12c-148">Eseguire il cmdlet seguente per creare criteri percorso contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="3c12c-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="3c12c-149">Eseguire il cmdlet seguente per applicare i criteri percorso creati nel passaggio 3 ai criteri di un utente.</span><span class="sxs-lookup"><span data-stu-id="3c12c-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```