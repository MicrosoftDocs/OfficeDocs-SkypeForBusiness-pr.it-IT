---
title: Cortana'assistenza vocale in Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.openlocfilehash: c7659e7dba89c18b31f7bf111283da569591790b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858923"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana'assistenza vocale in Teams

> [!Note]
> Cortana'assistenza vocale è supportata nelle app per dispositivi mobili Microsoft Teams per iOS e Android e negli schermi Microsoft Teams per gli utenti di Stati Uniti, Regno Unito, Canada, India e Australia. Microsoft Teams Rooms in Windows è supportato solo per i dispositivi con impostazioni locali impostate su it-it. Cortana'assistenza vocale non è attualmente disponibile per GCC, GCC-High, DoD e tenant EDU non statunitensi. Cortana'assistenza vocale nell'app Teams per dispositivi mobili è ora disponibile per i clienti EDU negli Stati Uniti. L'espansione in altre lingue e aree geografiche avverrà nell'ambito dei rilasci futuri.


Cortana'assistenza vocale nell'app Teams per dispositivi mobili, in Microsoft Teams Rooms su Windows e nei dispositivi di visualizzazione Microsoft Teams consente agli utenti Microsoft 365 Enterprise di semplificare le comunicazioni, la collaborazione e attività correlate alle riunioni usando il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono nell'angolo in alto a destra dell'app Teams per dispositivi mobili o pronunciando &#8220;Cortana&#8221; nella sala Microsoft Teams o usando un Microsoft Teams display. Per connettersi rapidamente con il team senza mani e mentre sono in viaggio, gli utenti possono pronunciare query come &#8220;chiama Megan&#8221; o &#8220;inviare un messaggio alla riunione successiva&#8221;. Gli utenti possono anche partecipare alle riunioni dicendo &#8220;partecipare alla riunione successiva&#8221; e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono recapitate usando servizi [di](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) livello enterprise Cortana pienamente conformi alle promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni per i Servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Controllo dell'amministratore e limitazioni

Cortana'assistenza vocale in Teams viene fornito usando servizi pienamente conformi alle promesse di privacy, sicurezza e conformità a livello aziendale di Office 365, come illustrato nelle Condizioni per i Servizi online (OST). La caratteristica verrà abilitata per impostazione predefinita per i tenant.

Gli amministratori del tenant possono controllare chi nel proprio tenant può usare Cortana'assistenza vocale Teams usando un criterio (TeamsCortanaPolicy). Questo criterio è impostato a livello di account utente o di tenant. Gli amministratori possono usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitato, abilitato solo con la chiamata al pulsante push o anche con la chiamata della parola di riattivazione (applicabile anche ai dispositivi che lo supportano, come lo schermo Microsoft Teams).

Gli amministratori possono usare i cmdlet di PowerShell seguenti per gestire questo criterio (il criterio non è attualmente disponibile nell'interfaccia di amministrazione di Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Ad esempio, il comando seguente crea un nuovo criterio con nome &#8220;EmployeeCortanaPolicy&#8221; in cui Cortana assistenza vocale in Microsoft Teams è disabilitata.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

Questo esempio mostra l'aggiornamento di un criterio esistente con nome &#8220;EmployeeCortanaPolicy&#8221; e l'abilitazione dell'assistenza vocale Cortana Microsoft Teams solo con la chiamata di un pulsante. Gli utenti potranno richiamare il Cortana selezionando il pulsante Cortana microfono in Teams. La chiamata di wake word (&#8220;Hey Cortana&#8221; o &#8220;Cortana&#8221;) verrà disabilitata.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

Questo esempio mostra l'aggiornamento dei criteri e l'abilitazione Cortana l'assistenza vocale sia con il pulsante di pressione che con la chiamata della parola di riattivazione.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

Al momento del rilascio iniziale per gli utenti Microsoft 365 Enterprise negli Stati Uniti in inglese, sono disponibili le funzioni seguenti:

- L Teams app per dispositivi mobili non supporta l'attivazione delle parole di riattivazione, ma sarà supportata in futuro.  

- Microsoft Teams Rooms su Windows e Microsoft Teams display supporteranno l'attivazione delle parole di riattivazione.

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
- toccando un microfono, che si chiama Cortana _premere per parlare_
- pronunciando "Ehi, Cortana", che si chiama _Cortana attivazione vocale_

Cortana push _to talk_ è abilitato per impostazione predefinita se il dispositivo è configurato per l'uso delle impostazioni locali. [Ulteriori informazioni.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language)  Cortana'icona sposta il _pulsante_ Presenta sotto il _pulsante Altro..._ nella console Teams Room. Per disabilitare Cortana _push per parlare,_ usare PowerShell. [Altre informazioni.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Per abilitare Cortana _attivazione vocale,_ è necessario che siano soddisfatte le condizioni seguenti:
- un Cortana certificato deve essere connesso alla Teams room. È possibile trovare un elenco di dispositivi certificati alla fine di questo articolo.
- la Teams room deve essere impostata per l'uso delle impostazioni locali. Altre lingue saranno disponibili in un secondo momento.
- è necessario apportare una delle modifiche di configurazione seguenti:
  - attivare la caratteristica nell'interfaccia Teams [altre informazioni.](/microsoftteams/rooms/rooms-manage)
  - aggiungere il seguente attributo XML al file XML SkypeSettings:
```xml
<SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
</SkypeSettings> 
```
A livello di riunione, le modifiche sono disponibili solo se Cortana _l'attivazione vocale_ è abilitata a livello di dispositivo.  Per abilitare Cortana _attivazione vocale durante_ una riunione, spostare l'interruttore **Attivato** o **Disattivato** per disabilitare. Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.


Le modifiche a livello di riunione sono disponibili se Cortana è abilitata a livello di dispositivo.

Per abilitare _Cortana'attivazione vocale_ durante una riunione, spostare l'interruttore **Attivato** o **Disattivato.** Al termine della riunione, Cortana torna al set di impostazioni a livello di dispositivo.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana dispositivi certificati per Teams Rooms
Cortana'attivazione _vocale_ può essere abilitata se si usa un Hub 500 di Lenovo o se si ha uno di questi dispositivi connessi alla chat room:
- Jabra Panacast 50 
- Microfoni da raduno
- Barra video Di Bose VB1 __
