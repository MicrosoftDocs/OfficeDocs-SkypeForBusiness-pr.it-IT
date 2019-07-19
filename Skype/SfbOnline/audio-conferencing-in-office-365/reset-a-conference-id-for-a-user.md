---
title: Reimpostare un ID conferenza per un utente in Skype for business online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni sui passaggi per reimpostare l'ID conferenza di una riunione dell'utente in Skype for business online e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni. "
ms.openlocfilehash: 0e214444b80f6562c733526acbb6f87c66e46922
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792106"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Reimpostare un ID conferenza per un utente in Skype for business online

> [!NOTE]
> Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.
  
> [!NOTE]
> Se il proprio provider di servizi di conferenza è Microsoft, gli ID conferenza degli utenti sono impostati solo su dinamico. Non è possibile modificarlo. Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Skype for Business abilitati per Audioconferenza. 

## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostare l'ID conferenza per un utente
   
1. Nell'interfaccia **di amministrazione di Skype for business**, fai clic su**utenti**di servizi di **audioconferenza** > , seleziona un utente e quindi nel riquadro azioni in **ID conferenza** fai clic su **Reimposta**.
    
2. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.
    
> [!NOTE]
> Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.
    
- Un ID conferenza conterrà 7 cifre e non è possibile modificarne la lunghezza nell'interfaccia di amministrazione di Skype for business o tramite Windows PowerShell.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- L'ID conferenza di un utente per l'audioconferenza può essere visualizzato nella parte inferiore del riquadro azioni in servizi di **audioconferenza** quando si seleziona l'utente nella pagina **utenti** .
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:
    
  - [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Learn about these advantages in the following topics:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin.md)
