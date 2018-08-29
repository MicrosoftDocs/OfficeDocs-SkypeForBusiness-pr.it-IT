---
title: Vedere, modificare e ripristinare un ID conferenza assegnato a un utente in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'Informazioni su come assegnare un ID conferenza per un utente in Skype for Business online e quale devono essere i parametri ID conferenza. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252309"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Visualizzare e reimpostare un ID conferenza assegnato a un utente in Skype for Business online

> [!Note]
> Per informazioni sugli ID di conferenza utente in Microsoft Teams, consulta [Visualizzare e reimpostare un ID conferenza assegnato a un utente in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Un ID conferenza viene assegnato automaticamente a un utente Skype for Business quando questo è configurato per l'audioconferenza in Office 365 e utilizza Microsoft come provider di servizi di audioconferenza. L'ID conferenza assegnato viene inviato nell'invito alla riunione durante la riunione pianificata. A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.

Benché un ID conferenza venga automaticamente creato e assegnato a un utente, può succedere che un utente non desideri utilizzarlo o voglia impostare un determinato numero o che non se lo ricordi o perda l'ID conferenza. È possibile utilizzare l'**interfaccia di amministrazione di Skype for Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.

Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefiniti oppure, se si reimposta l'ID conferenza, verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN. Per ulteriori informazioni sulla reimpostazione del PIN dell'organizzatore di una conferenza, [fare clic qui](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Visualizzare e reimpostare gli ID conferenza

### <a name="to-view-the-conference-id"></a>Per visualizzare l'ID conferenza

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**

È possibile visualizzare l'ID conferenza e inviarlo agli utenti.

1. Accedi a Office 365 con l'account aziendale o scolastico.

2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, seleziona l'utente che ha bisogno dell'ID conferenza.

4. Nella pagina Azione, cerca in **ID conferenza**.

    > [!TIP]
    > È possibile inviare tutte le informazioni sulla conferenza all'utente in un'email che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni sulla conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **Utenti**.

**Tramite Windows PowerShell**

È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente. Procedura:

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>Per reimpostare l'ID conferenza

È possibile reimpostare un ID conferenza per un utente se, per esempio, venisse dimenticato.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**

1. Accedi a Office 365 con l'account aziendale o scolastico.

2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell'**interfaccia di amministrazione di Skype for Business**> **Audioconferenze** > **Utenti**, nel riquadro Azioni in **ID conferenza**, fai clic su **Reimposta**.

4. Nella finestra **Reimpostare ID conferenza?**, fai clic su **Sì**. Verrà creato automaticamente un ID conferenza e verrà inviata un'email all'utente con il nuovo ID conferenza.

**Tramite Windows PowerShell**

È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell. Procedura:

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

   > [!IMPORTANT]
   >  Una volta reimpostato un ID conferenza o creato uno nuovo, quello precedente non può essere utilizzato dai chiamanti. È necessario invitare gli utenti a pianificare di nuovo gli inviti alle riunioni esistenti per assicurarsi che il nuovo ID conferenza venga aggiunto agli inviti. Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento delle riunioni per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

- Vedere [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) per ulteriori informazioni sul cmdlet.

- L'ID conferenza deve soddisfare la lunghezza in cifre impostata sul ponte per audioconferenze. Non è possibile utilizzare caratteri speciali o alfabetici negli ID conferenza; possono essere utilizzati solo i numeri.

- L'ID conferenza per tutti gli utenti di audioconferenze sarà di 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:

  - [Introduzione a Windows PowerShell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Motivi per utilizzare PowerShell di Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:

  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

