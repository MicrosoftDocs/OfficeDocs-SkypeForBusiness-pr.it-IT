---
title: Cortana'assistenza vocale in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Scopri come usare l'Cortana vocale con Teams
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
---

# <a name="cortana-voice-assistance-in-teams"></a>Cortana'assistenza vocale in Teams

> [!Note]
> Cortana l'assistenza vocale è supportata nelle app Microsoft Teams per dispositivi mobili iOS e Android e gli schermi Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia. Microsoft Teams Rooms in Windows è supportato solo per i dispositivi con impostazioni locali impostate su it-it. Cortana'assistenza vocale non è attualmente disponibile per GCC, GCC-High, DoD e tenant EDU non statunitensi. Cortana'assistenza vocale nell'app Teams per dispositivi mobili è ora disponibile per i clienti EDU negli Stati Uniti. L'espansione in altre lingue e aree geografiche avverrà nell'ambito dei rilasci futuri.


Cortana l'assistenza vocale nell'app Teams per dispositivi mobili, Microsoft Teams Rooms su Windows e nei dispositivi Microsoft Teams display Microsoft 365 Enterprise  per semplificare le comunicazioni, la collaborazione e le attività correlate alle riunioni usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando "Cortana" nella sala Microsoft Teams o usando un Microsoft Teams display. Per connettersi rapidamente con il team a mani libere e in viaggio, gli utenti possono pronunciare query come "chiama Megan" o "inviare un messaggio alla riunione successiva". Gli utenti possono anche partecipare alle riunioni pronunciando "Partecipa alla prossima riunione" e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono recapitate usando servizi [di](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) livello enterprise Cortana pienamente conformi alle promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni per i Servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Controllo dell'amministratore e limitazioni

Cortana'assistenza vocale in Teams viene fornito usando servizi pienamente conformi alle promesse di privacy, sicurezza e conformità a livello aziendale di Office 365, come illustrato nelle Condizioni per i Servizi online (OST). La caratteristica verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori tenant possono controllare chi nel proprio tenant può usare Cortana'assistenza vocale in Teams usando un criterio (TeamsCortanaPolicy). Questo criterio è impostato a livello di account utente o di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato solo con la chiamata al pulsante push o anche con la chiamata della parola di riattivazione (applicabile anche ai dispositivi che lo supportano, come lo schermo Microsoft Teams).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione Microsoft Teams di amministrazione).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con il nome "EmployeeCortanaPolicy" in cui Cortana'assistenza vocale in Microsoft Teams è disabilitata.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio mostra l'aggiornamento di un criterio esistente con il nome "EmployeeCortanaPolicy" e l'abilitazione dell'assistenza vocale Cortana in Microsoft Teams solo con la chiamata di un pulsante. Gli utenti potranno richiamare i Cortana selezionando il pulsante Cortana microfono in Teams. La chiamata wake word ("Ehi Cortana" o "Cortana") verrà disabilitata.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio mostra l'aggiornamento del criterio e l'abilitazione Cortana vocale con il pulsante push e la chiamata di parole di riattivazione.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Al momento del rilascio iniziale per Microsoft 365 Enterprise utenti negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:

- L Teams'app per dispositivi mobili non supporta l'attivazione di parole di riattivazione, ma sarà supportata in futuro.  

- Microsoft Teams Rooms nei dispositivi Windows e Microsoft Teams display supporteranno l'attivazione delle parole di riattivazione.

## <a name="user-control"></a>Controllo utente

I singoli utenti possono provare Cortana'assistenza vocale in dispositivi diversi:

- Seleziona il pulsante del microfono nell'app Teams per dispositivi mobili.

- Seleziona il pulsante del microfono o pronuncia "Cortana" in Microsoft Teams Rooms.

- Pronunciare "Cortana" su Microsoft Teams dispositivi.

È possibile controllare se Cortana in Teams è abilitato per il dispositivo usando un'impostazione nel dispositivo.

![mostra la progressione delle finestre per dispositivi mobili quando si abilita Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams Rooms in Windows

Le modifiche a livello di dispositivo sono disponibili solo se Cortana è abilitata a livello di tenant. 

A livello di dispositivo, è possibile configurare Cortana per l'uso in due modi diversi. È possibile abilitare una delle due opzioni o entrambe contemporaneamente: 
- Toccando un microfono, che si chiama Cortana _premere per parlare_
- Pronunciando "Ehi, Cortana", che si chiama Cortana _attivazione vocale_

Cortana Push _to talk_ è abilitato per impostazione predefinita se la chat room è impostata con una delle lingue seguenti: en-au (Australia), en-ca (Canada), en-gb (Regno Unito), en-in (India), en-us (Stati Uniti). [Ulteriori informazioni.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana'icona sposta il _pulsante Presenta_ sotto il _pulsante Altro..._ nella console Teams Room. Per disabilitare Cortana _push per parlare,_ usare PowerShell.[ Ulteriori informazioni.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Per abilitare _Cortana'attivazione vocale_, è necessario che siano soddisfatte le condizioni seguenti:
- un Cortana certificato deve essere connesso alla Teams room. È possibile trovare un elenco di dispositivi certificati alla fine di questo articolo.
- la Teams Room deve essere impostata con una delle lingue seguenti: en-au (Australia), en-ca (Canada), en-gb (Regno Unito), en-in (India), en-us (Stati Uniti). Altre lingue saranno disponibili in un secondo momento.
- è necessario apportare una delle modifiche di configurazione seguenti:
  - attivare la caratteristica nell'interfaccia Teams [altre informazioni.](/microsoftteams/rooms/rooms-manage)
  - aggiungere il seguente attributo XML al file XML SkypeSettings:

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
A livello di riunione, le modifiche sono disponibili solo se Cortana _l'attivazione vocale_ è abilitata a livello di dispositivo.  Per abilitare _Cortana'attivazione vocale durante_ una riunione, spostare l'interruttore **Attivato** o **Disattivato** per disabilitare. Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.


Le modifiche a livello di riunione sono disponibili se Cortana è abilitata a livello di dispositivo.

Per abilitare _Cortana'attivazione vocale_ durante una riunione, spostare l'interruttore **Attivato** o **Disattivato**. Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana dispositivi certificati per Teams Rooms
Cortana _l'attivazione_ vocale può essere abilitata se si usa un Hub 500 Di Lenovo o se si ha uno di questi dispositivi connessi alla chat room:
- Jabra Panacast 50 
- Microfoni da raduno
- Barra video Di Bose VB1

