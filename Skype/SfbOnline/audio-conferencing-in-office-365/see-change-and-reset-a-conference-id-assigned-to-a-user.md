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
ms.openlocfilehash: 79c83999fdf9a9736dfe1ee425337edf938d3375
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110012"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online

> [!Note]
> Per informazioni sugli ID conferenza degli utenti in Microsoft Teams, vedere Visualizzare e reimpostare un ID conferenza assegnato a un utente [in Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Un ID conferenza viene assegnato automaticamente a un utente Skype for Business quando è configurato per le audioconferenze in Microsoft 365 o Office 365 e usa Microsoft come provider di servizi di audioconferenza. L'ID conferenza assegnato viene inviato nell'invito alla riunione quando la riunione è pianificata. A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.

Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente non vuole usarlo e si vuole impostarlo su un determinato numero oppure quando gli utenti non ricordano o non hanno perso l'ID conferenza. È possibile utilizzare l'**interfaccia di amministrazione di Skype for Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.

Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN. Per ulteriori informazioni sulla reimpostazione del PIN dell'organizzatore di una conferenza, [fare clic qui](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Visualizzare e reimpostare gli ID conferenza

### <a name="to-view-the-conference-id"></a>Per visualizzare l'ID conferenza

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

È possibile visualizzare l'ID conferenza e inviarlo agli utenti.

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, seleziona l'utente che ha bisogno dell'ID conferenza.

4. Nella pagina Azione, cerca in **ID conferenza**.

    > [!TIP]
    > È possibile inviare tutte le informazioni di conferenza all'utente in un messaggio  di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento Invia informazioni conferenza tramite posta elettronica dopo aver selezionato l'utente nella **pagina** Utenti.

**Uso di Windows PowerShell**

È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente. A questo scopo, eseguire:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Per altre informazioni sul cmdlet, vedere [Get-CsOnlineDialInConferencingUser.](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)


### <a name="to-reset-the-conference-id"></a>Per reimpostare l'ID conferenza

È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. **Nell'interfaccia di amministrazione di Skype for Business** Gli utenti di audioconferenza , nel riquadro Azioni in ID >    >   **conferenza,** fare clic su **Reimposta**.

4. Nella finestra **Reimposta ID conferenza?** fare clic su **Sì.** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Uso di Windows PowerShell**

È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell. Per farlo, eseguire quanto segue:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

   > [!IMPORTANT]
   >  Dopo la creazione o la reimpostazione di un nuovo ID conferenza, il vecchio ID conferenza non può essere usato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono usare lo strumento di migrazione delle riunioni Skype for Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: Strumento di aggiornamento delle riunioni per [Skype for Business e Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype for Business online, Strumento di migrazione delle riunioni [(64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e Skype for Business online, Strumento di migrazione delle riunioni [(32 bit).](https://www.microsoft.com/download/details.aspx?id=54079)

- See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.

- L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze. Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.

- L'ID conferenza per tutti gli utenti di audioconferenza sarà di 9 cifre per impostazione predefinita e il numero di cifre non può essere modificato.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)