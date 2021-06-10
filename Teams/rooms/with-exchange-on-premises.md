---
title: Distribuire Microsoft Teams Rooms con Exchange locale
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
description: Leggere questo argomento per informazioni su come distribuire i Microsoft Teams Rooms in un ambiente ibrido con Exchange locale.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117354"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="fc411-103">Distribuire Microsoft Teams Rooms con Exchange locale</span><span class="sxs-lookup"><span data-stu-id="fc411-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="fc411-104">Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms in un ambiente ibrido con Exchange locale e Microsoft Teams o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="fc411-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="fc411-105">Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="fc411-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="fc411-106">Questo argomento riguarda le distribuzioni ibride Microsoft Teams Rooms con Exchange ospitate in locale.</span><span class="sxs-lookup"><span data-stu-id="fc411-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="fc411-107">Poiché questo tipo di distribuzione offre molte varianti diverse, non è possibile fornire istruzioni dettagliate per tutte.</span><span class="sxs-lookup"><span data-stu-id="fc411-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="fc411-108">Il processo seguente funziona per molte configurazioni.</span><span class="sxs-lookup"><span data-stu-id="fc411-108">The following process will work for many configurations.</span></span> <span data-ttu-id="fc411-109">Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fc411-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="fc411-110">Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in modo da trasformarli in account utente Microsoft Teams Rooms compatibili.</span><span class="sxs-lookup"><span data-stu-id="fc411-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="fc411-111">Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che Microsoft Teams Rooms dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc411-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="fc411-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc411-112">Requirements</span></span>

<span data-ttu-id="fc411-113">Prima di distribuire Microsoft Teams Rooms con Exchange locale, assicurarsi di aver soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="fc411-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="fc411-114">Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="fc411-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="fc411-115">Se si distribuiscono Microsoft Teams Rooms con Exchange locale, si usano gli strumenti di amministrazione di Active Directory per aggiungere un indirizzo di posta elettronica per l'account di dominio locale.</span><span class="sxs-lookup"><span data-stu-id="fc411-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="fc411-116">Questo account verrà sincronizzato con Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc411-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="fc411-117">Sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="fc411-117">You will need to:</span></span>
  
- <span data-ttu-id="fc411-118">Creare un account e sincronizzare l'account con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc411-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="fc411-119">Abilitare la cassetta postale remota e impostare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="fc411-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="fc411-120">Assegnare una Microsoft 365 o Office 365 licenza.</span><span class="sxs-lookup"><span data-stu-id="fc411-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="fc411-121">Abilitare l'account del dispositivo con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc411-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="fc411-122">Per abilitare l'account del dispositivo, l'ambiente dovrà soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc411-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="fc411-123">È necessario avere Skype for Business Online (Piano 2) o versione successiva nel piano Microsoft 365 o Office 365 piano.</span><span class="sxs-lookup"><span data-stu-id="fc411-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="fc411-124">Il piano deve supportare la funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="fc411-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="fc411-125">Se è necessario VoIP aziendale (telefonia PSTN) con provider di servizi di telefonia per Microsoft Teams Rooms è necessario Skype for Business Online (piano 3).</span><span class="sxs-lookup"><span data-stu-id="fc411-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="fc411-126">Quando si configura un account della chat room con Microsoft Teams o Skype for Business Online, il numero di telefono deve essere assegnato prima che l'account venga abilitato come account della chat room.</span><span class="sxs-lookup"><span data-stu-id="fc411-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="fc411-127">Gli utenti del tenant devono avere Exchange cassette postali.</span><span class="sxs-lookup"><span data-stu-id="fc411-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="fc411-128">L'account Microsoft Teams Rooms richiede una licenza di Skype for Business Online (Piano 2) o Skype for Business Online (Piano 3), ma non richiede una licenza Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fc411-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="fc411-129">Assegnare una Skype for Business Server licenza all'account Microsoft Teams Rooms account.</span><span class="sxs-lookup"><span data-stu-id="fc411-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="fc411-130">Creare un account e sincronizzare con Active Directory</span><span class="sxs-lookup"><span data-stu-id="fc411-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="fc411-131">Nello strumento Utenti e computer di **Active Directory** fare clic con il pulsante destro del mouse sulla cartella o sull'unità organizzativa in cui verranno creati gli account Microsoft Teams Rooms, fare clic su Nuovo **e** quindi su **Utente.**</span><span class="sxs-lookup"><span data-stu-id="fc411-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="fc411-132">Digitare il nome visualizzato del cmdlet precedente nella **casella Nome completo** e l'alias nella casella Nome **accesso** utente.</span><span class="sxs-lookup"><span data-stu-id="fc411-132">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="fc411-133">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fc411-133">Click **Next**.</span></span>

3. <span data-ttu-id="fc411-134">Digitare la password per l'account.</span><span class="sxs-lookup"><span data-stu-id="fc411-134">Type the password for this account.</span></span> <span data-ttu-id="fc411-135">Sarà necessario digitare di nuovo per la verifica.</span><span class="sxs-lookup"><span data-stu-id="fc411-135">You'll need to retype it for verification.</span></span> <span data-ttu-id="fc411-136">Verificare che la **casella di controllo Password non scada** mai sia l'unica opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="fc411-136">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc411-137">La **selezione della password non scade** mai è un requisito per Skype for Business Server in Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="fc411-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="fc411-138">Le regole di dominio potrebbero proibire le password che non scadono.</span><span class="sxs-lookup"><span data-stu-id="fc411-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="fc411-139">In questo caso, è necessario creare un'eccezione per ogni account Microsoft Teams Rooms dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc411-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="fc411-140">Dopo aver creato l'account, eseguire una sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="fc411-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="fc411-141">Al termine, passare alla pagina degli utenti nell'interfaccia di amministrazione di Microsoft 365 e verificare che l'account creato nei passaggi precedenti sia stato unito in online.</span><span class="sxs-lookup"><span data-stu-id="fc411-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="fc411-142">Abilitare la cassetta postale remota e impostare le proprietà</span><span class="sxs-lookup"><span data-stu-id="fc411-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="fc411-143">[Aprire la Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server di Exchange tramite Una sessione remota di PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="fc411-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="fc411-144">In Exchange PowerShell creare una cassetta postale per l'account (abilitare l'account tramite cassetta postale) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fc411-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="fc411-145">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="fc411-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="fc411-146">In Exchange PowerShell configurare le impostazioni seguenti nella cassetta postale sala per migliorare l'esperienza della riunione:</span><span class="sxs-lookup"><span data-stu-id="fc411-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="fc411-147">AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono la decisione di prenotazione della sala direttamente senza l'intervento dell'utente: free = accept; busy = decline).</span><span class="sxs-lookup"><span data-stu-id="fc411-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="fc411-148">AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione riunione).</span><span class="sxs-lookup"><span data-stu-id="fc411-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="fc411-149">DeleteComments: $false (Mantenere il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="fc411-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="fc411-150">DeleteSubject: $false (Mantieni l'oggetto delle convocazioni riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="fc411-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="fc411-151">RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).</span><span class="sxs-lookup"><span data-stu-id="fc411-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="fc411-152">AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).</span><span class="sxs-lookup"><span data-stu-id="fc411-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="fc411-153">AdditionalResponse: "Si tratta di una Riunione Skype room!"</span><span class="sxs-lookup"><span data-stu-id="fc411-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="fc411-154">Il testo aggiuntivo da aggiungere alla convocazione riunione.</span><span class="sxs-lookup"><span data-stu-id="fc411-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="fc411-155">Questo esempio configura queste impostazioni nella cassetta postale della chat room denominata Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="fc411-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="fc411-156">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="fc411-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="fc411-157">Assegnare una Microsoft 365 o Office 365 licenza</span><span class="sxs-lookup"><span data-stu-id="fc411-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="fc411-158">Connessione a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc411-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="fc411-159">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="fc411-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="fc411-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="fc411-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="fc411-161">L'account del dispositivo deve avere una licenza Microsoft 365 o Office 365, oppure Exchange e Microsoft Teams non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="fc411-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="fc411-162">Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, in modo da determinare quali SKU di licenza sono disponibili per l'account.</span><span class="sxs-lookup"><span data-stu-id="fc411-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="fc411-163">È possibile usare `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="fc411-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="fc411-164">per recuperare un elenco di SKU disponibili.</span><span class="sxs-lookup"><span data-stu-id="fc411-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="fc411-165">Successivamente, è possibile aggiungere una licenza usando il pulsante `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="fc411-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="fc411-166">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fc411-166">cmdlet.</span></span> <span data-ttu-id="fc411-167">In questo caso, $strLicense codice SKU visualizzato, ad esempio contoso:STANDARDPACK.</span><span class="sxs-lookup"><span data-stu-id="fc411-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="fc411-168">Per istruzioni dettagliate, vedere [Assegnare licenze agli account utente con Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="fc411-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="fc411-169">Abilitare l'account del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fc411-169">Enable the device account</span></span>

<span data-ttu-id="fc411-170">Skype for Business PowerShell online viene usato per gestire i servizi per Microsoft Teams e Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="fc411-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="fc411-171">Creare una sessione Windows PowerShell remota da un PC come segue:</span><span class="sxs-lookup"><span data-stu-id="fc411-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="fc411-172">Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente.</span><span class="sxs-lookup"><span data-stu-id="fc411-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="fc411-173">Se si usa la versione pubblica più [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="fc411-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="fc411-174">Ottenere l'indirizzo SIP dell'account:</span><span class="sxs-lookup"><span data-stu-id="fc411-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="fc411-175">**Facoltativo.**</span><span class="sxs-lookup"><span data-stu-id="fc411-175">**Optional.**</span></span> <span data-ttu-id="fc411-176">Se si vuole assegnare un numero di telefono all'account, l'operazione deve essere eseguita a questo punto.</span><span class="sxs-lookup"><span data-stu-id="fc411-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="fc411-177">Se si vuole assegnare un numero di telefono instradamento diretto:</span><span class="sxs-lookup"><span data-stu-id="fc411-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="fc411-178">Se si sta assegnando un numero di telefono fornito da Microsoft, usare il cmdlet seguente dopo aver eseguito il provisioning dell'utente con una licenza per il piano di chiamata:</span><span class="sxs-lookup"><span data-stu-id="fc411-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="fc411-179">Per abilitare l'account Microsoft Teams Rooms, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="fc411-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="fc411-180">Se non si sa quale valore usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente esistente usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="fc411-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="fc411-181">Assegnare una licenza all'account Microsoft Teams Rooms account</span><span class="sxs-lookup"><span data-stu-id="fc411-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="fc411-182">Accedere come amministratore tenant, aprire l'Microsoft 365 di amministrazione e fare clic sull'app Amministratore.</span><span class="sxs-lookup"><span data-stu-id="fc411-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="fc411-183">Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, reimpostazione password e altro ancora.**</span><span class="sxs-lookup"><span data-stu-id="fc411-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="fc411-184">Fare clic sull Microsoft Teams Rooms account e quindi fare clic sull'icona della penna per modificare le informazioni dell'account.</span><span class="sxs-lookup"><span data-stu-id="fc411-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="fc411-185">Fare clic **su Licenze**.</span><span class="sxs-lookup"><span data-stu-id="fc411-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="fc411-186">In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e VoIP aziendale requisiti.</span><span class="sxs-lookup"><span data-stu-id="fc411-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="fc411-187">È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale nel Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="fc411-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="fc411-188">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fc411-188">Click **Save**.</span></span>

<span data-ttu-id="fc411-189">Per la convalida, dovrebbe essere possibile usare qualsiasi client per accedere a questo account.</span><span class="sxs-lookup"><span data-stu-id="fc411-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fc411-190">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fc411-190">Related topics</span></span>

[<span data-ttu-id="fc411-191">Configurare gli account per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fc411-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="fc411-192">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fc411-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="fc411-193">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fc411-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="fc411-194">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fc411-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
<span data-ttu-id="fc411-195">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="fc411-195">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>