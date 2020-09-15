---
title: Distribuire Microsoft teams Rooms con Microsoft 365 o Office 365
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Microsoft 365 o Office 365, in cui i team o Skype for business e Exchange sono entrambi online.
ms.openlocfilehash: ee1f4da5cbcb65ab58c032ac651e0b563167a35b
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814795"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Distribuire Microsoft teams Rooms con Microsoft 365 o Office 365

Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Microsoft 365 o Office 365, in cui Microsoft teams o Skype for business e Exchange sono entrambi online.

Il modo più semplice per configurare gli account utente consiste nel configurarli con Windows PowerShell remoto. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o di convalidare gli account di risorse esistenti per poterli trasformare in account utente di Microsoft teams Rooms compatibili. Se si preferisce, è possibile eseguire la procedura seguente per configurare gli account che verranno usati dal dispositivo Microsoft teams rooms.

## <a name="requirements"></a>Requisiti

Prima di distribuire le sale di Microsoft teams con Microsoft 365 o Office 365, verificare di avere soddisfatto i requisiti. Per altre informazioni, Vedi [requisiti di Microsoft teams Rooms](requirements.md).

Per abilitare Skype for business, è necessario avere la seguente procedura:

- Skype for business online (piano 2 o un piano basato sull'organizzazione) o superiore nel piano Microsoft 365 o Office 365. Il piano deve consentire le funzionalità di conferenza telefonica con accesso esterno.

- Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per l'audioconferenza e il sistema telefonico.  Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessaria una licenza per i servizi di audioconferenza.

- Gli utenti del tenant devono avere cassette postali di Exchange.

- L'account di Microsoft teams Rooms richiede almeno una licenza di Skype for business online (piano 2), ma non richiede una licenza di Exchange Online. Per informazioni dettagliate, vedere [licenze di Microsoft teams Rooms](rooms-licensing.md) .

Per informazioni dettagliate sui piani di Skype for business online, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Aggiungere un account di dispositivo

1. Connettersi a PowerShell di Exchange Online. Per istruzioni, vedere [connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. In PowerShell di Exchange Online creare una nuova cassetta postale della sala o modificare una cassetta postale della sala esistente. Per impostazione predefinita, le cassette postali della sala non hanno account associati, quindi è necessario aggiungere un account quando si crea o si modifica una cassetta postale della sala che consente l'autenticazione con Skype room Systems V2.

   - Per creare una nuova cassetta postale della sala, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio crea una nuova cassetta postale della sala con le impostazioni seguenti:

     - Nome: Rigel-01

     - Alias: Rigel1

     - Account: Rigel1@contoso.onmicrosoft.com

     - Password account: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Per modificare una cassetta postale della sala esistente, usare la sintassi seguente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio Abilita l'account per la cassetta postale della sala esistente con il valore alias Rigel2 e imposta la password su 9898P@ $ $W 0RD. Tieni presente che l'account verrà Rigel2@contoso.onmicrosoft.com a causa del valore alias esistente.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Per informazioni dettagliate su sintassi e parametri, vedere [nuove cassette postali](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza di riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono direttamente la decisione di prenotazione della sala senza intervento umano: gratuito = accetta; occupato = declino).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).

   - DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni di riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "si tratta di una sala riunioni Skype!" (Il testo aggiuntivo da aggiungere alla convocazione di riunione)

   Questo esempio configura queste impostazioni nella cassetta postale della sala denominata Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connettersi a MS Online PowerShell per impostare le impostazioni di Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet di PowerShell.   Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

5. Se non si vuole che la password scada, usare la sintassi seguente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Questo esempio imposta la password per l'account Rigel1@contoso.onmicrosoft.com per non scadere mai.

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   È anche possibile impostare un numero di telefono per l'account eseguendo il comando seguente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. L'account del dispositivo deve avere una licenza valida per Microsoft 365 o Office 365 oppure Exchange e Microsoft teams o Skype for business non funzioneranno. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, determinando gli SKU di licenza disponibili per il proprio account. Puoi usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili per l'organizzazione Microsoft 365 o Office 365, come indicato di seguito:

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   È quindi possibile aggiungere una licenza usando la `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. In questo caso, $strLicense è il codice SKU visualizzato, ad esempio contoso: STANDARDPACK.

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   Per istruzioni dettagliate, vedere [assegnare licenze agli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Devi quindi abilitare l'account del dispositivo con Skype for business. Assicurarsi che l'ambiente soddisfi i requisiti definiti nei [requisiti di Microsoft teams Rooms](requirements.md).

   Avviare una sessione remota di [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) come indicato di seguito (assicurarsi di [installare i componenti di PowerShell per Skype for business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):
   
> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.
>
> Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Attiva quindi l'account di Microsoft teams Rooms per Skype for Business Server eseguendo il cmdlet seguente:

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Ottenere le informazioni di RegistrarPool dal nuovo account utente configurato, come illustrato in questo esempio:

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > New user accounts might not be created on the same registrar pool as existing user accounts in the tenant. The command above will prevent errors in account setup due to this situation.

### <a name="assign-a-license-to-your-account"></a>Assegnare una licenza al proprio account

1. Accedere come amministratore del tenant, aprire l'interfaccia di amministrazione di Microsoft 365 e fare clic sull'app di amministrazione.

2. Fare clic su **utenti e gruppi** e quindi su **Aggiungi utenti, Reimposta password e altro ancora**.

3. Selezionare l'account Microsoft teams Rooms e quindi fare clic o toccare l'icona della penna, ovvero modifica.

4. Fare clic sull'opzione **licenze** .

5. Nella sezione **assegnazione licenze** è necessario selezionare Skype for business online (piano 2) o Skype for business online (piano 3), a seconda della licenza e delle operazioni che si sono decisi in termini di necessità di VoIP aziendale. È necessario usare una licenza di piano 3 Se si vuole usare Cloud PBX in Microsoft teams rooms. Sarà necessario CloudPBX per la connettività vocale. Configura quindi la chiamata vocale ibrida o PSTN in base al metodo di connettività PSTN. Per altre informazioni, Vedi [licenze di Microsoft teams Rooms](rooms-licensing.md) .

6. Fare clic su **Salva** per completare l'attività.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Esempio: configurazione dell'account della sala in Exchange Online e Skype for business online

Comandi di PowerShell di Exchange Online:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Comandi di PowerShell di Azure Active Directory:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Comando di PowerShell per Skype for business:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> In questo articolo vengono aggiunte CloudPBX e PSTNCallingDomesticAndInternational. Sarà inoltre necessario usare l'interfaccia di amministrazione per assegnare un numero di telefono.

## <a name="validate"></a>Convalidare

Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for business per accedere all'account creato.

## <a name="see-also"></a>Vedere anche

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Licenze di Microsoft teams rooms](rooms-licensing.md)
