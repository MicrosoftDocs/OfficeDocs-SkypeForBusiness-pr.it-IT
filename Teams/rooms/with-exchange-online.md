---
title: Distribuire sale di Microsoft Teams con Exchange Online
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams con Exchange Online e Skype for Business Server locale.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662311"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="e488f-103">Distribuire sale di Microsoft Teams con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e488f-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="e488f-104">Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams con Exchange Online e Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="e488f-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="e488f-105">Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e altri online, la configurazione dipenderà da dove è ospitato ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="e488f-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="e488f-106">Questo argomento illustra le distribuzioni ibride per le sale di Microsoft Teams con Exchange ospitato online.</span><span class="sxs-lookup"><span data-stu-id="e488f-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="e488f-107">Poiché esistono così tante varianti diverse in questo tipo di distribuzione, non è possibile fornire istruzioni dettagliate per tutte.</span><span class="sxs-lookup"><span data-stu-id="e488f-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="e488f-108">Il processo seguente funziona per molte configurazioni.</span><span class="sxs-lookup"><span data-stu-id="e488f-108">The following process will work for many configurations.</span></span> <span data-ttu-id="e488f-109">Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale illustrato qui e per altre opzioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e488f-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="e488f-110">Il modo più semplice per configurare gli account utente è configurarli usando gli account Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e488f-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="e488f-111">Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in essere per trasformarli in account utente di Microsoft Teams Room compatibili.</span><span class="sxs-lookup"><span data-stu-id="e488f-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="e488f-112">Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che verranno utilizzati dal dispositivo Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e488f-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="e488f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e488f-113">Requirements</span></span>

<span data-ttu-id="e488f-114">Prima di distribuire le sale di Microsoft Teams con Exchange Online, assicurarsi di aver soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="e488f-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="e488f-115">Per altre informazioni, vedere Requisiti [di Sale di Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e488f-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="e488f-116">Per distribuire sale di Microsoft Teams con Exchange Online, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e488f-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="e488f-117">Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati.</span><span class="sxs-lookup"><span data-stu-id="e488f-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="e488f-118">I [cmdlet di Azure Active Directory Module for Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in questa sezione (ad esempio Set-MsolUser) sono stati testati nella configurazione degli account per i dispositivi Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e488f-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="e488f-119">È possibile che altri cmdlet funzionino, tuttavia, non sono stati testati in questo scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="e488f-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="e488f-120">Se è stato distribuito Active Directory Federation Services (ADFS), potrebbe essere necessario convertire l'account utente in un utente gestito prima di eseguire questa procedura e quindi convertirlo di nuovo in un utente federato dopo aver completato questa procedura.</span><span class="sxs-lookup"><span data-stu-id="e488f-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="e488f-121">Creare un account e impostare le proprietà di Exchange</span><span class="sxs-lookup"><span data-stu-id="e488f-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="e488f-122">Avviare una sessione Windows PowerShell remota in un PC e connettersi a Exchange Online come segue:</span><span class="sxs-lookup"><span data-stu-id="e488f-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="e488f-123">Dopo aver stabilito una sessione, è necessario creare una nuova cassetta postale e abilitarla come RoomMailboxAccount oppure modificare le impostazioni di una cassetta postale della sala esistente.</span><span class="sxs-lookup"><span data-stu-id="e488f-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="e488f-124">In questo modo l'account verrà autenticato nelle sale di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e488f-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="e488f-125">Se si sta modificando una cassetta postale delle risorse esistente:</span><span class="sxs-lookup"><span data-stu-id="e488f-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="e488f-126">Se si sta creando una nuova cassetta postale delle risorse:</span><span class="sxs-lookup"><span data-stu-id="e488f-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="e488f-127">Per migliorare l'esperienza della riunione, è necessario impostare le proprietà di Exchange per l'account utente nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e488f-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="e488f-128">Aggiungere un indirizzo di posta elettronica per l'account di dominio locale</span><span class="sxs-lookup"><span data-stu-id="e488f-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="e488f-129">Nello **strumento Active Directory Users and Computers AD** fare clic con il pulsante destro del mouse sul contenitore o sull'unità organizzativa in cui verranno creati gli account di Microsoft Teams Room, fare clic su **Nuovo** e quindi su **Utente.**</span><span class="sxs-lookup"><span data-stu-id="e488f-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="e488f-130">Digitare il nome visualizzato (- Identità) del cmdlet precedente (Set-Mailbox o New-Mailbox) nella casella Nome completo e l'alias nella casella Nome **accesso** utente. </span><span class="sxs-lookup"><span data-stu-id="e488f-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="e488f-131">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e488f-131">Click **Next**.</span></span>
3. <span data-ttu-id="e488f-132">Digitare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="e488f-132">Type the password for this account.</span></span> <span data-ttu-id="e488f-133">Sarà necessario digitare di nuovo l'elemento per la verifica.</span><span class="sxs-lookup"><span data-stu-id="e488f-133">You'll need to retype it for verification.</span></span> <span data-ttu-id="e488f-134">Verificare che la **casella di controllo Password senza scadenza** sia l'unica opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="e488f-134">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e488f-135">La **selezione di Password senza scadenza** è un requisito per Skype for Business Server nelle sale di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e488f-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="e488f-136">Le regole di dominio possono impedire le password che non scadono.</span><span class="sxs-lookup"><span data-stu-id="e488f-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="e488f-137">In questo caso, sarà necessario creare un'eccezione per ogni account utente di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e488f-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="e488f-138">Fare **clic su** Fine per creare l'account.</span><span class="sxs-lookup"><span data-stu-id="e488f-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="e488f-139">Dopo aver creato l'account, eseguire una sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="e488f-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="e488f-140">Questa operazione può essere eseguita con [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e488f-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="e488f-141">Al termine, passare alla pagina degli utenti e verificare che i due account creati nei passaggi precedenti siano stati uniti.</span><span class="sxs-lookup"><span data-stu-id="e488f-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="e488f-142">Assegnare una licenza di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="e488f-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="e488f-143">Prima di tutto, connettersi ad Azure AD per applicare alcune impostazioni dell'account.</span><span class="sxs-lookup"><span data-stu-id="e488f-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="e488f-144">È possibile eseguire questo cmdlet per connettersi.</span><span class="sxs-lookup"><span data-stu-id="e488f-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="e488f-145">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e488f-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e488f-146">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="e488f-146">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="e488f-147">L'account utente deve avere una licenza valida di Microsoft 365 o Office 365 per assicurarsi che Exchange e Skype for Business Server funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="e488f-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="e488f-148">Se si dispone della licenza, è necessario assegnare una posizione di utilizzo al proprio account utente, che determina quali SKU di licenza sono disponibili per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="e488f-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="e488f-149">Per eseguire l'attività, eseguire un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e488f-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="e488f-150">Usa quindi `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="e488f-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="e488f-151">per recuperare un elenco di SKU disponibili per l'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e488f-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="e488f-152">Dopo aver elencato gli SKU, puoi aggiungere una licenza usando il `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="e488f-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="e488f-153">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e488f-153">cmdlet.</span></span> <span data-ttu-id="e488f-154">In questo caso, $strLicense è il codice SKU visualizzato (ad esempio, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="e488f-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="e488f-155">Abilitare l'account utente con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e488f-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="e488f-156">Per creare una sessione Windows PowerShell remota da un PC, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="e488f-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="e488f-157">Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="e488f-157">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="e488f-158">Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="e488f-158">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="e488f-159">Per abilitare l'account Sale di Microsoft Teams per Skype for Business Server, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="e488f-159">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="e488f-160">Se non sei sicuro del valore da usare per il parametro RegistrarPool nel tuo ambiente, puoi ottenere il valore da un utente esistente di Skype for Business Server utilizzando questo comando</span><span class="sxs-lookup"><span data-stu-id="e488f-160">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="e488f-161">Assegnare una licenza Skype for Business Server all'account di Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e488f-161">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="e488f-162">Accedere come amministratore del tenant, aprire l'interfaccia di amministrazione di Microsoft 365 e fare clic sull'app Admin.</span><span class="sxs-lookup"><span data-stu-id="e488f-162">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="e488f-163">Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, Reimposta password e altro ancora.**</span><span class="sxs-lookup"><span data-stu-id="e488f-163">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="e488f-164">Fare clic sull'account Sale di Microsoft Teams e quindi sull'icona della penna per modificare le informazioni dell'account.</span><span class="sxs-lookup"><span data-stu-id="e488f-164">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="e488f-165">Fare clic **su Licenze.**</span><span class="sxs-lookup"><span data-stu-id="e488f-165">Click **Licenses**.</span></span>
5. <span data-ttu-id="e488f-166">In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e dei requisiti VoIP aziendale licenza.</span><span class="sxs-lookup"><span data-stu-id="e488f-166">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="e488f-167">È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale in Microsoft Teams Room.</span><span class="sxs-lookup"><span data-stu-id="e488f-167">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="e488f-168">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e488f-168">Click **Save**.</span></span>

<span data-ttu-id="e488f-169">Per la convalida, dovrebbe essere possibile utilizzare qualsiasi client Skype for Business per accedere a questo account.</span><span class="sxs-lookup"><span data-stu-id="e488f-169">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="e488f-170">Se attualmente si usano SKU E1, E3, E4 o E5 con Skype for Business Piano 2 con Audioconferenza o con Sistema telefonico e un Piano per chiamate, questi continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="e488f-170">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="e488f-171">Tuttavia, è consigliabile passare a un modello di gestione delle licenze più semplice, come descritto nell'aggiornamento delle licenze delle sale riunioni di [Teams,](rooms-licensing.md)dopo la scadenza delle licenze correnti.</span><span class="sxs-lookup"><span data-stu-id="e488f-171">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e488f-172">Se si usa Skype for Business Piano 2, è possibile utilizzare le sale di Microsoft Teams solo in modalità Solo Skype for Business, il che significa che tutte le riunioni saranno riunioni Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e488f-172">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="e488f-173">Per abilitare la sala riunioni per le riunioni di Microsoft Teams, è consigliabile acquistare la licenza per la sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="e488f-173">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e488f-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e488f-174">Related topics</span></span>

[<span data-ttu-id="e488f-175">Configurare gli account per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e488f-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="e488f-176">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e488f-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="e488f-177">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e488f-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="e488f-178">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e488f-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
<span data-ttu-id="e488f-179">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="e488f-179">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>
