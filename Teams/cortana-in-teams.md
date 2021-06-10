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
# <a name="cortana-voice-assistance-in-teams"></a>Assistenza vocale di Cortana in Teams

> [!Note]
> L'assistenza vocale di Cortana è supportata nelle app Microsoft Teams per dispositivi mobili iOS e Android e nei display Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia.  Microsoft Teams Rooms in Windows è supportato solo per gli utenti negli Stati Uniti. L'assistenza vocale di Cortana non è attualmente disponibile per i tenant GCC, GCC-High, DoD, EDU. L'espansione in altre lingue e aree geografiche avverrà nell'ambito dei rilasci futuri.

> [!Note]
> L'assistenza vocale di Cortana in Microsoft Teams Room viene rilasciata in Anteprima. Nella versione di anteprima, Cortana è supportata solo negli Stati Uniti con la lingua EN-US nei dispositivi che hanno collegato i microfoni di Rally.

L'assistenza vocale di Cortana nell'app Teams per dispositivi mobili, in Microsoft Teams Rooms in Windows e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti di Microsoft 365 Enterprise di semplificare le comunicazioni, la collaborazione e le attività correlate alle riunioni usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando &#8220;Cortana&#8221; nella sala Microsoft Teams o usando un display Microsoft Teams. Per connettersi rapidamente con il team a mani libere e in viaggio, gli utenti possono pronunciare query come &#8220;chiama Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;. Gli utenti possono anche partecipare alle riunioni dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono recapitate usando servizi di livello enterprise [di Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) pienamente conformi alle promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni per i Servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

L'immagine mostra l'invio di una chat con Cortana su un dispositivo mobile.

![una sequenza di schermate per dispositivi mobili che mostrano una sessione di chat di Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Controllo dell'amministratore e limitazioni

L'assistenza vocale di Cortana in Teams viene recapitata usando servizi pienamente conformi alle promesse di privacy, sicurezza e conformità a livello aziendale di Office 365, come illustrato nelle Condizioni per i Servizi online (OST). La caratteristica verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori tenant possono controllare chi nel tenant può usare l'assistenza vocale di Cortana in Teams usando un criterio (TeamsCortanaPolicy). Questo criterio può essere impostato a livello di account utente o di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitata, abilitata solo con la chiamata del pulsante push o anche con la chiamata della parola di riattivazione (applicabile ai dispositivi che la supportano, come lo schermo Microsoft Teams).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui l'assistenza vocale di Cortana in Microsoft Teams è disabilitata.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione dell'assistenza vocale di Cortana in Microsoft Teams solo con la chiamata al pulsante push. Gli utenti potranno richiamare Cortana selezionando il pulsante del microfono di Cortana in Teams. La chiamata di wake word (&#8220;Ehi Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio mostra l'aggiornamento dei criteri e l'abilitazione dell'assistenza vocale di Cortana sia con il pulsante push che con la chiamata della parola di riattivazione.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Al momento del rilascio iniziale per Microsoft 365 Enterprise utenti negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:

- L Teams app per dispositivi mobili non supporta l'attivazione delle parole di riattivazione, ma sarà supportata in futuro.  

- Microsoft Teams Rooms nei dispositivi Windows e Microsoft Teams display supportano l'attivazione delle parole di riattivazione.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare l'assistenza vocale di Cortana in diversi dispositivi:

- Seleziona il pulsante del microfono nell'app Teams per dispositivi mobili.

- Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.

- Pronuncia "Cortana" nei Microsoft Teams display.

Puoi controllare se Cortana in Teams è abilitata per il tuo dispositivo usando un'impostazione nel dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams'app per dispositivi mobili o Microsoft Teams schermo

  1. Aprire l'Teams per dispositivi mobili.

  2. Seleziona **Impostazioni**  >  **Cortana.**

  3. Spostare l'interruttore **Attivato** o **Disattivato**.

### <a name="microsoft-teams-display"></a>Microsoft Teams schermo

  1. Passare alla schermata ambiente (home) del Microsoft Teams schermo.

  2. Selezionare l'avatar dell'utente e quindi selezionare **Impostazioni**. Se Cortana è abilitata, pronuncia "Cortana, vai a Impostazioni".

  3. Spostare l'interruttore **Attivato** o **Disattivato**.
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams Rooms in Windows

Le modifiche a livello di dispositivo sono disponibili se Cortana è abilitata a livello di tenant. Cortana verrà rilasciata per impostazione predefinita.

Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Le modifiche a livello di riunione sono disponibili se Cortana è abilitata a livello di dispositivo.

Per abilitare l'assistenza vocale di Cortana durante una riunione, sposta l'interruttore **Attivato** o **Disattivato.** Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.
