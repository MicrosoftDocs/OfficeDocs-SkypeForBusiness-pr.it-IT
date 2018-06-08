---
title: Messaggi di posta elettronica inviati agli utenti quando le relative impostazioni di modifica
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Informazioni su quali informazioni automaticamente agli utenti viene inviato tramite posta elettronica quando modificano le impostazioni di conferenza telefonica. '
ms.openlocfilehash: 4766f8f236cbe94b11660165b8659a892d301285
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703435"
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>Messaggi di posta elettronica inviati agli utenti quando le relative impostazioni di modifica

Messaggi di posta elettronica inviati automaticamente agli utenti che sono [abilitati per le conferenze Audio](set-up-audio-conferencing.md) tramite Microsoft come provider di servizi di conferenza audio.
  
Per impostazione predefinita, sono disponibili quattro tipi di posta elettronica inviato agli utenti abilitati per le audioconferenze. Tuttavia, se si desidera limitare il numero di messaggi di posta elettronica inviati a utenti, è possibile disattivarlo. Audioconferenze con accesso esterno in Office 365 invierà tramite posta elettronica per gli utenti quando della posta elettronica:
  
- **Una licenza di accesso esterno alle audioconferenze è assegnata ai ruoli o quando si passa il provider di servizi di conferenza audio a Microsoft.**
    
     Questo messaggio di posta elettronica include l'ID conferenza, il numero di telefono predefinito conferenza per le riunioni, conferenze audio PIN dell'utente e le istruzioni e collegamento da utilizzare il Skype per Business Online Meeting aggiornare strumento che consente di aggiornare riunioni esistenti per il utente. Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [Assegnare Microsoft come provider di servizi di conferenza audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Se l'organizzazione è stato abilitato per gli ID conferenza dinamico, tutte le riunioni dell'utente che si pianifica dovranno gli ID conferenza univoco. È possibile impostare [gli ID dinamici audioconferenze all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Verificare la licenza Skype per le aziende](../images/audio-conferencing-user-enabled.png)
  
    È possibile trovare ulteriori informazioni su Skype Business licenza visualizzando i [di licenza di componente aggiuntivo Business e i team di Microsoft Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Conferenza predefinito o ID conferenza numero di telefono delle modifiche utente.**
    
    Questo messaggio di posta elettronica contiene l'ID conferenza, numero di telefono di conferenza predefinito e le istruzioni e collegamento per l'utilizzo di Skype per Business Online Meeting aggiornare strumento che consente di aggiornare riunioni esistenti per l'utente. Ma questo messaggio di posta elettronica non include conferenza PIN dell'utente. Reimpostare il PIN dell'organizzatore della conferenza
    
    > [!NOTE]
    > Se l'organizzazione è stato abilitato per gli ID conferenza dinamico, tutte le riunioni dell'utente che si pianifica dovranno gli ID conferenza univoco. È possibile impostare [gli ID dinamici audioconferenze all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Informazioni sul componente aggiuntivo per conferenze sono state modificate.](../images/audio-conferencing-info-change.png)
  
- **Viene reimpostato il PIN di un utente di audioconferenza.**
    
    Questo messaggio di posta elettronica contiene audioconferenza dell'organizzatore PIN, l'ID conferenza esistente e numero di telefono di conferenza predefinito per l'utente. Vedere [reimpostare il PIN per conferenze Audio](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > Se l'organizzazione è stato abilitato per gli ID conferenza dinamico, tutte le riunioni dell'utente che si pianifica dovranno gli ID conferenza univoco. È possibile impostare [gli ID dinamici audioconferenze all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Componente aggiuntivo per conferenze PIN modificato.](../images/audio-conferencing-pin-has-changed.png)
  
- **Licenza dell'utente è stato rimosso o quando il provider di servizi di conferenza audio viene impostato da Microsoft altri provider o nessuno.**
    
    Si verifica quando la licenza di **Accesso esterno alle audioconferenze** viene rimosso da un utente o quando si modifica il provider di servizi di conferenza audio di un utente da Microsoft a un provider di servizi di conferenza audio di terze parti o quando si imposta il provider su **Nessuno**. Questo messaggio di posta elettronica contiene le istruzioni e informazioni relative all'utente di utilizzare Skype per strumento di aggiornamento riunione in linea aziendale per rimuovere informazioni specifiche di conferenze audio, ad esempio l'impostazione predefinita ID conferenza telefonica numero o alla conferenza.
    
    Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Di seguito è riportato un esempio di questo messaggio di posta elettronica:
    
     ![Componente aggiuntivo per conferenze sono disattivata.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Apportare modifiche ai messaggi di posta elettronica inviati a tali

È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato è inclusa nelle informazioni sul contatti *da* . Per impostazione predefinita, il mittente dei messaggi di posta elettronica saranno da Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:
  
- Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.
    
- Il parametro _SendEmailOverride_ impostato su _True_.
    
È possibile apportare modifiche al messaggio di posta elettronica inviato a utenti, ad esempio l'indirizzo di posta elettronica inviato il messaggio di posta elettronica da e il nome visualizzato per la posta elettronica, eseguire:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Se si desidera modificare le informazioni sull'indirizzo di posta elettronica, è necessario assicurarsi che i criteri di posta elettronica in ingresso dell'ambiente di consentano i messaggi di posta elettronica che provengono da personalizzato specificato dall'indirizzo. Se si decide di sostituire le informazioni sul contatti *da* , è necessario verificare che i messaggi di posta elettronica viene inviati correttamente per gli utenti. È questo scopo, si verifica con un utente nell'organizzazione.
  
È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Che cosa accade se non si desidera posta elettronica da inviare loro?

Quando si disattiva invio messaggi di posta elettronica agli utenti, posta elettronica non verranno inviata anche quando un utente viene assegnato una licenza. In questo caso, l'ID conferenza, impostazione predefinita il numero di telefono per conferenze e, più importante, non verranno inviata le audioconferenze con accesso esterno PIN all'utente. In questo caso, è necessario che l'utente inviando un messaggio di posta elettronica separato o richiamando i.
  
Per impostazione predefinita, verranno inviati messaggi di posta elettronica per gli utenti, ma se si desidera impedire la ricezione posta elettronica per le conferenze audio, è possibile utilizzare Microsoft Teams, il Skype per Business admin center o Windows PowerShell. 

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica per gli utenti di modificare le relative impostazioni di connessione**.

4. Fai clic su **Salva**.
  
![30x30.png di logo sfb](../images/sfb-logo-30x30.png)  **utilizzando Skype per interfaccia di amministrazione di Business**
    
1. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
2. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**. 
    
3. Fai clic su **Salva**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Utilizzo di Windows PowerShell**
  
1. Eseguire le operazioni seguenti per disabilitare l'invio di tutti gli utenti di posta elettronica:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
## <a name="what-else-should-you-know-about-this-email"></a>Cos'altro occorre sapere su questo messaggio di posta elettronica?

- Per ulteriori in abilitazione e disabilitazione automaticamente l'invio di posta elettronica per gli utenti, vedere [abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- In alcuni casi utenti perderanno le informazioni sull'audio ed è necessario essere in grado di inviare loro tutte le informazioni sull'audio loro. Tale operazione può essere eseguita utilizzando il Skype per interfaccia di amministrazione di Business e facendo clic su **Invia informazioni conferenza tramite posta elettronica** in proprietà audioconferenze con accesso esterno di un utente. [Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md) Tuttavia, queste informazioni non includono il PIN per conferenze audio.
    
    Di seguito è riportato un esempio di questo messaggio di posta elettronica che verrà inviato a essi:
    
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
