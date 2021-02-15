---
title: Distribuire sale di Microsoft Teams con Microsoft 365 o Office 365
ms.author: v-cichur
author: cichur
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
description: Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams con Microsoft 365 o Office 365, dove Teams o Skype for Business ed Exchange sono entrambi online.
ms.openlocfilehash: 4ec54763379e4a13a69eb3e08019924708873faf
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196210"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Distribuire sale di Microsoft Teams con Microsoft 365 o Office 365

Leggere questo argomento per informazioni su come distribuire le sale di Microsoft Teams con Microsoft 365 o Office 365, dove Microsoft Teams o Skype for Business ed Exchange sono entrambi online.

Il modo più semplice per configurare gli account utente è configurarli usando gli account Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti per trasformarli in account utente di Microsoft Teams Room compatibili. Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno utilizzati dal dispositivo Microsoft Teams Rooms.

## <a name="requirements"></a>Requisiti

Prima di distribuire le sale di Microsoft Teams con Microsoft 365 o Office 365, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere Requisiti [di Sale di Microsoft Teams.](requirements.md)

Per abilitare Skype for Business, è necessario disporre di quanto segue:

- Skype for Business online (Piano 2 o un piano enterprise) o versione successiva nel piano Microsoft 365 o Office 365. Il piano deve consentire le funzionalità di conferenza telefonica con accesso esterno.

- Se sono necessarie funzionalità di accesso esterno per una riunione, è necessaria una licenza per audioconferenza e sistema telefonico.  Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessaria una licenza per i servizi di audioconferenza.

- Gli utenti del tenant devono disporre di cassette postali di Exchange.

- L'account Microsoft Teams Rooms richiede almeno una licenza di Skype for Business online (Piano 2), ma non di una licenza di Exchange Online. Per informazioni [dettagliate, vedere](rooms-licensing.md) le licenze Microsoft Teams Rooms.

Per informazioni dettagliate sui piani di Skype for Business online, vedere la descrizione del servizio [Skype for Business online.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Aggiungere un account del dispositivo

1. Connettersi a PowerShell di Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. In PowerShell di Exchange Online creare una nuova cassetta postale della chat room o modificarne una esistente. Per impostazione predefinita, le cassette postali della sala non sono associate ad account, quindi è necessario aggiungere un account quando si crea o si modifica una cassetta postale della sala che consente l'autenticazione con Skype Room Systems v2.

   - Per creare una nuova cassetta postale della sala, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

     - Nome: Rigel-01

     - Alias: Rigel1

     - Account: Rigel1@contoso.onmicrosoft.com

     - Password account: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Per modificare una cassetta postale della sala esistente, usare la sintassi seguente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias Rigel2 e imposta la password su 9898P@$$W 0rd. Si noti che l'account verrà Rigel2@contoso.onmicrosoft.com a causa del valore di alias esistente.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Per informazioni dettagliate su sintassi e parametri, vedere [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'uomo: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione riunione originale rimanga come specificato.)

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni riunione).

   - AdditionalResponse: "Questa è una sala riunioni Skype!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Per informazioni dettagliate su sintassi e parametri, [vedere Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Connettersi a PowerShell di MS Online per eseguire le impostazioni di Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet di PowerShell. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.

5. Se non si vuole che la password scada, usare la sintassi seguente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Questo esempio imposta la password per l'account Rigel1@contoso.onmicrosoft.com non scade mai.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   È anche possibile impostare un numero di telefono per l'account eseguendo il comando seguente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> Se la password non è impostata su Mai scadenza, l'account non potrà più accedere al dispositivo quando l'account raggiunge il periodo di scadenza. La password dovrà quindi essere cambiata per l'account e aggiornata anche in locale nel dispositivo MTR.

6. L'account del dispositivo deve avere una licenza valida di Microsoft 365 o Office 365 oppure Exchange e Microsoft Teams o Skype for Business non funzionano. Se si dispone della licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo. Ciò determina quali SKU di licenza sono disponibili per il proprio account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili per l'organizzazione di Microsoft 365 o Office 365, come segue:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Successivamente, puoi aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Questo esempio aggiunge all'account la licenza della sala riunioni:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Per istruzioni dettagliate, vedere [Assegnare licenze ad account utente con PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Puoi anche aggiungere funzionalità Sistema telefonico a questo account, ma devi prima configurarlo. Vedi [Che cos'è il Sistema telefonico?](../what-is-phone-system-in-office-365.md) Per maggiori dettagli. Questo esempio aggiunge il piano per chiamate PSTN nazionali e internazionali:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Successivamente, è necessario abilitare l'account del dispositivo con Skype for Business. Assicurarsi che l'ambiente soddisfi i requisiti definiti nei requisiti di [Microsoft Teams Room.](requirements.md)

   Avviare una sessione [Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) come indicato di seguito (assicurarsi di installare i componenti di PowerShell per Skype for [Business Online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
>
> Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Ottenere le informazioni di RegistrarPool dal nuovo account utente da configurare, come illustrato nell'esempio seguente:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Abilitare quindi l'account Sale di Microsoft Teams per Skype for Business Server eseguendo il cmdlet seguente:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > È possibile che i nuovi account utente non siano stati creati nello stesso pool di registrar degli account utente esistenti nel tenant. Il comando precedente impedirà errori nella configurazione dell'account a causa di questa situazione.

## <a name="validate"></a>Convalida

Per la convalida, dovrebbe essere possibile utilizzare qualsiasi client Skype for Business per accedere all'account creato.

## <a name="see-also"></a>Vedere anche

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Licenze per le sale di Microsoft Teams](rooms-licensing.md)
