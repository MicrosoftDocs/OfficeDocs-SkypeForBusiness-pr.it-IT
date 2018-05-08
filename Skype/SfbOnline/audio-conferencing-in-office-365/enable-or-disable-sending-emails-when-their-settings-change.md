---
title: Abilitare o disabilitare l'invio messaggi di posta elettronica quando le relative impostazioni di modifica
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: a588c5b425fe3d71ecd6d73193348b98e8e2f298
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Attivare o disattivare i messaggi di posta elettronica invio quando modificate le impostazioni di conferenze Audio

Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per le audioconferenze. È possibile che, tuttavia, se si desidera ridurre il numero di messaggi di posta elettronica inviati a Skype per utenti Business e Microsoft Teams. In tal caso, è possibile disabilitare l'invio di posta elettronica.
  
Se si disattiva invio messaggi di posta elettronica, messaggi di posta elettronica audioconferenze con accesso esterno non verranno inviate agli utenti, inclusi messaggi di posta elettronica per quando gli utenti sono abilitati o disattivati per le conferenze audio, quando viene reimpostato il proprio PIN e l'ID conferenza e i servizi di conferenza predefinito cambia il numero di telefono .
  
Di seguito è riportato un esempio di messaggio di posta elettronica inviato agli utenti quando vengono abilitati per le conferenze Audio:
  
![Posta elettronica per conferenze audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>I messaggi di posta elettronica quando vengono inviati agli utenti?

- Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che vengono abilitati per le conferenze audio:
    
  - Quando una licenza di **Conferenze Audio** viene assegnata loro.
    
  - Quando si reimposta manualmente conferenza PIN dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Se la licenza di **Conferenze Audio** viene rimosso da essi.
    
  - Quando viene modificato il provider di servizi di conferenza audio di un utente da Microsoft a un altro provider o **Nessuno**.
    
  - Quando si modifica il provider di servizi di conferenza audio di un utente a Microsoft.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Attivare o disattivare la posta elettronica non verrà inviato agli utenti

È possibile utilizzare Microsoft Teams, Skype per interfaccia di amministrazione di Business o Windows PowerShell per abilitare o disabilitare la posta elettronica inviato agli utenti.

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**
1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica per gli utenti di modificare le relative impostazioni di connessione**.

4. Fai clic su **Salva**.
  
![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
    
1. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistra fare clic su **audioconferenze**.
    
2. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.
    
3. Fai clic su **Salva**.
    
    > [!TIP]
    > È inoltre possibile inviare posta elettronica a un utente con le impostazioni di conferenza audio **all'audioconferenza** > **gli utenti**, selezionare l'utente e fare clic su **Invia informazioni conferenza tramite posta elettronica**.  In questo caso, verrà inviato un messaggio di posta elettronica che include solo ID conferenza e il numero di telefono di conferenza, ma non il PIN.  Per ulteriori informazioni, vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Utilizzo di Windows PowerShell**
  
- Eseguire il cmdlet seguente per disabilitare l'invio messaggi di posta elettronica: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Per assistenza per questo cmdlet, vedere [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

- Quando i messaggi di posta elettronica automatiche sono disabilitate, è possibile attivare ancora manualmente messaggio di posta elettronica con il numero di ID e il telefono di conferenza utilizzando il Skype per interfaccia di amministrazione di Business. Tuttavia, in tal caso, il PIN non sarà incluso. Se si desidera reimpostare il PIN di conferenza audio e l'invio di messaggi di posta elettronica è disattivato, sarà necessario inviarla all'utente in un altro modo.
    
- L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Messaggi di posta elettronica inviati agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md)

[Inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md)


