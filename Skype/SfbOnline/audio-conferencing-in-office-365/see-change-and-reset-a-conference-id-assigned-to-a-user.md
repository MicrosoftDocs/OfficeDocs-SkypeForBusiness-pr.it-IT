---
title: Visualizzare, modificare e ripristinare un ID conferenza assegnato a un utente
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informazioni su come assegnare un ID conferenza a un utente in Skype per le aziende e quali la conferenza ID devono essere parametri. '
ms.openlocfilehash: eccbcd31add14026d2b5f3a57348ae5d6f1db2a5
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703405"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a>Consente di visualizzare e reimpostare un ID conferenza assegnato a un utente

Al Skype per utenti Business o Microsoft Teams viene automaticamente assegnato un ID conferenza quando sono configurati per l'audioconferenza in Office 365 e utilizzare Microsoft come provider di servizi di conferenza audio. L'ID conferenza assegnato viene inviato nell'invito alla riunione durante la riunione pianificata. Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco. 
  
Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile che quando un utente non desidera utilizzare questo e si desidera impostare per un determinato numero o quando gli utenti non possono ricordare o sono persa loro ID conferenza. È possibile utilizzare il **Skype per interfaccia di amministrazione di Business** e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.
  
Verrà inviato un messaggio di posta elettronica all'utente con l'ID conferenza e i numeri di telefono di audioconferenza predefinito o se si reimposta l'ID conferenza verrà inviato un messaggio di posta elettronica diverso che includerà l'ID conferenza, ma non un PIN. Per ulteriori informazioni sulla reimpostazione PIN di un organizzatore della conferenza, [fare clic qui](reset-a-conference-id-for-a-user.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Consente di visualizzare e reimpostare gli ID conferenza

### <a name="to-view-the-conference-id"></a>Per visualizzare l'ID conferenza

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. In **Servizi di conferenza Audio**, cercare nella casella **ID conferenza**.

    > [!TIP]
    > È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza nella posta elettronica** .
  
È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente. A tale scopo, eseguire:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

È possibile visualizzare l'ID conferenza e inviare agli utenti.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, selezionare l'utente che ha necessità di ID conferenza
    
4. Nella pagina azione cercare nella casella **ID conferenza**.
    
    > [!TIP]
    > È possibile inviare tutte le informazioni di servizi di conferenza per utente in un messaggio di posta elettronica che include l'ID conferenza e i numeri di telefono audio facendo clic sul collegamento **Invia informazioni conferenza tramite posta elettronica** dopo aver selezionato l'utente nella pagina **utenti** .

È possibile utilizzare Windows PowerShell per visualizzare l'ID conferenza per un utente. A tale scopo, eseguire:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a>Per reimpostare l'ID conferenza

È possibile reimpostare un ID conferenza per un utente se, ad esempio, se si dimentica.
  
![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. In **Servizi di conferenza Audio**, fare clic su **Reimposta ID conferenza**.

4. Nella finestra di **reimpostare ID conferenza** , fare clic su **Reimposta**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell. Per farlo, eseguire quanto segue:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. In **Skype per Business admin center**> **audioconferenze** > **gli utenti**, nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.
    
4. Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    È possibile reimpostare l'ID conferenza per un utente tramite Windows PowerShell. Per farlo, eseguire quanto segue:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

   > [!IMPORTANT]
   >  Dopo che viene creato un nuovo ID conferenza o una viene reimpostata, l'ID conferenza precedente non può essere utilizzato per i chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business dello strumento di migrazione di riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.
    
- L'ID conferenza deve soddisfare la lunghezza in cifre impostare ponte per conferenze audio. Non è possibile utilizzare caratteri speciali o alfabetici conferenza ID; possono essere utilizzati solo i numeri.
    
- L'ID conferenza per tutti gli utenti di audioconferenze con accesso esterno sarà 7 cifre per impostazione predefinita e il numero di cifre non può essere modificato.
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

