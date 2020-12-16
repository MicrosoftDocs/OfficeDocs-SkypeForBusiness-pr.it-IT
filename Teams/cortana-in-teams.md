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
# <a name="cortana-voice-assistance-in-teams"></a>Assistenza vocale Cortana in teams

> [!Note]
> L'assistenza vocale di Cortana è supportata nelle app Microsoft teams per dispositivi mobili iOS e Android, nelle sale di Microsoft teams in Windows e in Microsoft teams, solo per gli utenti degli Stati Uniti. Attualmente non è disponibile per i tenant GCC, GCC-High, DoD e EDU. L'espansione in altre lingue e aree geografiche avverrà come parte delle versioni future.

> [!Note]
> Cortana Voice Assistance in Microsoft teams Rooms viene rilasciato in anteprima. Nella versione di anteprima, Cortana è supportato solo negli Stati Uniti con la lingua EN-US nei dispositivi con microfoni di Rally collegati.

Cortana Voice Assistance nell'app teams per dispositivi mobili, in Microsoft teams rooms in Windows e nei dispositivi di visualizzazione di Microsoft teams consente agli utenti di Microsoft 365 Enterprise di semplificare la comunicazione, la collaborazione e le attività correlate alla riunione usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono situato nell'angolo in alto a destra dell'app teams per dispositivi mobili o dicendo &#8220;Cortana&#8221; nella sala Microsoft teams o quando si usa una visualizzazione di Microsoft teams. Per comunicare rapidamente con il team in vivavoce e mentre si è in viaggio, gli utenti possono dire query come &#8220;chiamare Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;. Gli utenti possono partecipare alle riunioni anche dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono recapitate usando i [servizi di qualità aziendale di Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365, come indicato nelle [condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

L'immagine mostra l'invio di una chat tramite Cortana su un dispositivo mobile.

![una sequenza di schermate per dispositivi mobili che mostra una sessione di chat Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controllo di amministrazione e limitazioni

L'assistenza vocale di Cortana in teams viene recapitata con i servizi che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365 a livello aziendale, come indicato nei termini dei servizi online (OST). La caratteristica verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori del tenant possono controllare chi nel tenant può usare Cortana Voice Assistance in teams usando un criterio (TeamsCortanaPolicy). Questo criterio può essere impostato sia a livello di account utente che di livello di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato con la chiamata a pulsante solo, o anche con la chiamata di Word Wake (applicabile ai dispositivi che lo supportano, ad esempio Microsoft teams display).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

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

Al momento della versione iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese sono disponibili le funzioni seguenti:

- L'app teams per dispositivi mobili non supporta l'attivazione di Wake Word, ma sarà supportata in futuro.  

- Le sale di Microsoft Teams nei dispositivi di visualizzazione Windows e Microsoft teams supportano l'attivazione di Wake Word.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare Cortana Voice Assistance in dispositivi diversi:

- Selezionare il pulsante microfono nell'app teams per dispositivi mobili.

- Selezionare il pulsante del microfono o pronunciare "Cortana" nelle sale di Microsoft teams.

- Dire "Cortana" nei dispositivi di visualizzazione di Microsoft teams.

Puoi controllare se Cortana in teams è abilitato per il dispositivo usando un'impostazione nel dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>App teams per dispositivi mobili o visualizzazione Microsoft Teams

  1. Aprire l'app teams per dispositivi mobili.

  2. Selezionare **Impostazioni**  >  **Cortana**.

  3. Spostare l' **attiva o** **disattivata**.

### <a name="microsoft-teams-display"></a>Visualizzazione di Microsoft Teams

  1. Passare alla schermata ambiente (Home) della visualizzazione Microsoft teams.

  2. Selezionare l'avatar dell'utente e quindi selezionare **Impostazioni**. Se Cortana è abilitato, ad esempio, "Cortana, passa a impostazioni".

  3. Spostare l' **attiva o** **disattivata**.
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft teams rooms in Windows

Se Cortana è abilitato a livello di tenant, è possibile apportare modifiche a livello di dispositivo. Cortana verrà rilasciata per impostazione predefinita.

Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML di SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Se Cortana è abilitato a livello di dispositivo, è possibile apportare modifiche a livello di riunione.

Per abilitare l'assistenza **vocale di Cortana** durante una riunione, spostare l'attiva o **disattivata**. Al termine della riunione, Cortana torna al set di impostazioni del livello di dispositivo.
