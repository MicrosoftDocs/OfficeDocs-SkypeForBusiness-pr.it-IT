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
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118475"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="2adda-103">Assistenza vocale di Cortana in Teams</span><span class="sxs-lookup"><span data-stu-id="2adda-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="2adda-104">L'assistenza vocale di Cortana è supportata nelle app per dispositivi mobili iOS e Android di Microsoft Teams, nelle sale di Microsoft Teams per Windows e nei display di Microsoft Teams, solo per gli utenti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="2adda-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="2adda-105">Attualmente non è disponibile per i tenant GCC, GCC-High, DoD, EDU.</span><span class="sxs-lookup"><span data-stu-id="2adda-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="2adda-106">L'espansione in altre lingue e aree geografiche avverrà nell'ambito dei rilasci futuri.</span><span class="sxs-lookup"><span data-stu-id="2adda-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="2adda-107">L'assistenza vocale di Cortana nelle sale di Microsoft Teams viene rilasciata in Anteprima.</span><span class="sxs-lookup"><span data-stu-id="2adda-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="2adda-108">Nella versione di anteprima, Cortana è supportata solo negli Stati Uniti con la lingua EN-US nei dispositivi che hanno collegato i microfoni di Rally.</span><span class="sxs-lookup"><span data-stu-id="2adda-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="2adda-109">L'assistenza vocale di Cortana nell'app Teams per dispositivi mobili, nelle sale di Microsoft Teams in Windows e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti di Microsoft 365 Enterprise di semplificare le attività di comunicazione, collaborazione e riunione usando il linguaggio naturale parlato.</span><span class="sxs-lookup"><span data-stu-id="2adda-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="2adda-110">Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando &#8220;Cortana&#8221; nella Microsoft Teams Room o quando si usa un display Di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2adda-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="2adda-111">Per connettersi rapidamente con il team a mani libere e in viaggio, gli utenti possono pronunciare query come &#8220;chiama Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;.</span><span class="sxs-lookup"><span data-stu-id="2adda-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="2adda-112">Gli utenti possono anche partecipare alle riunioni dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="2adda-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="2adda-113">Queste esperienze di assistenza vocale vengono recapitate usando servizi di livello [enterprise di Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) pienamente conformi alle promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni per i Servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="2adda-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="2adda-114">L'immagine mostra l'invio di una chat con Cortana su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="2adda-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![una sequenza di schermate per dispositivi mobili che mostrano una sessione di chat di Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="2adda-116">Controllo dell'amministratore e limitazioni</span><span class="sxs-lookup"><span data-stu-id="2adda-116">Admin control and limitations</span></span>

<span data-ttu-id="2adda-117">L'assistenza vocale di Cortana in Teams viene recapitata usando servizi pienamente conformi alle promesse di privacy, sicurezza e conformità a livello aziendale di Office 365, come illustrato nelle Condizioni per i Servizi online (OST).</span><span class="sxs-lookup"><span data-stu-id="2adda-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="2adda-118">La caratteristica verrà abilitata per impostazione predefinita per i tenant.</span><span class="sxs-lookup"><span data-stu-id="2adda-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="2adda-119">Gli amministratori tenant possono controllare chi nel tenant può usare l'assistenza vocale di Cortana in Teams usando un criterio (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="2adda-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="2adda-120">Questo criterio può essere impostato a livello di account utente o di tenant.</span><span class="sxs-lookup"><span data-stu-id="2adda-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="2adda-121">Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitata, abilitata solo con la chiamata del pulsante push o anche con la chiamata di wake word (applicabile ai dispositivi che la supportano, come la visualizzazione di Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="2adda-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="2adda-122">Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="2adda-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="2adda-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2adda-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2adda-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2adda-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2adda-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2adda-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2adda-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2adda-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2adda-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2adda-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="2adda-128">Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui l'assistenza vocale di Cortana in Microsoft Teams è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="2adda-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="2adda-129">Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione dell'assistenza vocale di Cortana in Microsoft Teams solo con la chiamata al pulsante push.</span><span class="sxs-lookup"><span data-stu-id="2adda-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="2adda-130">Gli utenti potranno richiamare Cortana selezionando il pulsante microfono di Cortana in Teams.</span><span class="sxs-lookup"><span data-stu-id="2adda-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="2adda-131">La chiamata di wake word (&#8220;Ehi Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="2adda-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="2adda-132">Questo esempio mostra l'aggiornamento dei criteri e l'abilitazione dell'assistenza vocale di Cortana sia con il pulsante push che con la chiamata della parola di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="2adda-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="2adda-133">Al momento del rilascio iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2adda-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="2adda-134">L'app Teams per dispositivi mobili non supporta l'attivazione delle parole di riattivazione, ma sarà supportata in futuro.</span><span class="sxs-lookup"><span data-stu-id="2adda-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="2adda-135">Microsoft Teams Rooms nei dispositivi di visualizzazione Windows e Microsoft Teams supporterà l'attivazione delle parole di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="2adda-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="2adda-136">Controllo utente</span><span class="sxs-lookup"><span data-stu-id="2adda-136">User control</span></span>

<span data-ttu-id="2adda-137">I singoli utenti possono provare l'assistenza vocale di Cortana in diversi dispositivi:</span><span class="sxs-lookup"><span data-stu-id="2adda-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="2adda-138">Seleziona il pulsante del microfono nell'app Teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2adda-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="2adda-139">Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="2adda-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="2adda-140">Pronuncia "Cortana" nei dispositivi di visualizzazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2adda-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="2adda-141">Puoi controllare se Cortana in Teams è abilitata per il tuo dispositivo usando un'impostazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2adda-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="2adda-142">App Teams per dispositivi mobili o visualizzazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2adda-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="2adda-143">Aprire l'app Teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2adda-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="2adda-144">Seleziona **Impostazioni**  >  **Cortana.**</span><span class="sxs-lookup"><span data-stu-id="2adda-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="2adda-145">Spostare l'interruttore **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="2adda-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="2adda-146">Visualizzazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2adda-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="2adda-147">Passare alla schermata ambiente (home) del display di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2adda-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="2adda-148">Selezionare l'avatar dell'utente e quindi **selezionare Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="2adda-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="2adda-149">Se Cortana è abilitata, pronuncia "Cortana, vai a Impostazioni".</span><span class="sxs-lookup"><span data-stu-id="2adda-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="2adda-150">Spostare l'interruttore **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="2adda-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="2adda-151">Microsoft Teams Rooms in Windows</span><span class="sxs-lookup"><span data-stu-id="2adda-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="2adda-152">Le modifiche a livello di dispositivo sono disponibili se Cortana è abilitata a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="2adda-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="2adda-153">Cortana verrà rilasciata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2adda-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="2adda-154">Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="2adda-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="2adda-155">Le modifiche a livello di riunione sono disponibili se Cortana è abilitata a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2adda-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="2adda-156">Per abilitare l'assistenza vocale di Cortana durante una riunione, sposta l'interruttore **Attivato** o **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="2adda-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="2adda-157">Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2adda-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>