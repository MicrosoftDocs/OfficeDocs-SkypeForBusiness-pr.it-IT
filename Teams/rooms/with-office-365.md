---
title: Distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, dove Teams o Skype for Business e Exchange sono entrambi online.
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355645"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, dove Microsoft Teams e Exchange sono entrambi online.

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)

### <a name="add-a-resource-account"></a>Aggiungere un account della risorsa

1. Connessione per Exchange Online PowerShell. Per istruzioni, vedere [Connessione per Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. In Exchange Online PowerShell creare una nuova cassetta postale sala o modificare una cassetta postale della chat room esistente. Per impostazione predefinita, alle cassette postali della chat room non sono associati account, quindi sarà necessario aggiungere un account quando si crea o si modifica una cassetta postale della chat room che le consente di eseguire l'autenticazione con Microsoft Teams.

   - Per creare una nuova cassetta postale della chat room, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

     - Account: ConferenceRoom01@contoso.com
  
     - Nome: ConferenceRoom01

     - Alias: ConferenceRoom01

     - Password dell'account: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Per modificare una cassetta postale della chat room esistente, usare la sintassi seguente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias ConferenceRoom02 e imposta la password su 9898P@$$W 0rd. Si noti che l'account verrà ConferenceRoom02@contoso.com a causa del valore alias esistente.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

3. In Exchange Online PowerShell configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'uomo).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Si tratta di una Microsoft Teams sala riunioni!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale sala denominata ConferenceRoom01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connessione a PowerShell di MS Online per impostare Active Directory eseguendo il comando `Connect-MsolService` Cmdlet di PowerShell. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.

5. Impostare la password in modo che non scada mai usando la sintassi seguente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Questo esempio imposta la password per l'account ConferenceRoom01@contoso.onmicrosoft.com non scadrà mai.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   È anche possibile impostare un numero di telefono per l'account eseguendo il comando seguente:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > Se la password non è impostata su Non scadere mai, l'account non accederà più al dispositivo quando l'account raggiunge il periodo di scadenza. La password dovrà quindi essere modificata per l'account e aggiornata anche in locale in Teams Rooms. Gli utenti non possono partecipare alle riunioni in Teams Rooms la password è scaduta.

6. È necessario che l'account della risorsa abbia una licenza Microsoft 365 o Office 365 o che Exchange e Microsoft Teams non funzionino. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account delle risorse, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili per l'organizzazione Microsoft 365 o Office 365 come indicato di seguito:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Successivamente, è possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Questo esempio aggiunge la licenza Sala riunioni all'account:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   È anche possibile aggiungere Sistema telefonico a questo account, ma è necessario prima configurarlo. Vedere [Che cos'Sistema telefonico?](../what-is-phone-system-in-office-365.md) per altre informazioni. Questo esempio aggiunge il piano per chiamate PSTN nazionali e internazionali:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>Convalida

Per la convalida, dovrebbe essere possibile usare qualsiasi client Microsoft Teams per accedere all'account creato.

## <a name="see-also"></a>Vedere anche

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Microsoft Teams Rooms licenze](rooms-licensing.md)
