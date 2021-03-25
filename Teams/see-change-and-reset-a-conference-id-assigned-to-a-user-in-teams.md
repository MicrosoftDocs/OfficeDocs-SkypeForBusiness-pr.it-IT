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
description: Informazioni su come assegnare un ID conferenza a un utente in Microsoft Teams e quali devono essere i parametri degli ID conferenza.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117209"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams

Un ID conferenza viene assegnato automaticamente a un utente di Microsoft Teams quando è configurato per le audioconferenze in Microsoft 365 o Office 365 e usa Microsoft come provider di servizi di audioconferenza. L'ID conferenza assegnato viene inviato nell'invito alla riunione quando la riunione è pianificata. A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. 
  
Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente non vuole usarlo e si vuole impostarlo su un determinato numero oppure quando gli utenti non ricordano o non hanno perso l'ID conferenza. È possibile usare l'interfaccia di amministrazione di Microsoft Teams o Windows PowerShell per visualizzare, modificare e reimpostare l'ID conferenza.
  
Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN. Per altre informazioni su come reimpostare il PIN di un organizzatore della conferenza, vedere Reimpostare un ID conferenza per un utente [in Microsoft Teams.](reset-a-conference-id-for-a-user-in-teams.md) 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizzare e reimpostare gli ID conferenza

### <a name="to-view-the-conference-id"></a>Per visualizzare l'ID conferenza

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. In **Audioconferenza** cercare in **ID conferenza**.

    > [!TIP]
    > È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento Invia informazioni conferenza **tramite posta** elettronica.
  
**Uso di Windows PowerShell**

Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)
    
  
### <a name="to-reset-the-conference-id"></a>Per reimpostare l'ID conferenza

È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.
  
![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. In **Audioconferenza** fare clic **su Reimposta ID conferenza.**

4. Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**Uso di Windows PowerShell**

Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)


## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

   > [!IMPORTANT]
   >  Dopo la creazione o la reimpostazione di un nuovo ID conferenza, il vecchio ID conferenza non può essere usato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 
  
    
- L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze. Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più sulle Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)