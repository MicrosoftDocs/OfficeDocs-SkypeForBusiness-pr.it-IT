---
title: Assistente vocale di Cortana in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Informazioni su come usare l'Assistente vocale di Cortana con teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f820bf6c44eae2cfbdb13a683d017be2f93d6756
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255550"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="cce18-103">Assistenza vocale Cortana in teams</span><span class="sxs-lookup"><span data-stu-id="cce18-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="cce18-104">L'assistenza vocale di Cortana è supportata nelle app Microsoft teams per dispositivi mobili iOS e Android solo per gli utenti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="cce18-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="cce18-105">Attualmente non è disponibile per i tenant GCC, GCC-High, DoD e EDU.</span><span class="sxs-lookup"><span data-stu-id="cce18-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="cce18-106">L'espansione in altre lingue e aree geografiche avverrà come parte delle versioni future.</span><span class="sxs-lookup"><span data-stu-id="cce18-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="cce18-107">Cortana Voice Assistance nell'app teams per dispositivi mobili consente agli utenti di Microsoft 365 Enterprise di semplificare la comunicazione, la collaborazione e le attività correlate alla riunione usando il linguaggio naturale parlato.</span><span class="sxs-lookup"><span data-stu-id="cce18-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="cce18-108">Gli utenti possono parlare con Cortana facendo clic sul pulsante del microfono situato nell'angolo in alto a destra dell'app teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="cce18-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="cce18-109">Per comunicare rapidamente con il proprio team mentre si è in viaggio, gli utenti possono pronunciare query come &#8220;chiamare Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;.</span><span class="sxs-lookup"><span data-stu-id="cce18-109">To quickly connect with their team while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="cce18-110">Gli utenti possono partecipare alle riunioni anche dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="cce18-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="cce18-111">Queste esperienze di assistenza vocale vengono recapitate usando i [servizi di qualità aziendale di Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365, come indicato nelle [condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="cce18-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="cce18-112">L'immagine mostra l'invio di una chat in Cortana su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="cce18-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![Immagine mostra una sequenza di schermate per dispositivi mobili che mostra una sessione di chat Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="cce18-114">Controllo di amministrazione e limitazioni</span><span class="sxs-lookup"><span data-stu-id="cce18-114">Admin control and Limitations</span></span>

<span data-ttu-id="cce18-115">L'assistenza vocale di Cortana in teams viene recapitata con i servizi che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365 a livello aziendale, come indicato nei termini dei servizi online (OST).</span><span class="sxs-lookup"><span data-stu-id="cce18-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="cce18-116">La caratteristica verrà abilitata per impostazione predefinita per i tenant.</span><span class="sxs-lookup"><span data-stu-id="cce18-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="cce18-117">Gli amministratori del tenant possono controllare chi nel tenant può usare Cortana Voice Assistance in teams usando un criterio (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="cce18-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="cce18-118">Questo criterio può essere impostato sia a livello di account utente che di livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="cce18-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="cce18-119">Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato solo con la chiamata a pulsante push o anche con la chiamata di Word Wake (applicabile ai dispositivi che lo supportano).</span><span class="sxs-lookup"><span data-stu-id="cce18-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="cce18-120">Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="cce18-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="cce18-121">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="cce18-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="cce18-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="cce18-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="cce18-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="cce18-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="cce18-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="cce18-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="cce18-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="cce18-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="cce18-126">Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui Cortana Voice Assistant in Microsoft teams è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="cce18-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="cce18-127">Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione di Cortana Voice Assistant in Microsoft teams con solo chiamata Push Button.</span><span class="sxs-lookup"><span data-stu-id="cce18-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="cce18-128">Gli utenti saranno in grado di richiamare Cortana toccando il pulsante mic Cortana in teams.</span><span class="sxs-lookup"><span data-stu-id="cce18-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="cce18-129">La chiamata di Wake Word (&#8220;Hey Cortana&#8221;) verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="cce18-129">Wake word (&#8220;Hey Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="cce18-130">Questo esempio Mostra come aggiornare i criteri e abilitare Cortana Voice Assistant sia con il pulsante push che con la chiamata di riattivazione.</span><span class="sxs-lookup"><span data-stu-id="cce18-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="cce18-131">In occasione della versione iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese, l'app teams per dispositivi mobili non supporta l'attivazione di Wake Word, ma sarà supportata in futuro.</span><span class="sxs-lookup"><span data-stu-id="cce18-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="cce18-132">Controllo utente</span><span class="sxs-lookup"><span data-stu-id="cce18-132">User control</span></span>

<span data-ttu-id="cce18-133">I singoli utenti possono provare Cortana Voice Assistance nell'app teams per dispositivi mobili facendo clic sul pulsante microfono.</span><span class="sxs-lookup"><span data-stu-id="cce18-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="cce18-134">Possono anche controllare se Cortana in teams è abilitato per il dispositivo usando un'impostazione nell'app teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="cce18-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="cce18-135">Aprire l'app teams per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="cce18-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="cce18-136">Accedere a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="cce18-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="cce18-137">Selezionare **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="cce18-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="cce18-138">Spostare il selettore **su** attivato o **disattivato**, a seconda che si voglia Cortana assistenza vocale nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cce18-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>
