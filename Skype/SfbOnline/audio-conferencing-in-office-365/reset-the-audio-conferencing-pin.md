---
title: Reimpostare il PIN in Skype per conferenze Audio per le aziende Online
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'Scoprire che cosa è necessario tenere conto PIN e come reimpostarle in Skype Business online. '
ms.openlocfilehash: 7e47f3e33dbb6811f5fabafc1ccd213f8e0bac11
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490606"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Reimpostare il PIN in Skype per conferenze Audio per le aziende Online

> [!Note]
> Per informazioni sulla reimpostazione pin di conferenza Audio in Teams Microsoft, vedere [reimpostare il PIN di conferenza Audio nel team di Microsoft](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Un PIN è un codice costituito da numeri che viene creati per ogni Skype per gli utenti aziendali sono abilitato per le conferenze audio. PIN di conferenza audio vengono utilizzati per gli organizzatori delle riunioni per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono. Se si utilizza Skype per applicazioni aziendali per avviare la riunione, un PIN non è obbligatorio. Se gli utenti dimenticano il PIN e non possono trovare la posta elettronica che è stato inviato a tali quando sono stati abilitati per le conferenze audio, un amministratore può reimpostare il PIN o è possibile reimpostare i propri PIN.
  
È possibile avviare riunioni quando si unisce a un utente autenticato tramite il Skype per applicazioni aziendali o quando l'organizzatore accede a con il proprio PIN nel telefono. Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.
  
## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende**e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**, selezionare l'utente che si desidera reimpostare il PIN per.
    
4. Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Dispongono di un utente reimpostare il proprio PIN

Un utente può reimpostare un PIN utilizzando l'opzione **Reimposta PIN** nella pagina **conferenza telefonica** . In questa pagina è possibile accedere in uno dei tre modi:

* In un browser, accedere a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Skype per le aziende, fare clic sulla freccia **Mostra Menu** accanto al pulsante **Opzioni**e quindi fare clic su **Strumenti di** > **Le impostazioni di conferenza telefonica**.
* In Skype per le aziende, fare clic su **Opzioni**, fare clic su **Inoltro di chiamata** nel menu a sinistra e quindi nella sezione **Altre impostazioni di chiamata** , fare clic su **Modifica impostazioni online**. 

## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, alla reimpostazione del PIN. Dopo il PIN è stato ripristinato da un amministratore, il PIN verrà elencato come * * * in **Skype per interfaccia di amministrazione di Business** e i risultati quando si utilizza Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Invio automatico di messaggi di posta elettronica agli utenti è abilitata per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN. Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN a un utente e sarà necessario inviare manualmente le informazioni sul PIN all'utente.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita è non consentire una riunione di avvio per i chiamanti anonimi.
    
- Quando si attiva un utente per le conferenze audio, per impostazione predefinita vengono inviati i messaggi di posta elettronica che includono informazioni sulle conferenze e il proprio PIN. L'utente deve disporre di una cassetta postale Office 365, perché quando viene reimpostato un PIN, un nuovo PIN verrà inviato all'utente di posta elettronica per il proprio indirizzo SMTP principale (alias) è impostato per l'utente.
    
- Quando si imposta audioconferenze con accesso esterno, impostare le cifre necessari per il PIN nella propria organizzazione. PIN può essere da 4 a 12 cifre: il valore predefinito è 5. Se si modifica l'impostazione della lunghezza PIN, l'impostazione viene applicata solo su PIN appena generato e non viene applicata per l'impostazione del PIN per gli utenti che sono abilitati per le conferenze audio. Vedere [impostare la lunghezza del PIN per le riunioni di conferenze Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Messaggio di posta elettronica per impostazione predefinita viene impostato per l'indirizzo SMTP primario a Office 365 dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo non Office 365, ad esempio Hotmail o indirizzo di posta elettronica MSN. Per ignorare l'indirizzo di posta elettronica predefinito mediante Windows PowerShell. Questa opzione è particolarmente utile se gli utenti non dispongono di una cassetta postale di Exchange in Office 365.
    
- Per ignorare l'indirizzo dell'utente predefinito in cui viene inviato il messaggio di posta elettronica, l'amministratore tenant può utilizzare il cmdlet seguente: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress "u@hotmail.com". Il parametro SendEmail è necessario sostituire l'indirizzo di posta elettronica dell'utente.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Puoi impostare il PIN per Amos Marble eseguendo:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md)
