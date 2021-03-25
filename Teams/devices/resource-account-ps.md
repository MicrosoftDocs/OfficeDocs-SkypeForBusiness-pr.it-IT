---
title: Creazione di account delle risorse di Microsoft Teams per le barre di collaborazione per Microsoft Teams con PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leggere questo argomento per informazioni su come distribuire barre di collaborazione per Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115604"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Creare un account delle risorse di Microsoft 365 con PowerShell

Leggere questo argomento per informazioni su come creare account delle risorse per le barre di collaborazione per Microsoft Teams con PowerShell.

Il modo più semplice per creare un account delle risorse è usare l'interfaccia di amministrazione di Microsoft 365. [Vedere questo articolo su come eseguire questa operazione.](resource-account-ui.md)

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Office 365, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere [Distribuire barre di collaborazione per Microsoft Teams.](collab-bar-deploy.md)

- Se sono necessarie funzionalità PSTN per la barra di collaborazione, è necessaria la licenza Sistema telefonico.

- Gli account delle risorse devono avere cassette postali di Exchange. Poiché si tratta di account delle risorse, non è richiesta alcuna licenza di Exchange. È consigliabile usare la licenza Sale riunioni per gli account delle risorse.


### <a name="add-a-resource-account"></a>Aggiungere un account della risorsa

1. Connettersi a PowerShell di Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online.](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. In PowerShell di Exchange Online creare una nuova cassetta postale della chat room o modificare una cassetta postale della chat room esistente.

   - Per creare una nuova cassetta postale della chat room, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

     - Nome: Huddle-Room-01

     - Alias: HuddleRoom01

     - Account: huddleroom01@contoso.onmicrosoft.com

     - Password dell'account: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Per modificare una cassetta postale della chat room esistente, usare la sintassi seguente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias HuddleRoom02 e imposta la password su 808P@$$W 0rd. Si noti che l'account verrà HuddleRoom02@contoso.onmicrosoft.com a causa del valore alias esistente.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'utente: free = accept; busy = decline).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Questa sala ha una barra di collaborazione per Microsoft Teams!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Huddle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connettersi a PowerShell di MS Online per impostare Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet powershell.   Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

5. Impostare la password per huddleroom01@contoso.onmicrosoft.com non scadrà usando la sintassi seguente:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. L'account della risorsa deve avere una licenza di Office 365 valida, preferibilmente lo SKU della sala riunioni. È anche necessario assegnare una posizione di utilizzo all'account del dispositivo, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` per recuperare un elenco di SKU disponibili per il tenant di Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    È possibile assegnare la licenza usando Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con PowerShell di Office 365.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)




[Configurare gli account per le barre di collaborazione per Microsoft Teams con PowerShell](resource-account-ps.md)

[Distribuire barre di collaborazione per Microsoft Teams](collab-bar-deploy.md)

[Barre di collaborazione per le licenze di Microsoft Teams](../rooms/rooms-licensing.md)