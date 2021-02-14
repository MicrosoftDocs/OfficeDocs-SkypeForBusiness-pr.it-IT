---
title: Distribuire sale di Microsoft Teams con Exchange Online
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams con Exchange Online e Skype for Business Server locale.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662311"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Distribuire sale di Microsoft Teams con Exchange Online

Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams con Exchange Online e Skype for Business Server locale.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento illustra le distribuzioni ibride per le sale di Microsoft Teams con Exchange ospitato online. Poiché esistono così tante varianti diverse in questo tipo di distribuzione, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale illustrato qui e per altre opzioni di distribuzione.

Il modo più semplice per configurare gli account utente è configurarli usando gli account Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in essere per trasformarli in account utente di Microsoft Teams Room compatibili. Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno utilizzati dal dispositivo Microsoft Teams Rooms.

## <a name="requirements"></a>Requisiti

Prima di distribuire le sale di Microsoft Teams con Exchange Online, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere Requisiti [di Sale di Microsoft Teams.](requirements.md)
  
Per distribuire sale di Microsoft Teams con Exchange Online, seguire la procedura seguente. Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati. 

   > [!NOTE]
   >  I [cmdlet di Azure Active Directory Module for Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in questa sezione (ad esempio Set-MsolUser) sono stati testati nella configurazione degli account per i dispositivi Microsoft Teams Rooms. È possibile che altri cmdlet funzionino, tuttavia, non sono stati testati in questo scenario specifico.

Se è stato distribuito Active Directory Federation Services (ADFS), potrebbe essere necessario convertire l'account utente in un utente gestito prima di eseguire questa procedura e quindi convertirlo di nuovo in un utente federato dopo aver completato questa procedura.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Creare un account e impostare le proprietà di Exchange

1. Avviare una sessione Windows PowerShell remota in un PC e connettersi a Exchange Online come segue:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Dopo aver stabilito una sessione, è necessario creare una nuova cassetta postale e abilitarla come RoomMailboxAccount oppure modificare le impostazioni di una cassetta postale della sala esistente. In questo modo l'account verrà autenticato nelle sale di Microsoft Teams.

   Se si sta modificando una cassetta postale delle risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se si sta creando una nuova cassetta postale delle risorse:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Per migliorare l'esperienza della riunione, è necessario impostare le proprietà di Exchange per l'account utente nel modo seguente:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Aggiungere un indirizzo di posta elettronica per l'account di dominio locale

1. Nello **strumento Active Directory Users and Computers AD** fare clic con il pulsante destro del mouse sul contenitore o sull'unità organizzativa in cui verranno creati gli account di Microsoft Teams Room, fare clic su **Nuovo** e quindi su **Utente.**
2. Digitare il nome visualizzato (- Identità) del cmdlet precedente (Set-Mailbox o New-Mailbox) nella casella Nome completo e l'alias nella casella Nome **accesso** utente.  Fare clic su **Avanti**.
3. Digitare la password dell'account. Sarà necessario digitare di nuovo l'elemento per la verifica. Verificare che la **casella di controllo Password senza scadenza** sia l'unica opzione selezionata.

    > [!NOTE]
    > La **selezione di Password senza scadenza** è un requisito per Skype for Business Server nelle sale di Microsoft Teams. Le regole di dominio possono impedire le password che non scadono. In questo caso, sarà necessario creare un'eccezione per ogni account utente di Microsoft Teams Rooms.
  
4. Fare **clic su** Fine per creare l'account.
5. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Questa operazione può essere eseguita con [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell. Al termine, passare alla pagina degli utenti e verificare che i due account creati nei passaggi precedenti siano stati uniti.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Assegnare una licenza di Microsoft 365 o Office 365

1. Prima di tutto, connettersi ad Azure AD per applicare alcune impostazioni dell'account. È possibile eseguire questo cmdlet per connettersi. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. L'account utente deve avere una licenza valida di Microsoft 365 o Office 365 per assicurarsi che Exchange e Skype for Business Server funzionino correttamente. Se si dispone della licenza, è necessario assegnare una posizione di utilizzo al proprio account utente, che determina quali SKU di licenza sono disponibili per il proprio account. Per eseguire l'attività, eseguire un passaggio successivo.
3. Usa quindi `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> per recuperare un elenco di SKU disponibili per l'organizzazione di Microsoft 365 o Office 365.
4. Dopo aver elencato gli SKU, puoi aggiungere una licenza usando il `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. In questo caso, $strLicense è il codice SKU visualizzato (ad esempio, contoso:STANDARDPACK). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Abilitare l'account utente con Skype for Business Server

1. Per creare una sessione Windows PowerShell remota da un PC, seguire questa procedura:

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
>
> Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Per abilitare l'account Sale di Microsoft Teams per Skype for Business Server, eseguire questo comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se non sei sicuro del valore da usare per il parametro RegistrarPool nel tuo ambiente, puoi ottenere il valore da un utente esistente di Skype for Business Server utilizzando questo comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Assegnare una licenza Skype for Business Server all'account di Microsoft Teams Rooms

1. Accedere come amministratore del tenant, aprire l'interfaccia di amministrazione di Microsoft 365 e fare clic sull'app Admin.
2. Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, Reimposta password e altro ancora.**
3. Fare clic sull'account Sale di Microsoft Teams e quindi sull'icona della penna per modificare le informazioni dell'account.
4. Fare clic **su Licenze.**
5. In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e dei requisiti VoIP aziendale licenza. È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale in Microsoft Teams Room.
6. Fare clic su **Salva**.

Per la convalida, dovrebbe essere possibile utilizzare qualsiasi client Skype for Business per accedere a questo account.

> [!NOTE]
> Se attualmente si usano SKU E1, E3, E4 o E5 con Skype for Business Piano 2 con Audioconferenza o con Sistema telefonico e un Piano per chiamate, questi continueranno a funzionare. Tuttavia, è consigliabile passare a un modello di gestione delle licenze più semplice, come descritto nell'aggiornamento delle licenze delle sale riunioni di [Teams,](rooms-licensing.md)dopo la scadenza delle licenze correnti.

> [!IMPORTANT]
> Se si usa Skype for Business Piano 2, è possibile utilizzare le sale di Microsoft Teams solo in modalità Solo Skype for Business, il che significa che tutte le riunioni saranno riunioni Skype for Business. Per abilitare la sala riunioni per le riunioni di Microsoft Teams, è consigliabile acquistare la licenza per la sala riunioni.
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
