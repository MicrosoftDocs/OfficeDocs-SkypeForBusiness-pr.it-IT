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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Vedere Skype for Business procedura online per assegnare una licenza di conferenza telefonica con accesso esterno e un ID conferenza a un utente e molte altre impostazioni per i servizi di conferenza telefonica con accesso esterno. '
ms.openlocfilehash: 3a0f6d37612c345c8561fbd2a64b4c90fdb27957
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237243"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Se desideri gestire le impostazioni in Teama, consulta [gestire le impostazioni di Audioconferenze per l'organizzazione in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Potrebbe essere più facile visualizzare tutte le impostazioni di audioconferenza Skype for Business in un'unica posizione.


## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di audioconferenza

> [!NOTE]
> Non è possibile assegnare licenze usando **l'Skype for Business di amministrazione.** È necessario usare l'interfaccia Microsoft 365 di amministrazione. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Per assegnare una licenza per un utente**

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione passare a **Utenti** utenti attivi e quindi selezionare l'utente o gli utenti  >  nell'elenco degli utenti disponibili.

    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**. Puoi anche assegnare licenze a più utenti con Windows Powershell. Per istruzioni e script di Esempio di PowerShell, vedere [Assegnare Skype for Business licenze.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.

4. Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**. Per ulteriori informazioni sulle licenze, consulta [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Dopo aver assegnato la licenza, Microsoft potrebbe non comparire inizialmente nell'elenco come provider di servizi di audioconferenza. In questo caso, disconnettersi dall'interfaccia di amministrazione o premere CTRL+F5 per aggiornare la finestra del browser.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Abilitare o disabilitare i messaggi di posta elettronica inviati agli utenti di servizi di audioconferenza

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business** nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fare clic su **Salva**.

    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza passando alle proprietà dei servizi di audioconferenza dell'utente e facendo clic su Invia informazioni conferenza **tramite posta elettronica.** L'ID conferenza e il numero di telefono predefinito per i servizi di audioconferenza sono inclusi nell'invito alla riunione, ma non nel PIN.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Uso di Windows PowerShell**

- You can also use the Windows PowerShell and run:

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    È possibile usare [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviati agli utenti

È possibile apportare modifiche al messaggio di posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente. Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Per apportare modifiche all'indirizzo di posta elettronica che invia il messaggio agli utenti, è necessario:

- Immettere l'indirizzo di posta elettronica nel _parametro SendEmailFromAddress._

- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.

- Imposta il parametro _SendEmailOverride_ su _True_.

Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se desideri modificare le informazioni dell'indirizzo di posta elettronica, devi assicurarti che le politiche interne di posta elettronica della tua organizzazione consentono i messaggi che arrivano da un indirizzo personalizzato.

È possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.

Vedere [Messaggi di posta elettronica inviati automaticamente agli utenti quando cambiano le impostazioni di audioconferenza.](emails-sent-to-users-when-their-settings-change.md)

## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. Nella **Interfaccia di amministrazione di Skype for Business**, nel riquadro di navigazione sinistro, vai su **Audioconferenza** e nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.

4. Nella finestra **Reimposta ID conferenza?** fare clic su **Sì.** Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati. Questa impostazione è abilitata in modo predefinito

    > [!IMPORTANT]
    >  Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Gli utenti possono usare lo strumento Skype for Business migrazione delle riunioni per aggiornare le riunioni esistenti. Per informazioni su come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni di Skype for Business, vedere: Strumento di aggiornamento delle riunioni per [Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype for Business Online, Strumento di migrazione delle riunioni [(64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e strumento di migrazione delle riunioni [(32 bit) di Skype for Business Online.](https://www.microsoft.com/download/details.aspx?id=54079)

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco. Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente non vuole usarlo e si vuole impostarlo su un determinato numero oppure gli utenti non ricordano o non hanno perso l'ID conferenza. È possibile utilizzare l'interfaccia di amministrazione di Skype for Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.


1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business** nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**

3. Fare **clic su** Utenti e quindi selezionare l'utente per cui si vuole reimpostare il PIN.

4. Nel riquadro Azioni, in **PIN,** fare clic su **Reimposta**.

Gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per le audioconferenze o quando il PIN viene reimpostato. Se però l'invio automatico dei messaggi di posta elettronica è stato disabilitato, non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN e sarà necessario inviare manualmente il PIN all'utente. The PIN will only be shown once after it has been reset. Dopo essere stato visualizzato subito dopo la reimpostazione, il PIN non verrà più visualizzato nelle proprietà dell'utente. verrà invece visualizzato ******.

Vedere [Reimpostare il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin.md)

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni sui servizi di audioconferenza a un utente

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business** nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**

3. Fare **clic su** Utenti e quindi selezionare l'utente per cui si vuole reimpostare il PIN.

4. In the Action pane, click **Send conference info via email**.

    > [!NOTE]
    > In questo caso, il PIN dei servizi di audioconferenza non viene inviato all'utente.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Impostazione dei numeri di telefono inclusi per gli inviti

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. Nel riquadro di navigazione sinistro, vai su  **Audioconferenza** > **Utenti**. Selezionare l'utente da abilitare per le audioconferenze.

4. Nel riquadro Azioni, è possibile impostare il **Numero a pagamento** e, se permesso, il **Numero verde**.

5. Fare clic su **Salva**.

Vedere [Impostare i numeri di telefono inclusi per gli inviti.](set-the-phone-numbers-included-on-invites.md)


## <a name="choosing-audio-conferencing-bridge-settings"></a>La scelta delle impostazioni di ponte per audioconferenza

**Impostare l'esperienza della riunione quando i chiamanti aderiscono a una riunione**


1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Impostazioni bridge Microsoft **per audioconferenze.**  >  

4. In **Esperienza di partecipazione alla riunione** selezionare le azioni seguenti:

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. Se si deseleziona questa casella di controllo, gli utenti che hanno già partecipato alla riunione per impostazione predefinita non verranno avvisati quando qualcuno entra o esce dalla riunione.

     Questa impostazione può essere impostata per riunione per riunione quando un utente partecipa a una  riunione con un'app Skype for Business e modifica l'impostazione Annuncia quando le persone entrano o abbandonano nel **menu** Opzioni Riunione Skype della riunione.

   - **Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella di controllo, ai chiamanti non verrà richiesto di registrare il proprio nome prima che partecipino a una riunione.

5. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
Vedere [Modificare le impostazioni per un bridge di audioconferenza.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Impostare la lunghezza del PIN per le riunioni**

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Impostazioni bridge Microsoft **per audioconferenze.**  >  

4. In **Sicurezza** immettere il numero di cifre desiderato per il PIN nell'elenco Lunghezza **PIN** e quindi fare clic su **Salva.**

    Il codice PIN deve essere compreso tra 4 e 12 cifre. The default is 5.
    
Vedere [Modificare le impostazioni per un bridge di audioconferenza.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Abilitare o disabilitare l'invio di posta elettronica agli utenti audio**

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business** nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fare clic su **Salva**.

    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza, passando alle proprietà dei servizi di audioconferenza dell'utente e facendo clic su Invia informazioni conferenza **tramite posta elettronica.**

    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare le lingue principale (predefinita) e secondaria (alternativa) in un bridge di audioconferenza


1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a **Audioconferenza** e quindi fare clic su **Bridge Microsoft.**

4. Selezionare un numero di telefono nell'elenco, fare clic su  Imposta lingue nel riquadro  Azioni e quindi nella pagina Imposta lingue fare clic sull'elenco Usa lingua principale per visualizzare l'elenco completo delle lingue supportate. 

    È anche possibile impostare le lingue principale e secondaria supportate quando si seleziona Microsoft come provider di servizi di audioconferenza. L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate le lingue per i chiamanti.

See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Visualizzare i numeri di accesso esterno per i servizi di audioconferenza

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.
 
3. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Bridge Microsoft **per audioconferenze.**  >   Qui puoi:

   - Visualizzare i numeri di telefono impostati da Microsoft 365 o Office 365 da usare per le audioconferenze.

   - Visualizzare la posizione e le lingue principale e secondaria che verranno usate dall'operatore automatico di audioconferenza.

   - Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando sono abilitati per le audioconferenze. Tuttavia, se il numero di telefono predefinito del bridge di audioconferenza cambia, il numero di telefono predefinito per gli utenti esistenti non cambia.

È possibile passare a Utenti di **audioconferenza** e selezionare le proprietà dell'utente per modificare il numero predefinito per un utente scegliendo un nuovo numero nell'elenco dei numeri disponibili  >   nell'organizzazione.

Vedere [Visualizzare un elenco di numeri di audioconferenza.](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedere con l'account aziendale o dell'istituto di istruzione.

2. Passare all'interfaccia di amministrazione > **Skype for Business**.

3. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Audioconferenza **>** **utenti**.

See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

Esistono diverse impostazioni che è possibile gestire a livello di organizzazione usando Windows PowerShell. In questo modo è facile applicare le impostazioni a tutti gli utenti.

To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).

Ecco le impostazioni a livello di organizzazione:

- **Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Impostazione di registrazione del nome** Il valore predefinito è _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Impostazione della lunghezza del PIN** Il valore predefinito è 5.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Impostazione solo partecipazione a riunioni da un telefono** Il valore predefinito è _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Impostazione se si desidera inviare messaggi di posta elettronica agli utenti** Il valore predefinito è _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Impostazione del nome visualizzato per il messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Per altre informazioni su Windows PowerShell
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto solo all'uso dell'interfaccia di amministrazione, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)

## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user.md)
