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
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="80059-103">Creare un account delle risorse di Microsoft 365 tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="80059-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="80059-104">Leggere questo argomento per informazioni su come creare gli account delle risorse per le barre di collaborazione per Microsoft teams tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80059-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="80059-105">Il modo più semplice per creare un account di risorse consiste nell'usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80059-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="80059-106">[Vedere questo articolo su come eseguire questa](resource-account-ui.md)operazione.</span><span class="sxs-lookup"><span data-stu-id="80059-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="80059-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80059-107">Requirements</span></span>

<span data-ttu-id="80059-108">Prima di distribuire le sale di Microsoft teams con Office 365, assicurarsi di avere soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="80059-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="80059-109">Per altre informazioni, vedere [distribuire barre di collaborazione per Microsoft teams](collab-bar-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="80059-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="80059-110">Se sono necessarie funzionalità PSTN per la barra di collaborazione, sarà necessaria la licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="80059-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="80059-111">Gli account delle risorse devono avere cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="80059-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="80059-112">Poiché si tratta di account delle risorse, non è richiesta alcuna licenza di Exchange.</span><span class="sxs-lookup"><span data-stu-id="80059-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="80059-113">È consigliabile l'utilizzo della licenza sale riunioni per gli account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="80059-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="80059-114">Aggiungere un account di risorse</span><span class="sxs-lookup"><span data-stu-id="80059-114">Add a resource account</span></span>

1. <span data-ttu-id="80059-115">Connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80059-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="80059-116">Per istruzioni, vedere [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span><span class="sxs-lookup"><span data-stu-id="80059-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="80059-117">In PowerShell di Exchange Online creare una nuova cassetta postale della sala o modificare una cassetta postale della sala esistente.</span><span class="sxs-lookup"><span data-stu-id="80059-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="80059-118">Per creare una nuova cassetta postale della sala, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80059-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="80059-119">Questo esempio crea una nuova cassetta postale della sala con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80059-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="80059-120">Nome: rannicchiata-Sala-01</span><span class="sxs-lookup"><span data-stu-id="80059-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="80059-121">Alias: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="80059-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="80059-122">Account: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="80059-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="80059-123">Password account: P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="80059-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="80059-124">Per modificare una cassetta postale della sala esistente, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80059-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="80059-125">Questo esempio Abilita l'account per la cassetta postale della sala esistente con il valore alias HuddleRoom02 e imposta la password su 808P@ $ $W 0RD.</span><span class="sxs-lookup"><span data-stu-id="80059-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="80059-126">Tieni presente che l'account verrà HuddleRoom02@contoso.onmicrosoft.com a causa del valore alias esistente.</span><span class="sxs-lookup"><span data-stu-id="80059-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="80059-127">Per informazioni dettagliate su sintassi e parametri, vedere [nuove cassette postali](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="80059-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="80059-128">In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza di riunione:</span><span class="sxs-lookup"><span data-stu-id="80059-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="80059-129">AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono direttamente la decisione di prenotazione della sala senza intervento umano: gratuito = accetta; occupato = declino).</span><span class="sxs-lookup"><span data-stu-id="80059-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="80059-130">AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).</span><span class="sxs-lookup"><span data-stu-id="80059-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="80059-131">DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="80059-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="80059-132">DeleteSubject: $false (Mantieni l'oggetto delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="80059-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="80059-133">RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).</span><span class="sxs-lookup"><span data-stu-id="80059-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="80059-134">AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).</span><span class="sxs-lookup"><span data-stu-id="80059-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="80059-135">AdditionalResponse: "questa sala ha una barra di collaborazione per Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="80059-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="80059-136">(Il testo aggiuntivo da aggiungere alla convocazione di riunione)</span><span class="sxs-lookup"><span data-stu-id="80059-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="80059-137">In questo esempio vengono configurate queste impostazioni nella cassetta postale della sala denominata rannicchiate-Room-01.</span><span class="sxs-lookup"><span data-stu-id="80059-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="80059-138">Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="80059-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="80059-139">Connettersi a MS Online PowerShell per impostare le impostazioni di Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80059-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="80059-140">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="80059-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="80059-141">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="80059-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="80059-142">Impostare la password per huddleroom01@contoso.onmicrosoft.com per non scadere usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80059-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="80059-143">L'account delle risorse deve avere una licenza di Office 365 valida, preferibilmente la SKU della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="80059-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="80059-144">È inoltre necessario assegnare una posizione di utilizzo all'account del dispositivo, determinando gli SKU di licenza disponibili per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="80059-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="80059-145">Puoi usare `Get-MsolAccountSku` per recuperare un elenco di SKU disponibili per il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="80059-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="80059-146">È possibile assegnare la licenza tramite Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="80059-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="80059-147">Per istruzioni dettagliate, vedere [assegnare licenze agli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="80059-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="80059-148">Configurare gli account per le barre di collaborazione per Microsoft teams tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="80059-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="80059-149">Distribuire barre di collaborazione per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80059-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="80059-150">Barre di collaborazione per Microsoft teams Licensing</span><span class="sxs-lookup"><span data-stu-id="80059-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


