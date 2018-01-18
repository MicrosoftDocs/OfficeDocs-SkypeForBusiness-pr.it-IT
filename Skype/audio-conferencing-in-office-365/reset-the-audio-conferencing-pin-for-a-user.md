---
title: Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Find out what you should know about PINs and how to reset them for your users. '
ms.openlocfilehash: eca48bb053459b568edc415d712a289be0aef4ff
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a>Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente

Un PIN è un codice costituito da numeri che viene creati per ogni Skype per utenti Business e Teams Microsoft che sono abilitato per le conferenze audio. PIN di conferenza audio vengono utilizzati per gli organizzatori delle riunioni per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono. Se si utilizza Skype per applicazioni aziendali o Microsoft Teams per avviare la riunione, un PIN non è obbligatorio. Se gli utenti dimenticano il PIN e non possono trovare la posta elettronica che è stato inviato a tali quando sono stati abilitati per le conferenze audio, sarà necessario un amministratore di reimpostare il PIN. Un utente non può reimpostare i propri PIN.
  
È possibile avviare riunioni quando si unisce a un utente autenticato mediante un Skype per applicazioni aziendali o Microsoft Teams oppure quando l'organizzatore accede a con il proprio PIN nel telefono. Quando una riunione richiede un PIN per avviare, gli utenti che partecipa al telefono verrà effettuata nella sala di attesa e vengono ascoltare la musica di attesa finché la riunione viene avviato. Se l'organizzatore di una riunione non richiede un PIN avviare la riunione telefonicamente, i chiamanti non verranno richiesto di fornire un PIN quando partecipano a riunione.
  
## <a name="reset-a-conference-organizers-pin"></a>Reimpostare il PIN dell'organizzatore della conferenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende**e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**, selezionare l'utente che si desidera reimpostare il PIN per.
    
4. Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.
    
## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Per motivi di sicurezza, il PIN viene visualizzato solo a un amministratore in una sola volta, quando viene reimpostato il PIN. Dopo il PIN è stato ripristinato da un amministratore, il PIN verrà elencato come * * * in **Skype per interfaccia di amministrazione di Business** e i risultati quando si utilizza Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Invio automatico di messaggi di posta elettronica agli utenti è abilitata per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN. Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN a un utente e sarà necessario inviare manualmente le informazioni sul PIN all'utente.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita per non consentire una riunione di avvio per i chiamanti anonimi.
    
- Quando si attiva un utente per le conferenze audio, per impostazione predefinita vengono inviati i messaggi di posta elettronica che includono informazioni sulle conferenze e il proprio PIN. L'utente deve disporre di una cassetta postale Office 365, perché quando viene reimpostato un PIN, un nuovo PIN verrà inviato all'utente di posta elettronica per il proprio indirizzo SMTP principale (alias) è impostato per l'utente.
    
- Quando si imposta audioconferenze con accesso esterno, impostare le cifre necessari per il PIN nella propria organizzazione. PIN può essere da 4 a 12 cifre: il valore predefinito è 5. Se si modifica l'impostazione della lunghezza PIN, l'impostazione viene applicata solo su PIN appena generato e non viene applicata per l'impostazione del PIN per gli utenti che sono abilitati per le conferenze audio. Vedere [impostare la lunghezza del PIN per le riunioni di conferenze Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Messaggio di posta elettronica per impostazione predefinita viene impostato per l'indirizzo SMTP primario a Office 365 dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo non Office 365, ad esempio Hotmail o indirizzo di posta elettronica MSN. Per ignorare l'indirizzo di posta elettronica predefinito mediante Windows PowerShell. Ciò è utile se gli utenti non dispongano di una cassetta postale di Exchange in Office 365.
    
- Per ignorare l'indirizzo dell'utente predefinito in cui viene inviato il messaggio di posta elettronica, l'amministratore tenant può utilizzare il cmdlet seguente: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress "u@hotmail.com". Il parametro SendEmail è necessario sostituire l'indirizzo di posta elettronica dell'utente.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Puoi impostare il PIN per Amos Marble eseguendo:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell è incentrato sulla gestione degli utenti e quali utenti sono consentiti o non è autorizzati a eseguire. Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti:
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md)
