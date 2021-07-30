---
title: Distribuire Microsoft Teams Rooms con Exchange Online
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
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online e Skype for Business Server locali.
ms.openlocfilehash: 6684173df916b268b35061c735614188e1d58e40
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646247"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Distribuire Microsoft Teams Rooms con Exchange Online

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online e Skype for Business Server locali.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento riguarda le distribuzioni ibride per Microsoft Teams Rooms con Exchange ospitate online. Poiché questo tipo di distribuzione offre molte varianti diverse, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.

Il modo più semplice per configurare gli account utente è configurarli usando gli account Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in modo da trasformarli in account utente Microsoft Teams Rooms compatibili. Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che Microsoft Teams Rooms dispositivo.

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Exchange Online, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)
  
Per distribuire Microsoft Teams Rooms con Exchange Online, seguire la procedura seguente. Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati. 

   > [!NOTE]
   >  Il [modulo Azure Active Directory](/powershell/azure/active-directory/overview) per i cmdlet Windows PowerShell in questa sezione, ad esempio Set-MsolUser, è stato testato nella configurazione degli account per Microsoft Teams Rooms dispositivi. È possibile che altri cmdlet funzionino, ma non sono stati testati in questo scenario specifico.

Se è stato distribuito Active Directory Federation Services (AD FS), potrebbe essere necessario convertire l'account utente in un utente gestito prima di eseguire questa procedura e quindi convertire di nuovo l'utente in un utente federato dopo aver completato questa procedura.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Creare un account e impostare Exchange proprietà

1. Avviare una sessione Windows PowerShell remota in un PC e connettersi a Exchange Online come indicato di seguito:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Dopo aver stabilito una sessione, si creerà una nuova cassetta postale e la si abiliterà come RoomMailboxAccount oppure si modificheranno le impostazioni per una cassetta postale della chat room esistente. In questo modo l'account verrà autenticato Microsoft Teams Rooms.

   Se si sta modificando una cassetta postale delle risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se si sta creando una nuova cassetta postale per le risorse:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Per migliorare l'esperienza della riunione, è necessario impostare le proprietà Exchange sull'account utente nel modo seguente:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Aggiungere un indirizzo di posta elettronica per l'account di dominio locale

1. Nello **strumento Active Directory Users and Computers fare** clic con il pulsante destro del mouse sul contenitore o sull'unità organizzativa in cui verranno creati gli account Microsoft Teams Rooms, fare clic su **Nuovo** e quindi su **Utente.**
2. Digitare il nome visualizzato (- Identity) del cmdlet precedente (Set-Mailbox o New-Mailbox) nella casella **Nome** completo e l'alias nella casella **Nome accesso** utente. Fare clic su **Avanti**.
3. Digitare la password per l'account. Sarà necessario digitare di nuovo per la verifica. Verificare che la **casella di controllo Password non scada** mai sia l'unica opzione selezionata.

    > [!NOTE]
    > La **selezione della password non scade** mai è un requisito per Skype for Business Server in Microsoft Teams Rooms. Le regole di dominio potrebbero proibire le password che non scadono. In questo caso, è necessario creare un'eccezione per ogni account Microsoft Teams Rooms utente.
  
4. Fare **clic su** Fine per creare l'account.
5. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Questa operazione può essere eseguita usando [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) in PowerShell. Al termine, passare alla pagina degli utenti e verificare che i due account creati nei passaggi precedenti siano stati uniti.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Assegnare una Microsoft 365 o Office 365 licenza

1. Prima di tutto, connettersi ad Azure AD per applicare alcune impostazioni dell'account. È possibile eseguire questo cmdlet per connettersi. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview) non è supportato.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. L'account utente deve avere una licenza Microsoft 365 o Office 365 per assicurarsi che Exchange e Skype for Business Server funzionino. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account utente, in modo da determinare quali SKU di licenza sono disponibili per l'account. L'attività verrà apportata nel passaggio seguente.
3. Usare quindi `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> per recuperare un elenco di SKU disponibili per l'Microsoft 365 o Office 365 organizzazione.
4. Dopo aver elencato gli SKU, è possibile aggiungere una licenza usando il comando `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. In questo caso, $strLicense codice SKU visualizzato, ad esempio contoso:STANDARDPACK. 

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

> [!NOTE]
> Se si sta configurando un Teams Rooms solo per partecipare a Microsoft Teams riunioni, non è necessario eseguire la procedura seguente. I passaggi seguenti sono necessari solo se si vuole abilitare il supporto per Skype for Business.

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

2. Per abilitare l'account Microsoft Teams Rooms per Skype for Business Server, eseguire questo comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se non si è certi del valore da usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente Skype for Business Server esistente usando questo comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Assegnare una Skype for Business Server al proprio account Microsoft Teams Rooms account

> [!NOTE]
> Se si sta configurando un Teams Rooms solo per partecipare a Microsoft Teams riunioni, non è necessario eseguire la procedura seguente. I passaggi seguenti sono necessari solo se si vuole abilitare il supporto per Skype for Business.

1. Accedere come amministratore tenant, aprire il interfaccia di amministrazione di Microsoft 365 e fare clic sull'app Amministratore.
2. Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, reimpostazione password e altro ancora.**
3. Fare clic sull Microsoft Teams Rooms account e quindi fare clic sull'icona della penna per modificare le informazioni dell'account.
4. Fare clic **su Licenze**.
5. In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e VoIP aziendale requisiti. È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale in Microsoft Teams Rooms.
6. Fare clic su **Salva**.

Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for Business per accedere a questo account.

> [!NOTE]
> Se attualmente si usano SKU E1, E3, E4 o E5 con Skype for Business Piano 2 con audioconferenza o con Sistema telefonico e un piano per chiamate, questi continueranno a funzionare. Tuttavia, è consigliabile passare a un modello di licenza più semplice, come descritto [in](rooms-licensing.md)Aggiornamento delle licenze Teams Sala riunioni, dopo la scadenza delle licenze correnti.

> [!IMPORTANT]
> Se si usa Skype for Business Piano 2, è possibile usare il Microsoft Teams Rooms solo in modalità solo Skype for Business, quindi tutte le riunioni verranno Skype for Business riunioni. Per abilitare la sala riunioni per le riunioni Microsoft Teams, è consigliabile acquistare la licenza Sala riunioni riunione.
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
