---
title: Distribuire le sale di Microsoft teams con Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Exchange Online.
ms.openlocfilehash: 2d75e3e744f19d5bce6f323a2f80be8fd836bd61
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243246"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="bcd8d-103">Distribuire le sale di Microsoft teams con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bcd8d-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="bcd8d-104">Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Exchange Online e Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="bcd8d-105">Se l'organizzazione ha una combinazione di servizi, con alcuni ospitati in locale e alcuni ospitati online, la configurazione dipenderà dalla posizione in cui è ospitato ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="bcd8d-106">Questo argomento illustra le distribuzioni ibride per le sale di Microsoft teams con Exchange Hosted online.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="bcd8d-107">Dato che sono presenti diverse varianti in questo tipo di distribuzione, non è possibile specificare istruzioni dettagliate per tutti.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="bcd8d-108">Il processo seguente funzionerà per molte configurazioni.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-108">The following process will work for many configurations.</span></span> <span data-ttu-id="bcd8d-109">Se il processo non è adatto per la configurazione, è consigliabile usare Windows PowerShell per ottenere lo stesso risultato finale come documentato qui e per altre opzioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="bcd8d-110">Il modo più semplice per configurare gli account utente consiste nel configurarli con Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="bcd8d-111">Microsoft fornisce [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), uno script che consente di creare nuovi account utente o di convalidare gli account di risorse esistenti per aiutarli a trasformare gli account utente in Microsoft teams Rooms compatibili.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="bcd8d-112">Se si preferisce, è possibile eseguire la procedura seguente per configurare gli account che verranno usati dal dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="bcd8d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcd8d-113">Requirements</span></span>

<span data-ttu-id="bcd8d-114">Prima di distribuire le sale di Microsoft teams con Exchange Online, assicurati di aver soddisfatto i requisiti.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="bcd8d-115">Per altre informazioni, Vedi [requisiti di Microsoft teams Rooms](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcd8d-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="bcd8d-116">Per distribuire le sale di Microsoft teams con Exchange Online, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="bcd8d-117">Assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="bcd8d-118">I [cmdlet di Azure Active Directory per Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in questa sezione, ad esempio set-MsolUser, sono stati testati in configurazione degli account per i dispositivi Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="bcd8d-119">Tuttavia, è possibile che altri cmdlet possano funzionare, ma non sono stati testati in questo scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="bcd8d-120">Creare un account e impostare le proprietà di Exchange</span><span class="sxs-lookup"><span data-stu-id="bcd8d-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="bcd8d-121">Avviare una sessione remota di Windows PowerShell in un PC e connettersi a Exchange Online nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="bcd8d-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="bcd8d-122">Dopo aver stabilito una sessione, è possibile creare una nuova cassetta postale e abilitarla come RoomMailboxAccount o modificare le impostazioni per una cassetta postale della sala esistente.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="bcd8d-123">In questo modo l'account verrà autenticato nelle sale di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="bcd8d-124">Se si sta modificando una cassetta postale di risorse esistente:</span><span class="sxs-lookup"><span data-stu-id="bcd8d-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="bcd8d-125">Se si sta creando una nuova cassetta postale per le risorse:</span><span class="sxs-lookup"><span data-stu-id="bcd8d-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="bcd8d-126">Per migliorare l'esperienza della riunione, è necessario impostare le proprietà di Exchange nell'account utente nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="bcd8d-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="bcd8d-127">Aggiungere un indirizzo di posta elettronica per l'account di dominio locale</span><span class="sxs-lookup"><span data-stu-id="bcd8d-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="bcd8d-128">Nello strumento **Active Directory utenti e computer** , fare clic con il pulsante destro del mouse sul contenitore o l'unità organizzativa in cui verranno creati gli account di Microsoft teams rooms, scegliere **nuovo**e quindi fare clic su **utente**.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="bcd8d-129">Digitare il nome visualizzato (-Identity) dal cmdlet Prior (Set-Mailbox o New-Mailbox) nella casella **nome completo** e l'alias nella casella **nome accesso utente** .</span><span class="sxs-lookup"><span data-stu-id="bcd8d-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="bcd8d-130">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-130">Click **Next**.</span></span>
3. <span data-ttu-id="bcd8d-131">Digitare la password per l'account.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-131">Type the password for this account.</span></span> <span data-ttu-id="bcd8d-132">È necessario ridigitarlo per la verifica.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-132">You'll need to retype it for verification.</span></span> <span data-ttu-id="bcd8d-133">Verificare che la casella di controllo **scadenza password non** sia l'unica opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-133">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcd8d-134">La selezione di **password non scade mai** è un requisito per Skype for Business Server in Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="bcd8d-135">Le regole di dominio potrebbero impedire le password che non scadono.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="bcd8d-136">In questo caso, è necessario creare un'eccezione per ogni account utente di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="bcd8d-137">Fare clic su **fine** per creare l'account.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="bcd8d-138">Dopo aver creato l'account, eseguire una sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="bcd8d-139">Questa operazione può essere eseguita usando [set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="bcd8d-140">Al termine, accedere alla pagina utenti e verificare che i due account creati nei passaggi precedenti siano Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="bcd8d-141">Assegnare una licenza di Office 365</span><span class="sxs-lookup"><span data-stu-id="bcd8d-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="bcd8d-142">Prima di tutto, Connetti ad Azure AD per applicare alcune impostazioni dell'account.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="bcd8d-143">Puoi eseguire questo cmdlet per la connessione.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="bcd8d-144">Per informazioni dettagliate su Active Directory, vedere [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="bcd8d-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="bcd8d-145">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) non è supportato.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="bcd8d-146">L'account utente deve avere una licenza di Office 365 valida per garantire che Exchange e Skype for Business Server funzionino.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="bcd8d-147">Se si ha la licenza, è necessario assegnare una posizione di utilizzo all'account utente, determinando gli SKU di licenza disponibili per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="bcd8d-148">Eseguire l'assegnazione in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="bcd8d-149">Quindi, USA`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="bcd8d-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="bcd8d-150">per recuperare un elenco di SKU disponibili per il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="bcd8d-151">Quando si elencano gli SKU, è possibile aggiungere una licenza usando l'`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="bcd8d-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="bcd8d-152">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-152">cmdlet.</span></span> <span data-ttu-id="bcd8d-153">In questo caso, $strLicense è il codice SKU visualizzato, ad esempio contoso: STANDARDPACK.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="bcd8d-154">Abilitare l'account utente con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bcd8d-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="bcd8d-155">Creare una sessione remota di Windows PowerShell da un PC come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bcd8d-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="bcd8d-156">Per abilitare l'account di Microsoft teams Rooms per Skype for Business Server, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="bcd8d-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="bcd8d-157">Se non si è certi del valore da usare per il parametro RegistrarPool nell'ambiente, è possibile ottenere il valore da un utente di Skype for Business Server esistente con questo comando</span><span class="sxs-lookup"><span data-stu-id="bcd8d-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="bcd8d-158">Assegnare una licenza di Skype for Business Server all'account di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="bcd8d-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="bcd8d-159">Accedere come amministratore del tenant, aprire il portale di amministrazione di Office 365 e fare clic sull'app di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="bcd8d-160">Fare clic su **utenti e gruppi** e quindi su **Aggiungi utenti, Reimposta password e altro ancora**.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="bcd8d-161">Fare clic sull'account Microsoft teams Rooms e quindi fare clic sull'icona della penna per modificare le informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="bcd8d-162">Fare clic su **licenze**.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="bcd8d-163">In **assegna licenze**selezionare Skype for business (piano 2) o Skype for business (piano 3), a seconda delle licenze e dei requisiti per la segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="bcd8d-164">È necessario usare una licenza di piano 3 Se si vuole usare Enterprise Voice in Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="bcd8d-165">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-165">Click **Save**.</span></span>

<span data-ttu-id="bcd8d-166">Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for business per accedere a questo account.</span><span class="sxs-lookup"><span data-stu-id="bcd8d-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bcd8d-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcd8d-167">See also</span></span>

[<span data-ttu-id="bcd8d-168">Configurare gli account per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcd8d-168">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="bcd8d-169">Pianificare le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcd8d-169">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="bcd8d-170">Distribuire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcd8d-170">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="bcd8d-171">Configurare una console Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="bcd8d-171">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="bcd8d-172">Gestire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcd8d-172">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
