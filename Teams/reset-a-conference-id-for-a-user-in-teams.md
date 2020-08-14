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
description: Informazioni sui passaggi per reimpostare l'ID conferenza di una riunione dell'utente in Microsoft teams e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662126"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Reimpostare un ID conferenza per un utente in Microsoft Teams

Un ID conferenza dinamico è incluso nella parte inferiore degli inviti alle riunioni insieme ai numeri di telefono di accesso esterno che possono essere usati dai chiamanti per chiamare una riunione. Quando l'utente compone il numero di telefono, l'operatore automatico per la riunione chiederà al chiamante di immettere l'ID conferenza in modo che possa partecipare alla riunione.
  
> [!NOTE]
> Gli ID conferenza vengono generati automaticamente, saranno compresi tra le cifre di 7-9 e vengono impostati quando si Abilita la conferenza audio per un utente. **Gli ID conferenza statici non sono supportati.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostare l'ID conferenza per un utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Fare clic su **modifica**.

3. In **audioconferenza** fare clic su **Reimposta ID conferenza**.

2. Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma è possibile disattivarli.   

    
> [!NOTE]
> Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio di posta elettronica verrà inviato all'indirizzo di posta elettronica principale, in molti casi, nella cassetta postale Microsoft 365 o Office 365. Il messaggio di posta elettronica contiene il nuovo ID conferenza, i numeri di telefono di accesso esterno predefiniti e le istruzioni per l'aggiornamento delle riunioni esistenti. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono di accesso esterno facendo clic su **Invia informazioni conferenza in posta elettronica** per l'utente nella sezione **audioconferenza** . Il PIN non è incluso.
    
- Un ID conferenza di 7-9 digit viene creato dal servizio teams. Non è possibile modificarne la lunghezza.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.
    
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md)
