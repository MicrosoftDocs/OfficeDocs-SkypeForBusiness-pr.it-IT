---
title: Assistenza vocale di Cortana in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Scopri come usare l'assistenza vocale di Cortana con Teams
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
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886735"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="554fa-103">Assistenza vocale di Cortana in Teams</span><span class="sxs-lookup"><span data-stu-id="554fa-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="554fa-104">L'assistenza vocale di Cortana è supportata nelle app per dispositivi mobili Microsoft Teams per iOS e Android e nei display di Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia.</span><span class="sxs-lookup"><span data-stu-id="554fa-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span>  <span data-ttu-id="554fa-105">Microsoft Teams Rooms per Windows è supportato solo per gli utenti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="554fa-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="554fa-106">L'assistenza vocale di Cortana non è attualmente disponibile per i tenant GCC, GCC-High, DoD, EDU.</span><span class="sxs-lookup"><span data-stu-id="554fa-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="554fa-107">L'espansione in altre lingue e aree geografiche avverrà nell'ambito dei rilasci futuri.</span><span class="sxs-lookup"><span data-stu-id="554fa-107">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="554fa-108">L'assistenza vocale di Cortana nelle sale di Microsoft Teams viene rilasciata in Anteprima.</span><span class="sxs-lookup"><span data-stu-id="554fa-108">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="554fa-109">Nella versione di anteprima, Cortana è supportata solo negli Stati Uniti con la lingua EN-US nei dispositivi che hanno collegato i microfoni di Rally.</span><span class="sxs-lookup"><span data-stu-id="554fa-109">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="554fa-110">L'assistenza vocale di Cortana nell'app Teams per dispositivi mobili, nelle sale di Microsoft Teams in Windows e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti di Microsoft 365 Enterprise di semplificare le attività di comunicazione, collaborazione e riunione usando il linguaggio naturale parlato.</span><span class="sxs-lookup"><span data-stu-id="554fa-110">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="554fa-111">Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando &#8220;Cortana&#8221; nella Microsoft Teams Room o quando si usa un display Di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="554fa-111">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="554fa-112">Per connettersi rapidamente con il team a mani libere e in viaggio, gli utenti possono pronunciare query come &#8220;chiama Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;.</span><span class="sxs-lookup"><span data-stu-id="554fa-112">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="554fa-113">Gli utenti possono anche partecipare alle riunioni dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="554fa-113">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="554fa-114">Queste esperienze di assistenza vocale vengono recapitate usando servizi di livello [enterprise di Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) pienamente conformi alle promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni per i Servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="554fa-114">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="554fa-115">L'immagine mostra l'invio di una chat con Cortana su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="554fa-115">The image shows sending a chat using Cortana on a mobile device.</span></span>

![una sequenza di schermate per dispositivi mobili che mostrano una sessione di chat di Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="554fa-117">Controllo dell'amministratore e limitazioni</span><span class="sxs-lookup"><span data-stu-id="554fa-117">Admin control and limitations</span></span>

<span data-ttu-id="554fa-118">L'assistenza vocale di Cortana in Teams viene recapitata usando servizi pienamente conformi alle promesse di privacy, sicurezza e conformità a livello aziendale di Office 365, come illustrato nelle Condizioni per i Servizi online (OST).</span><span class="sxs-lookup"><span data-stu-id="554fa-118">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="554fa-119">La caratteristica verrà abilitata per impostazione predefinita per i tenant.</span><span class="sxs-lookup"><span data-stu-id="554fa-119">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="554fa-120">Gli amministratori tenant possono controllare chi nel tenant può usare l'assistenza vocale di Cortana in Teams usando un criterio (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="554fa-120">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="554fa-121">Questo criterio può essere impostato a livello di account utente o di tenant.</span><span class="sxs-lookup"><span data-stu-id="554fa-121">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="554fa-122">Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitata, abilitata solo con la chiamata del pulsante push o anche con la chiamata di wake word (applicabile ai dispositivi che la supportano, come la visualizzazione di Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="554fa-122">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="554fa-123">Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="554fa-123">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="554fa-124">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="554fa-124">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="554fa-125">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="554fa-125">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="554fa-126">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="554fa-126">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="554fa-127">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="554fa-127">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="554fa-128">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="554fa-128">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="554fa-129">Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui l'assistenza vocale di Cortana in Microsoft Teams è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="554fa-129">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="554fa-130">Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione dell'assistenza vocale di Cortana in Microsoft Teams solo con la chiamata al pulsante push.</span><span class="sxs-lookup"><span data-stu-id="554fa-130">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="554fa-131">Gli utenti potranno richiamare Cortana selezionando il pulsante microfono di Cortana in Teams.</span><span class="sxs-lookup"><span data-stu-id="554fa-131">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="554fa-132">La chiamata di wake word (&#8220;Ehi Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="554fa-132">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="554fa-133">Questo esempio mostra l'aggiornamento dei criteri e l'abilitazione dell'assistenza vocale di Cortana sia con il pulsante push che con la chiamata della parola di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="554fa-133">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="554fa-134">Al momento del rilascio iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="554fa-134">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="554fa-135">L'app Teams per dispositivi mobili non supporta l'attivazione delle parole di riattivazione, ma sarà supportata in futuro.</span><span class="sxs-lookup"><span data-stu-id="554fa-135">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="554fa-136">Microsoft Teams Rooms nei dispositivi di visualizzazione Windows e Microsoft Teams supporterà l'attivazione delle parole di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="554fa-136">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="554fa-137">Controllo utente</span><span class="sxs-lookup"><span data-stu-id="554fa-137">User control</span></span>

<span data-ttu-id="554fa-138">I singoli utenti possono provare l'assistenza vocale di Cortana in diversi dispositivi:</span><span class="sxs-lookup"><span data-stu-id="554fa-138">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="554fa-139">Seleziona il pulsante del microfono nell'app Teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="554fa-139">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="554fa-140">Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="554fa-140">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="554fa-141">Pronuncia "Cortana" nei dispositivi di visualizzazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="554fa-141">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="554fa-142">Puoi controllare se Cortana in Teams è abilitata per il tuo dispositivo usando un'impostazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="554fa-142">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="554fa-143">App Teams per dispositivi mobili o visualizzazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="554fa-143">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="554fa-144">Aprire l'app Teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="554fa-144">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="554fa-145">Seleziona **Impostazioni**  >  **Cortana.**</span><span class="sxs-lookup"><span data-stu-id="554fa-145">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="554fa-146">Spostare l'interruttore **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="554fa-146">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="554fa-147">Visualizzazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="554fa-147">Microsoft Teams display</span></span>

  1. <span data-ttu-id="554fa-148">Passare alla schermata ambiente (home) del display di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="554fa-148">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="554fa-149">Selezionare l'avatar dell'utente e quindi **selezionare Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="554fa-149">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="554fa-150">Se Cortana è abilitata, pronuncia "Cortana, vai a Impostazioni".</span><span class="sxs-lookup"><span data-stu-id="554fa-150">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="554fa-151">Spostare l'interruttore **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="554fa-151">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="554fa-152">Microsoft Teams Rooms in Windows</span><span class="sxs-lookup"><span data-stu-id="554fa-152">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="554fa-153">Le modifiche a livello di dispositivo sono disponibili se Cortana è abilitata a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="554fa-153">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="554fa-154">Cortana verrà rilasciata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="554fa-154">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="554fa-155">Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="554fa-155">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="554fa-156">Le modifiche a livello di riunione sono disponibili se Cortana è abilitata a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="554fa-156">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="554fa-157">Per abilitare l'assistenza vocale di Cortana durante una riunione, sposta l'interruttore **Attivato** o **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="554fa-157">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="554fa-158">Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="554fa-158">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
