---
title: Avviare una conferenza Audio nel telefono senza un PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: c77921af87cab23b475c31205da4661755c56961
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>Avviare una conferenza Audio nel telefono senza un PIN

Può essere frustrante per gli utenti che accedono a una riunione per essere contenute nella sala d'attesa della riunione la musica di attesa perché Skype per Business o Microsoft Teams organizzatore della riunione non ha avviato la riunione. 
  
Se un organizzatore della riunione chiama alla riunione, per impostazione predefinita, è necessario un PIN per avviare una riunione. È possibile configurarlo in modo che tutti gli utenti possono connettersi a una riunione e non richiesto di immettere un PIN avviare la riunione. Per abilitare o disabilitare questa impostazione per un singolo utente, è possibile utilizzare Skype per interfaccia di amministrazione di Business.
  
Se un utente ha avviato la riunione da Skype per applicazioni aziendali o Teams Microsoft non è necessario per l'organizzatore della riunione un PIN. Un PIN è solo necessario quando l'organizzatore della riunione si unisce a loro riunione tramite un telefono. Il PIN per le riunioni viene inviato all'utente audio quando viene assegnati alla licenza di **Accesso esterno alle audioconferenze** e abilitati per le conferenze Audio. Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) e [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**. 
    
4. Nell'elenco, selezionare l'utente e nel riquadro azioni fare clic su **Modifica**. 
    
5. Nella pagina proprietà dell'utente, in **Opzioni riunione**, selezionare o deselezionare i chiamanti Consenti non autenticato **diventi il prima persone a una riunione. Se non, quindi si attenderà nella sala di attesa fino a quando non si unisce a un utente autenticato**.
    
6. Fare clic su **Salva**. 
    
 **Per abilitare o disabilitare i chiamanti anonimi per tutte le riunioni dell'utente tramite Windows Powershell**
  
- Esegui il seguente comando: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

- Se desideri reimpostare il PIN, vedi [Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Se è abilitato l'accesso anonimo o che non richiede un PIN avviare una riunione:
    
  - Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante viene richiesto se è l'organizzatore; Se afferma Sì, verrà richiesto per il PIN e dopo, inserisce il PIN, di inizio della riunione e l'utente verrà partecipare alla riunione.
    
  - Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se è l'organizzatore e mai, verrà richiesto per il PIN; la riunione è già stata avviata e il chiamante verrà accedervi.
    
- Se l'accesso anonimo o che non richiede un PIN avviare una riunione è disabilitato:
    
  - Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN. Poiché l'impostazione dell'organizzatore viene impostato su off, di inizio della riunione e i chiamanti anonimi verranno aggiunto alla riunione.
    
  - Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN, la riunione è già stata avviata e il chiamante verrà accedervi.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)
