---
title: Gestire le impostazioni di conferenze Audio per l'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Vedere Procedura per assegnare un ID conferenza telefonica con licenza e conferenza a un utente, impostato un provider di servizi di conferenza di terze parti e molte altre impostazioni di conferenza telefonica. '
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Gestire le impostazioni di conferenze Audio per l'organizzazione

Potrebbe risultare più semplice per poter visualizzare tutte le impostazioni di audioconferenza per Skype per le aziende e Teams Microsoft in un unico sito. 
  
## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di conferenze Audio

> [!NOTE]
> È possibile assegnare licenze utilizzando **Skype per interfaccia di amministrazione di Business**. È necessario utilizzare l'interfaccia di amministrazione di Office 365. Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **Per assegnare una licenza per un utente**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell' **interfaccia di amministrazione di Office 365**, passare a **utenti** > **utenti attivi**e quindi selezionare l'utente o gli utenti dall'elenco degli utenti disponibili.
    
    > [!NOTE]
    > Se si assegna le licenze per un massimo di 20 utenti contemporaneamente, è possibile utilizzare **Selezionare una visualizzazione** elenco a discesa, quindi scegliere una delle opzioni o creare una visualizzazione personalizzata. Quindi fare clic su **Modifica**, **Avanti** due volte, quindi selezionare la licenza e fare clic su **Invia**. È inoltre possibile assegnare licenze a più utenti utilizzando Windows Powershell. Per istruzioni ed esempi di script PowerShell, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**. 
    
4. Nella pagina **Licenze per i prodotti** , attivare **Servizi di conferenza Audio** e quindi fare clic su **Salva**. Per ulteriori informazioni sulle licenze, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Dopo aver assegnato alla licenza, Microsoft potrebbe non viene inizialmente visualizzato nell'elenco come provider di servizi di conferenza audio. In questo caso, disconnettersi dall'interfaccia di amministrazione di Office 365 oppure premere CTRL + F5 per aggiornare la finestra del browser. 
  
## <a name="assign-a-conference-id-for-a-user"></a>Assegnare un ID conferenza per un utente

Un ID conferenza viene automaticamente assegnato a un utente quando sono configurati per l'audioconferenza tramite Microsoft come provider di servizi di conferenza audio. L'ID conferenza assegnato può essere statico o dinamico e viene inviato nell'invito alla riunione durante la riunione pianificata. 
  
ID statico vengono utilizzati quando gli utenti dell'organizzazione non desiderano Memorizza numero casuale; possono selezionare un determinato numero o scegliere una facile da ricordare. Quando vengono utilizzati gli ID conferenza dinamico, ogni riunione pianificazioni un utente verranno ottenere assegnato un ID conferenza univoco. Se si desidera assegnare dinamico anziché gli ID conferenza statico, vedere [ID dinamico tramite servizi di conferenza Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Skype per interfaccia di amministrazione di Business non può essere utilizzato per assegnare un ID conferenza a un utente, ma è possibile utilizzare il cmdlet di Windows PowerShell per eseguire questa operazione.
  
Per impostare l'ID conferenza per un utente, eseguire:
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Un ID conferenza deve contenere 7 cifre e non è possibile modificare in Skype for Business admin center o utilizzando Windows PowerShell. 
  
Vedere [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) per ulteriori informazioni sul cmdlet.
  
> [!IMPORTANT]
>  Dopo aver creato un nuovo ID conferenza, l'ID conferenza precedente non può essere utilizzato per i chiamanti. È necessario avvisare gli utenti di pianificare di nuovo le riunioni gli inviti per verificare che la nuova conferenza che ID viene aggiunto a inviti esistente. Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Vedere [visualizzare, modificare e ripristinare un ID conferenza assegnato a un utente](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Modificare il provider di servizi di conferenza audio da Microsoft a un provider di terze parti

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**e quindi selezionare l'utente che si desidera modificare il provider di servizi di conferenza audio per.
    
4. Nel riquadro Azione, fai clic su **Modifica**. 
    
5. Nella pagina **proprietà** sotto il **nome del Provider**, scegliere il provider di servizi di conferenza audio per l'utente.
    
    > [!NOTE]
    > È possibile selezionare Microsoft come provider di servizi di conferenza audio o **Nessuno** solo se sono stati selezionati più utenti.
  
6. Fare clic su **Salva**. 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze con accesso esterno

È possibile utilizzare Skype per interfaccia di amministrazione di Business o Windows PowerShell per abilitare o disabilitare la posta elettronica inviato agli utenti.
  
 **Utilizzo di Skype per interfaccia di amministrazione di Business**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.
    
4. Fare clic su **Salva**.
    
    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di conferenza audio verranno le proprietà dell'utente per conferenze audio e facendo clic su **Invia informazioni conferenza tramite posta elettronica**. L'ID e imposta come predefinito audioconferenza numero di telefono conferenza è inclusi nell'invito alla riunione, ma non il PIN.
    
    Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md).
    
 **Utilizzo di Windows PowerShell**
  
- È inoltre possibile utilizzare Windows PowerShell ed eseguire: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    È possibile utilizzare [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti

È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente. Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:
  
- Immettere l'indirizzo di posta elettronica nel parametro _SendEmailFromAddress_ .
    
- Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
- Il parametro _SendEmailOverride_ impostato su _True_.
    
È possibile apportare modifiche al messaggio di posta elettronica inviato a utenti, ad esempio l'indirizzo di posta elettronica viene inviato dal messaggio di posta elettronica o il nome visualizzato per la posta elettronica mediante l'esecuzione:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se si desidera modificare le informazioni sull'indirizzo di posta elettronica, è necessario assicurarsi che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi di posta elettronica provenienti dall'indirizzo di posta elettronica personalizzato.
  
È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
Vedere [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Reimpostare la riunione ID conferenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.
    
4. Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**. Verrà creato automaticamente un ID conferenza e un messaggio di posta elettronica inviato all'utente con il nuovo ID conferenza se è abilitato l'invio di posta elettronica per gli utenti. È abilitato per impostazione predefinita.
    
    > [!IMPORTANT]
    >  Dopo aver creato un nuovo ID conferenza, l'ID conferenza precedente non può essere utilizzato per i chiamanti. È necessario avvisare gli utenti di pianificare di nuovo le riunioni gli inviti per verificare che la nuova conferenza che ID viene aggiunto a inviti esistente. Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [riunione dello strumento di aggiornamento per Skype per le aziende e Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4) [Skype online Business Strumento di migrazione (64 bit) delle riunioni](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business in linea, strumento di migrazione di riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Vedere [reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reimpostare il PIN dell'organizzatore della conferenza

ID statico vengono utilizzati quando gli utenti dell'organizzazione non desiderano Memorizza numero casuale; possono selezionare un determinato numero o utilizzare una facile da ricordare. Quando vengono utilizzati gli ID conferenza dinamico, ogni riunione pianificazioni un utente verranno ottenere assegnato un ID conferenza univoco. Se si desidera assegnare dinamico anziché [statico ID, conferenze Audio tramite dynamic gli ID](using-audio-conferencing-dynamic-ids-in-your-organization.md)conferenza all'interno dell'organizzazione.
  
Benché un ID conferenza statica verrà automaticamente creato e assegnato a un utente, è possibile quando non da un utente di utilizzare questo e si desidera impostare per un determinato numero o gli utenti non possono ricordare o sono persa loro ID conferenza. È possibile utilizzare Skype per interfaccia di amministrazione di Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.
    
4. Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.
    
Gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN. Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN e sarà necessario inviare manualmente il PIN all'utente. Il PIN sono visibili solo una volta dopo che è stata ripristinata. Dopo che viene visualizzata immediatamente dopo la reimpostazione, il PIN non verrà visualizzato più nella proprietà utente. in realtà, * * * verranno visualizzati. 
  
Vedere [reimpostare il PIN per le conferenze Audio per un utente](reset-the-audio-conferencing-pin-for-a-user.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.
    
4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
    > [!NOTE]
    > A tale scopo, conferenze audio PIN non viene inviato all'utente. 
  
Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md).
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>Impostazione del numero di telefono audioconferenza predefinito per gli organizzatori delle riunioni

 **Per impostare il numero di telefono di audioconferenza predefinito per gli organizzatori delle riunioni quando un utente si sta abilitando per le conferenze Audio**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**. Selezionare l'utente che si desidera abilitare per le audioconferenze.
    
4. Nel riquadro azioni, nella finestra delle proprietà dell'utente, fare clic su **Modifica**.
    
5. Nella pagina **proprietà** sotto il **nome del Provider**, utilizzare l'elenco a discesa per selezionare il provider di servizi di conferenza audio.
    
  - Se si seleziona Microsoft come provider di servizi di conferenza audio, è possibile scegliere il numero di telefono di audioconferenza predefinito dall'elenco.  
    
  - Se si seleziona un'AUDIOCONFERENZA di terze parti come provider di servizi di conferenza audio, è necessario immettere manualmente le tariffe e, se necessario, il numero verde. Questi numeri di telefono sarà il numero di telefono predefinito.
    
    Il numero di telefono predefinito audioconferenze con accesso esterno di un utente è il numero visualizzato nella invito alla riunione quando si pianifica una riunione.
    
6. Fare clic su **Salva**. 
    
Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).
  
 **Per impostare il numero di telefono di audioconferenza predefinito per gli organizzatori delle riunioni dopo aver abilitato un utente per le conferenze audio**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**, selezionare l'utente desiderato e nella pagina azione fare clic su **Modifica**.
    
4. Nella pagina **proprietà** sotto il **nome del Provider**, utilizzare l'elenco a discesa per selezionare il provider di servizi di conferenza audio.
    
  - Se l'utente utilizza Microsoft come provider di servizi di conferenza audio, è possibile scegliere il numero di telefono di audioconferenza predefinito dall'elenco.  
    
  - Se l'utente viene utilizzata un'AUDIOCONFERENZA di terze parti come provider di servizi di conferenza audio, sarà necessario immettere manualmente le tariffe e, se necessario, il numero verde.
    
    Il numero di telefono predefinito audioconferenze con accesso esterno di un utente è il numero visualizzato nella invito alla riunione quando si pianifica una riunione.
    
5. Fare clic su **Salva**. 
    
Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).
  
## <a name="setting-audio-conferencing-bridge-settings"></a>Configurazione delle impostazioni di ponte conferenza

 **Impostare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. Nella sezione **esperienza di partecipazione alle riunioni**, selezionare le seguenti operazioni:
    
  - **Abilitare questa impostazione voce relativa alla riunione e chiudere le notifiche per essere attivata** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.
    
    Ciò può essere impostata in base a una riunione per riunioni quando un utente partecipa a una riunione con un Skype per applicazioni aziendali o Microsoft Teams e cui modificare l'impostazione di **annuncio quando vengono inclusi o esclusi** dal menu riunione Skype o Microsoft Teams **le opzioni** del riunione.
    
  - **Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.
    
5. Dopo aver apportato le modifiche desiderate, fare clic su **Salva**.
    
Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Impostare la lunghezza del PIN per le riunioni**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge di Microsoft**.
    
4. In **protezione**, immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.
    
    Il codice PIN deve essere compreso tra 4 e 12 cifre. Il valore predefinito è 5.
    
Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Attivare o disattivare la posta elettronica non verrà inviato agli utenti audio**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.
    
4. Fare clic su **Salva**.
    
    Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia informazioni conferenza tramite posta elettronica**per le proprietà dell'utente per conferenze audio.
    
    In questo caso, verrà inviato un messaggio di posta elettronica che include solo ID conferenza e il numero di telefono di conferenza, ma non sarà incluso il codice PIN.
    
    Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md).
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare le lingue principale e secondarie su un ponte per conferenze audio

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.
    
4. Selezionare un numero di telefono dall'elenco, fare clic su **Imposta lingue** nel riquadro azioni e quindi nella pagina **gruppo** di lingue, fare clic sull'utilizzo nell'elenco **lingua principale** per visualizzare l'elenco completo delle lingue supportate.
    
    È inoltre possibile impostare le lingue principale e secondarie supportate quando si seleziona Microsoft come provider di servizi di conferenza audio. L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate lingue per i chiamanti.
    
Vedere [impostare le lingue di operatore automatico per le audioconferenze](set-auto-attendant-languages-for-audio-conferencing.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Vedere audioconferenza numeri di accesso

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **bridge di Microsoft**. È possibile:
    
  - Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le audioconferenze. 
    
  - Visualizzare il percorso e le lingue principale e secondarie che verranno utilizzate per l'operatore automatico di conferenze Audio.
    
  - Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le audioconferenze. Tuttavia, se viene modificato il numero di telefono predefinito di ponte per conferenze audio, non modifica il numero di telefono predefinito per gli utenti esistenti.
    
È possibile accedere ai **servizi di conferenza Audio** > **utenti** e selezionare le proprietà dell'utente per modificare il valore predefinito dei numeri per un utente di scegliere un nuovo numero dall'elenco di numeri che sono disponibili all'interno dell'organizzazione.
  
[Visualizzare un elenco di numeri di conferenza Audio](see-a-list-of-audio-conferencing-numbers.md), vedere.
  
## <a name="see-a-list-of-users-that-are-enabled"></a>Visualizzare un elenco di utenti abilitati

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**> e quindi **utenti**.
    
Vedere [visualizzare un elenco di utenti che sono abilitati per le audioconferenze](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

Sono disponibili diverse impostazioni che è possibile gestire a livello di organizzazione tramite Windows PowerShell. In questo modo semplice applicare le impostazioni per tutti gli utenti. 
    
Per ottenere ulteriori informazioni su ogni cmdlet, vedere [Skype per cmdlet Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Di seguito sono le impostazioni a livello di organizzazione: 
> 
- **Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **L'impostazione di registrazione del nome** Il valore predefinito è _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Impostazione della lunghezza PIN** Il valore predefinito è 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Impostazione solo dial-in riunioni da un telefono** Predefinito _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **L'impostazione se si desidera inviare la posta elettronica agli utenti** Il valore predefinito è _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **L'impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_. 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Se il nome visualizzato per il posta elettronica inviato agli utenti** Il valore predefinito è _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Per ulteriori informazioni su Windows PowerShell   
- Windows PowerShell è incentrato sulla gestione degli utenti e quali utenti sono consentiti o non è autorizzati a eseguire. Con Windows PowerShell, è possibile gestire Office 365 con un singolo punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi in velocità, la semplicità e produttività rispetto solo tramite l'interfaccia di amministrazione di Office 365, ad esempio se si sta creando le modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su queste vantaggiose caratteristiche negli argomenti seguenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di conferenze Audio per un utente](manage-the-audio-conferencing-settings-for-a-user.md)

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)

