---
title: Avviare un'audioconferenza tramite telefono senza un PIN in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione dall'interfaccia di amministrazione di Skype for Business o utilizzando uno script di PowerShell. "
ms.openlocfilehash: 146a23c35bca8e313f193dbd1407990fc8c6a788
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "35535867"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Avviare un'audioconferenza tramite telefono senza un PIN in Skype for Business online

> [!Note]
> Per informazioni sull'avvio di un'audioconferenza senza un PIN in Microsoft Teams, consulta [Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Potrebbe essere frustrante per gli utenti che accedono a una riunione che si terrà nella sala di attesa della riunione che ascolta la musica perché l'organizzatore della riunione Skype for business non ha avviato la riunione. 
  
If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.
  
A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app. A PIN is only required when a meeting organizer joins their meeting over a phone. The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione
    
1. Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, passa a**utenti**di servizi di **audioconferenza** > . 
    
2. Nell'elenco selezionare l'utente e fare clic su **modifica**nel riquadro azioni. 
    
3. Nella pagina delle proprietà dell'utente, in **Opzioni riunione**selezionare o deselezionare **Consenti ai chiamanti non autenticati di essere i primi partecipanti a una riunione. In caso contrario, aspetterà nella sala di attesa finché non si unisce un utente autenticato**.
    
4. Fai clic su **Salva**. 


    
 **Tramite Windows PowerShell**
  
- Esegui il seguente comando: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

- Se si vuole reimpostare il PIN, vedere [reimpostare il pin per la conferenza audio](reset-the-audio-conferencing-pin.md).
    
- Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è disabilitato:
    
  - Se la riunione non è ancora iniziata (non c'è nessuno nella riunione): A un chiamante verrà richiesto se è l'organizzatore; Se dice sì, verrà richiesto il PIN e, dopo aver inserito il PIN, verrà avviata la riunione e l'utente parteciperà alla riunione.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
- Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è abilitato:
    
  - If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.
    
  - Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
