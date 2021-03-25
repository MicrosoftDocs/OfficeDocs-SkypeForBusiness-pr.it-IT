---
title: Reimpostare il PIN di audioconferenza in Skype for Business online
ms.author: tonysmit
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Informazioni sui PIN e su come reimpostarli in Skype for Business online. '
ms.openlocfilehash: 4b042775a5a0525099c0116d7d55d0092f560cdf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114202"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Reimpostare il PIN di audioconferenza in Skype for Business online

> [!Note]
> Per informazioni sulla reimpostazione del PIN di audioconferenza in Microsoft Teams, vedere [reimpostare il PIN di audioconferenza di Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Un PIN è un codice costituito da numeri creati per ogni utente di Skype for Business abilitato per le audioconferenze. I PIN di audioconferenza vengono usati dagli organizzatori della riunione per identificare che sono l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono. Se usano l'app Skype for Business per avviare la riunione, non è necessario un PIN. Se gli utenti dimenticano il PIN e non lo trovano nel messaggio di posta elettronica inviato quando sono stati abilitati per le audioconferenze, un amministratore può reimpostare il PIN oppure reimpostare il PROPRIO PIN.
  
Le riunioni possono essere avviate quando un utente autenticato partecipa usando l'app Skype for Business o quando l'organizzatore partecipa con il proprio PIN tramite telefono. Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.
  
## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Passare all'interfaccia di amministrazione > **Skype for Business** e nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**
    
3. Fare clic **su Utenti**, selezionare l'utente per cui si vuole reimpostare il PIN.
    
4. Nel riquadro Azioni, in **PIN,** fare clic su **Reimposta**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Reimpostazione del PIN da parte dell'utente

Un utente può reimpostare un PIN utilizzando l'opzione **Reimposta PIN** nella pagina **conferenza telefonica** . Questa pagina è accessibile in uno dei tre modi seguenti:

* In un browser, accedere a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Skype for Business, fare clic sulla freccia **Mostra Menu** accanto al pulsante **Opzioni** e quindi fare clic su **Strumenti** > **Impostazioni di conferenza telefonica**.
* In Skype for Business, fare clic su **Opzioni**, fare clic su **Inoltro di chiamata** nel menu a sinistra e quindi nella sezione **Altre impostazioni di chiamata** , fare clic su **Modifica impostazioni online**. 

## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, alla reimpostazione del PIN. Dopo la reimpostazione del PIN da parte di un amministratore, il PIN verrà elencato come ******** nell'interfaccia di amministrazione di **Skype for Business** e nei risultati quando usano Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- L'invio automatico di messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per le audioconferenze o quando il PIN viene reimpostato. Se tuttavia l'invio automatico dei messaggi di posta elettronica è stato disabilitato, non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN a un utente e sarà necessario inviare manualmente le informazioni sul PIN all'utente.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita è non consentire l'avvio di una riunione da parte di chiamanti anonimi.
    
- Quando si abilita un utente per le audioconferenze, per impostazione predefinita vengono inviati messaggi di posta elettronica che includono le informazioni di conferenza e il PIN. L'utente deve avere una cassetta postale di Microsoft 365 o Office 365, perché quando viene reimpostato un PIN, all'utente verrà inviato un nuovo PIN tramite posta elettronica all'indirizzo SMTP principale (alias) impostato per l'utente.
    
- Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione. I PIN possono essere da 4 a 12 cifre, il valore predefinito è 5. Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze. Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Il messaggio di posta elettronica per impostazione predefinita verrà impostato sull'indirizzo SMTP principale di Microsoft 365 o Office 365 dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo non Microsoft 365 o non di Office 365, ad esempio un indirizzo di posta elettronica Hotmail o MSN. È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell. Questa opzione è utile se gli utenti non hanno una cassetta postale di Exchange in Microsoft 365 o Office 365.
    
- Per ignorare l'indirizzo utente predefinito in cui viene inviato il messaggio di posta elettronica, l'amministratore del tenant può usare il cmdlet seguente: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". Il parametro SendEmail è necessario per sostituire l'indirizzo di posta elettronica dell'utente.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Puoi impostare il PIN per Amos Marble eseguendo:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md)