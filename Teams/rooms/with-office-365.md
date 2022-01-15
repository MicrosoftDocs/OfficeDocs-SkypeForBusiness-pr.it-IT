---
title: Distribuire Microsoft Teams Rooms con Office 365
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Office 365.
ms.openlocfilehash: d4c66fb863c5c41a717808ddca43002752510fb5
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056026"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Distribuire Microsoft Teams Rooms con Office 365

Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Office 365.

## <a name="requirements"></a>Requisiti

Prima di distribuire Microsoft Teams Rooms con Office 365, assicurarsi di aver soddisfatto i requisiti. Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)

### <a name="add-a-resource-account"></a>Aggiungere un account della risorsa

1. Connessione a Exchange Online PowerShell. Per istruzioni, vedere [Connessione per Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. In Exchange Online PowerShell creare una nuova cassetta postale della chat room o modificare una cassetta postale della chat room esistente. Per impostazione predefinita, alle cassette postali della chat room non sono associati account. È necessario aggiungere un account quando si crea o si modifica una cassetta postale della chat room che consente l'autenticazione.

   - Per creare una nuova cassetta postale della chat room, usare la sintassi seguente:

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:

     - Nome: Sala riunioni 01

     - Alias: ConferenceRoom01

     - Account: ConferenceRoom01@contoso.com

     - Password dell'account: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Per modificare una cassetta postale della chat room esistente, usare la sintassi seguente:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias ConferenceRoom02 e imposta la password su 9898P@$$W 0rd.

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. In Exchange Online PowerShell configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:

   - AutomateProcessing: AutoAccept (la cassetta postale prende automaticamente una decisione di prenotazione sala direttamente senza l'intervento dell'uomo).

   - AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).

   - DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).

   - DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).

   - RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).

   - AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).

   - AdditionalResponse: "Si tratta di una Microsoft Teams sala riunioni!" Il testo aggiuntivo da aggiungere alla convocazione riunione.

   Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).
   
4. Connessione su PowerShell di MS Online impostare i valori di Active Directory eseguendo il cmdlet di powershell 'Connessione-MsolService -Credential $cred'. Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato. 

5. È consigliabile disabilitare la scadenza delle password Teams Rooms account. Di seguito è riportato un esempio di come disabilitare la scadenza della password per l'account ConferenceRoom01:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. L'account della risorsa deve avere una licenza Office 365 per connettersi a Microsoft Teams. È anche necessario assegnare una posizione di utilizzo all'account del dispositivo, in modo da determinare quali SKU di licenza sono disponibili per l'account. È possibile usare `Get-MsolAccountSku` per recuperare un elenco di SKU disponibili per il tenant Office 365 tenant. È possibile aggiungere una licenza usando il `Set-MsolUserLicense` cmdlet.

   Questo esempio assegna la licenza Sala riunioni a un utente con sede negli Stati Uniti.

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)


## <a name="validate"></a>Convalida

Per la convalida, dovrebbe essere possibile usare qualsiasi client Microsoft Teams per accedere all'account creato.

## <a name="see-also"></a>Vedere anche
[Aggiornare le cassette postali della chat room con metadati aggiuntivi per migliorare l'esperienza di ricerca e suggerimenti per le chat room](/powershell/module/exchange/set-place)

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Microsoft Teams Rooms licenze](rooms-licensing.md)
