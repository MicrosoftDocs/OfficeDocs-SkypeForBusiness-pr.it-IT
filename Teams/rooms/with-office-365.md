---
title: Creare account delle risorse per le chat room e i dispositivi Teams condivisi
ms.author: czawideh
author: cazawideh
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
description: Leggere questo articolo per informazioni su come creare account delle risorse per sale e dispositivi condivisi, tra cui Microsoft Teams Rooms, Teams Rooms su Surface Hub e hot desk su Teams display.
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514547"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Creare e configurare account delle risorse per le chat room e i dispositivi Teams condivisi

Questo articolo illustra i passaggi per creare account delle risorse per spazi e dispositivi condivisi e include la procedura per configurare gli account delle risorse per Microsoft Teams Rooms in Windows, Teams Rooms in Android, Teams Rooms su Surface Hub e hot desking su Teams visualizzato.

Microsoft 365 account delle risorse sono account Teams cassette postali e di posta elettronica dedicati a risorse specifiche, ad esempio una sala o un proiettore. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite al momento della creazione. Ad esempio, se si ha una risorsa comune, ad esempio una sala riunioni, è possibile configurare un account della risorsa per tale sala riunioni che accetti o rifiuti automaticamente gli inviti alle riunioni a seconda della disponibilità del calendario.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> Se è necessario abilitare l'account delle risorse per l'Skype for Business, vedere Distribuire Microsoft Teams Rooms [con Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="requirements"></a>Requisiti

A seconda dell'ambiente, è necessario uno o più ruoli per creare gli account delle risorse.

|**Ambiente**|**Ruoli obbligatori**|
|-----|-----|
|Azure Active Directory  <br/> |Amministratore globale o Amministratore utente  <br/> |
|Active Directory  <br/> |Active Directory Enterprise amministratori, amministratori di dominio o hanno diritti delegati per creare utenti. Azure Active Directory Connessione diritti di sincronizzazione.  <br/> |
|Exchange Online  <br/> |Amministratore globale o amministratore Exchange amministratore   <br/> |
|Exchange Server  <br/> |Exchange Gestione organizzazione o Gestione destinatari   <br/> |

Se si creano account delle risorse per Teams Rooms, l'UPN deve corrispondere all'indirizzo SMTP dell'account della risorsa. Vedere [Microsoft Teams Rooms requisiti prima](requirements.md) di distribuire Teams Rooms.

### <a name="what-license-do-you-need"></a>Quale licenza ti serve?

Prima di creare un account Microsoft 365 risorsa, verificare il tipo di licenza necessario:

- **Teams** riunioni Se si vuole associare l'account della risorsa a un dispositivo condiviso, ad esempio una sala di Microsoft Teams o uno schermo Teams con l'hot desking, e usarlo per partecipare a una riunione di Teams in modo che i partecipanti possano usarlo per presentare video e audio tramite di essa, è necessaria una licenza Sala riunioni. Per altre informazioni sulle licenze per le sale riunioni, vedere Teams Sala riunioni [licenze](rooms-licensing.md).

- **Chiamate PSTN** Se si vuole che la risorsa eseere o riceva chiamate da o verso un numero di telefono esterno , denominato rete telefonica a commutazione pubblica o chiamata PSTN, è necessario disporre di una licenza Microsoft 365 Sistema telefonico o Microsoft 365 Business Voice telefonica. È necessario completare il passaggio 1 solo nella panoramica seguente. Per altre informazioni, [Microsoft Teams licenze per i componenti](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) aggiuntivi.

- Se si usa solo un account&mdash;&mdash; delle risorse per prenotare una risorsa, invitare la risorsa alla riunione e fare in modo che accetti o rifiuti automaticamente l'invito non è necessario assegnare una licenza all'account della risorsa ed è necessario completare il passaggio 1 solo nella panoramica seguente.  

## <a name="overview"></a>Panoramica

**Passaggio 1: creare** [un nuovo account della risorsa](#create-a-resource-account). Oppure, se esiste già una cassetta postale della chat room e si vuole convertirla in un account delle risorse, è possibile modificare una cassetta [postale Exchange locale](?tabs=existing-account#create-a-resource-account) esistente.

**Passaggio 2 -**  Quindi, [configurare l'account](#configure-mailbox-properties) per Teams riunioni.

**Passaggio 3 -**  Se l'account della risorsa verrà associato a un dispositivo condiviso, ad esempio Teams con hot desking, [disattivare la scadenza della password](#turn-off-password-expiration).

**Passaggio 4 -**  Infine, [assegnare una licenza per la sala riunioni in](#assign-a-meeting-room-license) modo che l'account possa accedere Microsoft Teams.

Dopo aver creato e configurato gli account delle risorse, [](#next-steps) vedere Passaggi successivi per esaminare altre attività di configurazione, inclusi i gruppi di distribuzione, le funzionalità di rete e le chiamate.

## <a name="create-a-resource-account"></a>Creare un account della risorsa

> [!TIP]
> Quando si assegna un nome agli account delle risorse, è consigliabile usare una convenzione di denominazione standard all'inizio dell'indirizzo di posta elettronica. In questo modo è possibile creare gruppi dinamici per semplificare la gestione in Azure Active Directory. Ad esempio, è possibile usare "mtr-" per tutti gli account delle risorse che verranno associati a Microsoft Teams Rooms.

> [!TIP]
> È consigliabile creare tutti gli account delle risorse usando Exchange Online e Azure Active Directory.

Creare un account della risorsa usando un metodo da una delle schede seguenti:

#### <a name="in-microsoft-365-admin-center"></a>[**In interfaccia di amministrazione di Microsoft 365**](#tab/m365-admin-center)

1. Accedere all'interfaccia di amministrazione di Microsoft 365.

2. Specificare le credenziali di amministratore per il tenant Microsoft 365 tenant.

3. Passare a **Risorse** nel riquadro sinistro e quindi selezionare & **apparecchiature**. Se queste opzioni non sono disponibili nel riquadro sinistro, potrebbe essere necessario selezionare **Prima Mostra** tutto.

4. Selezionare **Aggiungi una cassetta postale della risorsa** per creare un nuovo account della chat room. Immettere un nome visualizzato e un indirizzo di posta elettronica per l'account, selezionare **Aggiungi** e quindi selezionare **Chiudi**.

5. Per impostazione predefinita, gli account delle risorse sono configurati con le impostazioni seguenti:

    - Consentire riunioni ripetute
    - Rifiutare automaticamente le riunioni al di fuori dei limiti seguenti
      - Finestra di prenotazione (giorni): 180
      - Durata massima (ore): 24
    - Accettare automaticamente convocazioni di riunione

    Per modificarle, selezionare Imposta **opzioni di pianificazione** prima di selezionare **Chiudi**. Se si vuole modificarle in un secondo momento, passare a **ResourcesRooms** >  **& attrezzature**, selezionare l'account della risorsa. In Opzioni **di prenotazione** selezionare **Modifica**.

6. Passare a **UtentiAttivi** >  utenti e selezionare la chat room creata per aprire il riquadro delle proprietà.

7. Assegnare quindi una password all'account della risorsa. Nel riquadro selezionare Reimposta **password**.
 
8. Se si richiede agli utenti di cambiare la password in un dispositivo condiviso, si verificano problemi di accesso. Deselezionare **Richiedi all'utente di cambiare la password** al primo accesso e selezionare **Reimposta**.

9. Nella sezione **Licenze e app** impostare Seleziona **posizione** sul paese o sull'area geografica in cui verrà installato il dispositivo. Selezionare quindi la licenza da assegnare, ad esempio Sala riunioni e selezionare **Salva modifiche**. La licenza può variare a seconda dell'organizzazione.

Per modificare le impostazioni della cassetta postale delle risorse, vedere [Configurare le proprietà della cassetta postale](#configure-mailbox-properties) o usare l'Exchange di amministrazione.

Potrebbe anche essere necessario applicare criteri di larghezza di banda o criteri riunione a questo account. Per [altre informazioni, vedere](#next-steps) Passaggi successivi.

#### <a name="with-exchange-online"></a>[**Con Exchange Online**](#tab/exchange-online)

1. Connessione a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Per impostazione predefinita, alle cassette postali della chat room non sono associati account. Aggiungere un account quando si crea una cassetta postale della chat room in modo che possa eseguire l'autenticazione con Microsoft Teams.

    Se si sta creando una nuova cassetta postale per le risorse:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Se non si è in una configurazione ibrida Exchange, è possibile continuare con il passaggio successivo, [Configurare le proprietà della cassetta postale](#configure-mailbox-properties).

Se si è in una configurazione ibrida Exchange, è necessario aggiungere un indirizzo di posta elettronica per l'account di dominio locale. Per [altre informazioni, vedere Sincronizzare](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) le directory degli account utente locali e Office 365 degli account utente.

#### <a name="with-exchange-server"></a>[**Con Exchange Server**](#tab/exchange-server)

  1. Connessione a Exchange Management Shell. [Aprire la Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server di Exchange usando una sessione remota di PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Per creare una nuova cassetta postale della chat room:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

   - Account: ConferenceRoom01@contoso.com
  
   - Nome: ConferenceRoom01

   - Alias: ConferenceRoom01

   - Password dell'account: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificare una cassetta postale Exchange chat room esistente**](#tab/existing-account)

Per modificare una cassetta postale della chat room esistente in modo che diventi un account delle risorse, usare la sintassi seguente:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias ConferenceRoom02 e imposta la password su 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Se si è in una configurazione ibrida Exchange, è necessario aggiungere anche un indirizzo di posta elettronica per l'account di dominio locale. Per [altre informazioni, vedere Sincronizzare](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) le directory degli account utente locali e Office 365 degli account utente.

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se si sta creando questo account per Teams room in Surface Hub, è consigliabile abilitare ActiveSync anche in questo account. In questo modo sarà possibile inviare messaggi di posta elettronica direttamente dal Surface Hub, che è possibile usare per funzionalità come Lavagna. Per [altre informazioni,](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) vedere Applicazione dei criteri di ActiveSync agli account Surface Hub dispositivo.

---

> [!IMPORTANT]
> Se si usa questo account della risorsa solo per prenotare spazio e accettare o rifiutare automaticamente gli inviti, la configurazione è stata completata. Se si usa questo account della risorsa per le chiamate PSTN, vedere Microsoft Teams [licenze](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per i componenti aggiuntivi per determinare la licenza necessaria.
>
> Passare alla sezione successiva solo se l'account della risorsa è per un Teams Rooms in Windows, Teams Rooms in Android, Teams Rooms su Surface Hub o un display Teams con hot desking.

## <a name="configure-mailbox-properties"></a>Configurare le proprietà della cassetta postale

In Exchange PowerShell, online o locale, configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:

- **AutomateProcessing: `AutoAccept`** Gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'uomo.

- **AddOrganizerToSubject: `$false`** L'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione.

- **DeleteComments: `$false`** Conservare il testo nel corpo del messaggio delle convocazioni di riunione in arrivo. Questa operazione è necessaria per elaborare riunioni Teams esterne e di terze parti per offrire un'esperienza One Touch Join.

- **DeleteSubject: `$false`** Mantenere l'oggetto delle convocazioni di riunione in arrivo.

- **ProcessExternalMeetingMessages: `$true`** Specifica se elaborare le convocazioni di riunione che hanno origine all'esterno dell'Exchange aziendale. Obbligatorio per le Teams esterne e [le riunioni di terze parti](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato.

- **AddAdditionalResponse: `$true`** Il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione.

- **AdditionalResponse: "Si tratta di una Microsoft Teams sala riunioni!"** Testo aggiuntivo da aggiungere alla risposta di accettazione della riunione.

Questo esempio configura queste impostazioni in una cassetta postale sala denominata ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Disattivare la scadenza della password

Se la password dell'account della risorsa scade, il dispositivo non accede dopo la data di scadenza. La password dovrà quindi essere modificata per l'account della risorsa e quindi aggiornata in ogni dispositivo. Per evitare questo problema, è possibile disattivare la scadenza della password.
  
> [!NOTE]
> **L'impostazione della password non scade** mai è un requisito per i dispositivi Microsoft Teams condivisi. Se le regole di dominio proibiscono le password che non scadono, è necessario creare un'eccezione per ogni account della risorsa Teams dispositivo.

Seguire i passaggi in una delle schede seguenti per disattivare la scadenza della password:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Prima di tutto, Connessione a PowerShell di Active Directory:

```PowerShell
   Connect-AzureAD
```

Quindi, vedere [Impostare una password in modo che non scada mai](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

Questo esempio imposta la password per l'account ConferenceRoom01@contoso.com non scade mai.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Connessione a PowerShell di MSOnline:

       ```PowerShell
       Connect-MsolService
       ```

       Per informazioni dettagliate su Active Directory, vedere [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Impostare la password in modo che non scada mai usando la sintassi seguente:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Questo esempio imposta la password per l'account ConferenceRoom01@contoso.com non scade mai.

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

    Questo esempio imposta la password per l'account ConferenceRoom01@contoso.com non scade mai.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Assegnare una licenza per una sala riunioni

L'account della risorsa deve avere una Microsoft 365 o Office 365 per accedere a Microsoft Teams.

> [!NOTE]
> Microsoft Teams Rooms Standard e Microsoft Teams Rooms Premium sono i due SKU disponibili per i dispositivi condivisi delle sale riunioni, tra cui Teams Rooms. È necessaria una licenza per la sala riunioni per Teams con hot desking. Per altre informazioni, vedere licenze [Teams sala riunioni](rooms-licensing.md).

Per assegnare licenze usando il interfaccia di amministrazione di Microsoft 365, vedere [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users). Per assegnare licenze Azure AD licenze, vedere una delle schede seguenti:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Connessione a Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Per informazioni dettagliate su Active Directory, [vedere Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Assegnare una posizione di utilizzo all'account delle risorse usando il `Set-AzureADUser` cmdlet. Questo determina quali SKU di licenza sono disponibili.

    In questo esempio l'utente si trova negli Stati Uniti :In this example, the user is located in the United States (US):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Usare quindi per `Get-AzureADSubscribedSku` recuperare un elenco di SKU disponibili per l'Microsoft 365 o Office 365 organizzazione.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Per assegnare la licenza, usare il `Set-AzureADUser` cmdlet e convertire l'ID SKU della licenza (vedere il passaggio 2) in un oggetto tipo di licenza di PowerShell. Assegnare quindi l'oggetto all'account della risorsa. Nell'esempio seguente l'ID SKU della licenza è 6070a4c8-34c6-4937-8dfb-39bbc6397a60 e viene assegnato all'account conferenceroom01@contoso.com:

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

1. Connessione a PowerShell di MSOnline.

   ```PowerShell
   Connect-MsolService
   ```

    Per informazioni dettagliate su Active Directory, vedere [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Assegnare una posizione di utilizzo all'account delle risorse usando il `Set-MsolUser` cmdlet. Questo determina quali SKU di licenza sono disponibili.

    In questo esempio l'utente si trova negli Stati Uniti (Stati Uniti).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    È quindi possibile usare per `Get-MsolAccountSku` recuperare un elenco di SKU disponibili per l'Microsoft 365 o Office 365 organizzazione.

4. Per assegnare la licenza, usare il `Set-MsolUser` cmdlet. In questo esempio la licenza "contoso:MEETING_ROOM" viene assegnata all'account conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Per convalidare la creazione dell'account e l'assegnazione della licenza, accedere a qualsiasi Teams client usando l'account creato.

## <a name="next-steps"></a>Passaggi successivi

### <a name="network-and-bandwidth"></a>Rete e larghezza di banda

Potrebbe essere necessario applicare criteri di rete, larghezza di banda o riunione personalizzati a questo account. Per altre informazioni sui criteri di rete e larghezza di banda, vedere Impostazioni [dei criteri riunione](/microsoftteams/meeting-policies-audio-and-video) per i & video. Per Teams Rooms, è consigliabile impostare la larghezza di banda dei criteri riunione su 10 Mbps.

Per scopi di collaborazione, attivare PowerPoint live, lavagna e note condivise. È possibile creare criteri di riunione per modificare le impostazioni dei partecipanti e dei guest per Teams Rooms. Ad esempio, esaminare le impostazioni della sala d'attesa, ad esempio i partecipanti da ammettere automaticamente alle riunioni. Per altre informazioni sui criteri Teams riunione, vedere [Gestire i criteri riunione in Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Chiamate

Non sono disponibili requisiti univoci per abilitare le chiamate con account delle risorse. L'account della risorsa viene abilitato per le chiamate nello stesso modo in cui si abilita un utente normale.

> [!NOTE]
> È consigliabile disattivare la segreteria telefonica per i dispositivi condivisi assegnando un criterio di chiamata agli account delle risorse del dispositivo. Per [altre informazioni, vedere](../teams-calling-policy.md) Teams chiamate e inoltro di chiamata.

### <a name="configure-distribution-groups"></a>Configurare i gruppi di distribuzione

Per organizzare le posizioni delle sale riunioni, è possibile aggiungere gli account delle risorse del dispositivo ai Exchange di distribuzione. Ad esempio, se si hanno uffici in tre posizioni geografiche diverse, è possibile creare tre gruppi di distribuzione e aggiungere gli account delle risorse appropriati a ogni posizione. Per altre informazioni, vedere [Creare un elenco di chat room](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

## <a name="related-articles"></a>Articoli correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Microsoft Teams Rooms licenze](rooms-licensing.md)
