---
title: "Gestire le impostazioni di audioconferenza per l'organizzazione"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
description: "See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. "
---

# Gestire le impostazioni di audioconferenza per l'organizzazione

Potrebbe essere utile visualizzare tutte le impostazioni di audioconferenza per Skype for Business e Microsoft Teams in un'unica posizione. 
  
## Assegnare una licenza di Audioconferenza

> [!NOTE]
> Per assegnare le licenze, non puoi utilizzare l' **Interfaccia di amministrazione di Skype for Business**, ma devi ricorrere all'interfaccia di amministrazione di Office 365. Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **Per assegnare una licenza a un utente**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell' **interfaccia di amministrazione di Office 365** accedi a **Utenti** > **Utenti attivi** > e quindi seleziona uno o più utenti dall'elenco di utenti disponibili.
    
    > [!NOTE]
    > Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata. Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**. Puoi anche assegnare licenze a più utenti con Windows Powershell. Per le istruzioni e per ottenere script PowerShell di esempio, consulta la sezione [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.
    
4. Nella pagina **Licenze prodotto**, seleziona la casella **Audioconferenza** e quindi fai clic su **Salva**. Per ulteriori informazioni sulle licenze, consulta [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Dopo l'assegnazione, la voce Microsoft potrebbe non risultare inclusa nell'elenco a discesa come provider di servizi di audioconferenza. In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser. 
  
## Assegnare un ID conferenza a un utente

Un ID conferenza viene assegnato automaticamente ad un utente quando gli ID vengono configurati per le audioconferenze utilizzando Microsoft come provider. L'ID conferenza assegnato può essere statico o dinamico e viene inviato nell'invito alla conferenza al momento della pianificazione della conferenza stessa. 
  
Gli ID statici vengono utilizzati nei casi in cui si preferisce non dover ricordare un numero casuale ogni volta, quando si preferisce selezionare un numero specifico o semplicemente se si preferisce avere un numero facile da ricordare. Quando si utilizzano ID dinamici per le conferenze, l'utente riceverà un ID conferenza univoco per ogni riunione pianificata. Se si desidera assegnare ID conferenza dinamici, piuttosto che statici, [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Non puoi usare l'interfaccia di amministrazione di Skype for Business per assegnare un ID conferenza a un utente, mentre puoi usare il cmdlet Windows PowerShell.
  
Per impostare l'ID conferenza per un utente, esegui:
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Un ID conferenza deve contenere 7 cifre e non può essere modificato nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell. 
  
Per ulteriori informazioni sul cmdlet, vedi [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
  
> [!IMPORTANT]
>  Dopo aver creato un nuovo ID conferenza, quello precedente non può più essere usato dai chiamanti. È consigliabile invitare gli utenti a riconfigurare le convocazioni di riunione attuali, in modo da aggiungervi il nuovo ID conferenza. Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti. Per scoprire come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni di Skype for Business, vedi:> [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Consulta [Visualizzare, modificare e ripristinare un ID conferenza assegnato a un utente](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## Modificare il provider di servizi di audioconferenza da Microsoft a un provider di terze parti

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, accedi ad **Audioconferenza telefonica con accesso esterno** > **Utenti** e quindi seleziona l'utente per cui desideri modificare il provider di servizi di audioconferenza.
    
4. Nel riquadro Azione, fai clic su **Modifica**. 
    
5. Nella pagina **Proprietà**, in **Nome provider**, seleziona il provider di servizi di audioconferenza per l'utente.
    
    > [!NOTE]
    > Se hai selezionato più utenti, puoi scegliere solo Microsoft come provider di servizi di audioconferenza o **Nessuno**. 
  
6. Fai clic su **Salva**. 
    
Consulta [Modificare il provider di servizi di conferenza telefonica con accesso esterno per gli utenti](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e).
  
## Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti in audioconferenza

Puoi usare l'interfaccia di amministrazione di Skype for Business o Windows PowerShell per abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti.
  
 **Utilizzo dell'interfaccia di amministrazione di Skype for Business**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedi all' **interfaccia di amministrazione di Office 365** > **Skype for Business** e nella barra di spostamento sinistra fai clic su **Audioconferenza**.
    
3. Nella pagina **Impostazioni bridge Microsoft** seleziona o deseleziona la casella **Invia automaticamente messaggi di posta elettronica agli utenti in caso di modifiche alla configurazione delle audioconferenze**.
    
4. Fai clic su **Salva**.
    
    Puoi anche inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza e facendo clic su **Invia informazioni sulla conferenza tramite posta elettronica**. Nella convocazione di riunione sono inclusi l'ID conferenza e il numero di telefono predefinito per i servizi di conferenza telefonica con accesso esterno, ma non il PIN.
    
    Vedi [Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
 **Uso di Windows PowerShell**
  
- Puoi anche usare Windows PowerShell ed eseguire: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    Puoi usare [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusi i messaggi di posta elettronica.
    
## Modificare le informazioni sul contatto dei mittenti dei messaggi di posta elettronica inviati agli utenti

Puoi apportare modifiche ai messaggi di posta elettronica inviati automaticamente agli utenti con l'indirizzo effettivo e il nome visualizzato delle informazioni sul contatto del mittente. Per impostazione predefinita, il mittente sarà Office 365, ma puoi modificare l'indirizzo di posta elettronica e il nome visualizzato utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285). Per apportare modifiche all'indirizzo di posta elettronica da cui viene inviato il messaggio agli utenti, procedi come segue:
  
- Immetti l'indirizzo di posta elettronica nel parametro  _SendEmailFromAddress_.
    
- Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.
    
- Imposta il parametro  _SendEmailOverride_ su _True_.
    
Puoi apportare modifiche all'e-mail inviata ai tuoi utenti, ad esempio modificando l'indirizzo del mittente o il nome visualizzato, eseguendo
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.
  
Puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusi i messaggi di posta elettronica.
  
Vedi [Messaggi che vengono automaticamente inviati agli utenti quando modificare le impostazioni di conferenze Audio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Reimpostare l'ID conferenza di una riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Audioconferenza** e quindi nel riquadro Azione, in **ID conferenza** fai clic su **Ripristina**.
    
4. Nella finestra **Reimpostare l'ID conferenza?** fai clic su **Sì**. L'ID conferenza viene creato automaticamente e comunicato all'utente tramite e-mail (se l'opzione di invio tramite posta elettronica è abilitata). L'impostazione è abilitata in modo predefinito.
    
    > [!IMPORTANT]
    >  Dopo aver creato un nuovo ID conferenza, quello precedente non può più essere usato dai chiamanti. È consigliabile invitare gli utenti a riconfigurare le convocazioni di riunione attuali, in modo da aggiungervi il nuovo ID conferenza. Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti. Per scoprire come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni di Skype for Business, vedi:> [Meeting Update Tool per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Vedi [Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md)
  
## Reimpostare il PIN dell'organizzatore della conferenza

Gli ID statici vengono utilizzati nei casi in cui si preferisce non dover ricordare un numero casuale ogni volta, quando si preferisce selezionare un numero specifico o semplicemente se si preferisce avere un numero facile da ricordare. Quando si utilizzano ID dinamici per le conferenze, l'utente riceverà un ID conferenza univoco per ogni riunione pianificata. Se si desidera assegnare ID conferenza dinamici, piuttosto che statici, [Utilizzo degli ID dinamici di conferenze Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Sebbene un ID conferenza statico verrà creato e assegnato ad un utente automaticamente, in alcuni casi un utente potrebbe desiderare un numero diverso oppure potrebbe non ricordare più il suo ID conferenza. Utilizzando l'interfaccia di amministrazione di Skype for Business e Windows PowerShell sarà possibile visualizzare, modificare e ripristinare l'ID conferenza.
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedi all' **interfaccia di amministrazione di Office 365** > **Skype for Business** e nella barra di spostamento sinistra fai clic su **Audioconferenza**.
    
3. Fai clic su **Utenti** e seleziona l'utente per cui desideri reimpostare il PIN.
    
4. Nel riquadro Azione, alla voce **PIN**, fai clic su **Reimposta**.
    
Gli utenti riceveranno un messaggio di posta elettronica con il PIN al momento dell'abilitazione per i servizi di audioconferenza o della reimpostazione del PIN. Se invece hai disattivato l'invio automatico dei messaggi di posta elettronica, all'utente non verrà inviato un messaggio di posta elettronica per la reimpostazione del PIN e dovrai inviare manualmente il PIN all'utente. Il PIN viene visualizzato solo dopo la reimpostazione. In seguito non comparirà più nelle proprietà dell'utente e al suo posto verrà visualizzato *****. 
  
Vedi [Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente](reset-the-audio-conferencing-pin-for-a-user.md).
  
## Inviare un messaggio di posta elettronica con le informazioni audioconferenza a un utente

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedi all' **interfaccia di amministrazione di Office 365** > **Skype for Business** e nella barra di spostamento sinistra fai clic su **Audioconferenza**.
    
3. Fai clic su **Utenti** e seleziona l'utente per cui desideri reimpostare il PIN.
    
4. Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
    > [!NOTE]
    > In seguito a questa operazione, il PIN di audioconferenza non viene inviato all'utente. 
  
Vedi [Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
  
## Impostazione del numero di telefono predefinito per i servizi di audioconferenza per gli organizzatori della riunione

 **Per impostare il numero di telefono predefinito per i servizi di audioconferenza per gli organizzatori della riunione quando abiliti un utente per i servizi di audioconferenza**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella barra di spostamento sinistra, passa a **Audioconferenza** > **Utenti**. Seleziona uno o più utenti da rimuovere dalle audioconferenze.
    
4. Nel riquadro Azioni della sezione relativa alle proprietà per l'utente, fai clic su **Modifica**.
    
5. Nella pagina **Proprietà**, in **Nome provider**, seleziona il provider di servizi di audioconferenza nel menu a discesa.
    
  - Se selezioni Microsoft come provider di servizi di audioconferenza, puoi scegliere anche il numero predefinito per i servizi di audioconferenza.  
    
  - Se selezioni un provider di servizi di audioconferenza di terze parti come provider dei servizi di audioconferenza, devi inserire a mano il numero di telefono a pagamento e, se necessario, il numero verde. Questi saranno il numero di telefono predefinito.
    
    Il numero di telefono predefinito per i servizi di audioconferenza è il numero visualizzato nella convocazione di riunione quando viene pianificata una riunione.
    
6. Fai clic su **Salva**.
    
Vedere [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
 **Per impostare il numero di telefono predefinito dopo aver abilitato un utente per i servizi di audioconferenza**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. In **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, accedi a **Servizi di audioconferenza** > **Utenti** e seleziona le voci desiderate. Nella pagina Azioni, fai clic su **Modifica**.
    
4. Nella pagina **Proprietà**, in **Nome provider**, seleziona il provider di servizi di audioconferenza nel menu a discesa.
    
  - Se l'utente utilizza Microsoft come provider di servizi di audioconferenza, puoi scegliere anche il numero predefinito per i servizi di audioconferenza.  
    
  - Se l'utente utilizza un provider di servizi di audioconferenza di terze parti come provider dei servizi di audioconferenza, devi inserire a mano il numero di telefono a pagamento e, se necessario, il numero verde.
    
    Il numero di telefono predefinito per i servizi di audioconferenza è il numero visualizzato nella convocazione di riunione quando viene pianificata una riunione.
    
5. Fai clic su **Salva**.
    
Vedere [Impostare i numeri di telefono di conferenze Audio per organizzatori che sono presenti gli inviti di riunioni](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## Configurare le impostazioni del bridge per i servizi di audioconferenza

 **Impostare l'esperienza della riunione quando i chiamanti vi partecipano**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di audioconferenza** > **Impostazioni bridge Microsoft**.
    
4. In **Esperienza di partecipazione a una riunione**, seleziona le azioni seguenti:
    
  - **Consenti attivazione notifiche di accesso e uscita da una riunione** Questa opzione è selezionata per impostazione predefinita. Se la deselezioni, per impostazione predefinita gli utenti che hanno già eseguito l'accesso alla riunione non ricevono una notifica quando qualcuno entra o esce dalla riunione.
    
    L'impostazione può essere definita di volta in volta quando un utente partecipa a una riunione tramite la app Skype for Business o Microsoft Teams e modifica l'impostazione **Annuncia l'entrata o l'uscita dei partecipanti** nel menu **Opzioni** della riunione Skype o Microsoft Teams.
    
  - **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita. Se la deselezioni, ai chiamanti non sarà richiesto di registrare il proprio nome prima di partecipare a una riunione.
    
5. Dopo aver apportato le modifiche, fai clic su **Salva**.
    
Vedi [Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Impostare la lunghezza dei PIN per le riunioni**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di audioconferenza** > **Impostazioni bridge Microsoft**.
    
4. Alla voce **Sicurezza**, inserisci il numero di cifre desiderato per il PIN in **Lunghezza PIN** e quindi fai clic su **Salva**.
    
    Il PIN deve contenere tra 4 e 12 cifre. Il valore predefinito è 5.
    
Vedi [Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Abilitare o disabilitare l'invio dei messaggi di posta elettronica agli utenti audio**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Accedi all' **interfaccia di amministrazione di Office 365** > **Skype for Business** e nella barra di spostamento sinistra fai clic su **Audioconferenza**.
    
3. Nella pagina **Impostazioni bridge Microsoft** seleziona o deseleziona la casella **Invia automaticamente messaggi di posta elettronica agli utenti in caso di modifiche alla configurazione delle audioconferenze**.
    
4. Fai clic su **Salva**.
    
    Puoi anche inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza e facendo clic su **Invia informazioni sulla conferenza tramite posta elettronica**.
    
    Se esegui questa operazione, il messaggio inviato conterrà solo l'ID conferenza e il numero di telefono della conferenza, ma escluderà il PIN.
    
    Vedi [Inviare un messaggio di posta elettronica a un utente con le informazioni di conferenze Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
## Visualizzare e impostare la lingua principale e le lingue secondarie in un bridge di audioconferenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Audioconferenza** e quindi fai clic su **Bridge Microsoft**.
    
4. Nel riquadro Azioni, seleziona il numero di telefono dall'elenco, fai clic su **Imposta lingue** e quindi, nella pagina **Imposta lingue**, usa l'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate.
    
    Puoi impostare la lingua principale e le lingue secondarie supportate quando selezioni Microsoft come provider dei servizi di conferenza telefonica con accesso esterno. L'ordine di selezione nell'elenco corrisponderà all'ordine delle lingue presentate ai chiamanti.
    
Vedi [Impostazione delle lingue dell'operatore automatico per le conferenze Audio](set-auto-attendant-languages-for-audio-conferencing.md).
  
## Visualizzare i numeri di accesso esterno per i servizi l'audioconferenza

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di audioconferenza** > **Bridge Microsoft**. Qui è possibile:
    
  - Visualizzare i numeri di telefono impostati da Office 365 per l'utilizzo con le audioconferenze. 
    
  - Visualizzare la posizione e le lingue primaria e secondaria che verranno utilizzate dall'operatore automatico di audioconferenza.
    
  - Selezionare il numero di telefono predefinito per i servizi di audioconferenza che sarà assegnato agli utenti quando vengono abilitati per le audioconferenze. Tuttavia, se il numero di telefono predefinito del bridge di audioconferenza viene modificato, il numero di telefono predefinito per gli utenti esistenti non cambierà.
    
Puoi accedere ad **Audioconferenza** > **Utenti** e selezionare le proprietà dell'utente per modificarne il numero predefinito. A tale scopo scegli un nuovo numero dall'elenco dei numeri disponibili nell'organizzazione.
  
Vedi [Visualizzare un elenco di numeri di conferenze Audio](see-a-list-of-audio-conferencing-numbers.md).
  
## Visualizza un elenco di utenti abilitati

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di audioconferenza** > **Utenti**.
    
Vedi [Visualizzare un elenco di utenti abilitati per conferenze Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Sono disponibili diverse impostazioni per gestire le impostazioni a livello dell'organizzazione tramite Windows PowerShell. In questo modo puoi applicare con facilità tali impostazioni a tutti gli utenti. Ecco le impostazioni a livello dell'organizzazione:
    
    Per ulteriori informazioni su ogni cmdlet, consulta [Skype for Business Online cmdlets (Cmdlet di Skype for Business online)](https://go.microsoft.com/fwlink/?LinkId=627324).
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

    Il valore predefinito è  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

    Il valore predefinito è  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

    La lunghezza predefinita è di 5 cifre.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

    Il valore predefinito è  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Il valore predefinito è  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

    Il valore predefinito è  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

    Il valore predefinito è  _$null_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

    Il valore predefinito è  _$null_.
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Perché usare Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## Vedere anche

#### 

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

