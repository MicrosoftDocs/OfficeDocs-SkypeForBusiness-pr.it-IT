---
title: Visualizzare, modificare e reimpostare l'ID conferenza di un utente
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Scopri come assegnare un ID conferenza a un utente in Microsoft Teams e quali devono essere i parametri degli ID conferenza.
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642117"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams

Un ID conferenza viene assegnato automaticamente a un utente di Microsoft Teams quando è configurato per i servizi di audioconferenza in Microsoft 365 o Office 365 e utilizza Microsoft come provider di servizi di audioconferenza. L'ID conferenza assegnato viene inviato nell'invito alla riunione al momento della pianificazione della riunione. A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.
  
Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte l'utente potrebbe non voler usare questo ID e impostarlo su un determinato numero oppure quando gli utenti non riescono a ricordare o hanno perso l'ID conferenza. È possibile usare l'interfaccia di amministrazione di Microsoft Teams o Windows PowerShell per visualizzare, modificare e reimpostare l'ID conferenza.
  
Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN. Per altre informazioni su come reimpostare il PIN di un organizzatore della conferenza, vedere [Reimpostare un ID conferenza per un utente in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) .

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Visualizzare e reimpostare gli ID conferenza

### <a name="to-view-the-conference-id"></a>Per visualizzare l'ID conferenza

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Visualizzare l'ID conferenza usando l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro fare clic su **Utenti** e quindi selezionare l'utente dall'elenco di utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. In **Audioconferenza**, controlla in **ID conferenza**.

    > [!TIP]
    > Puoi inviare tutte le informazioni sulla conferenza all'utente in un messaggio e-mail che include l'ID conferenza e i numeri di telefono dell'audio facendo clic sul collegamento **Invia le informazioni sulla conferenza tramite posta elettronica** .
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Visualizzare l'ID conferenza usando Windows PowerShell

Per altre informazioni, vedere le [informazioni di riferimento su PowerShell di Microsoft Teams](/powershell/module/teams/?view=teams-ps) .

### <a name="to-reset-the-conference-id"></a>Per reimpostare l'ID conferenza

È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Reimpostare l'ID conferenza usando l'interfaccia di amministrazione di Microsoft Teams

1. Nel riquadro di spostamento sinistro fare clic su **Utenti** e quindi selezionare l'utente dall'elenco di utenti disponibili.

2. Nella parte superiore della pagina, fai clic su **Modifica**.

3. In **Audioconferenza** fai clic su **Reimposta ID conferenza**.

4. Nella finestra **Reimposta ID conferenza** fare clic su **Reimposta**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Reimpostare l'ID conferenza usando Windows PowerShell

Per altre informazioni, vedere le [informazioni di riferimento su PowerShell di Microsoft Teams](/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

> [!IMPORTANT]
> Dopo aver creato o reimpostato un nuovo ID conferenza, il vecchio ID conferenza non può essere usato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.

- L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze. Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che semplifica il lavoro quotidiano quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare i servizi di audioconferenza in Microsoft 365 per Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
