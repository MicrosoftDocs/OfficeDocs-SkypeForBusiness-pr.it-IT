---
title: Reimpostare un ID conferenza per un utente su Skype for Business online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni sui passaggi per reimpostare l'ID conferenza di un utente su Skype for Business online e ottenere collegamenti di aggiornamento e migrazione della riunione. "
ms.openlocfilehash: 34e165d92f4dc63eea8fc31c05612b6e20b64025
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850062"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Reimpostare un ID conferenza per un utente su Skype for Business online

> [!NOTE]
> Per informazioni sulla reimpostazione di un ID conferenza su Microsoft Teams, consulta [Reimpostare un ID conferenza per un utente su Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Un ID conferenza dinamico è incluso nella parte inferiore dell'invito alla riunione insieme ai numeri di telefono di accesso esterno che possono essere utilizzati dai chiamanti per partecipare a una riunione. Quando l'utente compone il numero di telefono, l'operatore automatico della riunione richiede di inserire l'ID conferenza per poter partecipare alla riunione.
  
> [!NOTE]
> Se il provider di servizi di conferenza è Microsoft, l'ID conferenza degli utenti è impostato su Solo dinamico per impostazione predefinita. Purtroppo, non è possibile modificarlo in statico nell'Interfaccia di amministrazione di Skype for Business o utilizzando Windows Powershell, dato che questa opzione non è più supportata. Gli ID conferenza vengono impostati automaticamente solo per gli utenti di Skype for Business abilitati per Audioconferenza. 

## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostazione dell'ID conferenza di una riunione per un utente
   
1. Nell'**Interfaccia di amministrazione di Skype for Business**, clicca su **Audioconferenza** > **Utenti**, seleziona un utente, e poi nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.
    
2. Nella finestra **Reimpostare ID conferenza?**, fai clic su **Sì**. Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza. Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma questa impostazione può essere disattivata.
    
> [!NOTE]
> Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- Facendo clic su **Invia informazioni conferenza tramite posta elettronica**, puoi inviare all'utente tutte le informazioni relative alla conferenza in un messaggio di posta elettronica che contiene l'ID conferenza e i numeri di telefono per l'accesso esterno. Il PIN non è incluso.
    
- Un ID conferenza conterrà 7 cifre e tale lunghezza non può essere modificata nell'Interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene mostrato nella sezione **ID conferenza**.
    
- Per visualizzare l'ID conferenza di un utente per un'audioconferenza, osserva la parte inferiore del riquadro Azioni alla voce **Audioconferenza** dopo aver selezionato l'utente nella pagina **Utenti**.
    
- Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. È necessario informare gli utenti di pianificare di nuovo gli inviti alle riunioni esistenti per assicurarsi che il nuovo ID conferenza venga aggiunto agli inviti. Gli utenti possono utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business per aggiornare le riunioni esistenti. Per scoprire come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni di Skype for Business, consulta:
    
  - [Strumento di aggiornamento delle riunioni di Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare il PIN di Audioconferenza](reset-the-audio-conferencing-pin.md)
