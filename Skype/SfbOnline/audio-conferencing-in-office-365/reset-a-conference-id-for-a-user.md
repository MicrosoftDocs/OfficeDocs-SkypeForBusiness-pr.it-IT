---
title: Reimpostare un ID conferenza per un utente in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "Informazioni sulla procedura per reimpostare l'ID conferenza di una riunione di un utente in Skype for Business online e ottenere i collegamenti agli strumenti di aggiornamento e migrazione delle riunioni. "
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164705"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Reimpostare un ID conferenza per un utente in Skype for Business online

> [!NOTE]
> Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.
  
> [!NOTE]
> Se il tuo provider di conferenze è Microsoft, gli ID conferenza degli utenti sono impostati su Solo dinamici. Questa impostazione non può essere modificata. Gli ID conferenza vengono impostati automaticamente solo per gli utenti Skype for Business abilitati per le audioconferenze. 

## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostazione dell'ID conferenza per un utente
   
1. **Nell'interfaccia di amministrazione di Skype for Business** fai clic su Utenti servizi di audioconferenza, seleziona un utente, quindi nel riquadro   >  Azione, in **ID** conferenza, fai clic **su Reimposta.**
    
2. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.
    
> [!NOTE]
> Dopo aver reimpostato l'ID conferenza, all'utente verrà inviata un'e-mail con il nuovo ID conferenza. Questo messaggio verrà inviato all'indirizzo di posta elettronica principale, in molti casi alla cassetta postale di Microsoft 365 o Office 365. L'e-mail contiene il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso e le istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business per aggiornare le riunioni esistenti. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.
    
- Un ID conferenza contiene 7 cifre e non puoi modificarne la lunghezza nell'interfaccia di amministrazione di Skype for Business o utilizzando Windows PowerShell.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- L'ID conferenza di un utente per i servizi di audioconferenza può essere visualizzato nella parte inferiore del riquadro Azioni in **Audioconferenza** quando si seleziona l'utente nella **pagina** Utenti.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:
    
  - [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per quanto riguarda Windows PowerShell riguarda la gestione degli utenti e le operazioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin.md)
