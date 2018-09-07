---
title: Inviare un messaggio di posta elettronica a un utente con Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Inviare agli utenti un messaggio di posta elettronica con le loro informazioni di audioconferenza su Skype for Business online.
ms.openlocfilehash: 7b32608eae4fa5bb0d7f5b1eafbf49825ee937ad
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849976"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza in Skype for Business online

> [!Note]
> Per informazioni sull'invio di informazioni di Audioconferenza agli utenti su Microsoft Teams, consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza su Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

In alcuni casi, potrebbe essere necessario inviare agli utenti di Skype for Business le informazioni di Audioconferenza. A tale scopo, puoi utilizzare l'**Interfaccia di amministrazione di Skype for Business** e fare clic su **Invia informazioni sulla conferenza tramite posta elettronica** nelle proprietà dell'utente. Quando invii questo messaggio di posta elettronica, esso contiene tutte le informazioni di Audioconferenza, tra cui:
  
- Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.
    
- L'ID conferenza dell'utente.
    
   
Di seguito è riportato un esempio di messaggio di posta elettronica inviato:
  
![Messaggio di posta elettronica sulla conferenza telefonica con accesso esterno](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

1. Nel riquadro di navigazione sinistro, fai clic su **Utenti** e quindi seleziona l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**.

1. Accedi a Office 365 con l'account aziendale o scolastico.
    
2. Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** e nel riquadro di navigazione sinistro fai clic su **Audioconferenza**.
    
3. Fai clic su **Utenti**e quindi seleziona l'utente.
    
4. Nel riquadro Azioni, fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
> [!TIP]
> È inoltre possibile inviare un messaggio di posta elettronica all'utente con le impostazioni di conferenza audio modificando le proprietà dell'utente e quindi facendo clic su **Audioconferenza** > **Inviare informazioni di conferenza tramite posta elettronica**. 

## <a name="what-else-should-you-know-about-this-email"></a>Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che essi vengono abilitati per le audioconferenze:
    
  - Quando una licenza di **Audioconferenza** viene loro assegnata.
    
  - Quando reimposti manualmente il PIN per audioconferenza dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando una licenza di **Audioconferenza** è rimossa a loro.
    
  - Quando il provider di servizi di audioconferenza per un utente passa da Microsoft a un altro provider o viene impostato su **Nessuno**.
    
  - Quando il provider di conferenza telefonica con accesso esterno per un utente diventa Microsoft.
    
- Per impostazione predefinita, il mittente dei messaggi di posta elettronica sarà Office 365, ma puoi modificare l'indirizzo di posta elettronica e il nome visualizzato utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983). Per apportare modifiche all'indirizzo di posta elettronica da cui viene inviato il messaggio agli utenti, procedi come segue:
    
  - Immetti l'indirizzo di posta elettronica nel parametro SendEmailFromAddress.
    
  - Imposta il parametro SendEmailOverride su True.
    
  - Inserisci il nome di posta elettronica visualizzato nel parametro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Per inviare un messaggio di posta elettronica con le informazioni conferenza telefonica con accesso esterno all'utente, procedi come segue:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché è importante utilizzare PowerShell di Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare Audioconferenza in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
