---
title: Distribuire Microsoft teams Rooms con Microsoft 365 o Office 365
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Microsoft 365 o Office 365, in cui i team o Skype for business e Exchange sono entrambi online.
ms.openlocfilehash: ee1f4da5cbcb65ab58c032ac651e0b563167a35b
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814795"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="7f49c-103">Distribuire Microsoft teams Rooms con Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="7f49c-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="7f49c-104">Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Microsoft 365 o Office 365, in cui Microsoft teams o Skype for business e Exchange sono entrambi online.</span><span class="sxs-lookup"><span data-stu-id="7f49c-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="7f49c-105">Il modo più semplice per configurare gli account utente consiste nel configurarli con Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="7f49c-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="7f49c-106">Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o di convalidare gli account di risorse esistenti per poterli trasformare in account utente di Microsoft teams Rooms compatibili.</span><span class="sxs-lookup"><span data-stu-id="7f49c-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="7f49c-107">Se si preferisce, è possibile eseguire la procedura seguente per configurare gli account che verranno usati dal dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="7f49c-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f49c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f49c-108">Requirements</span></span>

<span data-ttu-id="7f49c-109">Prima di distribuire le sale di Microsoft teams con Microsoft 365 o Office 365, verificare di avere soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="7f49c-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="7f49c-110">Per altre informazioni, Vedi [requisiti di Microsoft teams Rooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f49c-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="7f49c-111">Per abilitare Skype for business, è necessario avere la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="7f49c-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="7f49c-112">Skype for business online (piano 2 o un piano basato sull'organizzazione) o superiore nel piano Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f49c-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="7f49c-113">Il piano deve consentire le funzionalità di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="7f49c-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="7f49c-114">Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per l'audioconferenza e il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="7f49c-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="7f49c-115">Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessaria una licenza per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="7f49c-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="7f49c-116">Gli utenti del tenant devono avere cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7f49c-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="7f49c-117">L'account di Microsoft teams Rooms richiede almeno una licenza di Skype for business online (piano 2), ma non richiede una licenza di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f49c-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="7f49c-118">Per informazioni dettagliate, vedere [licenze di Microsoft teams Rooms](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="7f49c-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="7f49c-119">Per informazioni dettagliate sui piani di Skype for business online, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="7f49c-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="7f49c-120">Aggiungere un account di dispositivo</span><span class="sxs-lookup"><span data-stu-id="7f49c-120">Add a device account</span></span>

1. <span data-ttu-id="7f49c-121">Connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f49c-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="7f49c-122">Per istruzioni, vedere [connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="7f49c-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="7f49c-123">In PowerShell di Exchange Online creare una nuova cassetta postale della sala o modificare una cassetta postale della sala esistente.</span><span class="sxs-lookup"><span data-stu-id="7f49c-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="7f49c-124">Per impostazione predefinita, le cassette postali della sala non hanno account associati, quindi è necessario aggiungere un account quando si crea o si modifica una cassetta postale della sala che consente l'autenticazione con Skype room Systems V2.</span><span class="sxs-lookup"><span data-stu-id="7f49c-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="7f49c-125">Per creare una nuova cassetta postale della sala, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7f49c-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="7f49c-126">Questo esempio crea una nuova cassetta postale della sala con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f49c-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="7f49c-127">Nome: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="7f49c-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="7f49c-128">Alias: Rigel1</span><span class="sxs-lookup"><span data-stu-id="7f49c-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="7f49c-129">Account: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7f49c-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="7f49c-130">Password account: P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="7f49c-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="7f49c-131">Per modificare una cassetta postale della sala esistente, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7f49c-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="7f49c-132">Questo esempio Abilita l'account per la cassetta postale della sala esistente con il valore alias Rigel2 e imposta la password su 9898P@ $ $W 0RD.</span><span class="sxs-lookup"><span data-stu-id="7f49c-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="7f49c-133">Tieni presente che l'account verrà Rigel2@contoso.onmicrosoft.com a causa del valore alias esistente.</span><span class="sxs-lookup"><span data-stu-id="7f49c-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="7f49c-134">Per informazioni dettagliate su sintassi e parametri, vedere [nuove cassette postali](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="7f49c-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="7f49c-135">In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza di riunione:</span><span class="sxs-lookup"><span data-stu-id="7f49c-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="7f49c-136">AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono direttamente la decisione di prenotazione della sala senza intervento umano: gratuito = accetta; occupato = declino).</span><span class="sxs-lookup"><span data-stu-id="7f49c-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="7f49c-137">AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).</span><span class="sxs-lookup"><span data-stu-id="7f49c-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="7f49c-138">DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="7f49c-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="7f49c-139">DeleteSubject: $false (Mantieni l'oggetto delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="7f49c-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="7f49c-140">RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).</span><span class="sxs-lookup"><span data-stu-id="7f49c-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="7f49c-141">AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).</span><span class="sxs-lookup"><span data-stu-id="7f49c-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="7f49c-142">AdditionalResponse: "si tratta di una sala riunioni Skype!"</span><span class="sxs-lookup"><span data-stu-id="7f49c-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="7f49c-143">(Il testo aggiuntivo da aggiungere alla convocazione di riunione)</span><span class="sxs-lookup"><span data-stu-id="7f49c-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="7f49c-144">Questo esempio configura queste impostazioni nella cassetta postale della sala denominata Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="7f49c-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="7f49c-145">Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="7f49c-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="7f49c-146">Connettersi a MS Online PowerShell per impostare le impostazioni di Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f49c-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="7f49c-147">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="7f49c-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="7f49c-148">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="7f49c-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="7f49c-149">Se non si vuole che la password scada, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7f49c-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="7f49c-150">Questo esempio imposta la password per l'account Rigel1@contoso.onmicrosoft.com per non scadere mai.</span><span class="sxs-lookup"><span data-stu-id="7f49c-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="7f49c-151">È anche possibile impostare un numero di telefono per l'account eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7f49c-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="7f49c-152">L'account del dispositivo deve avere una licenza valida per Microsoft 365 o Office 365 oppure Exchange e Microsoft teams o Skype for business non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="7f49c-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="7f49c-153">Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, determinando gli SKU di licenza disponibili per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="7f49c-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="7f49c-154">Puoi usare `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="7f49c-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="7f49c-155">per recuperare un elenco di SKU disponibili per l'organizzazione Microsoft 365 o Office 365, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7f49c-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="7f49c-156">È quindi possibile aggiungere una licenza usando la `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="7f49c-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="7f49c-157">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7f49c-157">cmdlet.</span></span> <span data-ttu-id="7f49c-158">In questo caso, $strLicense è il codice SKU visualizzato, ad esempio contoso: STANDARDPACK.</span><span class="sxs-lookup"><span data-stu-id="7f49c-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="7f49c-159">Per istruzioni dettagliate, vedere [assegnare licenze agli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7f49c-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="7f49c-160">Devi quindi abilitare l'account del dispositivo con Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7f49c-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="7f49c-161">Assicurarsi che l'ambiente soddisfi i requisiti definiti nei [requisiti di Microsoft teams Rooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f49c-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="7f49c-162">Avviare una sessione remota di [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) come indicato di seguito (assicurarsi di [installare i componenti di PowerShell per Skype for business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="7f49c-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>
   
> [!NOTE]
> <span data-ttu-id="7f49c-163">Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.</span><span class="sxs-lookup"><span data-stu-id="7f49c-163">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="7f49c-164">Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="7f49c-164">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="7f49c-165">Attiva quindi l'account di Microsoft teams Rooms per Skype for Business Server eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="7f49c-165">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="7f49c-166">Ottenere le informazioni di RegistrarPool dal nuovo account utente configurato, come illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="7f49c-166">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > New user accounts might not be created on the same registrar pool as existing user accounts in the tenant. The command above will prevent errors in account setup due to this situation.

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="7f49c-167">Assegnare una licenza al proprio account</span><span class="sxs-lookup"><span data-stu-id="7f49c-167">Assign a license to your account</span></span>

1. <span data-ttu-id="7f49c-168">Accedere come amministratore del tenant, aprire l'interfaccia di amministrazione di Microsoft 365 e fare clic sull'app di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="7f49c-168">Login as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>

2. <span data-ttu-id="7f49c-169">Fare clic su **utenti e gruppi** e quindi su **Aggiungi utenti, Reimposta password e altro ancora**.</span><span class="sxs-lookup"><span data-stu-id="7f49c-169">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="7f49c-170">Selezionare l'account Microsoft teams Rooms e quindi fare clic o toccare l'icona della penna, ovvero modifica.</span><span class="sxs-lookup"><span data-stu-id="7f49c-170">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="7f49c-171">Fare clic sull'opzione **licenze** .</span><span class="sxs-lookup"><span data-stu-id="7f49c-171">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="7f49c-172">Nella sezione **assegnazione licenze** è necessario selezionare Skype for business online (piano 2) o Skype for business online (piano 3), a seconda della licenza e delle operazioni che si sono decisi in termini di necessità di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7f49c-172">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="7f49c-173">È necessario usare una licenza di piano 3 Se si vuole usare Cloud PBX in Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="7f49c-173">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="7f49c-174">Sarà necessario CloudPBX per la connettività vocale.</span><span class="sxs-lookup"><span data-stu-id="7f49c-174">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="7f49c-175">Configura quindi la chiamata vocale ibrida o PSTN in base al metodo di connettività PSTN.</span><span class="sxs-lookup"><span data-stu-id="7f49c-175">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="7f49c-176">Per altre informazioni, Vedi [licenze di Microsoft teams Rooms](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="7f49c-176">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for more details.</span></span>

6. <span data-ttu-id="7f49c-177">Fare clic su **Salva** per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="7f49c-177">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="7f49c-178">Esempio: configurazione dell'account della sala in Exchange Online e Skype for business online</span><span class="sxs-lookup"><span data-stu-id="7f49c-178">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="7f49c-179">Comandi di PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="7f49c-179">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="7f49c-180">Comandi di PowerShell di Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="7f49c-180">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="7f49c-181">Comando di PowerShell per Skype for business:</span><span class="sxs-lookup"><span data-stu-id="7f49c-181">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="7f49c-182">In questo articolo vengono aggiunte CloudPBX e PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="7f49c-182">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="7f49c-183">Sarà inoltre necessario usare l'interfaccia di amministrazione per assegnare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="7f49c-183">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="7f49c-184">Convalidare</span><span class="sxs-lookup"><span data-stu-id="7f49c-184">Validate</span></span>

<span data-ttu-id="7f49c-185">Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for business per accedere all'account creato.</span><span class="sxs-lookup"><span data-stu-id="7f49c-185">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f49c-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f49c-186">See also</span></span>

[<span data-ttu-id="7f49c-187">Configurare gli account per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f49c-187">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="7f49c-188">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="7f49c-188">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="7f49c-189">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="7f49c-189">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="7f49c-190">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="7f49c-190">Configure a Microsoft Teams Rooms console</span></span>](console.md)

<span data-ttu-id="7f49c-191">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="7f49c-191">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>

[<span data-ttu-id="7f49c-192">Licenze di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="7f49c-192">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
