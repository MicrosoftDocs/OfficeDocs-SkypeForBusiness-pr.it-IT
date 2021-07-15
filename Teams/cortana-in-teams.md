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
# <a name="cortana-voice-assistance-in-teams"></a>Cortana'assistenza vocale in Teams

> [!Note]
> Cortana assistenza vocale è supportata nelle app Microsoft Teams per dispositivi mobili iOS e Android e nei display Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia. Microsoft Teams Rooms in Windows è supportato solo per gli utenti negli Stati Uniti. Cortana'assistenza vocale non è attualmente disponibile per i tenant GCC, GCC-High, DoD e EDU non statunitensi. Cortana'assistenza vocale nell'app Teams per dispositivi mobili è ora disponibile per i clienti EDU negli Stati Uniti. L'espansione in altre lingue e aree geografiche avverrà nell'ambito dei rilasci futuri.

> [!Note]
> Cortana'assistenza vocale in Microsoft Teams Rooms viene rilasciata in Anteprima. Nella versione di anteprima, Cortana è supportata solo negli Stati Uniti con lingua EN-US nei dispositivi che hanno collegato microfoni Da rally.

Cortana'assistenza vocale nell'app Teams per dispositivi mobili, in Microsoft Teams Rooms in Windows e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti di Microsoft 365 Enterprise di semplificare le comunicazioni, la collaborazione e le attività correlate alle riunioni usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando &#8220;Cortana&#8221; nella sala Microsoft Teams o usando un Microsoft Teams display. Per connettersi rapidamente con il team a mani libere e in viaggio, gli utenti possono pronunciare query come &#8220;chiama Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;. Gli utenti possono anche partecipare alle riunioni dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono recapitate usando servizi [di](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) livello enterprise Cortana pienamente conformi alle promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni per i Servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Controllo dell'amministratore e limitazioni

Cortana'assistenza vocale in Teams viene fornito usando servizi pienamente conformi alle promesse di privacy, sicurezza e conformità a livello aziendale di Office 365, come illustrato nelle Condizioni per i Servizi online (OST). La caratteristica verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori tenant possono controllare chi nel proprio tenant può usare Cortana'assistenza vocale in Teams usando un criterio (TeamsCortanaPolicy). Questo criterio è impostato a livello di account utente o di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato solo con la chiamata del pulsante push o anche con la chiamata della parola di riattivazione (applicabile anche ai dispositivi che lo supportano, come lo schermo Microsoft Teams).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui Cortana'assistenza vocale in Microsoft Teams è disabilitata.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione dell'assistenza vocale Cortana in Microsoft Teams solo con la chiamata di un pulsante. Gli utenti potranno richiamare il Cortana selezionando il pulsante Cortana microfono in Teams. La chiamata di wake word (&#8220;Hey Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio mostra come aggiornare i criteri e abilitare l'Cortana vocale con il pulsante di pressione e la chiamata della parola di riattivazione.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Al momento del rilascio iniziale per Microsoft 365 Enterprise utenti negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:

- L Teams app per dispositivi mobili non supporta l'attivazione delle parole di riattivazione, ma sarà supportata in futuro.  

- Microsoft Teams Rooms nei dispositivi Windows e Microsoft Teams display supportano l'attivazione delle parole di riattivazione.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare Cortana'assistenza vocale in dispositivi diversi:

- Seleziona il pulsante del microfono nell'app Teams per dispositivi mobili.

- Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.

- Pronunciare "Cortana" su Microsoft Teams dispositivi.

È possibile controllare se Cortana in Teams è abilitato per il dispositivo usando un'impostazione nel dispositivo.

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams Rooms in Windows

Le modifiche a livello di dispositivo sono disponibili se Cortana è abilitata a livello di tenant. Cortana verrà rilasciato per impostazione predefinita.

Per abilitare Cortana a livello di dispositivo, questi attributi XML devono essere aggiunti nel file XML SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Le modifiche a livello di riunione sono disponibili se Cortana è abilitata a livello di dispositivo.

Per abilitare l'Cortana vocale durante una riunione, spostare l'interruttore **Attivato** o **Disattivato.** Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.
