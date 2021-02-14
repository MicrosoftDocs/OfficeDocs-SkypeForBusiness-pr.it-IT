---
title: Visualizzare, modificare e reimpostare l'ID conferenza di un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: Informazioni su come assegnare un ID conferenza a un utente in Microsoft Teams e quali parametri devono essere gli ID conferenza.
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691152"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams

Un ID conferenza viene assegnato automaticamente a un utente di Microsoft Teams quando è configurato per le audioconferenze in Microsoft 365 o Office 365 e utilizza Microsoft come provider di servizi di audioconferenza. L'ID conferenza assegnato viene inviato nell'invito alla riunione al momento della pianificazione. A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. 
  
Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente potrebbe non volerlo usare e impostarlo su un determinato numero oppure quando gli utenti non ricordano o non ricordano più il proprio ID conferenza. È possibile usare l'interfaccia di amministrazione di Microsoft Teams Windows PowerShell visualizzare, modificare e reimpostare l'ID conferenza.
  
Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN. Per altre informazioni su come reimpostare il PIN di un organizzatore di una conferenza, vedere Reimpostare un ID conferenza per un utente [in Microsoft Teams.](reset-a-conference-id-for-a-user-in-teams.md) 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizzare e reimpostare gli ID conferenza

### <a name="to-view-the-conference-id"></a>Per visualizzare l'ID conferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. In **Audioconferenza** cercare in **ID conferenza.**

    > [!TIP]
    > Facendo clic sul collegamento Invia informazioni conferenza tramite posta elettronica è possibile inviare all'utente tutte le informazioni conferenza **in** un messaggio di posta elettronica contenente l'ID conferenza e i numeri di telefono audio.
  
**Uso Windows PowerShell**

Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
    
  
### <a name="to-reset-the-conference-id"></a>Per reimpostare l'ID conferenza

È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.
  
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi selezionare l'utente nell'elenco di utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. In **Audioconferenza** fare clic **su Reimposta ID conferenza.**

4. Nella finestra **Reimposta ID conferenza,** fai clic su **Reimposta.** A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Uso Windows PowerShell**

Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)


## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

   > [!IMPORTANT]
   >  Dopo aver creato un nuovo ID conferenza o averne reimpostato uno, quello precedente non può più essere usato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 
  
    
- L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze. Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
    
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
