---
title: Distribuire Microsoft Teams Rooms con Exchange Online
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
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online e Skype for Business Server locali.
ms.openlocfilehash: 2f92f85ddf39c5e1a813492b3092eeeef9b77e4c
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796680"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="fbdbd-103">Distribuire Microsoft Teams Rooms con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fbdbd-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="fbdbd-104">Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Exchange Online e Skype for Business Server locali.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="fbdbd-105">Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà da dove è ospitato ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="fbdbd-106">Questo argomento riguarda le distribuzioni ibride per Microsoft Teams Rooms con Exchange ospitate online.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="fbdbd-107">Poiché questo tipo di distribuzione offre molte varianti diverse, non è possibile fornire istruzioni dettagliate per tutte.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="fbdbd-108">Il processo seguente funziona per molte configurazioni.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-108">The following process will work for many configurations.</span></span> <span data-ttu-id="fbdbd-109">Se il processo non è giusto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale documentato qui e per altre opzioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="fbdbd-110">Il modo più semplice per configurare gli account utente è configurarli usando gli account Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="fbdbd-111">Microsoft fornisce [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o convalidare gli account delle risorse esistenti in modo da trasformarli in account utente Microsoft Teams Rooms compatibili.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="fbdbd-112">Se si preferisce, è possibile seguire la procedura seguente per configurare gli account che Microsoft Teams Rooms dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="fbdbd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbdbd-113">Requirements</span></span>

<span data-ttu-id="fbdbd-114">Prima di distribuire Microsoft Teams Rooms con Exchange Online, assicurarsi di aver soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="fbdbd-115">Per altre informazioni, vedere requisiti [Microsoft Teams Rooms.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="fbdbd-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="fbdbd-116">Per distribuire Microsoft Teams Rooms con Exchange Online, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="fbdbd-117">Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="fbdbd-118">Il [modulo Azure Active Directory](/powershell/azure/active-directory/overview?view=azureadps-1.0) per i cmdlet Windows PowerShell in questa sezione, ad esempio Set-MsolUser, è stato testato nella configurazione degli account per Microsoft Teams Rooms dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="fbdbd-119">È possibile che altri cmdlet funzionino, ma non sono stati testati in questo scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="fbdbd-120">Se è stato distribuito Active Directory Federation Services (AD FS), potrebbe essere necessario convertire l'account utente in un utente gestito prima di eseguire questa procedura e quindi convertire di nuovo l'utente in un utente federato dopo aver completato questa procedura.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="fbdbd-121">Creare un account e impostare Exchange proprietà</span><span class="sxs-lookup"><span data-stu-id="fbdbd-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="fbdbd-122">Avviare una sessione Windows PowerShell remota in un PC e connettersi a Exchange Online come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fbdbd-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="fbdbd-123">Dopo aver stabilito una sessione, si creerà una nuova cassetta postale e la si abiliterà come RoomMailboxAccount oppure si modificheranno le impostazioni per una cassetta postale della chat room esistente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="fbdbd-124">In questo modo l'account verrà autenticato Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="fbdbd-125">Se si sta modificando una cassetta postale delle risorse esistente:</span><span class="sxs-lookup"><span data-stu-id="fbdbd-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="fbdbd-126">Se si sta creando una nuova cassetta postale per le risorse:</span><span class="sxs-lookup"><span data-stu-id="fbdbd-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="fbdbd-127">Per migliorare l'esperienza della riunione, è necessario impostare le proprietà Exchange sull'account utente nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="fbdbd-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="fbdbd-128">Aggiungere un indirizzo di posta elettronica per l'account di dominio locale</span><span class="sxs-lookup"><span data-stu-id="fbdbd-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="fbdbd-129">Nello **strumento Active Directory Users and Computers fare** clic con il pulsante destro del mouse sul contenitore o sull'unità organizzativa in cui verranno creati gli account Microsoft Teams Rooms, fare clic su **Nuovo** e quindi su **Utente.**</span><span class="sxs-lookup"><span data-stu-id="fbdbd-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="fbdbd-130">Digitare il nome visualizzato (- Identity) del cmdlet precedente (Set-Mailbox o New-Mailbox) nella casella **Nome** completo e l'alias nella casella **Nome accesso** utente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="fbdbd-131">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-131">Click **Next**.</span></span>
3. <span data-ttu-id="fbdbd-132">Digitare la password per l'account.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-132">Type the password for this account.</span></span> <span data-ttu-id="fbdbd-133">Sarà necessario digitare di nuovo per la verifica.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-133">You'll need to retype it for verification.</span></span> <span data-ttu-id="fbdbd-134">Verificare che la **casella di controllo Password non scada** mai sia l'unica opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-134">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fbdbd-135">La **selezione della password non scade** mai è un requisito per Skype for Business Server in Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="fbdbd-136">Le regole di dominio potrebbero proibire le password che non scadono.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="fbdbd-137">In questo caso, è necessario creare un'eccezione per ogni account Microsoft Teams Rooms utente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="fbdbd-138">Fare **clic su** Fine per creare l'account.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="fbdbd-139">Dopo aver creato l'account, eseguire una sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="fbdbd-140">Questa operazione può essere eseguita usando [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="fbdbd-141">Al termine, passare alla pagina degli utenti e verificare che i due account creati nei passaggi precedenti siano stati uniti.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="fbdbd-142">Assegnare una Microsoft 365 o Office 365 licenza</span><span class="sxs-lookup"><span data-stu-id="fbdbd-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="fbdbd-143">Prima di tutto, connettersi ad Azure AD per applicare alcune impostazioni dell'account.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="fbdbd-144">È possibile eseguire questo cmdlet per connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="fbdbd-145">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="fbdbd-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="fbdbd-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="fbdbd-147">L'account utente deve avere una licenza Microsoft 365 o Office 365 per assicurarsi che Exchange e Skype for Business Server funzionino.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="fbdbd-148">Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account utente, in modo da determinare quali SKU di licenza sono disponibili per l'account.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="fbdbd-149">L'attività verrà apportata nel passaggio seguente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="fbdbd-150">Usare quindi `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="fbdbd-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="fbdbd-151">per recuperare un elenco di SKU disponibili per l'Microsoft 365 o Office 365 organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="fbdbd-152">Dopo aver elencato gli SKU, è possibile aggiungere una licenza usando il comando `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="fbdbd-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="fbdbd-153">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-153">cmdlet.</span></span> <span data-ttu-id="fbdbd-154">In questo caso, $strLicense codice SKU visualizzato, ad esempio contoso:STANDARDPACK.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="fbdbd-155">Abilitare l'account utente con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbdbd-155">Enable the user account with Skype for Business Server</span></span>

> [!NOTE]
> <span data-ttu-id="fbdbd-156">Se si sta configurando un Teams Rooms solo per partecipare a Microsoft Teams riunioni, non è necessario eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-156">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="fbdbd-157">I passaggi seguenti sono necessari solo se si vuole abilitare il supporto per Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-157">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="fbdbd-158">Creare una sessione Windows PowerShell remota da un PC come segue:</span><span class="sxs-lookup"><span data-stu-id="fbdbd-158">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="fbdbd-159">Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-159">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="fbdbd-160">Se si usa la versione pubblica più [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-160">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="fbdbd-161">Per abilitare l'account Microsoft Teams Rooms per Skype for Business Server, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="fbdbd-161">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="fbdbd-162">Se non si è certi del valore da usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente Skype for Business Server esistente usando questo comando</span><span class="sxs-lookup"><span data-stu-id="fbdbd-162">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="fbdbd-163">Assegnare una Skype for Business Server al proprio account Microsoft Teams Rooms account</span><span class="sxs-lookup"><span data-stu-id="fbdbd-163">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

> [!NOTE]
> <span data-ttu-id="fbdbd-164">Se si sta configurando un Teams Rooms solo per partecipare a Microsoft Teams riunioni, non è necessario eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-164">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="fbdbd-165">I passaggi seguenti sono necessari solo se si vuole abilitare il supporto per Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-165">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="fbdbd-166">Accedere come amministratore tenant, aprire l'Microsoft 365 di amministrazione e fare clic sull'app Amministratore.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-166">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="fbdbd-167">Fare clic **su Utenti e gruppi** e quindi su Aggiungi **utenti, reimpostazione password e altro ancora.**</span><span class="sxs-lookup"><span data-stu-id="fbdbd-167">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="fbdbd-168">Fare clic sull Microsoft Teams Rooms account e quindi fare clic sull'icona della penna per modificare le informazioni dell'account.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-168">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="fbdbd-169">Fare clic **su Licenze**.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-169">Click **Licenses**.</span></span>
5. <span data-ttu-id="fbdbd-170">In **Assegna licenze** selezionare Skype for Business (Piano 2) o Skype for Business (Piano 3), a seconda delle licenze e VoIP aziendale requisiti.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-170">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="fbdbd-171">È necessario usare una licenza di Piano 3 se si vuole usare VoIP aziendale in Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-171">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="fbdbd-172">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-172">Click **Save**.</span></span>

<span data-ttu-id="fbdbd-173">Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for Business per accedere a questo account.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-173">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="fbdbd-174">Se attualmente si usano SKU E1, E3, E4 o E5 con Skype for Business Piano 2 con audioconferenza o con Sistema telefonico e un piano per chiamate, questi continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-174">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="fbdbd-175">Tuttavia, è consigliabile passare a un modello di licenza più semplice, come descritto [in](rooms-licensing.md)Aggiornamento delle licenze Teams Sala riunioni, dopo la scadenza delle licenze correnti.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-175">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbdbd-176">Se si usa Skype for Business Piano 2, è possibile usare il Microsoft Teams Rooms solo in modalità solo Skype for Business, quindi tutte le riunioni verranno Skype for Business riunioni.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-176">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="fbdbd-177">Per abilitare la sala riunioni per le riunioni Microsoft Teams, è consigliabile acquistare la licenza Sala riunioni riunione.</span><span class="sxs-lookup"><span data-stu-id="fbdbd-177">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fbdbd-178">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fbdbd-178">Related topics</span></span>

[<span data-ttu-id="fbdbd-179">Configurare gli account per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fbdbd-179">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="fbdbd-180">Piano per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fbdbd-180">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="fbdbd-181">Distribuire Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fbdbd-181">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="fbdbd-182">Configurare una console per Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="fbdbd-182">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
<span data-ttu-id="fbdbd-183">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="fbdbd-183">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>
