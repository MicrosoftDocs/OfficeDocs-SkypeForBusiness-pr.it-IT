---
title: Reimpostare il PIN per audioconferenze in Skype for Business
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Scoprire che cosa è necessario sapere sul PIN e come reimpostarlo in Skype for Business online. '
ms.openlocfilehash: 57431b51607f963f6dbd6da688e9bf7bd2758b53
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854296"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Reimpostare il PIN per audioconferenze in Skype for Business

> [!Note]
> Per informazioni sulla reimpostazione del PIN di audioconferenza in Microsoft Teams, vedere [reimpostare il PIN di audioconferenza di Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Un PIN è un codice numerico che viene creato per ogni utente Skype for Business abilitato alle audioconferenze. Il PIN di audioconferenza viene utilizzato dall'organizzatore della riunione per dimostrare di essere l'organizzatore della stessa e poter avviare la riunione tramite telefono. Se per avviare la riunione l'organizzatore utilizza il client Skype for Business,  il PIN non è necessario. Se gli utenti dimenticano il PIN e non ritrovano la posta elettronica in cui è stato inviato quando sono stati abilitati per le audioconferenze, un amministratore o loro stessi possono reimpostare il PIN.
  
Le riunioni possono iniziare quando un utente autenticato partecipa utilizzando un client Skype for Business o quando l'organizzatore partecipa con il proprio PIN tramite telefono. Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.
  
## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

1. Accedi a Office 365 con il tuo account aziendale o scolastico.
    
2. Vai a**Centro di amministrazione di Office 365** > **Skype for Business**e nel riquadro di navigazione sinistro fai clic su **Audioconferenza**.
    
3. Fai clic su **Utenti** e quindi seleziona l'utente a cui desideri reimpostare il PIN.
    
4. Nel riquadro Azioni, alla voce **PIN**, fai clic su **Reimposta**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Reimpostazione del PIN da parte dell'utente

Un utente può reimpostare un PIN utilizzando l'opzione **Reimposta PIN** nella pagina **conferenza telefonica** . Questa pagina è accessibile in uno dei tre modi seguenti:

* In un browser, accedere a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Skype for Business, fare clic sulla freccia **Mostra Menu** accanto al pulsante **Opzioni**e quindi fare clic su **Strumenti** > **Impostazioni di conferenza telefonica**.
* In Skype for Business, fare clic su **Opzioni**, fare clic su **Inoltro di chiamata** nel menu a sinistra e quindi nella sezione **Altre impostazioni di chiamata** , fare clic su **Modifica impostazioni online**. 

## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, alla reimpostazione del PIN. Dopo la reimpostazione del PIN da parte dell'amministratore, il PIN sarà visualizzato come *********** nell'interfaccia di amministrazione di Skype for Business e nei risultati quando si utilizza **Get-CsCsOnlineDialInConfencingUser** in Windows PowerShell.
    
- L'invio automatico dei messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN al momento dell'abilitazione per i servizi di audioconferenza con accesso esterno o della reimpostazione del PIN. Se invece disabiliti l'invio automatico dei messaggi di posta elettronica, all'utente non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN e dovrai inviare manualmente all'utente le informazioni relative al PIN.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita non consente a un chiamante anonimo di avviare una riunione.
    
- Quando si attiva un utente per le audioconferenze, per impostazione predefinita vengono inviati i messaggi di posta elettronica che includono informazioni sulle conferenze e il proprio PIN. L'utente deve disporre di una cassetta postale di Office 365, perché quando il PIN viene reimpostato, all'utente verrà inviato un nuovo PIN tramite messaggio di posta elettronica all'indirizzo SMTP primario (alias) impostato per l'utente.
    
- Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione. I PIN possono essere composti da 4 fino a 12 cifre; il valore predefinito è 5. Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze. Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Il messaggio di posta elettronica verrà inviato per impostazione predefinita all'indirizzo SMTP primario di Office 365 dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo non Office 365, ad esempio Hotmail o indirizzo di posta elettronica MSN. È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell. Questa opzione è particolarmente utile se gli utenti non dispongono di una cassetta postale di Exchange in Office 365.
    
- Per sostituire l'indirizzo predefinito  a cui viene inviato il messaggio di posta elettronica, l'amministratore tenant può utilizzare il cmdlet seguente: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress "u@hotmail.com". È necessario il parametro  SendEmail per sostituire l'indirizzo di posta elettronica dell'utente.
    
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
  
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md)
