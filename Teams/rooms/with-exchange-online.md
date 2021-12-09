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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online e Skype for Business Server locali.
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355635"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Distribuire Microsoft Teams Rooms con Exchange Online

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento riguarda le distribuzioni ibride per Microsoft Teams Rooms con Exchange ospitate online. Poiché questo tipo di distribuzione offre moltissime varianti diverse, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Exchange Online, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)
  
Per distribuire Microsoft Teams Rooms con Exchange Online, seguire la procedura seguente. Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati. 

   > [!NOTE]
   >  Il modulo Azure Active Directory per [i cmdlet](/powershell/azure/active-directory/overview) Windows PowerShell in questa sezione, ad esempio Set-MsolUser, è stato testato nella configurazione degli account per Microsoft Teams Rooms dispositivi. È possibile che altri cmdlet funzionino, ma non sono stati testati in questo scenario specifico.

Se è stato distribuito Active Directory Federation Services (AD FS), potrebbe essere necessario convertire l'account utente in un utente gestito prima di eseguire questa procedura e quindi convertire di nuovo l'utente in un utente federato dopo aver completato questa procedura.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Creare un account e impostare Exchange proprietà

1. Avviare una sessione Windows PowerShell remota in un PC e connettersi a Exchange Online come indicato di seguito:

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. Dopo aver stabilito una sessione, si creerà una nuova cassetta postale e la si abiliterà come RoomMailboxAccount oppure si modificheranno le impostazioni per una cassetta postale della chat room esistente. In questo modo l'account verrà autenticato Microsoft Teams Rooms.

   Se si sta modificando una cassetta postale delle risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se si sta creando una nuova cassetta postale per le risorse:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Per migliorare l'esperienza della riunione, è necessario impostare le proprietà Exchange sull'account utente nel modo seguente:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
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

1. Prima di tutto, connettersi Azure AD per applicare alcune impostazioni dell'account. È possibile eseguire questo cmdlet per connettersi. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview) non è supportato.

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. L'account utente deve avere una licenza Microsoft 365 o Office 365 per assicurarsi che Exchange funzioni. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account utente, in modo da determinare quali SKU di licenza sono disponibili per l'account. L'attività verrà apportata nel passaggio seguente.
3. Usare quindi `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> per recuperare un elenco di SKU disponibili per l'Microsoft 365 o Office 365 organizzazione.
4. È possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. In questo caso, viene applicata Microsoft Teams Rooms Standard licenza. 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
