---
title: Reimpostare un ID conferenza per un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 6cc73876d188f1ae00ec267e14af4771ded7b957
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2018
---
# <a name="reset-a-conference-id-for-a-user"></a>Reimpostare un ID conferenza per un utente

Quando le organizzazioni non è stato abilitato per gli ID conferenza dinamico, un ID conferenza statica viene creato automaticamente quando Skype per utenti Business o Microsoft Teams è abilitata per le conferenze Audio tramite Microsoft come provider. Questo ID conferenza è incluso nella parte inferiore dell'insieme ai numeri di telefono di accesso esterno che possono essere utilizzati per i chiamanti per chiamare una riunione convocazioni di riunione. Quando l'utente digita il numero di telefono, l'operatore automatico per la riunione verrà chiedere al chiamante di immettere l'ID conferenza in modo che è possibile partecipare alla riunione.
  
> [!NOTE]
> Se il provider di servizi di conferenza Microsoft, ID conferenza degli utenti è impostato su dinamico solo per impostazione predefinita. Purtroppo, non sarà possibile modificare in Skype per Business Admin Center o utilizzando Windows Powershell. È necessario contattare il supporto tecnico Microsoft. 
  
ID statico vengono utilizzati quando gli utenti dell'organizzazione non desiderano Memorizza numero casuale; possono selezionare un determinato numero o utilizzare una facile da ricordare. Quando vengono utilizzati gli ID conferenza dinamico, ogni riunione pianificazioni un utente verranno ottenere assegnato un ID conferenza univoco. Se si desidera assegnare dinamico anziché gli ID, [fare clic qui](using-audio-conferencing-dynamic-ids-in-your-organization.md)di conferenza statico.
  
ID conferenza vengono impostate automaticamente solo solo per Skype per utenti Business e Microsoft Teams abilitato per le conferenze Audio tramite Microsoft come i provider di servizi di conferenza audio. Se è necessario reimpostare un ID conferenza per un utente che utilizza un provider di servizi di conferenza audio di terze parti (ACP), sarà necessario immettere manualmente un ID conferenza nella pagina delle proprietà dell'utente.
  
## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostare l'ID conferenza per un utente

**Utilizzo del team di Microsoft e Skype for Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. Fare clic sul menu accanto a **Ponti di conferenza**e quindi fare clic su **Reimposta id conferenza** nell'elenco a discesa.

2. Nella finestra di **reimpostare id conferenza** , fare clic su **Ok**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Per impostazione predefinita, messaggi di posta elettronica inviati a utenti, ma si possono essere disattivata.   

**Utilizzo di Skype per interfaccia di amministrazione di Business**
    
1. In **Skype per interfaccia di amministrazione di Business**, fare clic su **servizi di conferenza Audio** > **gli utenti**, selezionare un utente e quindi nel riquadro azioni in **ID conferenza** fare clic su **Reimposta**.
    
2. Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Per impostazione predefinita, messaggi di posta elettronica inviati a utenti, ma si possono essere disattivata.
    
> [!NOTE]
> Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio viene inviato all'indirizzo e-mail principale, che, in molti casi, corrisponde alla cassetta postale di Office 365. Nell'e-mail è contenuto il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso esterno e alcune istruzioni per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business, che consente di aggiornare le riunioni esistenti. 
  
## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono di accesso esterno facendo clic su **Invia informazioni conferenza tramite posta elettronica** dell'utente nel riquadro azioni. Il PIN non è incluso.
    
- Un ID conferenza conterrà 7 cifre e non è possibile modificare la lunghezza in Skype for Business admin center o utilizzando Windows PowerShell.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- L'ID conferenza per un utente per le conferenze audio può essere visualizzato nella parte inferiore del riquadro delle azioni in **servizi di conferenza Audio** quando si seleziona l'utente nella pagina **utenti** .
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono utilizzare Skype per strumento riunione Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere:
    
  - [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Reimpostare il PIN di audioconferenza per un utente](reset-the-audio-conferencing-pin-for-a-user.md)
