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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vedere Skype per operazioni aziendali in linea per assegnare un ID conferenza telefonica con licenza e di conferenza per un utente e molte altre impostazioni di conferenza telefonica. '
ms.openlocfilehash: 55e0e09e9b1b0875fd2ebd19aea5c3ae99392299
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890331"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online

> [!NOTE]
> Se desideri gestire le impostazioni in Teama, consulta [gestire le impostazioni di Audioconferenze per l'organizzazione in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Potrebbe risultare più semplice per poter visualizzare tutte le impostazioni di audioconferenza per Skype for Business in un unico sito.


## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di conferenze Audio

> [!NOTE]
> È possibile assegnare licenze utilizzando **Skype per interfaccia di amministrazione di Business**. È necessario utilizzare l'interfaccia di amministrazione di Office 365. Assegnare un ID conferenza a un utente

 **Per assegnare una licenza per un utente**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Nel riquadro di spostamento sinistro dell' **interfaccia di amministrazione di Office 365**, passare a **utenti** > **utenti attivi**e quindi selezionare l'utente o gli utenti dall'elenco degli utenti disponibili.

    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**. Puoi anche assegnare licenze a più utenti con Windows Powershell. Per istruzioni ed esempi di script PowerShell, vedere [Assegnare Skype per le licenze di Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.

4. Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**. Per ulteriori informazioni sulle licenze, consulta [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Dopo aver assegnato alla licenza, Microsoft potrebbe non viene inizialmente visualizzato nell'elenco come provider di servizi di conferenza audio. In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze con accesso esterno

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fai clic su **Salva**.

    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di conferenza audio verranno le proprietà dell'utente per conferenze audio e facendo clic su **Invia informazioni conferenza tramite posta elettronica**. L'ID e imposta come predefinito audioconferenza numero di telefono conferenza è inclusi nell'invito alla riunione, ma non il PIN.

    [Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Utilizzo di Windows PowerShell**

- You can also use the Windows PowerShell and run:

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    È possibile utilizzare [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti

È possibile apportare modifiche al messaggio di posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente. Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:

- Immettere l'indirizzo di posta elettronica nel parametro _SendEmailFromAddress_ .

- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.

- Imposta il parametro _SendEmailOverride_ su _True_.

Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se desideri modificare le informazioni dell'indirizzo di posta elettronica, devi assicurarti che le politiche interne di posta elettronica della tua organizzazione consentono i messaggi che arrivano da un indirizzo personalizzato.

È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.

Vedere [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nella **Interfaccia di amministrazione di Skype for Business**, nel riquadro di navigazione sinistro, vai su **Audioconferenza** e nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.

4. Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**. Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati. Questa impostazione è abilitata in modo predefinito

    > [!IMPORTANT]
    >  Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

Reimpostare il PIN dell'organizzatore della conferenza

## <a name="reset-a-conference-organizers-pin"></a>Reimpostare il PIN dell'organizzatore della conferenza

A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile quando non da un utente di utilizzare questo e si desidera impostare per un determinato numero o gli utenti non possono ricordare o sono persa loro ID conferenza. È possibile utilizzare l'interfaccia di amministrazione di Skype for Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.


1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.

3. Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.

4. Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.

Gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN. Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN e sarà necessario inviare manualmente il PIN all'utente. The PIN will only be shown once after it has been reset. Dopo che viene visualizzata immediatamente dopo la reimpostazione, il PIN non verrà visualizzato più nella proprietà utente. in realtà, * * * verranno visualizzati.

Vedere [reimpostare il PIN per conferenze Audio](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.

3. Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.

4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.

    > [!NOTE]
    > A tale scopo, conferenze audio PIN non viene inviato all'utente.

[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)

## <a name="setting-the-phone-numbers-included-on-invites"></a>L'impostazione del telefono invita numeri incluso nel

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nel riquadro di navigazione sinistro, vai su  **Audioconferenza** > **Utenti**. Selezionare l'utente che si desidera abilitare per le audioconferenze.

4. Nel riquadro Azioni, è possibile impostare il **Numero a pagamento** e, se permesso, il **Numero verde**.

5. Fai clic su **Salva**.

Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>La scelta delle impostazioni di ponte per audioconferenza

**Impostare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**


1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.

4. Nella sezione **esperienza di partecipazione alle riunioni**, selezionare le seguenti operazioni:

  - **Enable meeting entry and exit notifications to be turned on** This is selected by default. Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.

    Può essere impostata in base a una riunione per riunioni quando un utente partecipa a una riunione con un Skype per applicazioni aziendali e di cui modificare l'impostazione di **annuncio quando vengono inclusi o esclusi** dal menu riunione Skype **Opzioni** della riunione.

  - **Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, ai chiamanti non verrà richiesto di registrare il proprio nome prima che partecipino a una riunione.

5. Dopo aver apportato le modifiche, fai clic su **Salva**.
    
Vedere [modificare le impostazioni per un ponte per conferenze Audio](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Impostare la lunghezza del PIN per le riunioni**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.

4. In **protezione**, immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.

    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.
    
Vedere [modificare le impostazioni per un ponte per conferenze Audio](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Attivare o disattivare la posta elettronica non verrà inviato agli utenti audio**

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fai clic su **Salva**.

    Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia informazioni conferenza tramite posta elettronica**per le proprietà dell'utente per conferenze audio.

    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

    Visualizzare e impostare la lingua principale e le lingue secondarie in un bridge di audioconferenza

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare il primario (impostazione predefinita) e lingue secondarie (alternative) su un ponte per conferenze audio


1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.

4. Selezionare un numero di telefono dall'elenco, fare clic su **Imposta lingue** nel riquadro azioni e quindi nella pagina **gruppo** di lingue, fare clic sull'utilizzo nell'elenco **lingua principale** per visualizzare l'elenco completo delle lingue supportate.

    È inoltre possibile impostare le lingue principale e secondarie supportate quando si seleziona Microsoft come provider di servizi di conferenza audio. L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate le lingue per i chiamanti.

Visualizzare i numeri di accesso esterno per i servizi l'audioconferenza

## <a name="see-audio-conferencing-dial-in-numbers"></a>Vedere audioconferenza numeri di accesso

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **bridge di Microsoft**. Qui puoi:

  - Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le audioconferenze.

  - Visualizzare il percorso e le lingue principale e secondarie che verranno utilizzate per l'operatore automatico di conferenze Audio.

  - Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le audioconferenze. Tuttavia, se viene modificato il numero di telefono predefinito di ponte per conferenze audio, non modifica il numero di telefono predefinito per gli utenti esistenti.

È possibile accedere ai **servizi di conferenza Audio** > **utenti** e selezionare le proprietà dell'utente per modificare il valore predefinito dei numeri per un utente di scegliere un nuovo numero dall'elenco di numeri che sono disponibili all'interno dell'organizzazione.

[Visualizzare un elenco di numeri di conferenza Audio](see-a-list-of-audio-conferencing-numbers.md), vedere.

## <a name="see-a-list-of-users-that-are-enabled"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

2. Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.

3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**> e quindi **utenti**.

Vuoi sapere come gestire queste operazioni con Windows PowerShell?

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Sono disponibili diverse impostazioni per gestire le impostazioni a livello dell'organizzazione tramite Windows PowerShell. In questo modo puoi applicare con facilità tali impostazioni a tutti gli utenti. Ecco le impostazioni a livello dell'organizzazione:

Sono disponibili diverse impostazioni che è possibile gestire a livello di organizzazione tramite Windows PowerShell. In questo modo semplice applicare le impostazioni per tutti gli utenti.

Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:

Di seguito sono le impostazioni a livello di organizzazione:

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


