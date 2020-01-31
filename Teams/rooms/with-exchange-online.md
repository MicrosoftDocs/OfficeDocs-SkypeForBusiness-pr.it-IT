---
title: Distribuire le sale di Microsoft teams con Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Exchange Online.
ms.openlocfilehash: e53fd2ebd25ef6b625ada84b60d58e42e8c13a28
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628422"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Distribuire le sale di Microsoft teams con Exchange Online

Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Exchange Online e Skype for Business Server locale.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà dalla posizione in cui è ospitato ogni servizio. Questo argomento illustra le distribuzioni ibride per le sale di Microsoft teams con Exchange Hosted online. Dato che sono presenti diverse varianti in questo tipo di distribuzione, non è possibile specificare istruzioni dettagliate per tutti. Il processo seguente funzionerà per molte configurazioni. Se il processo non è adatto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale come documentato qui e per altre opzioni di distribuzione.

Il modo più semplice per configurare gli account utente consiste nel configurarli con Windows PowerShell remoto. Microsoft fornisce [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o di convalidare gli account di risorse esistenti per aiutarli a trasformare gli account utente in Microsoft teams Rooms compatibili. Se si preferisce, è possibile eseguire la procedura seguente per configurare gli account che verranno usati dal dispositivo Microsoft teams rooms.

## <a name="requirements"></a>Requisiti

Prima di distribuire le sale di Microsoft teams con Exchange Online, assicurati di aver soddisfatto i requisiti. Per altre informazioni, Vedi [requisiti di Microsoft teams Rooms](requirements.md).
  
Per distribuire le sale di Microsoft teams con Exchange Online, eseguire la procedura seguente. Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati. 

   > [!NOTE]
   >  I [cmdlet di Azure Active Directory per Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in questa sezione, ad esempio set-MsolUser, sono stati testati in configurazione degli account per i dispositivi Microsoft teams rooms. Tuttavia, è possibile che altri cmdlet possano funzionare, ma non sono stati testati in questo scenario specifico.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Creare un account e impostare le proprietà di Exchange

1. Avviare una sessione remota di Windows PowerShell in un PC e connettersi a Exchange Online nel modo seguente:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. Dopo aver stabilito una sessione, è possibile creare una nuova cassetta postale e abilitarla come RoomMailboxAccount o modificare le impostazioni per una cassetta postale della sala esistente. In questo modo l'account verrà autenticato nelle sale di Microsoft teams.

   Se si sta modificando una cassetta postale di risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se si sta creando una nuova cassetta postale per le risorse:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Per migliorare l'esperienza della riunione, è necessario impostare le proprietà di Exchange nell'account utente nel modo seguente:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Aggiungere un indirizzo di posta elettronica per l'account di dominio locale

1. Nello strumento **Active Directory utenti e computer** , fare clic con il pulsante destro del mouse sul contenitore o l'unità organizzativa in cui verranno creati gli account di Microsoft teams rooms, scegliere **nuovo**e quindi fare clic su **utente**.
2. Digitare il nome visualizzato (-Identity) dal cmdlet Prior (Set-Mailbox o New-Mailbox) nella casella **nome completo** e l'alias nella casella **nome accesso utente** . Fare clic su **Avanti**.
3. Digitare la password per l'account. È necessario ridigitarlo per la verifica. Verificare che la casella di controllo **scadenza password non** sia l'unica opzione selezionata.

    > [!NOTE]
    > La selezione di **password non scade mai** è un requisito per Skype for Business Server in Microsoft teams rooms. Le regole di dominio potrebbero impedire le password che non scadono. In questo caso, è necessario creare un'eccezione per ogni account utente di Microsoft teams rooms.
  
4. Fare clic su **fine** per creare l'account.
5. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Questa operazione può essere eseguita usando [set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell. Al termine, accedere alla pagina utenti e verificare che i due account creati nei passaggi precedenti siano Stati Uniti.

### <a name="assign-an-office-365-license"></a>Assegnare una licenza di Office 365

1. Prima di tutto, Connetti ad Azure AD per applicare alcune impostazioni dell'account. Puoi eseguire questo cmdlet per la connessione. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. L'account utente deve avere una licenza di Office 365 valida per garantire che Exchange e Skype for Business Server funzionino. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account utente, determinando gli SKU di licenza disponibili per il proprio account. Eseguire l'assegnazione in un passaggio successivo.
3. Quindi, USA`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> per recuperare un elenco di SKU disponibili per il tenant di Office 365.
4. Quando si elencano gli SKU, è possibile aggiungere una licenza usando l'`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. In questo caso, $strLicense è il codice SKU visualizzato, ad esempio contoso: STANDARDPACK. 

    ```PowerShell
      Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Abilitare l'account utente con Skype for Business Server

1. Creare una sessione remota di Windows PowerShell da un PC come indicato di seguito:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Per abilitare l'account di Microsoft teams Rooms per Skype for Business Server, eseguire questo comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se non si è certi del valore da usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente di Skype for Business Server esistente con questo comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Assegnare una licenza di Skype for Business Server all'account di Microsoft teams rooms

1. Accedere come amministratore del tenant, aprire il portale di amministrazione di Office 365 e fare clic sull'app di amministrazione.
2. Fare clic su **utenti e gruppi** e quindi su **Aggiungi utenti, Reimposta password e altro ancora**.
3. Fare clic sull'account Microsoft teams Rooms e quindi fare clic sull'icona della penna per modificare le informazioni sull'account.
4. Fare clic su **licenze**.
5. In **assegna licenze**selezionare Skype for business (piano 2) o Skype for business (piano 3), a seconda delle licenze e dei requisiti per la segreteria telefonica aziendale. È necessario usare una licenza di piano 3 Se si vuole usare Enterprise Voice in Microsoft teams rooms.
6. Fai clic su **Salva**.

Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for business per accedere a questo account.

> [!NOTE]
> Se attualmente si usano SKU E1, E3, E4 o E5 con Skype for Business Plan 2 con servizi di audioconferenza o con il sistema telefonico Office 365 e un piano per le chiamate, questi continueranno a funzionare. Tuttavia, è consigliabile passare a un modello di licenze più semplice, come descritto in [Teams Meeting Room Update Licensing](rooms-licensing.md), dopo la scadenza delle licenze correnti.

> [!IMPORTANT]
> Se si usa Skype for Business Plan 2, è possibile usare solo le sale di Microsoft teams in modalità solo Skype for business, quindi tutte le riunioni saranno riunioni Skype for business. Per abilitare la sala riunioni per le riunioni di Microsoft teams, ti consigliamo di acquistare la licenza della sala riunioni.
  
## <a name="see-also"></a>Vedere anche

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Pianificare le sale di Microsoft Teams](rooms-plan.md)
  
[Distribuire le sale di Microsoft Teams](rooms-deploy.md)
  
[Configurare una console Microsoft teams rooms](console.md)
  
[Gestire le sale di Microsoft Teams](rooms-manage.md)
