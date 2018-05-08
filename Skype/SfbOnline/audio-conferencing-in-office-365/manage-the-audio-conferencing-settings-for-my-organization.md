---
title: Gestire le impostazioni di conferenze Audio per l'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b2759e4ee1f8e8cac2f753eb5afecbf13642abb0
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Gestire le impostazioni di conferenze Audio per l'organizzazione

Potrebbe risultare più semplice per poter visualizzare tutte le impostazioni di audioconferenza per Skype per le aziende e Teams Microsoft in un unico sito. 
  
## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di conferenze Audio

> [!NOTE]
> È possibile assegnare licenze utilizzando **Skype per interfaccia di amministrazione di Business**. È necessario utilizzare l'interfaccia di amministrazione di Office 365. Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **Per assegnare una licenza per un utente**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell' **interfaccia di amministrazione di Office 365**, passare a **utenti** > **utenti attivi**e quindi selezionare l'utente o gli utenti dall'elenco degli utenti disponibili.
    
    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**. Puoi anche assegnare licenze a più utenti con Windows Powershell. Per istruzioni ed esempi di script PowerShell, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**. 
    
4. Nella pagina **Licenze per i prodotti** , attivare **Servizi di conferenza Audio** e quindi fare clic su **Salva**. Per ulteriori informazioni sulle licenze, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Dopo aver assegnato alla licenza, Microsoft potrebbe non viene inizialmente visualizzato nell'elenco come provider di servizi di conferenza audio. In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser. 
  
## <a name="assign-a-conference-id-for-a-user"></a>Un ID conferenza viene assegnato automaticamente ad un utente quando gli ID vengono configurati per le audioconferenze utilizzando Microsoft come provider. L'ID conferenza assegnato può essere statico o dinamico e viene inviato nell'invito alla conferenza al momento della pianificazione della conferenza stessa.

Un ID conferenza viene automaticamente assegnato a un utente quando sono configurati per l'audioconferenza tramite Microsoft come provider di servizi di conferenza audio. L'ID conferenza viene inviato nell'invito alla riunione durante la riunione pianificata. Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.
  
Per impostare l'ID conferenza per un utente, esegui:
  
Un ID conferenza deve contenere 7 cifre e non può essere modificato nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Un ID conferenza deve contenere 7 cifre e non è possibile modificare in Skype for Business admin center o utilizzando Windows PowerShell. 
  
See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.
  
> [!IMPORTANT]
>  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Modificare il provider di servizi di audioconferenza da Microsoft a un provider di terze parti
    
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze con accesso esterno

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica per gli utenti di modificare le relative impostazioni di connessione**.

4. Fai clic su **Salva**.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.
    
4. Fai clic su **Salva**.
    
    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di conferenza audio verranno le proprietà dell'utente per conferenze audio e facendo clic su **Invia informazioni conferenza tramite posta elettronica**. L'ID e imposta come predefinito audioconferenza numero di telefono conferenza è inclusi nell'invito alla riunione, ma non il PIN.
    
    [Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)
    
 **Utilizzo di Windows PowerShell**
  
- You can also use the Windows PowerShell and run: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    È possibile utilizzare [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti

È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente. Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:
  
- Immettere l'indirizzo di posta elettronica nel parametro _SendEmailFromAddress_ .
    
- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.
    
- Il parametro _SendEmailOverride_ impostato su _True_.
    
Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.
  
È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.
  
Vedere [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. In **Servizi di conferenza Audio**, fare clic su **Reimposta ID conferenza**.  

4. Nella **reimpostare ID conferenza?** finestra, fare clic su **Reimposta**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**  

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.
    
4. Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Reimpostare il PIN dell'organizzatore della conferenza
  
## <a name="reset-a-conference-organizers-pin"></a>Reimpostare il PIN dell'organizzatore della conferenza

Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco. Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile quando non da un utente di utilizzare questo e si desidera impostare per un determinato numero o gli utenti non possono ricordare o sono persa loro ID conferenza. È possibile utilizzare Skype per interfaccia di amministrazione di Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. In **Servizi di conferenza Audio**, fare clic su **Reimposta PIN**e quindi fare clic su **Reimposta**. 
  
![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business** 

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.
    
4. Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.
    
Gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN. Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN e sarà necessario inviare manualmente il PIN all'utente. The PIN will only be shown once after it has been reset. Dopo che viene visualizzata immediatamente dopo la reimpostazione, il PIN non verrà visualizzato più nella proprietà utente. in realtà, * * * verranno visualizzati. 
  
Vedere [reimpostare il PIN per conferenze Audio](reset-the-audio-conferencing-pin.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. In **Servizi di conferenza Audio**, fare clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**. 

    > [!NOTE]
    > A tale scopo, conferenze audio PIN non viene inviato all'utente. 

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**  

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.
    
4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
    > [!NOTE]
    > A tale scopo, conferenze audio PIN non viene inviato all'utente. 
  
[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)
  
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
    
6. Fai clic su **Salva**. 
    
Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).
  
 **Per impostare il numero di telefono di audioconferenza predefinito per gli organizzatori delle riunioni dopo aver abilitato un utente per le conferenze audio**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**, selezionare l'utente desiderato e nella pagina azione fare clic su **Modifica**.
    
4. Nella pagina **proprietà** sotto il **nome del Provider**, utilizzare l'elenco a discesa per selezionare il provider di servizi di conferenza audio.
    
  - Se l'utente utilizza Microsoft come provider di servizi di conferenza audio, è possibile scegliere il numero di telefono di audioconferenza predefinito dall'elenco.  
    
  - Se l'utente viene utilizzata un'AUDIOCONFERENZA di terze parti come provider di servizi di conferenza audio, sarà necessario immettere manualmente le tariffe e, se necessario, il numero verde.
    
    Il numero di telefono predefinito audioconferenze con accesso esterno di un utente è il numero visualizzato nella invito alla riunione quando si pianifica una riunione.
    
5. Fai clic su **Salva**. 
    
Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>La scelta delle impostazioni di ponte conferenza

**Impostare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**

 ![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **voce della riunione e chiudere le notifiche**.

    Questa opzione è attivata per impostazione predefinita. Se si disabilita questa opzione, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.

4. In **tipo di annunci di entrata/uscita**scegliere **toni** o **i nomi o numeri di telefono**. 

    Se si sceglie **nomi o numeri di telefono**, è anche possibile scegliere di attivare o disattivare **i chiamanti Ask per registrare il proprio nome prima di partecipare alla riunione**. 

1. Fai clic su **Salva**.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business** 
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
4. Nella sezione **esperienza di partecipazione alle riunioni**, selezionare le seguenti operazioni:
    
  - **Enable meeting entry and exit notifications to be turned on** This is selected by default. Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.
    
    Ciò può essere impostata in base a una riunione per riunioni quando un utente partecipa a una riunione con un Skype per applicazioni aziendali o Microsoft Teams e cui modificare l'impostazione di **annuncio quando vengono inclusi o esclusi** dal menu riunione Skype o Microsoft Teams **le opzioni** del riunione.
    
  - **Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.
    
5. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Impostare la lunghezza del PIN per le riunioni**

 ![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.

    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business** 
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.
    
4. In **protezione**, immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.
    
    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.
    
Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Attivare o disattivare la posta elettronica non verrà inviato agli utenti audio**

 ![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.

4. Fai clic su **Salva**. 
 
    Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**per le proprietà dell'utente per conferenze audio.
    
    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business** 
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.
    
3. Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.
    
4. Fai clic su **Salva**.
    
    Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia informazioni conferenza tramite posta elettronica**per le proprietà dell'utente per conferenze audio.
    
    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.
    
    Visualizzare e impostare la lingua principale e le lingue secondarie in un bridge di audioconferenza
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare il primario (impostazione predefinita) e lingue secondarie (alternative) su un ponte per conferenze audio

 ![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**. 

2. Selezionare un numero di telefono dall'elenco e fare clic su **Modifica**.

3. Selezionare le lingue desiderate nella sezione **lingua predefinita** e le relative **lingue alternative (facoltative)**.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business** 

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.
    
4. Selezionare un numero di telefono dall'elenco, fare clic su **Imposta lingue** nel riquadro azioni e quindi nella pagina **gruppo** di lingue, fare clic sull'utilizzo nell'elenco **lingua principale** per visualizzare l'elenco completo delle lingue supportate.
    
    È inoltre possibile impostare le lingue principale e secondarie supportate quando si seleziona Microsoft come provider di servizi di conferenza audio. L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate lingue per i chiamanti.
    
Visualizzare i numeri di accesso esterno per i servizi l'audioconferenza
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png)  Vedere audioconferenza numeri di accesso

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **bridge di Microsoft**. È possibile:
    
  - Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le audioconferenze. 
    
  - Visualizzare il percorso e le lingue principale e secondarie che verranno utilizzate per l'operatore automatico di conferenze Audio.
    
  - Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le audioconferenze. Tuttavia, se viene modificato il numero di telefono predefinito di ponte per conferenze audio, non modifica il numero di telefono predefinito per gli utenti esistenti.
    
È possibile accedere ai **servizi di conferenza Audio** > **utenti** e selezionare le proprietà dell'utente per modificare il valore predefinito dei numeri per un utente di scegliere un nuovo numero dall'elenco di numeri che sono disponibili all'interno dell'organizzazione.
  
[Visualizzare un elenco di numeri di conferenza Audio](see-a-list-of-audio-conferencing-numbers.md), vedere.
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png) Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**> e quindi **utenti**.
    
Vuoi sapere come gestire queste operazioni con Windows PowerShell?
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Sono disponibili diverse impostazioni per gestire le impostazioni a livello dell'organizzazione tramite Windows PowerShell. In questo modo puoi applicare con facilità tali impostazioni a tutti gli utenti. Ecco le impostazioni a livello dell'organizzazione:

Sono disponibili diverse impostazioni che è possibile gestire a livello di organizzazione tramite Windows PowerShell. In questo modo semplice applicare le impostazioni per tutti gli utenti. 
    
Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:

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
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## <a name="related-topics"></a>See also

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user.md)


