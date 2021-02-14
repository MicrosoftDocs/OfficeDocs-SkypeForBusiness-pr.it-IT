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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Inviare agli utenti un messaggio di posta elettronica con le loro informazioni di audioconferenza su Skype for Business online.
ms.openlocfilehash: f2137d05ebe588a316704fabf4c8878910a40bc0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163899"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Inviare un messaggio di posta elettronica con le informazioni sulle audioconferenze a un utente in Skype for Business online

> [!Note]
> Per informazioni sull'invio di informazioni di Audioconferenza agli utenti su Microsoft Teams, consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza su Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

Sometimes Skype for Business users may need you to send them their Audio Conferencing information. You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user. When you send this email, it will contain all of the audio conferencing information, including:
  
- Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.
    
- L'ID conferenza dell'utente.
    
   
Ecco un esempio di messaggio di posta elettronica inviato:
  
![Posta elettronica di conferenza telefonica con accesso esterno](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**.

1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Accedi all'interfaccia di amministrazione > **Skype for Business** e, nella barra di spostamento sinistra, fai clic su **Audioconferenza.**
    
3. Fare **clic su** Utenti e quindi selezionare l'utente.
    
4. In the Action pane, click **Send conference info via email**.
    
> [!TIP]
> Puoi anche inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza modificando le proprietà dell'utente e facendo clic su **Invia** informazioni conferenza tramite  >  **posta elettronica.** 

## <a name="what-else-should-you-know-about-this-email"></a>Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Dopo aver abilitato i servizi di audioconferenza, agli utenti dell'organizzazione vengono inviati diversi messaggi di posta elettronica:
    
  - Quando una licenza di **Audioconferenza** viene loro assegnata.
    
  - Quando si reimposta manualmente il PIN dell'utente per i servizi di audioconferenza.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando una licenza di **Audioconferenza** è rimossa a loro.
    
  - Quando il provider dei servizi di audioconferenza per un utente viene modificato da Microsoft a un altro provider o **a Nessuno.**
    
  - Quando il provider di servizi di audioconferenza per un utente viene modificato in Microsoft.
    
- Per impostazione predefinita, il mittente dei messaggi verrà inviato da Microsoft 365 o Office 365, ma puoi modificare l'indirizzo e il nome visualizzato utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](https://go.microsoft.com/fwlink/?LinkId=708983) Per apportare modifiche all'indirizzo di posta elettronica che invia il messaggio agli utenti, è necessario:
    
  - Immettere l'indirizzo di posta elettronica nel parametro SendEmailFromAddress.
    
  - Imposta il parametro SendEmailOverride su True.
    
  - Immettere il nome visualizzato del messaggio di posta elettronica nel parametro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Per inviare un messaggio di posta elettronica con le informazioni per i servizi di audioconferenza, eseguire le operazioni seguenti:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Per quanto riguarda Windows PowerShell, Skype for Business online riguarda la gestione degli utenti e le operazioni che sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
