---
title: Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti quando cambiano le impostazioni, quali ad esempio le modifiche del pin o del numero predefinito della conferenza. "
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164265"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online

> [!Note]
> Se si desidera abilitare o disabilitare l'invio di messaggi di posta elettronica in Microsoft Teams, consulta [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.
  
Se disabiliti l'invio di e-mail, i messaggi e-mail per i servizi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi e-mail relativi all'attivazione o alla disattivazione dei servizi di audioconferenza, alla reimpostazione del PIN e alla modifica dell'ID conferenza e del numero di telefono predefinito per la conferenza.
  
Ecco un esempio di messaggio di posta elettronica che viene inviato agli utenti quando sono abilitati per le audioconferenze:
  
![Posta elettronica per Audioconferenza](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>I messaggi di posta elettronica quando vengono inviati agli utenti?

- Dopo aver abilitato i servizi di audioconferenza, agli utenti dell'organizzazione vengono inviati diversi messaggi di posta elettronica:
    
  - Quando una licenza di **Audioconferenza** viene assegnata a loro.
    
  - Quando si reimposta manualmente il PIN dell'utente per i servizi di audioconferenza.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando la licenza di **Audioconferenza** viene loro rimossa.
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **nessuno.**
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Abilitare o disabilitare l'invio di posta elettronica agli utenti

Puoi utilizzare l'interfaccia di amministrazione di Skype for Business Windows PowerShell per abilitare o disabilitare la posta elettronica inviata agli utenti.

 
![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**
    
1. **Nell'interfaccia di amministrazione di Skype for Business,** nella barra di spostamento sinistra, fai clic su **Audioconferenza.**
    
2. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.
    
3. Fare clic su **Salva**.
    
    > [!TIP]
    > You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Uso Windows PowerShell**
  
- Esegui il seguente comando per disabilitare l'invio di messaggi di posta elettronica: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Per assistenza su questo cmdlet, vedi [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

- When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.
    
- L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell riguarda la gestione degli utenti e le operazioni che sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[E-mail inviate agli utenti in caso di modifica delle impostazioni per i servizi di audioconferenza](emails-sent-to-users-when-their-settings-change.md)

[Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md)


