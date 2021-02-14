---
title: Reimpostare un ID conferenza per un utente in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sulla procedura per reimpostare l'ID conferenza di una riunione di un utente in Microsoft Teams e ottenere i collegamenti agli strumenti di aggiornamento e migrazione delle riunioni.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662126"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Reimpostare un ID conferenza per un utente in Microsoft Teams

Un ID conferenza dinamico è incluso nella parte inferiore degli inviti alle riunioni insieme ai numeri di telefono per l'accesso esterno che possono essere usati dai chiamanti per accedere a una riunione. Quando l'utente compone il numero di telefono, l'operatore automatico della riunione chiederà al chiamante di immettere l'ID conferenza per poter partecipare alla riunione.
  
> [!NOTE]
> Gli ID conferenza vengono generati automaticamente, saranno compresi tra 7 e 9 cifre e vengono impostati quando abiliti l'Audioconferenza per un utente. **Gli ID conferenza statici non sono supportati.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostazione dell'ID conferenza per un utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. Fare **clic su Modifica.**

3. In **Audioconferenza fare** clic **su Reimposta ID conferenza.**

2. Nella finestra **Reimposta ID conferenza,** fai clic su **Reimposta.** A conference ID will be automatically created and an email sent to the user with the new conference ID. Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma questa opzione può essere disattivata.   

    
> [!NOTE]
> Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio verrà inviato all'indirizzo di posta elettronica principale, in molti casi alla cassetta postale di Microsoft 365 o Office 365. L'e-mail contiene il nuovo ID conferenza, i numeri di telefono predefiniti per l'accesso e le istruzioni per aggiornare le riunioni esistenti. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- Facendo clic su Invia informazioni conferenza tramite posta elettronica per l'utente nella sezione  Audioconferenza, è possibile inviare all'utente tutte le informazioni relative alla conferenza in un messaggio di posta elettronica contenente l'ID conferenza e i numeri di telefono per l'accesso **esterno.** Il PIN non è incluso.
    
- Il servizio Teams crea un ID conferenza di 7-9 cifre. Non è possibile modificarne la lunghezza.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
    
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md)
