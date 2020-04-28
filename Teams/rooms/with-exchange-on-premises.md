---
title: Distribuire le sale di Microsoft teams con Exchange locale
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams in un ambiente ibrido con Exchange in locale.
ms.openlocfilehash: 39e78b914edb547737ed75c20191dd9beba242c6
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905298"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Distribuire le sale di Microsoft teams con Exchange in locale

Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams in un ambiente ibrido con Exchange in locale e Microsoft teams o Skype for business online.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà dalla posizione in cui è ospitato ogni servizio. Questo argomento illustra le distribuzioni ibride per le sale di Microsoft teams con Exchange ospitato in locale. Dato che sono presenti diverse varianti in questo tipo di distribuzione, non è possibile specificare istruzioni dettagliate per tutti. Il processo seguente funzionerà per molte configurazioni. Se il processo non è adatto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale come documentato qui e per altre opzioni di distribuzione.

Microsoft fornisce [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o di convalidare gli account di risorse esistenti per aiutarli a trasformare gli account utente in Microsoft teams Rooms compatibili. Se si preferisce, è possibile eseguire la procedura seguente per configurare gli account che verranno usati dal dispositivo Microsoft teams rooms.
  
## <a name="requirements"></a>Requisiti

Prima di distribuire le sale di Microsoft teams con Exchange in locale, accertarsi di avere soddisfatto i requisiti. Per altre informazioni, Vedi [requisiti di Microsoft teams Rooms](requirements.md).
  
Se si distribuiscono le sale di Microsoft teams con Exchange locale, si utilizzeranno gli strumenti di amministrazione di Active Directory per aggiungere un indirizzo di posta elettronica per l'account di dominio locale. Questo account verrà sincronizzato con Office 365. Sarà necessario:
  
- Creare un account e sincronizzare l'account con Active Directory.

- Abilitare la cassetta postale remota e impostare le proprietà.

- Assegnare una licenza di Office 365.

- Abilitare l'account del dispositivo con Skype for Business Server. Per abilitare l'account del dispositivo, è necessario che l'ambiente soddisfi i prerequisiti seguenti:

  - È necessario avere Skype for business online (piano 2) o versione successiva nel piano di Office 365. Il piano deve supportare le funzionalità di conferenza.
  
  - Se si ha bisogno di VoIP aziendale (telefonia PSTN) con i provider di servizi di telefonia per Microsoft teams Rooms è necessario Skype for business online (piano 3).
  
  - Gli utenti del tenant devono avere cassette postali di Exchange.
  
  - L'account di Microsoft teams Rooms richiede una licenza di Skype for business online (piano 2) o Skype for business online (piano 3), ma non richiede una licenza di Exchange Online.

- Assegnare una licenza di Skype for Business Server all'account di Microsoft teams rooms.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Creare un account e sincronizzarlo con Active Directory

1. Nello strumento **utenti e computer di Active Directory** fare clic con il pulsante destro del mouse sulla cartella o sull'unità organizzativa in cui verranno creati gli account di Microsoft teams rooms, scegliere **nuovo**e quindi fare clic su **utente**.

2. Digitare il nome visualizzato del cmdlet precedente nella casella **nome completo** e l'alias nella casella **nome accesso utente** . Fare clic su **Avanti**.

3. Digitare la password per l'account. È necessario ridigitarlo per la verifica. Verificare che la casella di controllo **scadenza password non** sia l'unica opzione selezionata.

    > [!NOTE]
    > La selezione di **password non scade mai** è un requisito per Skype for Business Server in Microsoft teams rooms. Le regole di dominio potrebbero impedire le password che non scadono. In questo caso, dovrai creare un'eccezione per ogni account del dispositivo Microsoft teams rooms.
  
4. Dopo aver creato l'account, eseguire una sincronizzazione della directory. Al termine, accedere alla pagina utenti nell'interfaccia di amministrazione di Microsoft 365 e verificare che l'account creato nei passaggi precedenti sia stato unito a online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Abilitare la cassetta postale remota e impostare le proprietà

1. [Aprire Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server Exchange usando Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. In PowerShell di Exchange creare una cassetta postale per l'account (abilitare la cassetta postale per l'account) eseguendo il comando seguente:

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Per informazioni dettagliate su sintassi e parametri, vedere [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. In PowerShell di Exchange configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza di riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono direttamente la decisione di prenotazione della sala senza intervento umano: gratuito = accetta; occupato = declino).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).

   - DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni di riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "si tratta di una sala riunioni Skype!" (Il testo aggiuntivo da aggiungere alla convocazione di riunione)

   Questo esempio configura queste impostazioni nella cassetta postale della sala denominata Project-Rigel-01.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Assegnare una licenza di Office 365

1. Connettersi ad Azure Active Directory. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

2. L'account del dispositivo deve avere una licenza di Office 365 valida oppure Exchange e Microsoft teams non funzioneranno. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, determinando gli SKU di licenza disponibili per il proprio account. Puoi usare`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. È quindi possibile aggiungere una licenza usando la`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. In questo caso, $strLicense è il codice SKU visualizzato, ad esempio contoso: STANDARDPACK.

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

   Per istruzioni dettagliate, vedere [assegnare licenze agli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Abilitare l'account del dispositivo

Skype for Business Online PowerShell viene usato per gestire i servizi sia per Microsoft teams che per Skype for business online.

1. Creare una sessione remota di Windows PowerShell da un PC come indicato di seguito:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Ottenere l'indirizzo SIP dell'account:

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Per abilitare l'account di Microsoft teams rooms, eseguire questo comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Se non si è certi del valore da usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente esistente usando questo comando:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Assegnare una licenza all'account di Microsoft teams rooms

1. Accedere come amministratore del tenant, aprire il portale di amministrazione di Office 365 e fare clic sull'app di amministrazione.
2. Fare clic su **utenti e gruppi** e quindi su **Aggiungi utenti, Reimposta password e altro ancora**.
3. Fare clic sull'account Microsoft teams Rooms e quindi fare clic sull'icona della penna per modificare le informazioni sull'account.
4. Fare clic su **licenze**.
5. In **assegna licenze**selezionare Skype for business (piano 2) o Skype for business (piano 3), a seconda delle licenze e dei requisiti per la segreteria telefonica aziendale. È necessario usare una licenza di piano 3 Se si vuole usare VoIP aziendale nelle sale di Microsoft teams.
6. Fare clic su **Salva**.

Per la convalida, dovresti essere in grado di usare qualsiasi client per accedere a questo account.
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
