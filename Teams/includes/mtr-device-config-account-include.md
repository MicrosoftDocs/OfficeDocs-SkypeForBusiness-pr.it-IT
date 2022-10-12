
Ogni dispositivo Microsoft Teams Rooms necessita di un proprio account delle risorse. L'account della risorsa è l'account a cui accede il dispositivo Teams Rooms ed è ciò che gli utenti dell'organizzazione invitano a prenotare teams room.

Quando si crea la cassetta postale delle risorse, è possibile specificare se consentire le riunioni ricorrenti, impostare la sala per l'accettazione automatica degli inviti, il numero di giorni futuri per accettare gli inviti e così via.

> [!TIP]
> Quando si denominano gli account delle risorse, è consigliabile usare una convenzione di denominazione standard all'inizio dell'indirizzo di posta elettronica. Ciò consentirà di creare gruppi dinamici per semplificare la gestione in Azure Active Directory. Ad esempio, è possibile usare "mtr-" per tutti gli account delle risorse che verranno associati a Microsoft Teams Rooms.

> [!TIP]
> È consigliabile creare tutti gli account delle risorse usando Exchange Online e Azure Active Directory.

Creare un account della risorsa usando un metodo da una delle schede seguenti:

#### <a name="in-microsoft-365-admin-center"></a>[**In interfaccia di amministrazione di Microsoft 365**](#tab/m365-admin-center)

1. Accedere all'interfaccia di amministrazione di Microsoft 365.

2. Fornire le credenziali di amministratore per il tenant di Microsoft 365.

3. Passare a **Risorse** nel riquadro sinistro e quindi selezionare **Sale & apparecchiature**. Se queste opzioni non sono disponibili nel riquadro sinistro, potrebbe essere necessario selezionare **Prima Mostra tutto** .

4. Selezionare **Aggiungi risorsa** per creare un nuovo account di risorsa. Immettere un nome visualizzato e un indirizzo di posta elettronica per l'account e quindi selezionare **Salva**.

5. Per impostazione predefinita, gli account delle risorse sono configurati con le impostazioni seguenti:

    - Consentire riunioni di ripetizione
    - Rifiutare automaticamente le riunioni al di fuori dei limiti seguenti
      - Finestra di prenotazione (giorni): 180
      - Durata massima (ore): 24
    - Accettare automaticamente le convocazioni riunione

    Se si vogliono modificare, selezionare **Modifica opzioni di prenotazione** prima di selezionare **Chiudi**. Se si vogliono modificare in un secondo momento, passare a **Sale risorse** > **& apparecchiature**, selezionare l'account della risorsa. In **Opzioni di prenotazione** selezionare **Modifica**.

6. Passare a **Utenti** > **attivi** e selezionare la chat room creata per aprire il riquadro delle proprietà.

7. Assegnare quindi una password all'account della risorsa. Nel riquadro, seleziona **Reimposta password**.

8. La richiesta agli utenti di cambiare la password in un dispositivo condiviso causerà problemi di accesso. Deseleziona **Richiedi all'utente di cambiare la password al primo accesso** e seleziona **Reimposta password**.

Potrebbe anche essere necessario applicare criteri di larghezza di banda o criteri di riunione a questo account. È possibile impostare i criteri cassetta postale in un passaggio successivo.

#### <a name="with-exchange-online"></a>[**Con Exchange Online**](#tab/exchange-online)

1. Connettersi a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Per impostazione predefinita, le cassette postali della sala non hanno account associati. Aggiungere un account quando si crea una cassetta postale della sala in modo che possa eseguire l'autenticazione con Microsoft Teams.

    Se si sta creando una nuova cassetta postale delle risorse:

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    In questo esempio viene creata una nuova cassetta postale della sala con le impostazioni seguenti:

    - Account: ConferenceRoom01@contoso.com

    - Nome: Sala Conferenze01

    - Alias: ConferenceRoom01

    - Password account: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Se si usa una configurazione ibrida di Exchange, è necessario aggiungere un indirizzo di posta elettronica per l'account di dominio locale. Per altre informazioni, vedere [Sincronizzare directory di account utente locali e Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

#### <a name="with-exchange-server"></a>[**Con Exchange Server**](#tab/exchange-server)

  1. Connettersi a Exchange Management Shell. [Aprire Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server Exchange tramite una connessione remota di PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

  2. Per creare una nuova cassetta postale della sala:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```

      In questo esempio viene creata una nuova cassetta postale della sala con le impostazioni seguenti:

      - Account: ConferenceRoom01@contoso.com

      - Nome: Sala Conferenze01

      - Alias: ConferenceRoom01

      - Password account: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificare una cassetta postale della sala di Exchange esistente**](#tab/existing-account)

Per modificare una cassetta postale della sala esistente in modo che diventi un account di risorsa, usare la sintassi seguente:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

In questo esempio viene abilitato l'account per la cassetta postale della sala esistente con il valore alias ConferenceRoom02 e la password viene impostata su 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Se si è in una configurazione ibrida di Exchange, è necessario aggiungere anche un indirizzo di posta elettronica per l'account di dominio locale. Per altre informazioni, vedere [Sincronizzare directory di account utente locali e Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se stai creando questo account per Teams Room su Surface Hub, devi anche abilitare ActiveSync per questo account. In questo modo potrai inviare e-mail direttamente da Surface Hub, che potrai usare per funzionalità come Whiteboard. Per ulteriori informazioni, vedi [Applicazione dei criteri di ActiveSync agli account dei dispositivi (Surface Hub).](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)

---

> [!IMPORTANT]
> Se si usa questo account della risorsa solo per prenotare spazio e accettare o rifiutare automaticamente gli inviti, la configurazione è stata completata. Se si usa questo account di risorse per le chiamate PSTN, vedere [Licenze per i componenti aggiuntivi di Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per determinare la licenza necessaria.
