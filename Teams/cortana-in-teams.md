---
title: Assistenza vocale Cortana in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Informazioni su come usare Cortana Voice Assistance con teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686442"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="ba034-103">Assistenza vocale Cortana in teams</span><span class="sxs-lookup"><span data-stu-id="ba034-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="ba034-104">L'assistenza vocale di Cortana è supportata nelle app Microsoft teams per dispositivi mobili iOS e Android, nelle sale di Microsoft teams in Windows e in Microsoft teams, solo per gli utenti degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ba034-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="ba034-105">Attualmente non è disponibile per i tenant GCC, GCC-High, DoD e EDU.</span><span class="sxs-lookup"><span data-stu-id="ba034-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="ba034-106">L'espansione in altre lingue e aree geografiche avverrà come parte delle versioni future.</span><span class="sxs-lookup"><span data-stu-id="ba034-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="ba034-107">Cortana Voice Assistance in Microsoft teams Rooms viene rilasciato in anteprima.</span><span class="sxs-lookup"><span data-stu-id="ba034-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="ba034-108">Nella versione di anteprima, Cortana è supportato solo negli Stati Uniti con la lingua EN-US nei dispositivi con microfoni di Rally collegati.</span><span class="sxs-lookup"><span data-stu-id="ba034-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="ba034-109">Cortana Voice Assistance nell'app teams per dispositivi mobili, in Microsoft teams rooms in Windows e nei dispositivi di visualizzazione di Microsoft teams consente agli utenti di Microsoft 365 Enterprise di semplificare la comunicazione, la collaborazione e le attività correlate alla riunione usando il linguaggio naturale parlato.</span><span class="sxs-lookup"><span data-stu-id="ba034-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="ba034-110">Gli utenti possono parlare con Cortana selezionando il pulsante del microfono situato nell'angolo in alto a destra dell'app teams per dispositivi mobili o dicendo &#8220;Cortana&#8221; nella sala Microsoft teams o quando si usa una visualizzazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ba034-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="ba034-111">Per comunicare rapidamente con il team in vivavoce e mentre si è in viaggio, gli utenti possono dire query come &#8220;chiamare Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;.</span><span class="sxs-lookup"><span data-stu-id="ba034-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="ba034-112">Gli utenti possono partecipare alle riunioni anche dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="ba034-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="ba034-113">Queste esperienze di assistenza vocale vengono recapitate usando i [servizi di qualità aziendale di Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365, come indicato nelle [condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="ba034-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="ba034-114">L'immagine mostra l'invio di una chat tramite Cortana su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="ba034-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![una sequenza di schermate per dispositivi mobili che mostra una sessione di chat Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="ba034-116">Controllo di amministrazione e limitazioni</span><span class="sxs-lookup"><span data-stu-id="ba034-116">Admin control and limitations</span></span>

<span data-ttu-id="ba034-117">L'assistenza vocale di Cortana in teams viene recapitata con i servizi che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365 a livello aziendale, come indicato nei termini dei servizi online (OST).</span><span class="sxs-lookup"><span data-stu-id="ba034-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="ba034-118">La caratteristica verrà abilitata per impostazione predefinita per i tenant.</span><span class="sxs-lookup"><span data-stu-id="ba034-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="ba034-119">Gli amministratori del tenant possono controllare chi nel tenant può usare Cortana Voice Assistance in teams usando un criterio (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="ba034-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="ba034-120">Questo criterio può essere impostato sia a livello di account utente che di livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="ba034-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="ba034-121">Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato con la chiamata a pulsante solo, o anche con la chiamata di Word Wake (applicabile ai dispositivi che lo supportano, ad esempio Microsoft teams display).</span><span class="sxs-lookup"><span data-stu-id="ba034-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="ba034-122">Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="ba034-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="ba034-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ba034-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ba034-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ba034-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ba034-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ba034-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ba034-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ba034-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="ba034-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="ba034-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="ba034-128">Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui l'assistenza vocale Cortana in Microsoft teams è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="ba034-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="ba034-129">Questo esempio Mostra come aggiornare un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e abilitare l'assistenza vocale Cortana in Microsoft teams con solo chiamata Push Button.</span><span class="sxs-lookup"><span data-stu-id="ba034-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="ba034-130">Gli utenti saranno in grado di richiamare Cortana selezionando il pulsante mic Cortana in teams.</span><span class="sxs-lookup"><span data-stu-id="ba034-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="ba034-131">Wake Word (&#8220;Hey Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="ba034-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="ba034-132">Questo esempio Mostra come aggiornare i criteri e abilitare l'assistenza vocale di Cortana sia con il pulsante push che con la chiamata di Word Wake.</span><span class="sxs-lookup"><span data-stu-id="ba034-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="ba034-133">Al momento della versione iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese sono disponibili le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba034-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="ba034-134">L'app teams per dispositivi mobili non supporta l'attivazione di Wake Word, ma sarà supportata in futuro.</span><span class="sxs-lookup"><span data-stu-id="ba034-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="ba034-135">Le sale di Microsoft Teams nei dispositivi di visualizzazione Windows e Microsoft teams supportano l'attivazione di Wake Word.</span><span class="sxs-lookup"><span data-stu-id="ba034-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="ba034-136">Controllo utente</span><span class="sxs-lookup"><span data-stu-id="ba034-136">User control</span></span>

<span data-ttu-id="ba034-137">I singoli utenti possono provare Cortana Voice Assistance in dispositivi diversi:</span><span class="sxs-lookup"><span data-stu-id="ba034-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="ba034-138">Selezionare il pulsante microfono nell'app teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ba034-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="ba034-139">Selezionare il pulsante del microfono o pronunciare "Cortana" nelle sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ba034-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="ba034-140">Dire "Cortana" nei dispositivi di visualizzazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ba034-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="ba034-141">Puoi controllare se Cortana in teams è abilitato per il dispositivo usando un'impostazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba034-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="ba034-142">App teams per dispositivi mobili o visualizzazione Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba034-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="ba034-143">Aprire l'app teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ba034-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="ba034-144">Selezionare **Impostazioni**  >  **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="ba034-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="ba034-145">Spostare l' **attiva o** **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="ba034-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="ba034-146">Visualizzazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba034-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="ba034-147">Passare alla schermata ambiente (Home) della visualizzazione Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ba034-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="ba034-148">Selezionare l'avatar dell'utente e quindi selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="ba034-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="ba034-149">Se Cortana è abilitato, ad esempio, "Cortana, passa a impostazioni".</span><span class="sxs-lookup"><span data-stu-id="ba034-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="ba034-150">Spostare l' **attiva o** **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="ba034-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="ba034-151">Microsoft teams rooms in Windows</span><span class="sxs-lookup"><span data-stu-id="ba034-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="ba034-152">Se Cortana è abilitato a livello di tenant, è possibile apportare modifiche a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba034-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="ba034-153">Cortana verrà rilasciata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ba034-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="ba034-154">Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML di SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="ba034-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="ba034-155">Se Cortana è abilitato a livello di dispositivo, è possibile apportare modifiche a livello di riunione.</span><span class="sxs-lookup"><span data-stu-id="ba034-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="ba034-156">Per abilitare l'assistenza **vocale di Cortana** durante una riunione, spostare l'attiva o **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="ba034-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="ba034-157">Al termine della riunione, Cortana torna al set di impostazioni del livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba034-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
