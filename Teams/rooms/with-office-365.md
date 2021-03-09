---
title: Distribuire sale di Microsoft Teams con Microsoft 365 o Office 365
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
description: Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams con Microsoft 365 o Office 365, dove Teams o Skype for Business ed Exchange sono entrambi online.
ms.openlocfilehash: 7a25fb17e4b9fce4a51c6e2be5828ecafff59894
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569122"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="9433e-103">Distribuire sale di Microsoft Teams con Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="9433e-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="9433e-104">Leggere questo argomento per informazioni su come distribuire le sale di Microsoft Teams con Microsoft 365 o Office 365, dove Microsoft Teams o Skype for Business ed Exchange sono entrambi online.</span><span class="sxs-lookup"><span data-stu-id="9433e-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="9433e-105">Il modo più semplice per configurare gli account utente è configurarli tramite la Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9433e-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="9433e-106">Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti per trasformarli in account utente di Microsoft Teams Room compatibili.</span><span class="sxs-lookup"><span data-stu-id="9433e-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="9433e-107">Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno utilizzati dal dispositivo Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="9433e-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="9433e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9433e-108">Requirements</span></span>

<span data-ttu-id="9433e-109">Prima di distribuire le sale di Microsoft Teams con Microsoft 365 o Office 365, assicurarsi di aver soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="9433e-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="9433e-110">Per altre informazioni, vedere Requisiti [di Sale di Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="9433e-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="9433e-111">Per abilitare Skype for Business, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9433e-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="9433e-112">Skype for Business online (Piano 2 o un piano enterprise) o versione successiva nel piano Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="9433e-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="9433e-113">Il piano deve consentire le funzionalità di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9433e-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="9433e-114">Se sono necessarie funzionalità di accesso esterno per una riunione, è necessaria una licenza per Audioconferenza e Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="9433e-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="9433e-115">Se sono necessarie funzionalità di chiamata in uscita durante una riunione, è necessaria una licenza per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="9433e-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="9433e-116">Gli utenti del tenant devono disporre di cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="9433e-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="9433e-117">L'account Microsoft Teams Rooms richiede almeno una licenza di Skype for Business online (Piano 2), ma non di una licenza di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9433e-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="9433e-118">Per informazioni [dettagliate, vedere](rooms-licensing.md) le licenze Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="9433e-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="9433e-119">Per informazioni dettagliate sui piani di Skype for Business online, vedere la descrizione del servizio [Skype for Business online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="9433e-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="9433e-120">Aggiungere un account del dispositivo</span><span class="sxs-lookup"><span data-stu-id="9433e-120">Add a device account</span></span>

1. <span data-ttu-id="9433e-121">Connettersi a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9433e-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="9433e-122">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online.](https://go.microsoft.com/fwlink/p/?linkid=396554)</span><span class="sxs-lookup"><span data-stu-id="9433e-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="9433e-123">In PowerShell di Exchange Online creare una nuova cassetta postale della sala o modificarne una esistente.</span><span class="sxs-lookup"><span data-stu-id="9433e-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="9433e-124">Per impostazione predefinita, le cassette postali della sala non sono associate ad account, quindi è necessario aggiungere un account quando si crea o si modifica una cassetta postale della sala che consente l'autenticazione con Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="9433e-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="9433e-125">Per creare una nuova cassetta postale della sala, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9433e-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9433e-126">In questo esempio viene creata una nuova cassetta postale della chat room con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9433e-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="9433e-127">Nome: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="9433e-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="9433e-128">Alias: Rigel1</span><span class="sxs-lookup"><span data-stu-id="9433e-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="9433e-129">Account: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9433e-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="9433e-130">Password account: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="9433e-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="9433e-131">Per modificare una cassetta postale della sala esistente, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9433e-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9433e-132">Questo esempio abilita l'account per la cassetta postale della chat room esistente con il valore alias Rigel2 e imposta la password su 9898P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="9433e-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="9433e-133">Si noti che l'account verrà Rigel2@contoso.onmicrosoft.com a causa del valore di alias esistente.</span><span class="sxs-lookup"><span data-stu-id="9433e-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="9433e-134">Per informazioni dettagliate su sintassi e parametri, vedere [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="9433e-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="9433e-135">In PowerShell di Exchange Online configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza della riunione:</span><span class="sxs-lookup"><span data-stu-id="9433e-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="9433e-136">AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'uomo: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="9433e-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="9433e-137">AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).</span><span class="sxs-lookup"><span data-stu-id="9433e-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="9433e-138">DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="9433e-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9433e-139">DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="9433e-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9433e-140">RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione riunione originale rimanga come specificato.)</span><span class="sxs-lookup"><span data-stu-id="9433e-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="9433e-141">AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni riunione).</span><span class="sxs-lookup"><span data-stu-id="9433e-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="9433e-142">AdditionalResponse: "Questa è una sala riunioni Skype!"</span><span class="sxs-lookup"><span data-stu-id="9433e-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="9433e-143">Il testo aggiuntivo da aggiungere alla convocazione riunione.</span><span class="sxs-lookup"><span data-stu-id="9433e-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="9433e-144">Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="9433e-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="9433e-145">Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="9433e-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="9433e-146">Connettersi a PowerShell di MS Online per eseguire le impostazioni di Active Directory eseguendo il `Connect-MsolService -Credential $cred` cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9433e-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="9433e-147">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="9433e-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9433e-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="9433e-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="9433e-149">Se non si vuole che la password scada, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9433e-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="9433e-150">Questo esempio imposta la password per l'account Rigel1@contoso.onmicrosoft.com non scade mai.</span><span class="sxs-lookup"><span data-stu-id="9433e-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="9433e-151">È anche possibile impostare un numero di telefono per l'account eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="9433e-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> <span data-ttu-id="9433e-152">Se la password non è impostata su Mai scadenza, l'account non potrà più accedere al dispositivo quando l'account raggiunge il periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9433e-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="9433e-153">La password dovrà quindi essere cambiata per l'account e aggiornata anche in locale nel dispositivo MTR.</span><span class="sxs-lookup"><span data-stu-id="9433e-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="9433e-154">L'account del dispositivo deve avere una licenza valida di Microsoft 365 o Office 365 oppure Exchange e Microsoft Teams o Skype for Business non funzionano.</span><span class="sxs-lookup"><span data-stu-id="9433e-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="9433e-155">Se si dispone della licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, che determina quali SKU di licenza sono disponibili per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="9433e-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="9433e-156">È possibile usare `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="9433e-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="9433e-157">per recuperare un elenco di SKU disponibili per l'organizzazione di Microsoft 365 o Office 365, come segue:</span><span class="sxs-lookup"><span data-stu-id="9433e-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="9433e-158">Successivamente, puoi aggiungere una licenza usando il pulsante `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="9433e-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="9433e-159">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9433e-159">cmdlet.</span></span> <span data-ttu-id="9433e-160">Questo esempio aggiunge all'account la licenza della sala riunioni:</span><span class="sxs-lookup"><span data-stu-id="9433e-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="9433e-161">Per istruzioni dettagliate, vedere [Assegnare licenze ad account utente con PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="9433e-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="9433e-162">Puoi anche aggiungere funzionalità Sistema telefonico a questo account, ma devi prima configurarlo.</span><span class="sxs-lookup"><span data-stu-id="9433e-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="9433e-163">Vedi [Che cos'è il Sistema telefonico?](../what-is-phone-system-in-office-365.md) Per maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="9433e-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="9433e-164">Questo esempio aggiunge il piano per chiamate PSTN nazionali e internazionali:</span><span class="sxs-lookup"><span data-stu-id="9433e-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="9433e-165">Successivamente, è necessario abilitare l'account del dispositivo con Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9433e-165">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="9433e-166">Assicurarsi che l'ambiente soddisfi i requisiti definiti nei requisiti di [Microsoft Teams Room.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="9433e-166">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="9433e-167">Avviare una sessione [Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) come indicato di seguito (assicurarsi di installare i componenti di PowerShell per Skype for [Business Online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="9433e-167">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="9433e-168">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="9433e-168">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="9433e-169">Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="9433e-169">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="9433e-170">Ottenere le informazioni di RegistrarPool dal nuovo account utente da configurare, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9433e-170">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="9433e-171">Abilitare quindi l'account Sale di Microsoft Teams per Skype for Business Server eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="9433e-171">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="9433e-172">È possibile che i nuovi account utente non siano stati creati nello stesso pool di registrar degli account utente esistenti nel tenant.</span><span class="sxs-lookup"><span data-stu-id="9433e-172">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="9433e-173">Il comando precedente evita errori nella configurazione dell'account a causa di questa situazione.</span><span class="sxs-lookup"><span data-stu-id="9433e-173">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="9433e-174">Convalida</span><span class="sxs-lookup"><span data-stu-id="9433e-174">Validate</span></span>

<span data-ttu-id="9433e-175">Per la convalida, dovrebbe essere possibile utilizzare qualsiasi client Skype for Business per accedere all'account creato.</span><span class="sxs-lookup"><span data-stu-id="9433e-175">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="9433e-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9433e-176">See also</span></span>

[<span data-ttu-id="9433e-177">Configurare gli account per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9433e-177">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="9433e-178">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="9433e-178">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="9433e-179">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="9433e-179">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="9433e-180">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="9433e-180">Configure a Microsoft Teams Rooms console</span></span>](console.md)

<span data-ttu-id="9433e-181">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="9433e-181">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>

[<span data-ttu-id="9433e-182">Licenze per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9433e-182">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
