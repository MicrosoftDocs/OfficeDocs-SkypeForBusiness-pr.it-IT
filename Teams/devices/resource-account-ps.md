---
title: Creazione di account delle risorse di Microsoft teams per le barre di collaborazione per Microsoft teams tramite PowerShell
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
description: Leggere questo argomento per informazioni su come distribuire barre di collaborazione per Microsoft teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268053"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Creare un account delle risorse di Microsoft 365 tramite PowerShell

Leggere questo argomento per informazioni su come creare gli account delle risorse per le barre di collaborazione per Microsoft teams tramite PowerShell.

Il modo più semplice per creare un account di risorse consiste nell'usare l'interfaccia di amministrazione di Microsoft 365. [Vedere questo articolo su come eseguire questa](resource-account-ui.md)operazione.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Requisiti

Prima di distribuire le sale di Microsoft teams con Office 365, assicurarsi di avere soddisfatto i requisiti. Per altre informazioni, vedere [distribuire barre di collaborazione per Microsoft teams](collab-bar-deploy.md).

- Se sono necessarie funzionalità PSTN per la barra di collaborazione, sarà necessaria la licenza per il sistema telefonico.

- Gli account delle risorse devono avere cassette postali di Exchange. Poiché si tratta di account delle risorse, non è richiesta alcuna licenza di Exchange. È consigliabile l'utilizzo della licenza sale riunioni per gli account delle risorse.


### <a name="add-a-resource-account"></a>Aggiungere un account di risorse

1. Connettersi a PowerShell di Exchange Online. Per istruzioni, vedere [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. In PowerShell di Exchange Online creare una nuova cassetta postale della sala o modificare una cassetta postale della sala esistente.

   - Per creare una nuova cassetta postale della sala, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio crea una nuova cassetta postale della sala con le impostazioni seguenti:

     - Nome: rannicchiata-Sala-01

     - Alias: HuddleRoom01

     - Account: huddleroom01@contoso.onmicrosoft.com

     - Password account: P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Per modificare una cassetta postale della sala esistente, usare la sintassi seguente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio Abilita l'account per la cassetta postale della sala esistente con il valore alias HuddleRoom02 e imposta la password su 808P@ $ $W 0RD. Tieni presente che l'account verrà HuddleRoom02@contoso.onmicrosoft.com a causa del valore alias esistente.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Per informazioni dettagliate su sintassi e parametri, vedere [nuove cassette postali](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza di riunione:

   - AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono direttamente la decisione di prenotazione della sala senza intervento umano: gratuito = accetta; occupato = declino).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).

   - DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni di riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "questa sala ha una barra di collaborazione per Microsoft Teams!" (Il testo aggiuntivo da aggiungere alla convocazione di riunione)

   In questo esempio vengono configurate queste impostazioni nella cassetta postale della sala denominata rannicchiate-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Connettersi a MS Online PowerShell per impostare le impostazioni di Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet di PowerShell.   Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

5. Impostare la password per huddleroom01@contoso.onmicrosoft.com per non scadere usando la sintassi seguente:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. L'account delle risorse deve avere una licenza di Office 365 valida, preferibilmente la SKU della sala riunioni. È inoltre necessario assegnare una posizione di utilizzo all'account del dispositivo, determinando gli SKU di licenza disponibili per il proprio account. Puoi usare `Get-MsolAccountSku` per recuperare un elenco di SKU disponibili per il tenant di Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    È possibile assegnare la licenza tramite Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Per istruzioni dettagliate, vedere [assegnare licenze agli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).




[Configurare gli account per le barre di collaborazione per Microsoft teams tramite PowerShell](resource-account-ps.md)

[Distribuire barre di collaborazione per Microsoft Teams](collab-bar-deploy.md)

[Barre di collaborazione per Microsoft teams Licensing](../rooms/rooms-licensing.md)


