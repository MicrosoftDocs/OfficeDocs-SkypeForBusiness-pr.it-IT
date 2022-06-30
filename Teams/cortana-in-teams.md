---
title: Assistenza vocale di Cortana in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Scopri come usare l'assistenza vocale di Cortana con Teams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3c4ff65fb87bed077e1020764382314d5d15c62
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562435"
---
# <a name="cortana-voice-assistance-in-teams"></a>Assistenza vocale di Cortana in Teams

> [!NOTE]
> L'assistenza vocale di Cortana è supportata nelle app per dispositivi mobili Microsoft Teams per iOS e Android e negli schermi di Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia. Microsoft Teams Rooms in Windows è supportato solo per i dispositivi con impostazioni locali impostate su en-us. L'assistenza vocale di Cortana non è attualmente disponibile per i tenant GCC, GCC-High, DoD e EDU non statunitensi. L'assistenza vocale di Cortana nell'app Teams per dispositivi mobili è ora disponibile per i clienti EDU negli Stati Uniti. L'espansione di altre lingue e aree geografiche verrà eseguita nelle versioni future.

L'assistenza vocale di Cortana nell'app Teams per dispositivi mobili, nei Microsoft Teams Rooms in Windows e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti Microsoft 365 Enterprise di semplificare le attività di comunicazione, collaborazione e riunioni usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando "Cortana" in Microsoft Teams Room o quando usano uno schermo di Microsoft Teams. Per connettersi rapidamente con il team in vivavoce e quando si è in viaggio, gli utenti possono pronunciare query come "chiama Megan" o "inviare un messaggio alla riunione successiva". Gli utenti possono anche partecipare alle riunioni pronunciando "Partecipa alla riunione successiva" e usando l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono fornite tramite [servizi di livello aziendale di Cortana](/microsoft-365/admin/misc/cortana-integration) che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365, come indicato nelle [Condizioni per i servizi online](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true).

## <a name="admin-control-and-limitations"></a>Amministrazione controllo e limitazioni

L'assistenza vocale di Cortana in Teams viene fornita utilizzando servizi completamente conformi ai Office 365 promesse di privacy, sicurezza e conformità a livello aziendale, come indicato nelle Condizioni per i servizi online. La funzionalità verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori tenant possono controllare chi nel proprio tenant può usare l'assistenza vocale di Cortana in Teams usando un criterio (TeamsCortanaPolicy). Questo criterio è impostato a livello di account utente o di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitata, abilitata solo con la chiamata tramite pulsante di scelta rapida o anche con chiamata di parola di attivazione (applicabile ai dispositivi che la supportano, come la visualizzazione di Microsoft Teams).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con il nome "EmployeeCortanaPolicy" in cui l'assistenza vocale di Cortana in Microsoft Teams è disabilitata.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio mostra l'aggiornamento di un criterio esistente con il nome "EmployeeCortanaPolicy" e l'abilitazione dell'assistenza vocale di Cortana in Microsoft Teams solo con la chiamata tramite pulsante push. Gli utenti potranno richiamare Cortana selezionando il pulsante del microfono di Cortana in Teams. La chiamata alla parola di attivazione ("Ehi Cortana" o "Cortana") verrà disabilitata.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio mostra l'aggiornamento dei criteri e l'abilitazione dell'assistenza vocale di Cortana sia con il pulsante di scelta rapida che con la chiamata di parola di attivazione.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Al momento, della versione iniziale per Microsoft 365 Enterprise utenti negli Stati Uniti in inglese, sono disponibili le seguenti funzioni:

- L'app Teams per dispositivi mobili non supporta l'attivazione delle parole di attivazione, ma sarà supportata in futuro.

- Microsoft Teams Rooms nei dispositivi di visualizzazione Windows e Microsoft Teams supporteranno l'attivazione di parole di attivazione.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare l'assistenza vocale di Cortana in dispositivi diversi:

- Selezionare il pulsante del microfono nell'app Teams per dispositivi mobili.

- Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.

- Pronuncia "Cortana" in Microsoft Teams visualizza i dispositivi.

Puoi controllare se Cortana in Teams è abilitata per il tuo dispositivo utilizzando un'impostazione nel dispositivo.

![mostra la progressione delle finestre per dispositivi mobili quando abiliti Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams Rooms in Windows

Apportare modifiche a livello di dispositivo è disponibile solo se Cortana è abilitata a livello di tenant.

A livello di dispositivo, puoi configurare Cortana per l'uso in due modi diversi. È possibile abilitare entrambe le opzioni o entrambe contemporaneamente:

- Toccando un microfono, che si chiama _Cortana Push per parlare_
- Pronunciando "Ehi Cortana", che si chiama _Attivazione vocale di Cortana_

_Il push per parlare_ di Cortana è abilitato per impostazione predefinita se la chat room è configurata con una delle lingue seguenti: en-au (Australia), en-ca (Canada), en-gb (Regno Unito), en-in (India), en-us (Stati Uniti). [Ulteriori informazioni.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) L'icona di Cortana sposterà il pulsante _Presenta_ nel menu _Altro..._ nella console della sala riunioni di Teams. Per disabilitare Cortana _Push per parlare_ , usa PowerShell. [Ulteriori informazioni.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Per abilitare _l'attivazione vocale_ di Cortana, queste condizioni devono essere soddisfatte:

- un dispositivo certificato per Cortana deve essere connesso a Teams Room. È possibile trovare un elenco di dispositivi certificati alla fine di questo articolo.
- Teams Room deve essere configurato con una delle seguenti lingue: en-au (Australia), en-ca (Canada), en-gb (Regno Unito), en-in (India), en-us (Stati Uniti). Altre lingue saranno disponibili in un secondo momento.
- è necessario apportare una delle seguenti modifiche alla configurazione:
  - attivare la funzionalità nell'interfaccia di amministrazione di Teams [Altre informazioni.](/microsoftteams/rooms/rooms-manage)
  - aggiungere il seguente attributo XML al file XML SkypeSettings:

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

A livello di riunione, apportare modifiche è disponibile solo se _l'attivazione vocale_ di Cortana è abilitata a livello di dispositivo.  Per abilitare _l'attivazione vocale_ di Cortana durante una riunione, spostare l'interruttore **su Attivato** o **Disattivato** per disabilitarlo. Al termine della riunione, Cortana torna alle impostazioni del livello del dispositivo impostate.

Apportare modifiche a livello di riunione è disponibile se Cortana è abilitata a livello di dispositivo.

Per abilitare _l'attivazione vocale_ di Cortana durante una riunione, sposta l'interruttore **su Attivato** o **Disattivato**. Al termine della riunione, Cortana torna alle impostazioni del livello del dispositivo impostate.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Dispositivi certificati Cortana per Teams Rooms

_L'attivazione vocale_ di Cortana può essere abilitata se si utilizza un Lenovo Hub 500 o se uno di questi dispositivi è connesso alla chat room:

- Jabra Panacast 50
- Microfoni da rally
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
