---
title: Distribuire Microsoft Teams Rooms con Exchange locale (ibrida)
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leggere questo argomento per informazioni su come distribuire le Microsoft Teams Rooms in un ambiente ibrido con Exchange locale.
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767229"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Distribuire Microsoft Teams Rooms con Exchange locale (ibrida)

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms in un ambiente ibrido con Exchange locali e Microsoft Teams.
  
Se l'organizzazione ha una combinazione di servizi, con alcuni servizi ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio. Questo argomento riguarda le distribuzioni ibride Microsoft Teams Rooms con Exchange ospitate in locale. Poiché questo tipo di distribuzione offre moltissime varianti diverse, non è possibile fornire istruzioni dettagliate per tutte. Il processo seguente funziona per molte configurazioni. Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.
  
## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Exchange locale, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere Microsoft Teams Rooms [requisiti.](requirements.md)

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Abilitare la cassetta postale remota e impostare le proprietà

1. [Aprire la Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server di Exchange tramite Una sessione remota di PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. In Exchange PowerShell creare una nuova cassetta postale sala o modificare una cassetta postale della chat room esistente. Per impostazione predefinita, alle cassette postali della chat room non sono associati account, quindi sarà necessario aggiungere un account quando si crea o si modifica una cassetta postale della chat room che le consente di eseguire l'autenticazione con Microsoft Teams.

   - Per creare una nuova cassetta postale della chat room, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

     - Account: ConferenceRoom01@contoso.com
  
     - Nome: ConferenceRoom01

     - Alias: ConferenceRoom01

     - Password dell'account: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
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

3. In Exchange PowerShell configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono le decisioni di prenotazione della sala direttamente senza l'intervento dell'uomo).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni di riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Si tratta di una Microsoft Teams sala riunioni!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale sala denominata ConferenceRoom01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="set-password-to-never-expire"></a>Impostare la password in modo che non scada mai

1. Nello strumento Utenti e computer di **Active Directory** trovare l'account Microsoft Teams Rooms, fare clic con il pulsante destro del mouse su di esso e scegliere **Proprietà**.

2. Selezionare la **casella di controllo Nessuna scadenza password** e quindi fare clic su **OK.**

   > [!NOTE]
   > La **selezione della password non scade** mai è un requisito per Microsoft Teams Rooms. Le regole di dominio potrebbero proibire le password che non scadono. In questo caso, è necessario creare un'eccezione per ogni account Microsoft Teams Rooms account.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Assegnare una Microsoft 365 o Office 365 licenza

1. Connessione a Azure Active Directory. Per informazioni dettagliate Azure Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

2. È necessario che l'account della risorsa abbia una licenza Microsoft 365 o Office 365 o che Exchange e Microsoft Teams non funzionino. Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account delle risorse, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> per recuperare un elenco di SKU disponibili.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. Successivamente, è possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Questo esempio aggiunge la licenza Sala riunioni all'account:

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

Per la convalida, dovrebbe essere possibile usare qualsiasi client per accedere a questo account.
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
