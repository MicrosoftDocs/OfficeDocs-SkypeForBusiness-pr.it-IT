---
title: Distribuire sale di Microsoft Teams con Exchange locale
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
description: Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams in un ambiente ibrido con Exchange locale.
ms.openlocfilehash: fcf7216a4fcadee1e81ef11b5310b9d0a88e378a
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460516"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Distribuire sale di Microsoft Teams con Exchange locale

Leggere questo argomento per informazioni su come distribuire le sale di Microsoft Teams in un ambiente ibrido con Exchange locale e Microsoft Teams o Skype for Business online.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento illustra le distribuzioni ibride per le sale di Microsoft Teams con Exchange ospitato in locale. Poiché esistono così tante varianti diverse in questo tipo di distribuzione, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale illustrato qui e per altre opzioni di distribuzione.

Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti per trasformarli in account utente di Microsoft Teams Room compatibili. Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno utilizzati dal dispositivo Microsoft Teams Rooms.
  
## <a name="requirements"></a>Requisiti

Prima di distribuire le sale di Microsoft Teams con Exchange locale, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere Requisiti [di Sale di Microsoft Teams.](requirements.md)
  
Se si distribuiscono sale di Microsoft Teams con Exchange locale, si usano gli strumenti di amministrazione di Active Directory per aggiungere un indirizzo di posta elettronica per l'account di dominio locale. Questo account verrà sincronizzato con Microsoft 365 o Office 365. Sarà necessario:
  
- Creare un account e sincronizzare l'account con Active Directory.

- Abilitare la cassetta postale remota e impostare le proprietà.

- Assegnare una licenza di Microsoft 365 o Office 365.

- Abilitare l'account del dispositivo con Skype for Business Server. Per abilitare l'account del dispositivo, l'ambiente dovrà soddisfare i prerequisiti seguenti:

  - Devi avere Skype for Business online (Piano 2) o versione successiva nel tuo piano Microsoft 365 o Office 365. Il piano deve supportare la funzionalità di conferenza.
  
  - Se è necessario VoIP aziendale (telefonia PSTN) utilizzando provider di servizi di telefonia per le sale di Microsoft Teams, è necessario Skype for Business online (Piano 3).
  
  - Gli utenti del tenant devono disporre di cassette postali di Exchange.
  
  - L'account Microsoft Teams Rooms richiede una licenza Di Skype for Business online (Piano 2) o Skype for Business online (Piano 3), ma non richiede una licenza di Exchange Online.

- Assegnare una licenza Skype for Business Server all'account Microsoft Teams Rooms.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Creare un account e sincronizzare con Active Directory

1. Nello strumento Utenti e computer di **Active Directory** fare clic con il pulsante destro del mouse sulla cartella o sull'unità organizzativa in cui verranno creati gli account delle chat room di Microsoft Teams, fare clic su Nuovo e quindi su **Utente.**

2. Digitare il nome visualizzato del cmdlet precedente nella casella **Nome** completo e l'alias nella **casella Nome accesso** utente. Fare clic su **Avanti**.

3. Digitare la password dell'account. Sarà necessario digitare di nuovo l'elemento per la verifica. Verificare che la **casella di controllo Password senza scadenza** sia l'unica opzione selezionata.

    > [!NOTE]
    > La **selezione di Password senza scadenza** è un requisito per Skype for Business Server nelle sale di Microsoft Teams. Le regole di dominio possono impedire le password che non scadono. In questo caso, sarà necessario creare un'eccezione per ogni account di dispositivo di Microsoft Teams Rooms.
  
4. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Al termine, passare alla pagina degli utenti nell'interfaccia di amministrazione di Microsoft 365 e verificare che l'account creato nei passaggi precedenti sia stato unito in online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Abilitare la cassetta postale remota e impostare le proprietà

1. [Aprire Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server Exchange tramite una sessione remota di PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. In Exchange PowerShell creare una cassetta postale per l'account (abilitare l'account con cassetta postale) eseguendo il comando seguente:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Per informazioni dettagliate su sintassi e parametri, vedere [Enable-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)

3. In Exchange PowerShell configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'uomo: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione riunione originale rimanga come specificato.)

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni riunione).

   - AdditionalResponse: "Questa è una sala riunioni Skype!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Assegnare una licenza di Microsoft 365 o Office 365

1. Connettersi ad Azure Active Directory. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

2. L'account del dispositivo deve avere una licenza valida di Microsoft 365 o Office 365, oppure Exchange e Microsoft Teams non funzionano. Se si dispone della licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, che determina quali SKU di licenza sono disponibili per il proprio account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Successivamente, puoi aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. In questo caso, $strLicense è il codice SKU visualizzato (ad esempio, contoso:STANDARDPACK).

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

   Per istruzioni dettagliate, vedere [Assegnare licenze ad account utente con PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>Abilitare l'account del dispositivo

PowerShell di Skype for Business online viene usato per gestire i servizi sia per Microsoft Teams che per Skype for Business online.

1. Per creare una sessione Windows PowerShell remota da un PC, seguire questa procedura:
> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
>
> Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Ottenere l'indirizzo SIP dell'account:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Per abilitare l'account di Microsoft Teams Rooms, eseguire questo comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se non si sa quale valore usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente esistente usando questo comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Assegnare una licenza all'account di Microsoft Teams Rooms

1. Accedere come amministratore tenant, aprire l'interfaccia di amministrazione di Microsoft 365 e fare clic sull'app Admin.
2. Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, Reimposta password e altro ancora.**
3. Fare clic sull'account Sale di Microsoft Teams e quindi sull'icona della penna per modificare le informazioni dell'account.
4. Fare clic **su Licenze.**
5. In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e dei requisiti VoIP aziendale licenza. È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale nelle sale di Microsoft Teams.
6. Fare clic su **Salva**.

Per la convalida, dovrebbe essere possibile usare qualsiasi client per accedere a questo account.
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
