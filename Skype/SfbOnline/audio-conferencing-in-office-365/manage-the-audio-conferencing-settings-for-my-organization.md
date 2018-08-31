---
title: Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulta passi per Skype for Business Online per assegnare una licenza e un ID conferenza per un utente e molte altre impostazioni di conferenza telefonica. '
ms.openlocfilehash: 7f4387e7d818730de3b2b0336453a3f6ec9b39e7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780492"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online

> [!NOTE]
> Se desideri gestire le impostazioni in Teama, consulta [gestire le impostazioni di Audioconferenze per l'organizzazione in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Potrebbe risultare più semplice poter visualizzare tutte le impostazioni di Audioconferenza per Skype for Business in un unico sito.


## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di Audioconferenza

> [!NOTE]
> Non è possibile assegnare licenze utilizzando la **interfaccia di amministrazione Skype for Business**. È necessario utilizzare l'interfaccia di amministrazione di Office 365. |||UNTRANSLATED_CONTENT_START|||See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).|||UNTRANSLATED_CONTENT_END|||

 **Assegnare una licenza per un utente**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Nella barra di navigazione sinistra dell'**interfaccia di amministrazione di Office 365**, vai su **Utenti** > **Utenti attivi**, e seleziona l'utente nella lista di utenti disponibili.

    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**. Puoi anche assegnare licenze a più utenti con Windows Powershell. Per istruzioni ed esempi di script per PowerShell, consulta [Assegnare licenze per Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.

4. Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**. Per ulteriori informazioni sulle licenze, consulta [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Dopo aver assegnato la licenza, Microsoft potrebbe non apparire inizialmente nell'elenco come provider di servizi di audioconferenza. In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fai clic su **Salva**.

    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza facendo clic su **Invia informazioni conferenza tramite posta elettronica**. L'ID e il numero di conferenza predefinito sono inclusi nell'invito alla riunione, ma non il PIN.

    |||UNTRANSLATED_CONTENT_START|||See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).|||UNTRANSLATED_CONTENT_END|||

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Tramite Windows PowerShell**

- Puoi anche usare Windows PowerShell ed eseguire:

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Puoi usare il [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per la tua organizzazione, inclusa la posta elettronica.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti

È possibile apportare modifiche al messaggio di posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente. Per impostazione predefinita, il mittente sarà Office 365, ma puoi modificare l'indirizzo di posta elettronica e il nome visualizzato utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285). Per apportare modifiche all'indirizzo di posta elettronica da cui viene inviato il messaggio agli utenti, procedi come segue:

- Inserisci l'indirizzo di posta elettronica nel parametro _SendEmailFromDisplayName_.

- Inserisci il nome di posta elettronica visualizzato nel parametro _SendEmailFromDisplayName_.

- Imposta il parametro _SendEmailOverride_ su _True_.

Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se desideri modificare le informazioni dell'indirizzo di posta elettronica, devi assicurarti che le politiche interne di posta elettronica della tua organizzazione consentono i messaggi che arrivano da un indirizzo personalizzato.

Puoi usare il [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per la tua organizzazione, inclusa la posta elettronica.

Consulta [Messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando le loro impostazioni di Audioconferenza vengono modificate](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nella **Interfaccia di amministrazione di Skype for Business**, nel riquadro di navigazione sinistro, vai su **Audioconferenza** e nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.

4. Nella finestra **Reimpostare ID conferenza?**, fai clic su **Sì**. Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati. Questa impostazione è abilitata in modo predefinito

    > [!IMPORTANT]
    >  Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. È necessario informare gli utenti di pianificare di nuovo gli inviti alle riunioni esistenti per assicurarsi che il nuovo ID conferenza venga aggiunto agli inviti. Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento delle riunioni per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

|||UNTRANSLATED_CONTENT_START|||See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).|||UNTRANSLATED_CONTENT_END|||

## <a name="reset-a-conference-organizers-pin"></a>Reimpostare il PIN dell'organizzatore della conferenza

A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. Benché un ID conferenza venga automaticamente creato e assegnato a un utente, può succedere che un utente non desideri utilizzarlo o voglia impostare un determinato numero o che non se lo ricordi o perda l'ID conferenza. È possibile utilizzare l'interfaccia di amministrazione di Skype for Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.


1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.

3. Fai clic su **Utenti**e quindi seleziona l'utente a cui desideri reimpostare il PIN.

4. Nel riquadro Azioni, alla voce **PIN**, fai clic su **Reimposta**.

Gli utenti riceveranno un messaggio di posta elettronica con il nuovo PIN quando essi sono abilitati a entrare nella conferenza o quando il PIN viene reimpostato. Ma se hai disabilitato l'invio automatico di messaggi di posta elettronica, allora il messaggio di posta elettronica di reimpostazione del PIN non verrà inviato agli utenti e dovrai inviare il PIN manualmente. Il PIN verrà visualizzato solo una volta reimpostato. Una volta visualizzato dopo essere stato reimpostato, il PIN non verrà più visualizzato nelle proprietà dell'utente bensì apparirà come *****.

Consulta [Reimpostare il PIN di Audioconferenza](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di Audioconferenza a un utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.

3. Fai clic su **Utenti** e quindi seleziona l'utente a cui desideri reimpostare il PIN.

4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.

    > [!NOTE]
    > Quando fai ciò, il PIN per accedere alla conferenza non viene inviato all'utente.

|||UNTRANSLATED_CONTENT_START|||See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).|||UNTRANSLATED_CONTENT_END|||

## <a name="setting-the-phone-numbers-included-on-invites"></a>Impostare i numeri di telefono inclusi negli inviti

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nel riquadro di navigazione sinistro, vai su  **Audioconferenza** > **Utenti**. Seleziona l'utente che desideri abilitare per le Audioconferenze.

4. Nel riquadro Azioni, è possibile impostare il **Numero a pagamento** e, se permesso, il **Numero verde**.

5. Fai clic su **Salva**.

Consulta [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>La scelta delle impostazioni di ponte per audioconferenza

**Impostare l'esperienza di riunione quando i chiamanti vi partecipano**


1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.

4. Alla voce **esperienza di partecipazione alle riunioni**, seleziona le seguenti operazioni:

  - **Abilita notifiche quando ci si unisce e si abbandona la riunione** Questa impostazione è selezionata in modo predefinito. Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.

    Questo può essere impostato per ogni riunione quando un utente si unisce usando l'app Skype for Business e modifica l'impostazione **Annuncia quando qualcuno si unisce o abbandona** nelle menu delle **Opzioni** della riunione in Skype for Business.

  - **Chiedi agli utenti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, ai chiamanti non verrà richiesto di registrare il proprio nome prima che partecipino a una riunione.

5. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
Consulta [Modificare le impostazioni per un ponte per audioconferenze](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Impostare la lunghezza del PIN per le riunioni**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.

4. Alla voce **Protezione**, immetti il numero di cifre che si desidera utilizzare per il PIN nel campo **Lunghezza del PIN** e quindi fai clic su **Salva**.

    Il codice PIN deve essere compreso tra 4 e 12 cifre. Il numero di cifre predefinito è 5.
    
Consulta [Modificare le impostazioni per un ponte per audioconferenze](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti audio**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fai clic su **Salva**.

    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza facendo clic su **Invia informazioni conferenza tramite posta elettronica**.

    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

    |||UNTRANSLATED_CONTENT_START|||See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).|||UNTRANSLATED_CONTENT_END|||

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare la lingua principale (impostazione predefinita) e secondaria (alternativa) su un ponte per audioconferenza


1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell'**Interfaccia di amministrazione Skype for Business**sulla barra di navigazione sinistra, vai su **Audioconferenza**, e poi fai clic su**Ponte Microsoft**.

4. Seleziona un numero di telefono dall'elenco, fai clic su **Imposta lingue** nel riquadro Azioni e quindi nella pagina **Imposta lingue**, fai clic sull'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate.

    Puoi anche impostare la lingua principale e secondaria supportate quando selezioni Microsoft come fornitore della conferenza. L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate le lingue per i chiamanti.

|||UNTRANSLATED_CONTENT_START|||See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).|||UNTRANSLATED_CONTENT_END|||

## <a name="see-audio-conferencing-dial-in-numbers"></a>Vedere numeri di accesso audioconferenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza** > **Ponte Microsoft**. Qui puoi:

  - Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le Audioconferenze.

  - Visualizzare il percorso e le lingue principale e secondaria che verranno utilizzate per l'operatore automatico di Audioconferenza.

  - Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le Audioconferenze. Ad ogni modo, se il numero telefonico predefinito per il ponte per audioconferenza viene modificato, il numero telefonico predefinito per gli utenti esistenti non verrà modificato.

Puoi andare su **Audioconferenza** > **Utenti** e selezionare le proprietà dell'utente per modificare il numero predefinito per un utente scegliendo un nuovo numero dall'elenco di numeri disponibili nella tua organizzazione.

Consulta [Consultare un elenco di numeri di Audioconferenza](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza** e poi **Utenti**.

Vuoi sapere come gestire queste operazioni con Windows PowerShell?[ ](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Sono disponibili diverse impostazioni per gestire le impostazioni a livello dell'organizzazione tramite Windows PowerShell. In questo modo puoi applicare con facilità tali impostazioni a tutti gli utenti. Ecco le impostazioni a livello dell'organizzazione:

Ci sono diverse impostazioni che puoi gestire a livello di organizzazione utilizzando Windows PowerShell. In questo modo puoi applicare facilmente le impostazioni a tutti gli utenti.

|||UNTRANSLATED_CONTENT_START|||To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).|||UNTRANSLATED_CONTENT_END|||

Di seguito trovi le impostazioni a livello di organizzazione:

- **Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Impostazione di registrazione del nome** Il valore predefinito è _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Impostazione della lunghezza del PIN** Il valore predefinito è 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Impostazione solo partecipazione a riunioni da un telefono** Il valore predefinito è _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Impostazione se si desidera inviare messaggi di posta elettronica agli utenti** Il valore predefinito è _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Impostazione del nome visualizzato per il messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell
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


