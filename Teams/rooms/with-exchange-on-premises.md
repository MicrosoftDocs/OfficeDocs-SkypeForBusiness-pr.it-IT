---
title: Distribuire le sale di Microsoft teams con Exchange locale
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams in un ambiente ibrido con Exchange in locale.
ms.openlocfilehash: d017706a0e512a4945eaccd69c0e11a7962ca518
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666158"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="5e6ea-103">Distribuire le sale di Microsoft teams con Exchange in locale</span><span class="sxs-lookup"><span data-stu-id="5e6ea-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="5e6ea-104">Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams in un ambiente ibrido con Exchange in locale e Microsoft teams o Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="5e6ea-105">Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà dalla posizione in cui è ospitato ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="5e6ea-106">Questo argomento illustra le distribuzioni ibride per le sale di Microsoft teams con Exchange ospitato in locale.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="5e6ea-107">Dato che sono presenti diverse varianti in questo tipo di distribuzione, non è possibile specificare istruzioni dettagliate per tutti.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="5e6ea-108">Il processo seguente funzionerà per molte configurazioni.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-108">The following process will work for many configurations.</span></span> <span data-ttu-id="5e6ea-109">Se il processo non è adatto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale come documentato qui e per altre opzioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="5e6ea-110">Microsoft fornisce [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o di convalidare gli account di risorse esistenti per aiutarli a trasformare gli account utente in Microsoft teams Rooms compatibili.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="5e6ea-111">Se si preferisce, è possibile eseguire la procedura seguente per configurare gli account che verranno usati dal dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="5e6ea-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e6ea-112">Requirements</span></span>

<span data-ttu-id="5e6ea-113">Prima di distribuire le sale di Microsoft teams con Exchange in locale, accertarsi di avere soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="5e6ea-114">Per altre informazioni, Vedi [requisiti di Microsoft teams Rooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="5e6ea-115">Se si distribuiscono le sale di Microsoft teams con Exchange locale, si utilizzeranno gli strumenti di amministrazione di Active Directory per aggiungere un indirizzo di posta elettronica per l'account di dominio locale.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="5e6ea-116">Questo account verrà sincronizzato con Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5e6ea-117">Sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-117">You will need to:</span></span>
  
- <span data-ttu-id="5e6ea-118">Creare un account e sincronizzare l'account con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="5e6ea-119">Abilitare la cassetta postale remota e impostare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="5e6ea-120">Assegnare una licenza di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="5e6ea-121">Abilitare l'account del dispositivo con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="5e6ea-122">Per abilitare l'account del dispositivo, è necessario che l'ambiente soddisfi i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="5e6ea-123">È necessario avere Skype for business online (piano 2) o versione successiva nel piano Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="5e6ea-124">Il piano deve supportare le funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="5e6ea-125">Se si ha bisogno di VoIP aziendale (telefonia PSTN) con i provider di servizi di telefonia per Microsoft teams Rooms è necessario Skype for business online (piano 3).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="5e6ea-126">Gli utenti del tenant devono avere cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="5e6ea-127">L'account di Microsoft teams Rooms richiede una licenza di Skype for business online (piano 2) o Skype for business online (piano 3), ma non richiede una licenza di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="5e6ea-128">Assegnare una licenza di Skype for Business Server all'account di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="5e6ea-129">Creare un account e sincronizzarlo con Active Directory</span><span class="sxs-lookup"><span data-stu-id="5e6ea-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="5e6ea-130">Nello strumento **utenti e computer di Active Directory** fare clic con il pulsante destro del mouse sulla cartella o sull'unità organizzativa in cui verranno creati gli account di Microsoft teams rooms, scegliere **nuovo**e quindi fare clic su **utente**.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="5e6ea-131">Digitare il nome visualizzato del cmdlet precedente nella casella **nome completo** e l'alias nella casella **nome accesso utente** .</span><span class="sxs-lookup"><span data-stu-id="5e6ea-131">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="5e6ea-132">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-132">Click **Next**.</span></span>

3. <span data-ttu-id="5e6ea-133">Digitare la password per l'account.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-133">Type the password for this account.</span></span> <span data-ttu-id="5e6ea-134">È necessario ridigitarlo per la verifica.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-134">You'll need to retype it for verification.</span></span> <span data-ttu-id="5e6ea-135">Verificare che la casella di controllo **scadenza password non** sia l'unica opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-135">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e6ea-136">La selezione di **password non scade mai** è un requisito per Skype for Business Server in Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="5e6ea-137">Le regole di dominio potrebbero impedire le password che non scadono.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="5e6ea-138">In questo caso, dovrai creare un'eccezione per ogni account del dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="5e6ea-139">Dopo aver creato l'account, eseguire una sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="5e6ea-140">Al termine, accedere alla pagina utenti nell'interfaccia di amministrazione di Microsoft 365 e verificare che l'account creato nei passaggi precedenti sia stato unito a online.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="5e6ea-141">Abilitare la cassetta postale remota e impostare le proprietà</span><span class="sxs-lookup"><span data-stu-id="5e6ea-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="5e6ea-142">[Aprire Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [connettersi al server Exchange usando Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="5e6ea-143">In PowerShell di Exchange creare una cassetta postale per l'account (abilitare la cassetta postale per l'account) eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="5e6ea-144">Per informazioni dettagliate su sintassi e parametri, vedere [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="5e6ea-145">In PowerShell di Exchange configurare le impostazioni seguenti nella cassetta postale della sala per migliorare l'esperienza di riunione:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="5e6ea-146">AutomateProcessing: AutoAccept (gli organizzatori della riunione ricevono direttamente la decisione di prenotazione della sala senza intervento umano: gratuito = accetta; occupato = declino).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="5e6ea-147">AddOrganizerToSubject: $false (l'organizzatore della riunione non viene aggiunto all'oggetto della convocazione di riunione).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="5e6ea-148">DeleteComments: $false (Mantieni il testo nel corpo del messaggio delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="5e6ea-149">DeleteSubject: $false (Mantieni l'oggetto delle convocazioni di riunione in arrivo).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="5e6ea-150">RemovePrivateProperty: $false (assicura che il contrassegno privato inviato dall'organizzatore della riunione nella convocazione di riunione originale rimanga come specificato).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="5e6ea-151">AddAdditionalResponse: $true (il testo specificato dal parametro AdditionalResponse viene aggiunto alle convocazioni di riunione).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="5e6ea-152">AdditionalResponse: "si tratta di una sala riunioni Skype!"</span><span class="sxs-lookup"><span data-stu-id="5e6ea-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="5e6ea-153">(Il testo aggiuntivo da aggiungere alla convocazione di riunione)</span><span class="sxs-lookup"><span data-stu-id="5e6ea-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="5e6ea-154">Questo esempio configura queste impostazioni nella cassetta postale della sala denominata Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="5e6ea-155">Per informazioni dettagliate su sintassi e parametri, vedere [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="5e6ea-156">Assegnare una licenza di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="5e6ea-156">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="5e6ea-157">Connettersi ad Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="5e6ea-158">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="5e6ea-159">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="5e6ea-160">L'account del dispositivo deve avere una licenza valida per Microsoft 365 o Office 365 oppure Exchange e Microsoft teams non funzionano.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-160">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="5e6ea-161">Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account del dispositivo, determinando gli SKU di licenza disponibili per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="5e6ea-162">Puoi usare`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="5e6ea-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="5e6ea-163">per recuperare un elenco di SKU disponibili.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="5e6ea-164">È quindi possibile aggiungere una licenza usando la`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="5e6ea-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="5e6ea-165">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-165">cmdlet.</span></span> <span data-ttu-id="5e6ea-166">In questo caso, $strLicense è il codice SKU visualizzato, ad esempio contoso: STANDARDPACK.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="5e6ea-167">Per istruzioni dettagliate, vedere [assegnare licenze agli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="5e6ea-168">Abilitare l'account del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5e6ea-168">Enable the device account</span></span>

<span data-ttu-id="5e6ea-169">Skype for Business Online PowerShell viene usato per gestire i servizi sia per Microsoft teams che per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="5e6ea-170">Creare una sessione remota di Windows PowerShell da un PC come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="5e6ea-171">Ottenere l'indirizzo SIP dell'account:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-171">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="5e6ea-172">Per abilitare l'account di Microsoft teams rooms, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-172">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="5e6ea-173">Se non si è certi del valore da usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente esistente usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="5e6ea-173">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="5e6ea-174">Assegnare una licenza all'account di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="5e6ea-174">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="5e6ea-175">Accedere come amministratore del tenant, aprire l'interfaccia di amministrazione di Microsoft 365 e fare clic sull'app di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-175">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="5e6ea-176">Fare clic su **utenti e gruppi** e quindi su **Aggiungi utenti, Reimposta password e altro ancora**.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-176">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="5e6ea-177">Fare clic sull'account Microsoft teams Rooms e quindi fare clic sull'icona della penna per modificare le informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-177">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="5e6ea-178">Fare clic su **licenze**.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-178">Click **Licenses**.</span></span>
5. <span data-ttu-id="5e6ea-179">In **assegna licenze**selezionare Skype for business (piano 2) o Skype for business (piano 3), a seconda delle licenze e dei requisiti per la segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-179">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="5e6ea-180">È necessario usare una licenza di piano 3 Se si vuole usare VoIP aziendale nelle sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-180">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="5e6ea-181">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-181">Click **Save**.</span></span>

<span data-ttu-id="5e6ea-182">Per la convalida, dovresti essere in grado di usare qualsiasi client per accedere a questo account.</span><span class="sxs-lookup"><span data-stu-id="5e6ea-182">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5e6ea-183">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5e6ea-183">Related topics</span></span>

[<span data-ttu-id="5e6ea-184">Configurare gli account per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e6ea-184">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="5e6ea-185">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="5e6ea-185">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="5e6ea-186">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="5e6ea-186">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="5e6ea-187">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="5e6ea-187">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
<span data-ttu-id="5e6ea-188">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="5e6ea-188">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>
