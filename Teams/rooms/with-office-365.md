---
title: Creare account delle risorse per sale e dispositivi di Teams condivisi
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leggere questo articolo per informazioni su come creare account di risorse per sale e dispositivi condivisi, tra cui Microsoft Teams Rooms, Teams Rooms su Surface Hub e hot desking su schermi Teams.
ms.openlocfilehash: 53d69a5dd91e012bc948bad1b9d7350afcbbb1b2
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760888"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Creare e configurare account di risorse per sale e dispositivi di Teams condivisi

Questo articolo illustra la procedura per creare gli account delle risorse per gli spazi e i dispositivi condivisi e include la procedura per configurare gli account delle risorse per Microsoft Teams Rooms in Windows, Teams Rooms in Android, Teams Rooms in Surface Hub e hot desking su schermi Teams.

Microsoft 365 account delle risorse sono cassette postali e Teams account dedicati a risorse specifiche, ad esempio una sala o un proiettore. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite al momento della creazione. Ad esempio, se si ha una risorsa comune, ad esempio una sala riunioni, è possibile configurare un account di risorsa per la sala riunioni che accetta o rifiuta automaticamente gli inviti alle riunioni in base alla disponibilità del calendario. 

Ogni account delle risorse è univoco per un'installazione Microsoft Teams Rooms o Teams visualizzare l'implementazione di hot desking.

> [!NOTE]
> Se si usano pannelli di Microsoft Teams, l'account della risorsa Teams Rooms accede sia a Teams Rooms che ai pannelli di Teams associati.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> Se è necessario abilitare l'uso dell'account delle risorse con Skype for Business, vedere [Distribuire Microsoft Teams Rooms con Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="requirements"></a>Requisiti

A seconda dell'ambiente, sono necessari uno o più ruoli per creare account delle risorse.

|**Ambiente**|**Ruoli obbligatori**|
|-----|-----|
|Azure Active Directory  <br/> |Amministratore globale o Amministratore utente  <br/> |
|Active Directory  <br/> |Active Directory Enterprise Admins, Domain Admins o hanno diritti delegati per la creazione di utenti. Azure Active Directory Connessione Diritti di sincronizzazione.  <br/> |
|Exchange Online  <br/> |Amministratore globale o amministratore Exchange   <br/> |
|Exchange Server  <br/> |gestione dell'organizzazione o gestione dei destinatari di Exchange   <br/> |

Se si creano account delle risorse per Teams Rooms, l'UPN deve corrispondere all'indirizzo SMTP dell'account della risorsa. Prima di distribuire Teams Rooms, vedere [i requisiti](requirements.md) di Microsoft Teams Rooms.

### <a name="what-license-do-you-need"></a>Di quale licenza hai bisogno?

Prima di creare un account della risorsa Microsoft 365, verificare il tipo di licenza necessario:

- **Teams riunioni** Se si vuole associare l'account della risorsa a un dispositivo condiviso, ad esempio una sala Microsoft Teams o uno schermo Teams con hot desking, e usarlo per partecipare a una riunione Teams in modo che i partecipanti possano usarla per presentare video e audio tramite tale dispositivo, è necessaria una licenza di Sala riunioni. Per altre informazioni sulle licenze per le sale riunioni, vedere [Licenze di Teams Sala riunioni](rooms-licensing.md).

- **Chiamate PSTN** Se si vuole che la risorsa effettui o riceva chiamate da o verso un numero di telefono esterno, ossia una chiamata PSTN o Public Switched Telephone Network, è necessaria una licenza Microsoft 365 Sistema telefonico o Microsoft 365 Business Voice. È sufficiente completare il passaggio 1 nella panoramica seguente. Per altre informazioni, vedere [Microsoft Teams licenze per componenti](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) aggiuntivi.

- Se si usa solo un account della risorsa per prenotare una risorsa&mdash;, invitare la risorsa alla riunione e chiedere che accetti o rifiuti automaticamente l'invito&mdash;che non è necessario assegnare una licenza all'account della risorsa ed è sufficiente completare il passaggio 1 nella panoramica seguente.  

## <a name="overview"></a>Panoramica

**Passaggio 1 -** [Creare un nuovo account delle risorse](#create-a-resource-account). In alternativa, se una cassetta postale della sala esiste già e si vuole convertirla in un account di risorsa, è possibile [modificare una cassetta postale della sala di Exchange esistente](?tabs=existing-account#create-a-resource-account).

**Passaggio 2 -**  Configurare quindi [l'account](#configure-mailbox-properties) per Teams Riunioni.

**Passaggio 3 -**  Se l'account della risorsa verrà associato a un dispositivo condiviso, ad esempio Teams display con hot desking, [disattivare la scadenza della password](#turn-off-password-expiration).

**Passaggio 4 -**  Infine, [assegnare una licenza per la sala riunioni](#assign-a-meeting-room-license) in modo che l'account possa accedere a Microsoft Teams.

Dopo aver creato e configurato gli account delle risorse, vedere [Passaggi successivi](#next-steps) per esaminare altre attività di configurazione, tra cui gruppi di distribuzione, funzionalità di rete e chiamate.

## <a name="create-a-resource-account"></a>Creare un account di risorsa

> [!TIP]
> Quando si denominano gli account delle risorse, è consigliabile usare una convenzione di denominazione standard all'inizio dell'indirizzo di posta elettronica. In questo modo sarà possibile creare gruppi dinamici per semplificare la gestione in Azure Active Directory. Ad esempio, è possibile usare "mtr-" per tutti gli account delle risorse che verranno associati a Microsoft Teams Rooms.

> [!TIP]
> È consigliabile creare tutti gli account delle risorse usando Exchange Online e Azure Active Directory.

Creare un account della risorsa usando un metodo da una delle schede seguenti:

#### <a name="in-microsoft-365-admin-center"></a>[**In interfaccia di amministrazione di Microsoft 365**](#tab/m365-admin-center)

1. Accedere all'interfaccia di amministrazione di Microsoft 365.

2. Fornire le credenziali di amministratore per il tenant di Microsoft 365.

3. Passare a **Risorse** nel riquadro sinistro e quindi selezionare **Sale & apparecchiature**. Se queste opzioni non sono disponibili nel riquadro sinistro, potrebbe essere necessario selezionare **Prima Mostra tutto** .

4. Selezionare **Aggiungi una cassetta postale delle risorse** per creare un nuovo account della chat room. Immetti un nome visualizzato e un indirizzo e-mail per l'account, seleziona **Aggiungi** e quindi **chiudi**.

5. Per impostazione predefinita, gli account delle risorse sono configurati con le impostazioni seguenti:

    - Consentire riunioni di ripetizione
    - Rifiutare automaticamente le riunioni al di fuori dei limiti seguenti
      - Finestra di prenotazione (giorni): 180
      - Durata massima (ore): 24
    - Accettare automaticamente le convocazioni riunione

    Se vuoi modificarle, seleziona **Imposta opzioni di pianificazione** prima di selezionare **Chiudi**. Se si vogliono modificare in un secondo momento, passare a **Sale risorse** > **& apparecchiature**, selezionare l'account della risorsa. In **Opzioni di prenotazione** selezionare **Modifica**.

6. Passare a **Utenti** > **attivi** e selezionare la chat room creata per aprire il riquadro delle proprietà.

7. Assegnare quindi una password all'account della risorsa. Nel riquadro, seleziona **Reimposta password**.
 
8. La richiesta agli utenti di cambiare la password in un dispositivo condiviso causerà problemi di accesso. Deseleziona **Richiedi all'utente di cambiare la password al primo accesso** e seleziona **Reimposta**.

9. Nella sezione **Licenze e app** impostare **Seleziona posizione** sul paese o sull'area geografica in cui verrà installato il dispositivo. Selezionare quindi la licenza da assegnare, ad esempio Sala riunioni, e selezionare **Salva modifiche**. La licenza può variare a seconda dell'organizzazione.

Per modificare le impostazioni della cassetta postale delle risorse, vedere [Configurare le proprietà della cassetta postale](#configure-mailbox-properties) o usare l'interfaccia di amministrazione di Exchange.

Potrebbe anche essere necessario applicare criteri di larghezza di banda o criteri di riunione a questo account. Per altre informazioni [, vedere Passaggi successivi](#next-steps) .

#### <a name="with-exchange-online"></a>[**Con Exchange Online**](#tab/exchange-online)

1. Connessione a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

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

Se non si è in una configurazione ibrida Exchange, è possibile continuare con il passaggio successivo [Configurare le proprietà della cassetta postale](#configure-mailbox-properties).

Se si usa una configurazione ibrida Exchange, è necessario aggiungere un indirizzo di posta elettronica per l'account di dominio locale. Per altre informazioni, vedere [Sincronizzare directory di account utente locali e Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

#### <a name="with-exchange-server"></a>[**Con Exchange Server**](#tab/exchange-server)

  1. Connessione a Exchange Management Shell. [Aprire Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server Exchange tramite una connessione remota di PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

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

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificare una cassetta postale della sala Exchange esistente**](#tab/existing-account)

Per modificare una cassetta postale della sala esistente in modo che diventi un account di risorsa, usare la sintassi seguente:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

In questo esempio viene abilitato l'account per la cassetta postale della sala esistente con il valore alias ConferenceRoom02 e la password viene impostata su 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Se si è in una configurazione ibrida Exchange, è necessario aggiungere anche un indirizzo di posta elettronica per l'account di dominio locale. Per altre informazioni, vedere [Sincronizzare directory di account utente locali e Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se si sta creando questo account per Teams Room in Surface Hub, è consigliabile abilitare ActiveSync anche per questo account. In questo modo sarà possibile inviare messaggi di posta elettronica direttamente dal Surface Hub, che è possibile usare per funzionalità come Whiteboard. Per altre informazioni, vedere [Applicazione dei criteri di ActiveSync agli account dei dispositivi (Surface Hub).](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)

---

> [!IMPORTANT]
> Se si usa questo account della risorsa solo per prenotare spazio e accettare o rifiutare automaticamente gli inviti, la configurazione è stata completata. Se si usa questo account di risorse per le chiamate PSTN, vedere [Microsoft Teams licenze per componenti aggiuntivi](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per determinare la licenza necessaria.
>
> Passare alla sezione successiva solo se l'account della risorsa è destinato a un Teams Rooms in Windows, Teams Rooms in Android, Teams Rooms in Surface Hub o un display Teams con hot desking.

## <a name="configure-mailbox-properties"></a>Configurare le proprietà della cassetta postale

In Exchange PowerShell, online o in locale, configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza di riunione:

- **Automateprocessing: `AutoAccept`** Gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza intervento umano.

- **AddOrganizerToSubject: `$false`** L'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione.

- **DeleteComments: `$false`** Mantenere il testo nel corpo del messaggio delle convocazioni riunione in arrivo. Questa operazione è necessaria per elaborare le riunioni Teams esterne e di terze parti per fornire l'esperienza One Touch Join.

- **DeleteSubject: `$false`** Mantenere l'oggetto delle convocazioni riunione in arrivo.

- **ProcessExternalMeetingMessages: `$true`** Specifica se elaborare le convocazioni riunione provenienti dall'esterno dell'organizzazione Exchange. Obbligatorio per le riunioni Teams esterne e [di terze parti](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga quello specificato.

- **AddAdditionalResponse: `$true`** Il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni riunione.

- **AdditionalResponse: "Questa è una Microsoft Teams sala riunioni!"** Testo aggiuntivo da aggiungere alla risposta di accettazione riunione.

In questo esempio vengono configurate queste impostazioni in una cassetta postale della sala denominata ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Disattivare la scadenza della password

Se la password dell'account delle risorse scade, il dispositivo non eseguirà l'accesso dopo la data di scadenza. La password dovrà quindi essere modificata per l'account della risorsa e quindi aggiornata in ogni dispositivo. Per evitare questo, puoi disattivare la scadenza della password.
  
> [!NOTE]
> L'impostazione della **password non scade mai** è un requisito per i dispositivi Microsoft Teams condivisi. Se le regole di dominio vietano password che non scadono, è necessario creare un'eccezione per ogni Teams account di risorse del dispositivo.

Segui i passaggi descritti in una delle schede seguenti per disattivare la scadenza della password:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Prima di tutto, Connessione a PowerShell di Active Directory:

```PowerShell
   Connect-AzureAD
```

Quindi, vedere [Impostare una password in modo che non scada mai](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

In questo esempio la password dell'account ConferenceRoom01@contoso.com non scade mai.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Connessione a PowerShell per MSOnline:

       ```PowerShell
       Connect-MsolService
       ```

       Per informazioni dettagliate su Active Directory, vedere Azure Active Directory (MSOnline).For details about Active Directory, see [Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Impostare la password in modo che non scada mai usando la sintassi seguente:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In questo esempio la password dell'account ConferenceRoom01@contoso.com non scade mai.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (locale)**](#tab/active-directory1-password/)

1. Connessione a PowerShell di Active Directory:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Per informazioni dettagliate su PowerShell di Active Directory, vedere [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. Impostare la password in modo che non scada mai usando la sintassi seguente:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    In questo esempio la password dell'account ConferenceRoom01@contoso.com non scade mai.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Assegnare una licenza per una sala riunioni

Per accedere a Microsoft Teams, l'account della risorsa deve avere una licenza Microsoft 365 o Office 365.

> [!NOTE]
> Microsoft Teams Rooms Standard e Microsoft Teams Rooms Premium sono i due SKU disponibili per i dispositivi delle sale riunioni condivise, tra cui Teams Rooms. Per gli schermi Teams con hot desking è necessaria una licenza per la sala riunioni. Per altre informazioni, vedere [Teams licenze per le sale riunioni](rooms-licensing.md).

Per assegnare licenze usando il interfaccia di amministrazione di Microsoft 365, vedere [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users). Per assegnare licenze con Azure AD, vedere una delle schede seguenti:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Connessione ad Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Per informazioni dettagliate su Active Directory, vedere [Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Assegnare una posizione di utilizzo all'account delle risorse usando il `Set-AzureADUser` cmdlet. Questo determina quali SKU di licenza sono disponibili.

    In questo esempio l'utente si trova nel Stati Uniti (Stati Uniti):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Quindi, usare `Get-AzureADSubscribedSku` per recuperare un elenco di SKU disponibili per l'Microsoft 365 o l'organizzazione Office 365.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Per assegnare la licenza, usare il `Set-AzureADUser` cmdlet e convertire l'ID SKU della licenza (vedere il passaggio 2) in un oggetto tipo di licenza di PowerShell. Quindi, assegnare l'oggetto all'account della risorsa. Nell'esempio seguente l'ID SKU della licenza è 6070a4c8-34c6-4937-8dfb-39bbc6397a60 e viene assegnato all'account conferenceroom01@contoso.com:

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. Connessione a PowerShell per MSOnline.

   ```PowerShell
   Connect-MsolService
   ```

    Per informazioni dettagliate su Active Directory, vedere [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Assegnare una posizione di utilizzo all'account delle risorse usando il `Set-MsolUser` cmdlet. Questo determina quali SKU di licenza sono disponibili.

    In questo esempio l'utente si trova nel Stati Uniti (Stati Uniti).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    È quindi possibile utilizzare `Get-MsolAccountSku` per recuperare un elenco di SKU disponibili per Microsoft 365 o Office 365 organizzazione.

4. Per assegnare la licenza, usare il `Set-MsolUser` cmdlet. In questo esempio la licenza "contoso:MEETING_ROOM" viene assegnata all'account conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Per convalidare la creazione dell'account e l'assegnazione della licenza, accedere a qualsiasi client Teams usando l'account creato.

## <a name="next-steps"></a>Passaggi successivi

### <a name="meeting-policies"></a>Criteri riunione

Potrebbe essere necessario applicare criteri personalizzati per la rete, la larghezza di banda o le riunioni a questo account. Per altre informazioni sui criteri di rete e larghezza di banda, vedere Impostazioni dei criteri [di riunione per audio & video](/microsoftteams/meeting-policies-audio-and-video). Per Teams Rooms, è consigliabile impostare la larghezza di banda dei criteri di riunione su 10 Mbps.

Per la collaborazione, attivare le note PowerPoint Live, Whiteboard e condivise. È consigliabile abilitare l'impostazione del criterio riunione "Riunione immediata nelle riunioni private". È consigliabile creare criteri di riunione per modificare le impostazioni dei partecipanti e dei guest per Teams Rooms. Ad esempio, esaminare le impostazioni della sala di attesa, ad esempio quelle per i partecipanti a cui si vuole consentire l'accesso automatico alle riunioni. Per altre informazioni sui criteri Teams riunione, vedere [Gestire i criteri riunione in Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Chiamate

Non esistono requisiti univoci per abilitare le chiamate con gli account delle risorse. È possibile abilitare l'account della risorsa per le chiamate allo stesso modo in cui si abilita un utente normale.

> [!NOTE]
> È consigliabile disattivare la segreteria telefonica per i dispositivi condivisi assegnando un criterio di chiamata agli account delle risorse del dispositivo. Per altre informazioni, vedi [Chiamate e inoltro di chiamata in Teams](../teams-calling-policy.md).

### <a name="configure-distribution-groups-for-teams-calendar"></a>Configurare i gruppi di distribuzione per Teams calendario

Per organizzare le posizioni delle sale riunioni, è possibile aggiungere gli account delle risorse del dispositivo a Exchange gruppi di distribuzione. Ad esempio, se si hanno uffici in tre diverse posizioni geografiche, è possibile creare tre gruppi di distribuzione e aggiungere gli account delle risorse appropriati a ogni posizione. Per altre informazioni, vedere [Creare un elenco di sale](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

### <a name="configure-places-for-outlook-calendar"></a>Configurare le posizioni per Calendario di Outlook
Per visualizzare i luoghi delle sale riunioni nel Finder sala Outlook, è necessario usare il cmdlet Set-Place Exchange PowerShell. Non solo Set-Place popola ricerca sala in Outlook, ma consente anche di aggiungere altri metadati, ad esempio la capacità della stanza o il piano di costruzione della stanza. Per altre informazioni, vedere [Set-Place](/powershell/module/exchange/set-place).

## <a name="related-articles"></a>Articoli correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Licenze di Microsoft Teams Rooms](rooms-licensing.md)
