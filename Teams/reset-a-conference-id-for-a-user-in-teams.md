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
description: Informazioni sulla procedura per reimpostare l'ID conferenza di una riunione in Microsoft Teams e ottenere collegamenti agli strumenti di aggiornamento e migrazione delle riunioni.
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117644"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Reimpostare un ID conferenza per un utente in Microsoft Teams

Un ID conferenza dinamico è incluso nella parte inferiore degli inviti alle riunioni insieme ai numeri di telefono di accesso esterno che possono essere usati dai chiamanti per accedere a una riunione. Quando l'utente compone il numero di telefono, l'operatore automatico della riunione chiederà al chiamante di immettere questo ID conferenza in modo che possa partecipare alla riunione.
  
> [!NOTE]
> Gli ID conferenza vengono generati automaticamente, saranno compresi tra 7 e 9 cifre e vengono impostati quando si abilitano le audioconferenze per un utente. **Gli ID conferenza statici non sono supportati.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Reimpostazione dell'ID conferenza per un utente

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Fare clic **su Modifica**.

3. In **Audioconferenza fare** clic **su Reimposta ID conferenza.**

2. Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Per impostazione predefinita, i messaggi di posta elettronica vengono inviati agli utenti, ma possono essere disattivati.   

    
> [!NOTE]
> Dopo la reimpostazione dell'ID conferenza, viene inviata all'utente un'e-mail con il nuovo ID conferenza. Questo messaggio di posta elettronica verrà inviato all'indirizzo di posta elettronica principale, in molti casi, Microsoft 365 o Office 365 cassetta postale. Il messaggio di posta elettronica contiene il nuovo ID conferenza, i numeri di telefono di accesso remoto predefiniti e le istruzioni per l'aggiornamento delle riunioni esistenti. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio  di posta elettronica che include l'ID conferenza e i numeri di telefono per l'accesso esterno facendo clic su Invia info conferenza tramite posta elettronica per l'utente nella sezione **Audioconferenza.** Il PIN non è incluso.
    
- Un ID conferenza da 7 a 9 cifre viene creato dal Teams servizio. Non è possibile modificarne la lunghezza.
    
- Dopo la reimpostazione, il nuovo ID conferenza viene riportato nella sezione **ID conferenza**.
    
- Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare il PIN di audioconferenza](reset-the-audio-conferencing-pin-in-teams.md)