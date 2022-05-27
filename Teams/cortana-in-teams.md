---
title: Cortana assistenza vocale in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Scopri come usare l'assistenza vocale Cortana con Teams
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
ms.openlocfilehash: b79640b5f9d85b845c8d7c74fa1d6931931a6b50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674988"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana assistenza vocale in Teams

> [!NOTE]
> l'assistenza vocale di Cortana è supportata nelle app per dispositivi mobili Microsoft Teams per iOS e Android e gli schermi Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia. Microsoft Teams Rooms in Windows è supportato solo per i dispositivi con impostazioni locali impostate su en-us. Cortana l'assistenza vocale non è attualmente disponibile per i tenant di GCC, GCC-Alto, DoD e EDU non statunitensi. Cortana'assistenza vocale nell'app per dispositivi mobili Teams è ora disponibile per i clienti EDU negli Stati Uniti. L'espansione di altre lingue e aree geografiche verrà eseguita nelle versioni future.

Cortana l'assistenza vocale nell'app per dispositivi mobili Teams, nei Microsoft Teams Rooms nei Windows e nei dispositivi di visualizzazione Microsoft Teams consente di Microsoft 365 Enterprise  utenti per semplificare la comunicazione, la collaborazione e le attività correlate alle riunioni usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app per dispositivi mobili Teams oppure pronunciando "Cortana" nella sala Microsoft Teams o usando uno schermo Microsoft Teams. Per connettersi rapidamente con il team in vivavoce e quando si è in viaggio, gli utenti possono pronunciare query come "chiama Megan" o "inviare un messaggio alla riunione successiva". Gli utenti possono anche partecipare alle riunioni pronunciando "Partecipa alla riunione successiva" e usando l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono fornite utilizzando [Cortana servizi di livello aziendale](/microsoft-365/admin/misc/cortana-integration) che soddisfano pienamente le promesse di privacy, sicurezza e conformità di Office 365, come indicato nelle [Condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true).

## <a name="admin-control-and-limitations"></a>Amministrazione controllo e limitazioni

Cortana l'assistenza vocale in Teams viene fornita tramite servizi che soddisfano pienamente le Office 365 promesse di privacy, sicurezza e conformità a livello aziendale, come indicato nelle Condizioni dei servizi online. La funzionalità verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori tenant possono controllare chi nel proprio tenant può usare Cortana l'assistenza vocale in Teams usando un criterio (TeamsCortanaPolicy). Questo criterio è impostato a livello di account utente o di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitata, abilitata solo con la chiamata tramite pulsante di scelta rapida o anche con chiamata di parola di attivazione (applicabile anche ai dispositivi che la supportano, come la visualizzazione Microsoft Teams).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (attualmente i criteri non sono disponibili nell Microsoft Teams interfaccia di amministrazione).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con il nome "EmployeeCortanaPolicy" in cui Cortana'assistenza vocale in Microsoft Teams è disabilitata.

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio mostra l'aggiornamento di un criterio esistente con il nome "EmployeeCortanaPolicy" e l'abilitazione di Cortana l'assistenza vocale in Microsoft Teams solo con la chiamata a pulsante. Gli utenti potranno richiamare Cortana selezionando il pulsante Cortana microfono in Teams. La chiamata alla parola di attivazione ("Ehi Cortana" o "Cortana") verrà disabilitata.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio mostra l'aggiornamento dei criteri e l'abilitazione di Cortana l'assistenza vocale sia con il pulsante di scelta rapida che con la chiamata di parola di attivazione.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Al momento, della versione iniziale per Microsoft 365 Enterprise utenti negli Stati Uniti in inglese, sono disponibili le seguenti funzioni:

- L'app per dispositivi mobili Teams non supporta l'attivazione di word di attivazione, ma sarà supportata in futuro.

- Microsoft Teams Rooms nei dispositivi di visualizzazione Windows e Microsoft Teams supporteranno l'attivazione di word di attivazione.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare Cortana'assistenza vocale in dispositivi diversi:

- Seleziona il pulsante del microfono nell'app per dispositivi mobili Teams.

- Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.

- Pronuncia "Cortana" sui dispositivi Microsoft Teams display.

Puoi controllare se Cortana in Teams è abilitato per il tuo dispositivo utilizzando un'impostazione nel dispositivo.

![mostra la progressione delle finestre mobili quando si abilita Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams Rooms su Windows

Apportare modifiche a livello di dispositivo è disponibile solo se Cortana è abilitata a livello di tenant.

A livello di dispositivo, è possibile configurare Cortana da utilizzare in due modi diversi. È possibile abilitare entrambe le opzioni o entrambe contemporaneamente:

- Toccando un microfono, chiamato Cortana _Premi per parlare_
- Pronunciando "Ehi, Cortana", chiamato _Cortana Attivazione vocale_

Cortana _Push per parlare_ è abilitato per impostazione predefinita se la chat room è configurata con una delle lingue seguenti: en-au (Australia), en-ca (Canada), en-gb (Regno Unito), en-in (India), en-us (Stati Uniti). [Ulteriori informazioni.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana'icona sposterà il pulsante _Presenta_ nel menu _Altro..._ nella console della sala Teams. Per disabilitare Cortana _Push per parlare_, usare PowerShell.[ Ulteriori informazioni.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Per abilitare _Cortana'attivazione vocale_, è necessario soddisfare queste condizioni:

- un dispositivo certificato Cortana deve essere collegato alla Teams Room. È possibile trovare un elenco di dispositivi certificati alla fine di questo articolo.
- la Teams Room deve essere configurata con una delle lingue seguenti: en-au (Australia), en-ca (Canada), en-gb (Regno Unito), en-in (India), en-us (Stati Uniti). Altre lingue saranno disponibili in un secondo momento.
- è necessario apportare una delle seguenti modifiche alla configurazione:
  - attivare la caratteristica nell'interfaccia di amministrazione di Teams [Altre informazioni.](/microsoftteams/rooms/rooms-manage)
  - aggiungere il seguente attributo XML al file XML SkypeSettings:

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

A livello di riunione, apportare modifiche è disponibile solo se Cortana _l'attivazione vocale_ è abilitata a livello di dispositivo.  Per abilitare Cortana _attivazione vocale_ durante una riunione, spostare l'interruttore **su Attivato** o **Disattivato** per disabilitarlo. Al termine della riunione, Cortana torna al livello di dispositivo impostato.

Apportare modifiche a livello di riunione è disponibile se Cortana è abilitata a livello di dispositivo.

Per abilitare _Cortana'attivazione vocale_ durante una riunione, spostare l'interruttore **su Attivato** o **Disattivato**. Al termine della riunione, Cortana torna al livello di dispositivo impostato.

## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana dispositivi certificati per Teams Rooms

Cortana _l'attivazione vocale_ può essere abilitata se si utilizza un Lenovo Hub 500 o se uno di questi dispositivi è connesso alla chat room:

- Jabra Panacast 50
- Microfoni da rally
- Bose Video Bar VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech
