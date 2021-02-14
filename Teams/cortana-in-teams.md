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
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686442"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistenza vocale di Cortana in Teams

> [!Note]
> L'assistenza vocale di Cortana è supportata nelle app per dispositivi mobili Microsoft Teams per iOS e Android, nelle sale di Microsoft Teams in Windows e in Microsoft Teams visualizzate solo per gli utenti negli Stati Uniti. Al momento non è disponibile per i tenant GCC, GCC-High, DoD ed EDU. L'espansione in altre lingue e aree geografiche avverrà nelle versioni future.

> [!Note]
> L'assistenza vocale di Cortana nelle sale di Microsoft Teams viene rilasciata in Anteprima. Nella sua versione di anteprima, Cortana è supportata solo negli Stati Uniti con la lingua EN-US nei dispositivi che hanno collegati microfoni Per Questo.

L'assistenza vocale di Cortana nell'app Teams per dispositivi mobili, nelle sale di Microsoft Teams in Windows e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti di Microsoft 365 Enterprise di semplificare le comunicazioni, la collaborazione e le attività correlate alle riunioni utilizzando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app teams per dispositivi mobili oppure pronunciando &#8220;&#8221; Cortana nella sala di Microsoft Teams o usando una visualizzazione di Microsoft Teams. Per connettersi rapidamente con il proprio team senza usare le mani e mentre si è in viaggio, gli utenti possono dire query come &#8220;chiamare Megan&#8221; o &#8220;inviare un messaggio al&#8221; riunione successivo. Gli utenti possono anche partecipare alle riunioni dicendo &#8220;partecipare alla mia prossima riunione&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono offrite utilizzando servizi di livello aziendale di [Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) che sono completamente conformi alle disposizioni di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni dei servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

L'immagine mostra l'invio di una chat con Cortana su un dispositivo mobile.

![Sequenza di schermi di dispositivi mobili che mostrano una sessione di chat di Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controllo amministrativo e limitazioni

L'assistenza vocale di Cortana in Teams viene consegnata utilizzando servizi completamente conformi alle disposizioni di privacy, sicurezza e conformità di Office 365 a livello aziendale, come illustrato nelle Condizioni dei servizi online (OST). La funzionalità verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori del tenant possono controllare chi nel proprio tenant può usare l'assistenza vocale di Cortana in Teams usando un criterio (TeamsCortanaPolicy). Questo criterio può essere impostato a livello di account utente o di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitata, abilitata solo con la chiamata del pulsante push o anche con la chiamata alla parola di riattivazione (applicabile ai dispositivi che la supportano, come la visualizzazione di Microsoft Teams).

Gli amministratori possono usare i seguenti cmdlet di PowerShell per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui l'assistenza vocale di Cortana in Microsoft Teams è disabilitata.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione dell'assistenza vocale di Cortana in Microsoft Teams solo con la chiamata del pulsante push. Gli utenti potranno richiamare Cortana selezionando il pulsante del microfono di Cortana in Teams. La chiamata di Wake Word (&#8220;Ehi Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio mostra l'aggiornamento dei criteri e l'abilitazione dell'assistenza vocale di Cortana sia con il pulsante push che con la chiamata di riattivazione della parola.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Al momento del rilascio iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:

- L'app Teams per dispositivi mobili non supporta l'attivazione di parole di riattivazione, ma sarà supportata in futuro.  

- Le sale di Microsoft Teams nei dispositivi di visualizzazione Windows e Microsoft Teams supportano l'attivazione delle parole di riattivazione.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare l'assistenza vocale di Cortana in diversi dispositivi:

- Selezionare il pulsante del microfono nell'app Teams per dispositivi mobili.

- Selezionare il pulsante del microfono o pronunciare "Cortana" in Microsoft Teams Rooms.

- Pronuncia "Cortana" sui dispositivi di visualizzazione di Microsoft Teams.

Puoi controllare se Cortana in Teams è abilitata per il tuo dispositivo utilizzando un'impostazione nel dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>App Teams per dispositivi mobili o visualizzazione di Microsoft Teams

  1. Aprire l'app Teams per dispositivi mobili.

  2. Seleziona **Impostazioni**  >  **Cortana.**

  3. Spostare l'interruttore **su Attivato** o **Disattivato.**

### <a name="microsoft-teams-display"></a>Visualizzazione di Microsoft Teams

  1. Passare alla schermata ambiente (home) della visualizzazione di Microsoft Teams.

  2. Selezionare l'avatar dell'utente e quindi selezionare **Impostazioni.** Se Cortana è abilitata, pronuncia "Cortana, vai a Impostazioni".

  3. Spostare l'interruttore **su Attivato** o **Disattivato.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Sale di Microsoft Teams su Windows

Apportare modifiche a livello di dispositivo è disponibile se Cortana è abilitata a livello di tenant. Cortana verrà rilasciata per impostazione predefinita.

Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML Di SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Apportare modifiche a livello di riunione è disponibile se Cortana è abilitata a livello di dispositivo.

Per abilitare l'assistenza vocale di Cortana durante una riunione, attiva **o** disattiva **l'interruttore.** Al termine della riunione, Cortana torna alle impostazioni a livello di dispositivo.
