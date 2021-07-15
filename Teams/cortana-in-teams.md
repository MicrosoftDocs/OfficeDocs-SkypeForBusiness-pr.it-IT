---
title: Cortana'assistenza vocale in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Scopri come usare l'Cortana vocale con Teams
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
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428212"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="0d2a1-103">Cortana'assistenza vocale in Teams</span><span class="sxs-lookup"><span data-stu-id="0d2a1-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="0d2a1-104">Cortana assistenza vocale è supportata nelle app Microsoft Teams per dispositivi mobili iOS e Android e nei display Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="0d2a1-105">Microsoft Teams Rooms in Windows è supportato solo per gli utenti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="0d2a1-106">Cortana'assistenza vocale non è attualmente disponibile per i tenant GCC, GCC-High, DoD e EDU non statunitensi.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="0d2a1-107">Cortana'assistenza vocale nell'app Teams per dispositivi mobili è ora disponibile per i clienti EDU negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="0d2a1-108">L'espansione in altre lingue e aree geografiche avverrà nell'ambito dei rilasci futuri.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="0d2a1-109">Cortana'assistenza vocale in Microsoft Teams Rooms viene rilasciata in Anteprima.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="0d2a1-110">Nella versione di anteprima, Cortana è supportata solo negli Stati Uniti con lingua EN-US nei dispositivi che hanno collegato microfoni Da rally.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="0d2a1-111">Cortana'assistenza vocale nell'app Teams per dispositivi mobili, in Microsoft Teams Rooms in Windows e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti di Microsoft 365 Enterprise di semplificare le comunicazioni, la collaborazione e le attività correlate alle riunioni usando il linguaggio naturale parlato.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="0d2a1-112">Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando &#8220;Cortana&#8221; nella sala Microsoft Teams o usando un Microsoft Teams display.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="0d2a1-113">Per connettersi rapidamente con il team a mani libere e in viaggio, gli utenti possono pronunciare query come &#8220;chiama Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="0d2a1-114">Gli utenti possono anche partecipare alle riunioni dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="0d2a1-115">Queste esperienze di assistenza vocale vengono recapitate usando servizi [di](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) livello enterprise Cortana pienamente conformi alle promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni per i Servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="0d2a1-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

## <a name="admin-control-and-limitations"></a><span data-ttu-id="0d2a1-116">Controllo dell'amministratore e limitazioni</span><span class="sxs-lookup"><span data-stu-id="0d2a1-116">Admin control and limitations</span></span>

<span data-ttu-id="0d2a1-117">Cortana'assistenza vocale in Teams viene fornito usando servizi pienamente conformi alle promesse di privacy, sicurezza e conformità a livello aziendale di Office 365, come illustrato nelle Condizioni per i Servizi online (OST).</span><span class="sxs-lookup"><span data-stu-id="0d2a1-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="0d2a1-118">La caratteristica verrà abilitata per impostazione predefinita per i tenant.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="0d2a1-119">Gli amministratori tenant possono controllare chi nel proprio tenant può usare Cortana'assistenza vocale in Teams usando un criterio (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="0d2a1-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="0d2a1-120">Questo criterio è impostato a livello di account utente o di tenant.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-120">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="0d2a1-121">Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato solo con la chiamata del pulsante push o anche con la chiamata della parola di riattivazione (applicabile anche ai dispositivi che lo supportano, come lo schermo Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="0d2a1-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="0d2a1-122">Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="0d2a1-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="0d2a1-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="0d2a1-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="0d2a1-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="0d2a1-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="0d2a1-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="0d2a1-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="0d2a1-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="0d2a1-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="0d2a1-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="0d2a1-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="0d2a1-128">Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui Cortana'assistenza vocale in Microsoft Teams è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="0d2a1-129">Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione dell'assistenza vocale Cortana in Microsoft Teams solo con la chiamata di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="0d2a1-130">Gli utenti potranno richiamare il Cortana selezionando il pulsante Cortana microfono in Teams.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="0d2a1-131">La chiamata di wake word (&#8220;Hey Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="0d2a1-132">Questo esempio mostra come aggiornare i criteri e abilitare l'Cortana vocale con il pulsante di pressione e la chiamata della parola di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="0d2a1-133">Al momento del rilascio iniziale per Microsoft 365 Enterprise utenti negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d2a1-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="0d2a1-134">L Teams app per dispositivi mobili non supporta l'attivazione delle parole di riattivazione, ma sarà supportata in futuro.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="0d2a1-135">Microsoft Teams Rooms nei dispositivi Windows e Microsoft Teams display supportano l'attivazione delle parole di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="0d2a1-136">Controllo utente</span><span class="sxs-lookup"><span data-stu-id="0d2a1-136">User control</span></span>

<span data-ttu-id="0d2a1-137">I singoli utenti possono provare Cortana'assistenza vocale in dispositivi diversi:</span><span class="sxs-lookup"><span data-stu-id="0d2a1-137">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="0d2a1-138">Seleziona il pulsante del microfono nell'app Teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="0d2a1-139">Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="0d2a1-140">Pronunciare "Cortana" su Microsoft Teams dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-140">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="0d2a1-141">È possibile controllare se Cortana in Teams è abilitato per il dispositivo usando un'impostazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="0d2a1-142">Microsoft Teams Rooms in Windows</span><span class="sxs-lookup"><span data-stu-id="0d2a1-142">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="0d2a1-143">Le modifiche a livello di dispositivo sono disponibili se Cortana è abilitata a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-143">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="0d2a1-144">Cortana verrà rilasciato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-144">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="0d2a1-145">Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="0d2a1-145">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="0d2a1-146">Le modifiche a livello di riunione sono disponibili se Cortana è abilitata a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-146">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="0d2a1-147">Per abilitare l'Cortana vocale durante una riunione, spostare l'interruttore **Attivato** o **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0d2a1-147">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="0d2a1-148">Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d2a1-148">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
