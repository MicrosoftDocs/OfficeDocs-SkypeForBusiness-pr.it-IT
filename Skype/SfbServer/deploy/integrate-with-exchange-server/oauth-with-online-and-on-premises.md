---
title: Integrazione tra Skype for Business Online e il server Exchange
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configurazione dell'autenticazione OAuth tra Exchange locale e Skype for Business online abilita le funzionalità di integrazione di Skype for Business ed Exchange descritte in Supporto delle funzionalità.
ms.openlocfilehash: 342362926ad0af169acd6c9af4715008425e71c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109712"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="e4230-103">Configurare l'integrazione e OAuth tra Skype for Business online e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e4230-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="e4230-104">La configurazione dell'integrazione tra il server Exchange e Skype for Business online abilita le funzionalità di integrazione di Skype for Business ed Exchange descritte in [Supporto delle funzionalità.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="e4230-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="e4230-105">Questo argomento si applica all'integrazione con Exchange Server 2013 fino al 2019.</span><span class="sxs-lookup"><span data-stu-id="e4230-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4230-106">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e4230-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4230-107">Tempo stimato per il completamento di questa attività: 15 minuti</span><span class="sxs-lookup"><span data-stu-id="e4230-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="e4230-108">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="e4230-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="e4230-109">Per sapere quali autorizzazioni sono necessarie, vedere [l'argomento Autorizzazioni dell'infrastruttura di Exchange e Shell.](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="e4230-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) topic.</span></span>

- <span data-ttu-id="e4230-110">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere [Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="e4230-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="e4230-111">Per informazioni sulla compatibilità, vedere [Compatibilità di Skype for Business con le app di Office.](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)</span><span class="sxs-lookup"><span data-stu-id="e4230-111">For information about compatibility, see [Skype for Business compatibility with Office apps](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="e4230-112">Configurare l'integrazione tra Exchange Server e O365</span><span class="sxs-lookup"><span data-stu-id="e4230-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="e4230-113">Passaggio 1: Configurare l'autenticazione OAuth tra Exchange Server e O365</span><span class="sxs-lookup"><span data-stu-id="e4230-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="e4230-114">Eseguire la procedura descritta nell'articolo seguente:</span><span class="sxs-lookup"><span data-stu-id="e4230-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="e4230-115">Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4230-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="e4230-116">Passaggio 2: Creare un nuovo account utente di posta per l'applicazione partner skype for business online</span><span class="sxs-lookup"><span data-stu-id="e4230-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="e4230-117">Questo passaggio viene eseguito sul server Exchange.</span><span class="sxs-lookup"><span data-stu-id="e4230-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="e4230-118">Verrà creato un utente di posta elettronica e gli verranno assegnati i diritti di ruolo di gestione appropriati.</span><span class="sxs-lookup"><span data-stu-id="e4230-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="e4230-119">Questo account verrà quindi utilizzato nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e4230-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="e4230-120">Specificare un dominio verificato per l'organizzazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e4230-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="e4230-121">Questo dominio deve essere lo stesso utilizzato come dominio SMTP primario utilizzato per gli account di Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="e4230-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="e4230-122">Questo dominio viene indicato \<your Verified Domain\> nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e4230-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="e4230-123">Deve inoltre \<DomainControllerFQDN\> essere il nome di dominio completo di un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="e4230-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="e4230-124">Questo comando nasconderà il nuovo utente di posta dagli elenchi indirizzi.</span><span class="sxs-lookup"><span data-stu-id="e4230-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="e4230-125">Questi due comandi successivi assegnano il ruolo di gestione UserApplication e ArchiveApplication a questo nuovo account.</span><span class="sxs-lookup"><span data-stu-id="e4230-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="e4230-126">Passaggio 3: Creare e abilitare un'applicazione partner per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e4230-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="e4230-127">Crea una nuova applicazione partner e userà l'account appena creato.</span><span class="sxs-lookup"><span data-stu-id="e4230-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="e4230-128">Eseguire il comando seguente in Exchange PowerShell nella propria organizzazione Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="e4230-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="e4230-129">Passaggio 4: Esportare il certificato di autorizzazione locale</span><span class="sxs-lookup"><span data-stu-id="e4230-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="e4230-130">Eseguire uno script di PowerShell per esportare il certificato di autorizzazione locale, che verrà importato nell'organizzazione Skype for Business online nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="e4230-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="e4230-131">Salvare il testo seguente in un file di script di PowerShell denominato, ad esempio, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="e4230-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="e4230-132">In PowerShell di Exchange nell'organizzazione exchange locale, eseguire lo script di PowerShell appena creato.</span><span class="sxs-lookup"><span data-stu-id="e4230-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="e4230-133">Ad esempio: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="e4230-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="e4230-134">Passaggio 5: Caricare il certificato di autorizzazione locale in ACS di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e4230-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="e4230-135">Successivamente, usare Windows PowerShell per caricare il certificato di autorizzazione locale esportato nel passaggio precedente in Azure Active Directory Access Control Services (ACS).</span><span class="sxs-lookup"><span data-stu-id="e4230-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="e4230-136">A tale scopo, è necessario che il modulo di Azure Active Directory per Windows PowerShell cmdlet sia già installato.</span><span class="sxs-lookup"><span data-stu-id="e4230-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="e4230-137">Se non è installato, passare a [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) per installare il modulo di Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4230-137">If it's not installed, go to [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="e4230-138">Completare i passaggi seguenti dopo l'installazione del modulo di Azure Active Directory Windows PowerShell installazione.</span><span class="sxs-lookup"><span data-stu-id="e4230-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="e4230-139">Fare clic **sul collegamento Azure Active Directory Module for Windows PowerShell** per aprire un'Windows PowerShell di lavoro in cui sono installati i cmdlet di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e4230-139">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed.</span></span> <span data-ttu-id="e4230-140">Tutti i comandi in questo passaggio verranno eseguiti usando la Windows PowerShell console di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e4230-140">All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="e4230-141">Salvare il testo seguente in un file script di PowerShell denominato, ad  `UploadAuthCert.ps1` esempio.</span><span class="sxs-lookup"><span data-stu-id="e4230-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="e4230-142">Eseguire lo script di PowerShell creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="e4230-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="e4230-143">Esempio:  `.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="e4230-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="e4230-144">Dopo avere avviato lo script, viene visualizzata una finestra di dialogo relativa alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="e4230-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="e4230-145">Immettere le credenziali per l'account di amministratore tenant dell'organizzazione di Microsoft Online Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e4230-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="e4230-146">Dopo aver eseguito lo script, lasciare aperta la Windows PowerShell per Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e4230-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="e4230-147">Questa verrà utilizzata per eseguire uno script di PowerShell nel prossimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e4230-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="e4230-148">Passaggio 6: verificare che il certificato sia stato caricato nell'entità servizio di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e4230-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="e4230-149">In PowerShell aperto e autenticato in Azure Active Directory, eseguire il comando seguente</span><span class="sxs-lookup"><span data-stu-id="e4230-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="e4230-150">Premere INVIO quando viene richiesto di specificare ReturnKeyValues</span><span class="sxs-lookup"><span data-stu-id="e4230-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="e4230-151">Verificare che sia presente una chiave elencata con la data di inizio e i dati di fine corrispondenti alle date di inizio e fine del certificato Oauth di Exchange</span><span class="sxs-lookup"><span data-stu-id="e4230-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="e4230-152">Verificare l'esito positivo</span><span class="sxs-lookup"><span data-stu-id="e4230-152">Verify your success</span></span>

<span data-ttu-id="e4230-153">Verificare che la configurazione sia corretta verificando che alcune funzionalità funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="e4230-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="e4230-154">Verificare che gli utenti di Skype for Business con il servizio Cloud Voicemail, in un'organizzazione con una configurazione Exchange Server ibrida, possano modificare correttamente i messaggi di saluto della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="e4230-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="e4230-155">Verificare che la cronologia delle conversazioni per i client mobili sia visibile nella cartella Cronologia conversazioni di Outlook.</span><span class="sxs-lookup"><span data-stu-id="e4230-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="e4230-156">Verificare che i messaggi di chat archiviati siano archiviati nella cassetta postale locale dell'utente nella cartella Ripuliture utilizzando [EWSEditor.](/archive/blogs/webdav_101/where-to-get-ewseditor)</span><span class="sxs-lookup"><span data-stu-id="e4230-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).</span></span>

<span data-ttu-id="e4230-157">In alternativa, esaminare il traffico.</span><span class="sxs-lookup"><span data-stu-id="e4230-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="e4230-158">Il traffico in un handshake OAuth è veramente distintivo (e non è simile all'autenticazione di base), in particolare per le aree di autenticazione, in cui inizierai a vedere il traffico dell'autorità emittente simile al seguente: 000000004-0000-0ff1-ce00-00000000000000@ (a volte con un segno / prima del segno @), nei token che vengono passati.</span><span class="sxs-lookup"><span data-stu-id="e4230-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="e4230-159">Non verrà visualizzato un nome utente o una password, che è il punto di OAuth.</span><span class="sxs-lookup"><span data-stu-id="e4230-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="e4230-160">Tuttavia, verrà visualizzata l'autorità emittente di "Office", in questo caso "4" è Skype for Business, e l'area di autenticazione dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="e4230-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="e4230-161">Se si desidera essere certi di aver utilizzato OAuth correttamente, assicurarsi di sapere cosa aspettarsi e conoscere l'aspetto del traffico.</span><span class="sxs-lookup"><span data-stu-id="e4230-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="e4230-162">Ecco [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)cosa aspettarsi, ecco un esempio piuttosto standard di traffico [OAuth in](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) un'applicazione Microsoft (molto utile da leggere, anche se non usa i token Refresh), e ci sono estensioni Fiddler che ti consentiranno di esaminare il token JWT OAuth (JSON Web Token).</span><span class="sxs-lookup"><span data-stu-id="e4230-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="e4230-163">Ecco un esempio [di configurazione di](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), ma puoi usare qualsiasi strumento di traccia di rete che ti piace per eseguire questo processo.</span><span class="sxs-lookup"><span data-stu-id="e4230-163">Here's an [example of setting one up](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e4230-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e4230-164">Related topics</span></span>

[<span data-ttu-id="e4230-165">Configurazione dell'autenticazione OAuth tra organizzazioni Exchange ed Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4230-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)