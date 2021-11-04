---
title: Distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: d052683b1f393afd777f6e17a4b38b96f17d6b5a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741582"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, dove Microsoft Teams o Skype for Business e Exchange sono entrambi online.

Il modo più semplice per configurare gli account utente è configurarli usando gli account Windows PowerShell. Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in modo da trasformarli in account utente Microsoft Teams Rooms compatibili. Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno Microsoft Teams Rooms dispositivo.

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Microsoft 365 o Office 365, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)

Per abilitare Skype for Business, è necessario disporre di quanto segue:

- Skype for Business Online (Piano 2 o piano basato Enterprise) o versione successiva nel piano Microsoft 365 o Office 365 piano. Il piano deve consentire le funzionalità di conferenza telefonica con accesso esterno.

- Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per audioconferenza e Sistema telefonico audio.  Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per i servizi di audioconferenza.

- Gli utenti del tenant devono avere Exchange cassette postali.

- L'account Microsoft Teams Rooms richiede almeno una licenza di Skype for Business Online (Piano 2), ma non richiede una licenza Exchange Online licenza. Vedere [Microsoft Teams Rooms licenze per](rooms-licensing.md) informazioni dettagliate.

Per informazioni dettagliate sui Skype for Business online, vedere la [Skype for Business Descrizione del servizio online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)

### <a name="add-a-device-account"></a>Aggiungere un account del dispositivo

1. Connessione per Exchange Online PowerShell. Per istruzioni, vedere [Connessione a Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. In Exchange Online PowerShell creare una nuova cassetta postale della chat room o modificare una cassetta postale della chat room esistente. Per impostazione predefinita, alle cassette postali della chat room non sono associati account, quindi è necessario aggiungere un account quando si crea o si modifica una cassetta postale della chat room che le consente di eseguire l'autenticazione con Skype Room Systems v2.

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

3. In Exchange Online PowerShell configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'utente: free = accept; busy = decline).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Si tratta di una Riunione Skype room!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connessione a PowerShell di MS Online per impostare Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet di PowerShell. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

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

6. L'account del dispositivo deve avere una licenza di Microsoft 365 o Office 365 valida o che Exchange e Microsoft Teams o Skype for Business non funzionino. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili per l'organizzazione Microsoft 365 o Office 365 come indicato di seguito:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Successivamente, è possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Questo esempio aggiunge la licenza Sala riunioni all'account:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   È anche possibile aggiungere Sistema telefonico a questo account, ma è necessario prima configurarlo. Vedere [Che cos'Sistema telefonico?](../what-is-phone-system-in-office-365.md) per altre informazioni. Questo esempio aggiunge il piano per chiamate PSTN nazionali e internazionali:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > Se si sta configurando Teams Rooms partecipare solo a Microsoft Teams riunioni, non procedere con il passaggio seguente. Quanto segue è necessario solo se si abilitazione del supporto per Skype for Business locale.

7. Per abilitare l'account del dispositivo Skype for Business locale, assicurarsi che l'ambiente soddisfi i requisiti definiti nei Microsoft Teams Rooms [locali.](requirements.md)

   Avviare una sessione [Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) come indicato di seguito (assicurarsi di installare Skype for Business componenti [di PowerShell online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

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

   Ottenere le informazioni di RegistrarPool dal nuovo account utente da configurare, come illustrato nell'esempio seguente:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Abilitare quindi l'account Microsoft Teams Rooms per Skype for Business Server eseguendo il cmdlet seguente:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > I nuovi account utente potrebbero non essere creati nello stesso pool di registrar degli account utente esistenti nel tenant. Il comando precedente impedirà errori nella configurazione dell'account a causa di questa situazione.

## <a name="validate"></a>Convalida

Per la convalida, dovrebbe essere possibile usare qualsiasi client Skype for Business per accedere all'account creato.

## <a name="see-also"></a>Vedere anche

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Microsoft Teams Rooms Licenze](rooms-licensing.md)
