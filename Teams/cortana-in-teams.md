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
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785390"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistenza vocale Cortana in teams

> [!Note]
> L'assistenza vocale di Cortana è supportata nelle app Microsoft teams per dispositivi mobili iOS e Android e in Microsoft teams, solo per gli utenti negli Stati Uniti. Attualmente non è disponibile per i tenant GCC, GCC-High, DoD e EDU. L'espansione in altre lingue e aree geografiche avverrà come parte delle versioni future.

Cortana Voice Assistance nell'app teams per dispositivi mobili e nei dispositivi di visualizzazione di Microsoft teams consente agli utenti di Microsoft 365 Enterprise di semplificare la comunicazione, la collaborazione e le attività correlate alla riunione usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono situato nell'angolo in alto a destra dell'app teams per dispositivi mobili o dicendo &#8220;Cortana&#8221; nella visualizzazione di Microsoft teams. Per comunicare rapidamente con il team in vivavoce e mentre si è in viaggio, gli utenti possono dire query come &#8220;chiamare Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;. Gli utenti possono partecipare alle riunioni anche dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono recapitate usando i [servizi di qualità aziendale di Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365, come indicato nelle [condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

L'immagine mostra l'invio di una chat tramite Cortana su un dispositivo mobile.

![Immagine mostra una sequenza di schermate per dispositivi mobili che mostra una sessione di chat Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controllo di amministrazione e limitazioni

L'assistenza vocale di Cortana in teams viene recapitata con i servizi che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365 a livello aziendale, come indicato nei termini dei servizi online (OST). La caratteristica verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori del tenant possono controllare chi nel tenant può usare Cortana Voice Assistance in teams usando un criterio (TeamsCortanaPolicy). Questo criterio può essere impostato sia a livello di account utente che di livello di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato solo con la chiamata a pulsante, o anche con la chiamata di Word Wake (applicabile ai dispositivi che lo supportano, ad esempio Microsoft teams display).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui l'assistenza vocale Cortana in Microsoft teams è disabilitata.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio Mostra come aggiornare un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e abilitare l'assistenza vocale Cortana in Microsoft teams con solo chiamata Push Button. Gli utenti saranno in grado di richiamare Cortana selezionando il pulsante mic Cortana in teams. Wake Word (&#8220;Hey Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio Mostra come aggiornare i criteri e abilitare l'assistenza vocale di Cortana sia con il pulsante push che con la chiamata di Word Wake.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> In occasione della versione iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese, l'app teams per dispositivi mobili non supporta l'attivazione di Wake Word, ma sarà supportata in futuro. L'attivazione di Word riattiva funzionerà sui dispositivi di visualizzazione di Microsoft teams alla versione iniziale.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare Cortana Voice Assistance nell'app teams per dispositivi mobili selezionando il pulsante microfono. Possono provare l'assistenza vocale di Cortana nei dispositivi di visualizzazione di Microsoft teams semplicemente dicendo &#8220;Cortana. &#8221; possono anche controllare se Cortana in teams è abilitato per il dispositivo usando un'impostazione nell'app teams per dispositivi mobili o nella visualizzazione di Microsoft teams.

1. Aprire l'app teams per dispositivi mobili oppure passare alla schermata ambiente (Home) della visualizzazione Microsoft teams.

2. Nell'app teams per dispositivi mobili passa a **Impostazioni** . Nella schermata Microsoft teams selezionare l'avatar utente e quindi selezionare impostazioni. Se Cortana è abilitato, ad esempio, &#8220;Cortana, passa a impostazioni. &#8221;

3. Selezionare **Cortana** .

4. Spostare il selettore **su** attivato o **disattivato** , a seconda che si voglia Cortana assistenza vocale nel dispositivo.
