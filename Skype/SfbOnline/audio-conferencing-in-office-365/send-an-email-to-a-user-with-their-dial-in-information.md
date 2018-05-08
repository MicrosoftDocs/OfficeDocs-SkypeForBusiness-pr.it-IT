---
title: Inviare un messaggio di posta elettronica a un utente con le loro informazioni di accesso esterno
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Inviare agli utenti un messaggio di posta elettronica con le loro informazioni di audioconferenza.
ms.openlocfilehash: da006b1e63dd36234acf20bb02fdffba2dc70fa2
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio

In alcuni casi potrebbe essere necessario Skype per utenti Business o Teams Microsoft è possibile inviare loro le informazioni di conferenze Audio. È possibile farlo utilizzando **Skype per interfaccia di amministrazione di Business** e fare clic su **Invia informazioni conferenza tramite posta elettronica** nelle proprietà di un utente. Quando si invia il messaggio di posta elettronica, contiene tutte le informazioni di audioconferenza, tra cui:
  
- Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.
    
- L'ID conferenza dell'utente.
    
   
Di seguito è riportato un esempio di messaggio di posta elettronica inviati:
  
![Posta elettronica di conferenza telefonica con accesso esterno](../images/audio-conferencing-info.png)
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-send-an-email-with-audio-conferencing-information-to-a-user"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png) Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende**e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**e quindi selezionare l'utente.
    
4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
> [!TIP]
> È inoltre possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio per la modifica delle proprietà dell'utente e quindi fare clic su **servizi di conferenza Audio** > **inviare informazioni conferenza tramite posta elettronica**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

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
