---
title: Distribuire sale di Microsoft Teams con Exchange locale
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams in un ambiente ibrido con Exchange locale.
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662321"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="3126a-103">Distribuire sale di Microsoft Teams con Exchange locale</span><span class="sxs-lookup"><span data-stu-id="3126a-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="3126a-104">Leggere questo argomento per informazioni su come distribuire le sale di Microsoft Teams in un ambiente ibrido con Exchange locale e Microsoft Teams o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3126a-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="3126a-105">Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online, la configurazione dipenderà da dove è ospitato ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="3126a-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="3126a-106">Questo argomento illustra le distribuzioni ibride per le sale di Microsoft Teams con Exchange ospitato in locale.</span><span class="sxs-lookup"><span data-stu-id="3126a-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="3126a-107">Poiché esistono così tante varianti diverse in questo tipo di distribuzione, non è possibile fornire istruzioni dettagliate per tutte.</span><span class="sxs-lookup"><span data-stu-id="3126a-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="3126a-108">Il processo seguente funziona per molte configurazioni.</span><span class="sxs-lookup"><span data-stu-id="3126a-108">The following process will work for many configurations.</span></span> <span data-ttu-id="3126a-109">Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale illustrato qui e per altre opzioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3126a-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="3126a-110">Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in essere per trasformarli in account utente di Microsoft Teams Room compatibili.</span><span class="sxs-lookup"><span data-stu-id="3126a-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="3126a-111">Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno utilizzati dal dispositivo Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="3126a-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3126a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3126a-112">Requirements</span></span>

<span data-ttu-id="3126a-113">Prima di distribuire le sale di Microsoft Teams con Exchange locale, assicurarsi di aver soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="3126a-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="3126a-114">Per altre informazioni, vedere Requisiti [di Sale di Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3126a-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="3126a-115">Se si distribuiscono sale di Microsoft Teams con Exchange locale, si usano gli strumenti di amministrazione di Active Directory per aggiungere un indirizzo di posta elettronica per l'account di dominio locale.</span><span class="sxs-lookup"><span data-stu-id="3126a-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="3126a-116">Questo account verrà sincronizzato con Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3126a-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="3126a-117">Sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="3126a-117">You will need to:</span></span>
  
- <span data-ttu-id="3126a-118">Creare un account e sincronizzare l'account con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3126a-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="3126a-119">Abilitare la cassetta postale remota e impostare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="3126a-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="3126a-120">Assegnare una licenza di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3126a-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="3126a-121">Abilitare l'account del dispositivo con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3126a-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="3126a-122">Per abilitare l'account del dispositivo, l'ambiente dovrà soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3126a-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="3126a-123">Devi avere Skype for Business online (Piano 2) o versione successiva nel tuo piano Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3126a-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="3126a-124">Il piano deve supportare la funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3126a-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="3126a-125">Se è necessario VoIP aziendale (telefonia PSTN) utilizzando provider di servizi di telefonia per le sale di Microsoft Teams, è necessario Skype for Business online (Piano 3).</span><span class="sxs-lookup"><span data-stu-id="3126a-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="3126a-126">Gli utenti del tenant devono disporre di cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3126a-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="3126a-127">L'account Microsoft Teams Rooms richiede una licenza Di Skype for Business online (Piano 2) o Skype for Business online (Piano 3), ma non richiede una licenza di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3126a-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="3126a-128">Assegnare una licenza Skype for Business Server all'account Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="3126a-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="3126a-129">Creare un account e sincronizzare con Active Directory</span><span class="sxs-lookup"><span data-stu-id="3126a-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="3126a-130">Nello strumento Utenti e computer di **Active Directory** fare clic con il pulsante destro del mouse sulla cartella o sull'unità organizzativa in cui verranno creati gli account delle chat room di Microsoft Teams, fare clic su Nuovo e quindi su **Utente.**</span><span class="sxs-lookup"><span data-stu-id="3126a-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="3126a-131">Digitare il nome visualizzato del cmdlet precedente nella casella **Nome** completo e l'alias nella **casella Nome accesso** utente.</span><span class="sxs-lookup"><span data-stu-id="3126a-131">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="3126a-132">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3126a-132">Click **Next**.</span></span>

3. <span data-ttu-id="3126a-133">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="3126a-133">Type the password for this account.</span></span> <span data-ttu-id="3126a-134">Sarà necessario digitare di nuovo l'elemento per la verifica.</span><span class="sxs-lookup"><span data-stu-id="3126a-134">You'll need to retype it for verification.</span></span> <span data-ttu-id="3126a-135">Verificare che la **casella di controllo Password senza scadenza** sia l'unica opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="3126a-135">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3126a-136">La **selezione di Password senza scadenza** è un requisito per Skype for Business Server nelle sale di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3126a-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="3126a-137">Le regole di dominio possono impedire le password che non scadono.</span><span class="sxs-lookup"><span data-stu-id="3126a-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="3126a-138">In questo caso, sarà necessario creare un'eccezione per ogni account di dispositivo di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="3126a-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="3126a-139">Dopo aver creato l'account, eseguire una sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="3126a-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="3126a-140">Al termine, passare alla pagina degli utenti nell'interfaccia di amministrazione di Microsoft 365 e verificare che l'account creato nei passaggi precedenti sia stato unito in online.</span><span class="sxs-lookup"><span data-stu-id="3126a-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="3126a-141">Abilitare la cassetta postale remota e impostare le proprietà</span><span class="sxs-lookup"><span data-stu-id="3126a-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="3126a-142">[Aprire Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server Exchange tramite una sessione remota di PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="3126a-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="3126a-143">In Exchange PowerShell creare una cassetta postale per l'account (abilitare l'account con cassetta postale) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3126a-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="3126a-144">Per informazioni dettagliate su sintassi e parametri, vedere [Enable-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="3126a-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="3126a-145">In Exchange PowerShell configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza della riunione:</span><span class="sxs-lookup"><span data-stu-id="3126a-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="3126a-146">AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'uomo: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="3126a-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="3126a-147">AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).</span><span class="sxs-lookup"><span data-stu-id="3126a-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="3126a-148">DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="3126a-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="3126a-149">DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="3126a-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="3126a-150">RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione riunione originale rimanga come specificato.)</span><span class="sxs-lookup"><span data-stu-id="3126a-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="3126a-151">AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni riunione).</span><span class="sxs-lookup"><span data-stu-id="3126a-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="3126a-152">AdditionalResponse: "Questa è una sala riunioni Skype!"</span><span class="sxs-lookup"><span data-stu-id="3126a-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="3126a-153">Il testo aggiuntivo da aggiungere alla convocazione riunione.</span><span class="sxs-lookup"><span data-stu-id="3126a-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="3126a-154">Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="3126a-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="3126a-155">Per informazioni dettagliate su sintassi e parametri, [vedere Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="3126a-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="3126a-156">Assegnare una licenza di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="3126a-156">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="3126a-157">Connettersi ad Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3126a-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="3126a-158">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="3126a-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="3126a-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="3126a-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="3126a-160">L'account del dispositivo deve avere una licenza valida di Microsoft 365 o Office 365, oppure Exchange e Microsoft Teams non funzionano.</span><span class="sxs-lookup"><span data-stu-id="3126a-160">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="3126a-161">Se si dispone della licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo. Ciò determina quali SKU di licenza sono disponibili per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="3126a-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="3126a-162">È possibile usare `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="3126a-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="3126a-163">per recuperare un elenco di SKU disponibili.</span><span class="sxs-lookup"><span data-stu-id="3126a-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="3126a-164">Successivamente, puoi aggiungere una licenza usando il pulsante `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="3126a-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="3126a-165">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3126a-165">cmdlet.</span></span> <span data-ttu-id="3126a-166">In questo caso, $strLicense è il codice SKU visualizzato (ad esempio, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="3126a-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="3126a-167">Per istruzioni dettagliate, vedere [Assegnare licenze ad account utente con PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="3126a-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="3126a-168">Abilitare l'account del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3126a-168">Enable the device account</span></span>

<span data-ttu-id="3126a-169">PowerShell di Skype for Business online viene usato per gestire i servizi sia per Microsoft Teams che per Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3126a-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="3126a-170">Per creare una sessione Windows PowerShell remota da un PC, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="3126a-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="3126a-171">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="3126a-171">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="3126a-172">Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="3126a-172">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="3126a-173">Ottenere l'indirizzo SIP dell'account:</span><span class="sxs-lookup"><span data-stu-id="3126a-173">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="3126a-174">Per abilitare l'account di Microsoft Teams Rooms, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="3126a-174">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="3126a-175">Se non si sa quale valore usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente esistente usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="3126a-175">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="3126a-176">Assegnare una licenza all'account di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="3126a-176">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="3126a-177">Accedere come amministratore del tenant, aprire l'interfaccia di amministrazione di Microsoft 365 e fare clic sull'app Admin.</span><span class="sxs-lookup"><span data-stu-id="3126a-177">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="3126a-178">Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, Reimposta password e altro ancora.**</span><span class="sxs-lookup"><span data-stu-id="3126a-178">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="3126a-179">Fare clic sull'account Sale di Microsoft Teams e quindi sull'icona della penna per modificare le informazioni dell'account.</span><span class="sxs-lookup"><span data-stu-id="3126a-179">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="3126a-180">Fare clic **su Licenze.**</span><span class="sxs-lookup"><span data-stu-id="3126a-180">Click **Licenses**.</span></span>
5. <span data-ttu-id="3126a-181">In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e dei requisiti VoIP aziendale licenza.</span><span class="sxs-lookup"><span data-stu-id="3126a-181">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="3126a-182">È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale nelle sale di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3126a-182">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="3126a-183">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3126a-183">Click **Save**.</span></span>

<span data-ttu-id="3126a-184">Per la convalida, dovrebbe essere possibile usare qualsiasi client per accedere a questo account.</span><span class="sxs-lookup"><span data-stu-id="3126a-184">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3126a-185">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3126a-185">Related topics</span></span>

[<span data-ttu-id="3126a-186">Configurare gli account per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3126a-186">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="3126a-187">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="3126a-187">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="3126a-188">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="3126a-188">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="3126a-189">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="3126a-189">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
<span data-ttu-id="3126a-190">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="3126a-190">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>
