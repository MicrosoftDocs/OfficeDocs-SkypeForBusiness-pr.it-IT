---
title: Distribuire Microsoft Teams Rooms con Exchange Online
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online.
ms.openlocfilehash: e6eb3253d7edb999ba74d28ef9a6d8ae835ac16d
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055486"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Distribuire Microsoft Teams Rooms con Exchange Online

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento riguarda le distribuzioni ibride per Microsoft Teams Rooms con Exchange ospitate online. Poiché questo tipo di distribuzione offre moltissime varianti diverse, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Exchange Online, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)
  
Per distribuire Microsoft Teams Rooms con Exchange Online, seguire la procedura seguente. Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet. 

   > [!NOTE]
   >  I [cmdlet Azure Active Directory module per Windows PowerShell](/powershell/azure/active-directory/overview?view=azureadps-1.0) in questa sezione, ad esempio Set-MsolUser, sono stati testati nella configurazione degli account per Microsoft Teams Rooms. È possibile che altri cmdlet funzionino, ma non sono stati testati in questo scenario specifico.

Se è stato distribuito Active Directory Federation Services (AD FS), potrebbe essere necessario convertire l'account utente in un utente gestito prima di eseguire questa procedura e quindi convertire di nuovo l'utente in un utente federato dopo aver completato questa procedura.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Creare un account e impostare Exchange proprietà

1. Avviare una sessione Windows PowerShell remota in un PC e connettersi a Exchange Online come indicato di seguito:

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. Dopo aver stabilito una sessione, si creerà una nuova cassetta postale e la si abiliterà come RoomMailboxAccount oppure si modificheranno le impostazioni per una cassetta postale della chat room esistente. In questo modo l'account verrà autenticato Microsoft Teams Rooms.

   Se si sta modificando una cassetta postale delle risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se si sta creando una nuova cassetta postale per le risorse:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Per migliorare l'esperienza della riunione, è necessario impostare le proprietà Exchange dell'account utente nel modo seguente:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Aggiungere un indirizzo di posta elettronica per l'account di dominio locale

1. Nello **strumento Active Directory Users and Computers fare** clic con il pulsante destro del mouse sul contenitore o sull'unità organizzativa in cui verranno creati gli account Microsoft Teams Rooms, fare clic su **Nuovo** e quindi su **Utente.**
2. Digitare il nome visualizzato (- Identity) del cmdlet precedente (Set-Mailbox o New-Mailbox) nella casella **Nome** completo e l'alias nella casella **Nome accesso** utente. Fare clic su **Avanti**.
3. Digitare la password per l'account. Sarà necessario digitare di nuovo per la verifica. Verificare che la **casella di controllo Password non scada** mai sia l'unica opzione selezionata.

    > [!NOTE]
    > La **selezione della password non scade mai** è un requisito per Microsoft Teams Rooms. Le regole di dominio potrebbero proibire le password che non scadono. In tal caso, sarà necessario creare un'eccezione per ogni account Microsoft Teams Rooms utente.
  
4. Fare **clic su** Fine per creare l'account.
5. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Questa operazione può essere eseguita usando [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell. Al termine, passare alla pagina dell'utente e verificare che i due account creati nei passaggi precedenti siano stati uniti.

### <a name="assign-an-office-365-license"></a>Assegnare una Office 365 licenza

1. Prima di tutto, connettersi Azure AD per applicare alcune impostazioni dell'account. È possibile eseguire questo cmdlet per connettersi. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.

    ``` PowerShell
   Connect-MsolService
    ```

2. L'account utente deve avere una licenza di Office 365 valida per connettersi a Microsoft Teams. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account utente, in modo da determinare quali SKU di licenza sono disponibili per l'account.
3. Usare 'Get-MsolAccountSku' per recuperare un elenco di SKU disponibili per il tenant Office 365.
4. Dopo aver elencato gli SKU, è possibile aggiungere una licenza usando l'opzione "Set-MsolUserLicense" <!-- Set-AzureADUserLicense--> cmdlet. 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>Convalida

Per la convalida, dovrebbe essere possibile usare qualsiasi client Microsoft Teams per accedere all'account creato.
  
## <a name="see-also"></a>Vedere anche

[Aggiornare le cassette postali della chat room con metadati aggiuntivi per migliorare l'esperienza di ricerca e suggerimenti per le chat room](/powershell/module/exchange/set-place)

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
