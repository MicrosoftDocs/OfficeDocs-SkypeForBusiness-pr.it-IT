---
title: Inviare un messaggio di posta elettronica a un utente con le loro informazioni di accesso esterno
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Inviare agli utenti un messaggio di posta elettronica con le loro informazioni di audioconferenza.
ms.openlocfilehash: cb7aaa956b6a679b918603e2aef2ff15ff04a779
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio

In alcuni casi potrebbe essere necessario Skype per utenti Business o Teams Microsoft è possibile inviare loro le informazioni di conferenze Audio. È possibile farlo utilizzando **Skype per interfaccia di amministrazione di Business** e fare clic su **Invia informazioni conferenza tramite posta elettronica** nelle proprietà di un utente. Quando si invia il messaggio di posta elettronica, contiene tutte le informazioni di audioconferenza, tra cui:
  
- Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.
    
- L'ID conferenza dell'utente.
    
    > [!NOTE]
    > ID statico vengono utilizzati quando gli utenti dell'organizzazione non desiderano Memorizza numero casuale; possono selezionare un determinato numero o utilizzare una facile da ricordare. Quando vengono utilizzati gli ID conferenza dinamico, ogni riunione pianificazioni un utente verranno ottenere assegnato un ID conferenza univoco. Se si desidera assegnare dinamico anziché gli ID, [fare clic qui](using-audio-conferencing-dynamic-ids-in-your-organization.md)di conferenza statico. 
  
Di seguito è riportato un esempio di messaggio di posta elettronica inviati:
  
![Posta elettronica di conferenza telefonica con accesso esterno](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende**e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**e quindi selezionare l'utente.
    
4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
> [!TIP]
> È inoltre possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio per la modifica delle proprietà dell'utente e quindi fare clic su **servizi di conferenza Audio** > **inviare informazioni conferenza tramite posta elettronica**. 
  
## <a name="what-else-should-you-know-about-this-email"></a>Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che vengono abilitati per le conferenze audio:
    
  - Quando una licenza di **Conferenze Audio** viene assegnata loro.
    
  - Quando si reimposta manualmente conferenza PIN dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando una licenza di **Audioconferenza** è stata rimossa da essi.
    
  - Quando viene modificato il provider di servizi di conferenza audio di un utente da Microsoft a un altro provider o **Nessuno**.
    
  - Quando si modifica il provider di servizi di conferenza audio di un utente a Microsoft.
    
- Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:
    
  - Immettere l'indirizzo di posta elettronica nel parametro SendEmailFromAddress.
    
  - Impostare il parametro SendEmailOverride su True.
    
  - Immettere il nome visualizzato posta elettronica nel parametro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Per inviare un messaggio di posta elettronica all'utente con le loro informazioni di audioconferenze con accesso esterno, eseguire le operazioni seguenti:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)
