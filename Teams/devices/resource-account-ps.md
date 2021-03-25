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
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="28144-103">Creare un account delle risorse di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="28144-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="28144-104">Leggere questo argomento per informazioni su come creare account delle risorse per le barre di collaborazione per Microsoft Teams con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28144-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="28144-105">Il modo più semplice per creare un account delle risorse è usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28144-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="28144-106">[Vedere questo articolo su come eseguire questa operazione.](resource-account-ui.md)</span><span class="sxs-lookup"><span data-stu-id="28144-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="28144-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28144-107">Requirements</span></span>

<span data-ttu-id="28144-108">Prima di distribuire Microsoft Teams Rooms con Office 365, assicurarsi di aver soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="28144-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="28144-109">Per altre informazioni, vedere [Distribuire barre di collaborazione per Microsoft Teams.](collab-bar-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="28144-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="28144-110">Se sono necessarie funzionalità PSTN per la barra di collaborazione, è necessaria la licenza Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="28144-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="28144-111">Gli account delle risorse devono avere cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="28144-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="28144-112">Poiché si tratta di account delle risorse, non è richiesta alcuna licenza di Exchange.</span><span class="sxs-lookup"><span data-stu-id="28144-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="28144-113">È consigliabile usare la licenza Sale riunioni per gli account delle risorse.</span><span class="sxs-lookup"><span data-stu-id="28144-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="28144-114">Aggiungere un account della risorsa</span><span class="sxs-lookup"><span data-stu-id="28144-114">Add a resource account</span></span>

1. <span data-ttu-id="28144-115">Connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28144-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="28144-116">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online.](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)</span><span class="sxs-lookup"><span data-stu-id="28144-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="28144-117">In PowerShell di Exchange Online creare una nuova cassetta postale della chat room o modificare una cassetta postale della chat room esistente.</span><span class="sxs-lookup"><span data-stu-id="28144-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="28144-118">Per creare una nuova cassetta postale della chat room, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="28144-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="28144-119">In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28144-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="28144-120">Nome: Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="28144-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="28144-121">Alias: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="28144-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="28144-122">Account: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="28144-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="28144-123">Password dell'account: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="28144-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="28144-124">Per modificare una cassetta postale della chat room esistente, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="28144-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="28144-125">Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias HuddleRoom02 e imposta la password su 808P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="28144-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="28144-126">Si noti che l'account verrà HuddleRoom02@contoso.onmicrosoft.com a causa del valore alias esistente.</span><span class="sxs-lookup"><span data-stu-id="28144-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="28144-127">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="28144-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="28144-128">In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza della riunione:</span><span class="sxs-lookup"><span data-stu-id="28144-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="28144-129">AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'utente: free = accept; busy = decline).</span><span class="sxs-lookup"><span data-stu-id="28144-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="28144-130">AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).</span><span class="sxs-lookup"><span data-stu-id="28144-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="28144-131">DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="28144-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="28144-132">DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="28144-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="28144-133">RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).</span><span class="sxs-lookup"><span data-stu-id="28144-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="28144-134">AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).</span><span class="sxs-lookup"><span data-stu-id="28144-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="28144-135">AdditionalResponse: "Questa sala ha una barra di collaborazione per Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="28144-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="28144-136">Il testo aggiuntivo da aggiungere alla convocazione riunione.</span><span class="sxs-lookup"><span data-stu-id="28144-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="28144-137">Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Huddle-Room-01.</span><span class="sxs-lookup"><span data-stu-id="28144-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="28144-138">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="28144-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="28144-139">Connettersi a PowerShell di MS Online per impostare Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet powershell.</span><span class="sxs-lookup"><span data-stu-id="28144-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="28144-140">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="28144-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="28144-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="28144-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="28144-142">Impostare la password per huddleroom01@contoso.onmicrosoft.com non scadrà usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="28144-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="28144-143">L'account della risorsa deve avere una licenza di Office 365 valida, preferibilmente lo SKU della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="28144-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="28144-144">È anche necessario assegnare una posizione di utilizzo all'account del dispositivo, in modo da determinare quali SKU di licenza sono disponibili per l'account.</span><span class="sxs-lookup"><span data-stu-id="28144-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="28144-145">È possibile usare `Get-MsolAccountSku` per recuperare un elenco di SKU disponibili per il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="28144-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="28144-146">È possibile assegnare la licenza usando Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="28144-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="28144-147">Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con PowerShell di Office 365.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="28144-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="28144-148">Configurare gli account per le barre di collaborazione per Microsoft Teams con PowerShell</span><span class="sxs-lookup"><span data-stu-id="28144-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="28144-149">Distribuire barre di collaborazione per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28144-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="28144-150">Barre di collaborazione per le licenze di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28144-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)