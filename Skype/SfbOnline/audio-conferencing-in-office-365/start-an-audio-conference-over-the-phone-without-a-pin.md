---
title: Avviare una conferenza Audio nel telefono senza un PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 8abdd9bcd61c55c7d55d896feef36afed22b312f
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703475"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>Avviare una conferenza Audio nel telefono senza un PIN

Può essere frustrante per gli utenti che accedono a una riunione per essere contenute nella sala d'attesa della riunione la musica di attesa perché Skype per Business o Microsoft Teams organizzatore della riunione non ha avviato la riunione. 
  
Se un organizzatore della riunione chiama alla riunione, per impostazione predefinita, è necessario un PIN per avviare una riunione. È possibile configurarlo in modo che tutti gli utenti possono connettersi a una riunione e non richiesto di immettere un PIN avviare la riunione. Puoi usare l'interfaccia di amministrazione di Skype for Business per abilitare o disabilitare questa impostazione per un singolo utente.
  
Se un utente ha avviato la riunione da Skype per applicazioni aziendali o Teams Microsoft non è necessario per l'organizzatore della riunione un PIN. Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono. Il PIN per le riunioni viene inviato all'utente audio quando viene assegnati alla licenza di **Accesso esterno alle audioconferenze** e abilitati per le conferenze Audio. Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) e [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**. 

2. Selezionare un utente nell'elenco e quindi fare clic su **Modifica** nella parte superiore della pagina. 

3. Fare clic sul menu accanto a **Ponti di conferenza**e quindi fare clic su **Modifica**.

4. Nel riquadro dei **provider di ponte conferenza** , abilitare o disabilitare i chiamanti Consenti non autenticato **diventi il prima persone a una riunione. Se non, quindi si attenderà nella sala di attesa fino a quando non si unisce a un utente autenticato**.
    
4. Fare clic su **Applica**. 

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
    
1. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**. 
    
2. Nell'elenco, selezionare l'utente e nel riquadro azioni fare clic su **Modifica**. 
    
3. Nella pagina proprietà dell'utente, in **Opzioni riunione**, selezionare o deselezionare i chiamanti Consenti non autenticato **diventi il prima persone a una riunione. Se non, quindi si attenderà nella sala di attesa fino a quando non si unisce a un utente autenticato**.
    
4. Fai clic su **Salva**. 


    
 **Utilizzo di Windows Powershell**
  
- Esegui il seguente comando: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

- Se si desidera reimpostare il PIN, vedere [reimpostare il PIN per le conferenze Audio](reset-the-audio-conferencing-pin.md).
    
- Se è abilitato l'accesso anonimo o che non richiede un PIN avviare una riunione:
    
  - Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante viene richiesto se è l'organizzatore; Se afferma Sì, verrà richiesto per il PIN e dopo, inserisce il PIN, di inizio della riunione e l'utente verrà partecipare alla riunione.
    
  - Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se è l'organizzatore e mai, verrà richiesto per il PIN; la riunione è già stata avviata e il chiamante verrà accedervi.
    
- Se l'accesso anonimo o che non richiede un PIN avviare una riunione è disabilitato:
    
  - Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN. Poiché l'impostazione dell'organizzatore viene impostato su off, di inizio della riunione e i chiamanti anonimi verranno aggiunto alla riunione.
    
  - Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN, la riunione è già stata avviata e il chiamante verrà accedervi.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
