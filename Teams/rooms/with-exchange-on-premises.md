---
title: Distribuire Microsoft Teams Rooms con Exchange locale
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leggere questo argomento per informazioni su come distribuire i Microsoft Teams Rooms in un ambiente ibrido con Exchange locale.
ms.openlocfilehash: 5424e670dcea86aff5f3c8842e2ab3e61cfecf480922ac664ac055ea502dbb09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296653"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Distribuire Microsoft Teams Rooms con Exchange locale

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms in un ambiente ibrido con Exchange locale e Microsoft Teams o Skype for Business Online.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento riguarda le distribuzioni ibride Microsoft Teams Rooms con Exchange ospitate in locale. Poiché questo tipo di distribuzione offre molte varianti diverse, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.

Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in modo da trasformarli in account utente Microsoft Teams Rooms compatibili. Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che Microsoft Teams Rooms dispositivo.
  
## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Exchange locale, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)
  
Se si distribuiscono Microsoft Teams Rooms con Exchange locale, si usano gli strumenti di amministrazione di Active Directory per aggiungere un indirizzo di posta elettronica per l'account di dominio locale. Questo account verrà sincronizzato con Microsoft 365 o Office 365. Sarà necessario:
  
- Creare un account e sincronizzare l'account con Active Directory.

- Abilitare la cassetta postale remota e impostare le proprietà.

- Assegnare una Microsoft 365 o Office 365 licenza.

- Abilitare l'account del dispositivo con Skype for Business Server. Per abilitare l'account del dispositivo, l'ambiente dovrà soddisfare i prerequisiti seguenti:

  - È necessario avere Skype for Business Online (Piano 2) o versione successiva nel piano Microsoft 365 o Office 365 piano. Il piano deve supportare la funzionalità di conferenza.
  
  - Se è necessario VoIP aziendale (telefonia PSTN) con provider di servizi di telefonia per Microsoft Teams Rooms è necessario Skype for Business Online (piano 3).

  - Quando si configura un account della chat room con Microsoft Teams o Skype for Business Online, il numero di telefono deve essere assegnato prima che l'account venga abilitato come account della chat room.
  
  - Gli utenti del tenant devono avere Exchange cassette postali.
  
  - L'account Microsoft Teams Rooms richiede una licenza di Skype for Business Online (Piano 2) o Skype for Business Online (Piano 3), ma non richiede una licenza Exchange Online.

- Assegnare una Skype for Business Server licenza all'account Microsoft Teams Rooms account.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Creare un account e sincronizzare con Active Directory

1. Nello strumento Utenti e computer di **Active Directory** fare clic con il pulsante destro del mouse sulla cartella o sull'unità organizzativa in cui verranno creati gli account Microsoft Teams Rooms, fare clic su Nuovo **e** quindi su **Utente.**

2. Digitare il nome visualizzato del cmdlet precedente nella **casella Nome completo** e l'alias nella casella Nome **accesso** utente. Fare clic su **Avanti**.

3. Digitare la password per l'account. Sarà necessario digitare di nuovo per la verifica. Verificare che la **casella di controllo Password non scada** mai sia l'unica opzione selezionata.

    > [!NOTE]
    > La **selezione della password non scade** mai è un requisito per Skype for Business Server in Microsoft Teams Rooms. Le regole di dominio potrebbero proibire le password che non scadono. In questo caso, è necessario creare un'eccezione per ogni account Microsoft Teams Rooms dispositivo.
  
4. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Al termine, passare alla pagina degli utenti del interfaccia di amministrazione di Microsoft 365 e verificare che l'account creato nei passaggi precedenti sia stato unito in online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Abilitare la cassetta postale remota e impostare le proprietà

1. [Aprire la Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server di Exchange tramite Una sessione remota di PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. In Exchange PowerShell creare una cassetta postale per l'account (abilitare l'account tramite cassetta postale) eseguendo il comando seguente:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. In Exchange PowerShell configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'utente: free = accept; busy = decline).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Si tratta di una Riunione Skype room!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Assegnare una Microsoft 365 o Office 365 licenza

1. Connessione a Azure Active Directory. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

2. L'account del dispositivo deve avere una licenza Microsoft 365 o Office 365, oppure Exchange e Microsoft Teams non funzionerà. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Successivamente, è possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. In questo caso, $strLicense codice SKU visualizzato, ad esempio contoso:STANDARDPACK.

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>Abilitare l'account del dispositivo

Skype for Business PowerShell online viene usato per gestire i servizi per Microsoft Teams e Skype for Business Online.

1. Creare una sessione Windows PowerShell remota da un PC come segue:
> [!NOTE]
> Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente.
>
> Se si usa la versione pubblica più [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. Ottenere l'indirizzo SIP dell'account:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **Facoltativo.** Se si vuole assegnare un numero di telefono all'account, l'operazione deve essere eseguita a questo punto. Se si vuole assegnare un numero di telefono instradamento diretto:

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    Se si sta assegnando un numero di telefono fornito da Microsoft, usare il cmdlet seguente dopo aver eseguito il provisioning dell'utente con una licenza per il piano di chiamata:
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. Per abilitare l'account Microsoft Teams Rooms, eseguire questo comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se non si sa quale valore usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente esistente usando questo comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Assegnare una licenza all'account Microsoft Teams Rooms account

1. Accedere come amministratore tenant, aprire il interfaccia di amministrazione di Microsoft 365 e fare clic sull'app Amministratore.
2. Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, reimpostazione password e altro ancora.**
3. Fare clic sull Microsoft Teams Rooms account e quindi fare clic sull'icona della penna per modificare le informazioni dell'account.
4. Fare clic **su Licenze**.
5. In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e VoIP aziendale requisiti. È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale nel Microsoft Teams Rooms.
6. Fare clic su **Salva**.

Per la convalida, dovrebbe essere possibile usare qualsiasi client per accedere a questo account.
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).