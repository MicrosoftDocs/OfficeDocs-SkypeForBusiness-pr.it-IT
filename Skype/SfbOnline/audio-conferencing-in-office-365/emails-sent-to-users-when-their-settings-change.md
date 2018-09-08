---
title: Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Scopri quali informazioni vengono inviate automaticamente agli utenti tramite posta elettronica quando modificano le impostazioni di conferenza telefonica in Skype for Business online. '
ms.openlocfilehash: 2ffe61d165b7cbfe6f91af9b819f892f88433724
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890427"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Skype for Business online

> [!Note]
> Se desideri informazioni relative alla posta elettronica automatica in Microsoft Teams, consulta[Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

I messaggi di posta elettronica vengono inviati automaticamente agli utenti che sono [abilitati per le audioconferenze](set-up-audio-conferencing.md) tramite Microsoft come provider di servizi di audioconferenza.
  
Per impostazione predefinita, sono disponibili quattro tipi di posta elettronica inviata agli utenti abilitati per le audioconferenze. Tuttavia, se desideri limitare il numero di messaggi di posta elettronica inviati agli utenti, puoi disabilitare l'opzione. Audioconferenza in Office 365 invierà posta elettronica agli utenti quando:
  
- **Viene assegnata loro una licenza di Audioconferenza o quando cambi il provider di audioconferenza e passi a Microsoft.**
    
     Questo messaggio di posta elettronica include l'ID conferenza, il numero di telefono predefinito per le riunioni, il PIN per le audioconferenze dell'utente e le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente. Consultare [Assegnare licenze Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [Assegnare Microsoft come provider di servizi di audioconferenza](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci. È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Verificare la licenza Skype for Business](../images/audio-conferencing-user-enabled.png)
  
    È possibile trovare ulteriori informazioni sulla licenza Skype for Business visualizzando [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **L'ID conferenza o il numero di telefono per le conferenze predefinito di un utente cambia.**
    
    Questo messaggio di posta elettronica contiene l'ID conferenza, il numero di telefono di conferenza predefinito, le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente. Tuttavia, questo messaggio di posta elettronica non include il PIN per l'audioconferenza dell'utente. Reimpostare il PIN dell'organizzatore della conferenza
    
    > [!NOTE]
    > Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci. È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Le informazioni sulle conferenze telefoniche sono state modificate.](../images/audio-conferencing-info-change.png)
  
- **Viene reimpostato il PIN di audioconferenza di un utente.**
    
    Questo messaggio di posta elettronica contiene il PIN di audioconferenza dell'organizzatore, l'ID conferenza esistente e il numero di telefono di conferenza predefinito per l'utente. Vedere [reimpostare il PIN per conferenze Audio](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci. È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![PIN di conferenza telefonica modificato.](../images/audio-conferencing-pin-has-changed.png)
  
- **Una licenza dell'utente è stata rimossa o quando il provider di servizi di audioconferenza viene modificato da Microsoft a altri provider o nessuno.**
    
    Si verifica quando la licenza di **Audioconferenza** viene rimossa da un utente o quando si modifica il provider di servizi di audioconferenza di un utente da Microsoft a un provider di servizi di audioconferenza di terze parti o quando si imposta il provider su **Nessuno**. Questo messaggio di posta elettronica contiene le istruzioni e informazioni che consentono all'utente di utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online per rimuovere informazioni specifiche di audioconferenze, ad esempio il numero di telefono di conferenza predefinito o l'ID conferenza.
    
    Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Conferenza telefonica disattivata.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Apportare modifiche ai messaggi di posta elettronica inviati

È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato è inclusa nelle informazioni sul contatti *da* . Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:
  
- Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.
    
- Il parametro _SendEmailOverride_ impostato su _True_.
    
È possibile apportare modifiche al messaggio di posta elettronica inviato a utenti, ad esempio l'indirizzo di posta elettronica inviato il messaggio di posta elettronica da e il nome visualizzato per la posta elettronica, eseguire:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Se si desidera modificare le informazioni sull'indirizzo di posta elettronica, è necessario assicurarsi che i criteri di posta elettronica in ingresso dell'ambiente di consentano i messaggi di posta elettronica che provengono da personalizzato specificato dall'indirizzo. Se decidi di sostituire le informazioni di contatto *Da*, devi verificare che i messaggi di posta elettronica vengano inviati correttamente agli utenti. Puoi farlo facendo un test con un utente della tua organizzazione.
  
È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se non vuoi che la posta elettronica venga inviata a loro?

Quando disattivi l'invio di messaggi di posta elettronica agli utenti, la posta elettronica non verrà inviata anche quando un utente riceve una licenza. In questo caso, l'ID conferenza, il numero di telefono per conferenze predefinito e, soprattutto, il PIN di audioconferenza non verranno inviati all'utente. In questo caso, devi informare l'utente inviandogli un messaggio di posta elettronica separato o chiamandolo.
  
Per impostazione predefinita, verranno inviati messaggi di posta elettronica agli utenti, ma se desideri impedire loro di ricevere posta elettronica per le audioconferenze, puoi utilizzare l'interfaccia di amministrazione di Skype for Business o Windows PowerShell. 
 
![30x30.png di logo sfb](../images/sfb-logo-30x30.png)  **utilizzando Skype per interfaccia di amministrazione di Business**
    
1. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
2. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**. 
    
3. Fai clic su **Salva**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Utilizzo di Windows PowerShell**
  
1. Esegui le operazioni seguenti per disabilitare l'invio di posta elettronica a tutti gli utenti:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
## <a name="what-else-should-you-know-about-this-email"></a>Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Per ulteriori informazioni su come abilitare e disabilitare automaticamente l'invio di posta elettronica agli utenti, consulta [Attivare o disattivare l'invio messaggi di posta elettronica quando le impostazioni di Audioconferenza vengono modificate](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- In alcuni casi, gli utenti perdono le informazioni audio e devi riuscire a inviare loro tutte le informazioni audio. Tale operazione può essere eseguita utilizzando il Skype per interfaccia di amministrazione di Business e facendo clic su **Invia informazioni conferenza tramite posta elettronica** in proprietà audioconferenze con accesso esterno di un utente. [Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md) Tuttavia, queste informazioni non includono il PIN di audioconferenza.
    
    Di seguito è riportato un esempio del messaggio di posta elettronica che verrà inviato:
    
     ![Posta elettronica di conferenza telefonica con accesso esterno](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
