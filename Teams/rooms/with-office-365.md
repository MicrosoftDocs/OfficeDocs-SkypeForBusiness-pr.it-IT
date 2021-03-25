---
title: Distribuire le chat room di Microsoft Teams con Microsoft 365 o Office 365
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
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, dove Teams o Skype for Business ed Exchange sono entrambi online.
ms.openlocfilehash: b5cfaab64840fe72dc989f00ed41760058afc765
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117334"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Distribuire le chat room di Microsoft Teams con Microsoft 365 o Office 365

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, dove Microsoft Teams o Skype for Business ed Exchange sono entrambi online.

Il modo più semplice per configurare gli account utente è configurarli usando gli account Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in modo da trasformarli in account utente di Microsoft Teams Rooms compatibili. Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno utilizzati dal dispositivo Microsoft Teams Rooms.

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere Requisiti [di Microsoft Teams Rooms](requirements.md).

Per abilitare Skype for Business, devi avere quanto segue:

- Skype for Business online (piano 2 o piano enterprise) o versione successiva nel piano Microsoft 365 o Office 365. Il piano deve consentire le funzionalità di conferenza telefonica con accesso esterno.

- Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per audioconferenze e sistema telefonico.  Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessaria una licenza per i servizi di audioconferenza.

- Gli utenti del tenant devono avere cassette postali di Exchange.

- L'account Microsoft Teams Rooms richiede almeno una licenza skype for business online (piano 2), ma non una licenza di Exchange Online. Per informazioni [dettagliate, vedere Licenze di Microsoft Teams Rooms.](rooms-licensing.md)

Per informazioni dettagliate sui piani skype for business online, consulta la descrizione del servizio [Skype for Business online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)

### <a name="add-a-device-account"></a>Aggiungere un account del dispositivo

1. Connettersi a PowerShell di Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)

2. In PowerShell di Exchange Online creare una nuova cassetta postale della chat room o modificare una cassetta postale della chat room esistente. Per impostazione predefinita, alle cassette postali della chat room non sono associati account, quindi sarà necessario aggiungere un account quando si crea o si modifica una cassetta postale della chat room che le consente di eseguire l'autenticazione con Skype Room Systems v2.

   - Per creare una nuova cassetta postale della chat room, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

     - Nome: Rigel-01

     - Alias: Rigel1

     - Account: Rigel1@contoso.onmicrosoft.com

     - Password dell'account: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Per modificare una cassetta postale della chat room esistente, usare la sintassi seguente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias Rigel2 e imposta la password su 9898P@$$W 0rd. Si noti che l'account verrà Rigel2@contoso.onmicrosoft.com a causa del valore alias esistente.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

3. In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'utente: free = accept; busy = decline).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Questa è una sala riunioni Skype!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connettersi a PowerShell di MS Online per impostare Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet PowerShell. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.

5. Se non si vuole che la password scada, usare la sintassi seguente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Questo esempio imposta la password per l'account Rigel1@contoso.onmicrosoft.com non scadrà mai.

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
> Se la password non è impostata su Non scadere mai, l'account non accederà più al dispositivo quando l'account raggiunge il periodo di scadenza. La password dovrà quindi essere modificata per l'account e aggiornata anche in locale nel dispositivo MTR.

6. L'account del dispositivo deve avere una licenza valida di Microsoft 365 o Office 365 oppure Exchange e Microsoft Teams o Skype for Business non funzionano. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili per l'organizzazione di Microsoft 365 o Office 365 nel modo seguente:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Successivamente, è possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Questo esempio aggiunge la licenza sala riunioni all'account:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con PowerShell di Office 365.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   È anche possibile aggiungere funzionalità del sistema telefonico a questo account, ma è necessario prima configurarlo. Per [altre informazioni, vedere Che cos'è](../what-is-phone-system-in-office-365.md) Sistema telefonico? Questo esempio aggiunge il piano per chiamate PSTN nazionali e internazionali:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Successivamente, devi abilitare l'account del dispositivo con Skype for Business. Assicurarsi che l'ambiente soddisfi i requisiti definiti nei [requisiti di Microsoft Teams Rooms.](requirements.md)

   Avviare una sessione [Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) come indicato di seguito (assicurarsi di installare i componenti di PowerShell di Skype for [Business online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte dell'ultimo modulo di PowerShell di Teams.
>
> Se si usa l'ultima versione pubblica di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   Ottenere le informazioni di RegistrarPool dal nuovo account utente da configurare, come illustrato nell'esempio seguente:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Quindi, abilitare l'account di Microsoft Teams Rooms per Skype for Business Server eseguendo il cmdlet seguente:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > I nuovi account utente potrebbero non essere creati nello stesso pool di registrar degli account utente esistenti nel tenant. Il comando precedente impedirà errori nella configurazione dell'account a causa di questa situazione.

## <a name="validate"></a>Convalida

Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for Business per accedere all'account che hai creato.

## <a name="see-also"></a>Vedere anche

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Licenze di Microsoft Teams Rooms](rooms-licensing.md)