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
description: 'Vedere i passaggi di Skype for business online per assegnare una licenza di conferenza telefonica con accesso esterno a un utente e molte altre impostazioni per i servizi di conferenza telefonica con accesso esterno. '
ms.openlocfilehash: 9567c8234c0ef7a5b65c5894666747eab3cff7a5
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777981"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online

> [!NOTE]
> Se desideri gestire le impostazioni in Teama, consulta [gestire le impostazioni di Audioconferenze per l'organizzazione in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Potrebbe essere più semplice visualizzare tutte le impostazioni di audioconferenza per Skype for business in un'unica posizione.


## <a name="assign-an-audio-conferencing-license"></a>Assegnare una licenza di audioconferenza

> [!NOTE]
> Non è possibile assegnare licenze usando l'interfaccia **di amministrazione di Skype for business**. È necessario usare l'interfaccia di amministrazione di Microsoft 365. Vedere [assegnare le licenze di Skype for business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Per assegnare una licenza per un utente**

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione, passa **a** > utenti**attivi**degli utenti e quindi seleziona l'utente o gli utenti dall'elenco degli utenti disponibili.

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Dopo aver assegnato la licenza, Microsoft potrebbe non essere visualizzata inizialmente nell'elenco come provider di servizi di audioconferenza. In questo caso, disconnettersi dall'interfaccia di amministrazione oppure premere CTRL + F5 per aggiornare la finestra del browser.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Abilitare o disabilitare i messaggi di posta elettronica inviati agli utenti di servizi di audioconferenza

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business** e nella barra di spostamento sinistra fare clic su servizi di **audioconferenza**.

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fare clic su **Salva**.

    You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Uso di Windows PowerShell**

- You can also use the Windows PowerShell and run:

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Puoi usare il [set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) per gestire altre impostazioni per l'organizzazione, incluso il messaggio di posta elettronica.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviati agli utenti

You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet. To make changes to the email address that is sending the email to the users, you must:

- Immettere l'indirizzo di posta elettronica nel parametro _SendEmailFromAddress_ .

- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.

- Imposta il parametro _SendEmailOverride_ su _True_.

Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se desideri modificare le informazioni dell'indirizzo di posta elettronica, devi assicurarti che le politiche interne di posta elettronica della tua organizzazione consentono i messaggi che arrivano da un indirizzo personalizzato.

Puoi usare il cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) per gestire altre impostazioni per l'organizzazione, incluso il messaggio di posta elettronica.

Vedere [i messaggi di posta elettronica inviati automaticamente agli utenti quando cambiano le impostazioni dei servizi di audioconferenza](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business**.

3. Nella **Interfaccia di amministrazione di Skype for Business**, nel riquadro di navigazione sinistro, vai su **Audioconferenza** e nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business** e nella barra di spostamento sinistra fare clic su servizi di **audioconferenza**.

3. Fare clic su **utenti**e quindi selezionare l'utente per cui si vuole reimpostare il PIN.

4. Nel riquadro azioni, in **pin**, fare clic su **Reimposta**.

Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.

Vedere [reimpostare il pin per la conferenza audio](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Inviare un messaggio di posta elettronica con informazioni per i servizi di audioconferenza a un utente

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business** e nella barra di spostamento sinistra fare clic su servizi di **audioconferenza**.

3. Fare clic su **utenti**e quindi selezionare l'utente per cui si vuole reimpostare il PIN.

4. In the Action pane, click **Send conference info via email**.

    > [!NOTE]
    > Quando si esegue questa operazione, il PIN per audioconferenza non viene inviato all'utente.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Impostazione dei numeri di telefono inclusi negli inviti

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business**.

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. Nel riquadro Azioni, è possibile impostare il **Numero a pagamento** e, se permesso, il **Numero verde**.

5. Fare clic su **Salva**.

Vedere [impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>La scelta delle impostazioni di ponte per audioconferenza

**Impostare l'esperienza della riunione quando i chiamanti partecipano a una riunione**


1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business**.

3. Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, **Vai a** > **impostazioni di Microsoft Bridge**per audioconferenza.

4. In **esperienza di partecipazione a una riunione**selezionare le azioni seguenti:

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     Questa operazione può essere impostata in base a una riunione per riunione quando un utente partecipa a una riunione con un'app Skype for business e modifica l'opzione **annuncia quando le persone entrano o lasciano** l'impostazione nel menu **Opzioni** riunione Skype della riunione.

   - **Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.

5. Vedi **Modificare le impostazioni per un bridge per audioconferenza**.
    
Vedere [modificare le impostazioni per un Bridge di audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Impostare la lunghezza del PIN per le riunioni**

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business**.

3. Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, **Vai a** > **impostazioni di Microsoft Bridge**per audioconferenza.

4. In **sicurezza**immettere il numero di cifre desiderato per il PIN nell'elenco **lunghezza PIN** e quindi fare clic su **Salva**.

    The PIN must be between 4 and 12 digits. The default is 5.
    
Vedere [modificare le impostazioni per un Bridge di audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti audio**

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business** e nella barra di spostamento sinistra fare clic su servizi di **audioconferenza**.

3. Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.

4. Fare clic su **Salva**.

    È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza, passando alle proprietà dei servizi di audioconferenza dell'utente e facendo clic su **Invia informazioni sulla conferenza tramite posta elettronica**.

    Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Visualizzare e impostare le lingue primarie (predefinite) e secondarie (Alternate) in un Bridge di audioconferenza


1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business**.

3. Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, passa a servizi di **audioconferenza**e quindi fai clic su **Bridge Microsoft**.

4. Selezionare un numero di telefono nell'elenco, fare clic su **imposta lingue** nel riquadro azioni, quindi nella pagina **set languages** fare clic sull'elenco Usa la **lingua principale** per visualizzare l'elenco completo delle lingue supportate.

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Visualizzare i numeri di accesso esterno per i servizi di audioconferenza

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - Visualizzare i numeri di telefono impostati da Office 365 per l'uso di servizi di audioconferenza.

   - Visualizzare la posizione e le lingue primarie e secondarie, che verranno usate dall'operatore automatico di audioconferenza.

   - Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.

È possibile accedere agli **Audio conferencing** > **utenti** di servizi di audioconferenza e selezionare le proprietà dell'utente per modificare il numero predefinito di un utente scegliendo un nuovo numero dall'elenco di numeri disponibili nell'organizzazione.

Vedere [visualizzare un elenco di numeri di conferenza audio](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.

1. Accedere con l'account di lavoro o dell'Istituto di istruzione.

2. Accedere all'interfaccia di amministrazione > **Skype for business**.

3. Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, passa a **audioconferenza**> e quindi **agli utenti**.

See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).

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

  ## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:

  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)

## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per un utente](manage-the-audio-conferencing-settings-for-a-user.md)


