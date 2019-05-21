---
title: Reimpostare il PIN per la conferenza audio in Skype for business online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Scopri cosa devi sapere sui pin e come reimpostarli in Skype for business online. '
ms.openlocfilehash: 11fafd6d79236fdddf3f73f384e9c339a5a775fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299087"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Reimpostare il PIN per la conferenza audio in Skype for business online

> [!Note]
> Per informazioni sulla reimpostazione del PIN di audioconferenza in Microsoft Teams, vedere [reimpostare il PIN di audioconferenza di Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.
  
Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.
  
## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedere all'interfaccia **di amministrazione** > di Office 365**Skype for business**e, nella barra di spostamento sinistra, fare clic su **audioconferenza**.
    
3. Fare clic su **utenti**, selezionare l'utente per cui si vuole reimpostare il PIN.
    
4. Nel riquadro azioni, in **pin**, fare clic su **Reimposta**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Reimpostazione del PIN da parte dell'utente

A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:

* In un browser, accedere a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Skype for Business, fare clic sulla freccia **Mostra Menu** accanto al pulsante **Opzioni**e quindi fare clic su **Strumenti** > **Impostazioni di conferenza telefonica**.
* In Skype for Business, fare clic su **Opzioni**, fare clic su **Inoltro di chiamata** nel menu a sinistra e quindi nella sezione **Altre impostazioni di chiamata** , fare clic su **Modifica impostazioni online**. 

## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as *********** in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.
    
- Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.
    
- L'impostazione predefinita consiste nel non consentire l'avvio di una riunione da parte di chiamanti anonimi.
    
- When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN. The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.
    
- When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- The email by default will be set to the Office 365 primary SMTP address of the user. You can send an email to a non-Office 365 address such as a Hotmail or MSN email address. You can override the default email address by using Windows PowerShell. This is useful if the users don't have an Exchange mailbox in Office 365.
    
- To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.
    
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
