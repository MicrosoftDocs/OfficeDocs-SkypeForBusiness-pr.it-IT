---
title: Visualizzare, modificare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Informazioni su come assegnare un ID conferenza per un utente in Skype for Business online e quale devono essere i parametri ID conferenza. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643606"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online

> [!Note]
> Per informazioni sugli ID conferenza utente in Microsoft Teams, vedere Visualizzare e reimpostare un ID conferenza [assegnato a un utente in Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Un ID conferenza viene assegnato automaticamente a un utente Skype for Business quando è configurato per le audioconferenze in Microsoft 365 o Office 365 e utilizza Microsoft come provider di servizi di audioconferenza. L'ID conferenza assegnato viene inviato nell'invito alla riunione al momento della pianificazione. A ogni riunione pianificata da un utente verrà assegnato un ID conferenza univoco.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Visualizzare e reimpostare gli ID conferenza

### <a name="to-view-the-conference-id"></a>Per visualizzare l'ID conferenza

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

È possibile visualizzare l'ID conferenza e inviarlo agli utenti.

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Accedi all'interfaccia di amministrazione > **Skype for Business.**

3. Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, seleziona l'utente che ha bisogno dell'ID conferenza.

4. Nella pagina Azione, cerca in **ID conferenza**.

    > [!TIP]
    > Facendo clic sul collegamento Invia informazioni conferenza tramite posta elettronica dopo aver selezionato  l'utente nella pagina Utenti, è  possibile inviare all'utente tutte le informazioni relative alla conferenza in un messaggio di posta elettronica contenente l'ID conferenza e i numeri di telefono audio.

**Uso Windows PowerShell**

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Vedi [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) per ulteriori informazioni sul cmdlet.


### <a name="to-reset-the-conference-id"></a>Per reimpostare l'ID conferenza

È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Accedi all'interfaccia di amministrazione > **Skype for Business.**

3. **Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro Azione sotto >    >   **ID** conferenza, fai clic su **Reimposta.**

4. Nella finestra **Reimposta ID conferenza?** fai clic su **Sì.** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Uso Windows PowerShell**

È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell. Per farlo, eseguire quanto segue:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

   > [!IMPORTANT]
   >  Dopo aver creato un nuovo ID conferenza o averne reimpostato uno, quello precedente non può più essere usato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire lo strumento, consulta: Strumento di aggiornamento riunioni per Skype for Business e [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype for Business Online, strumento di migrazione delle riunioni [(64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e Skype for Business online, strumento di migrazione delle riunioni [(32 bit).](https://www.microsoft.com/download/details.aspx?id=54079)

- See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.

- L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze. Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.

- L'ID conferenza per tutti gli utenti di audioconferenza è di 9 cifre per impostazione predefinita e il numero di cifre non può essere modificato.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

