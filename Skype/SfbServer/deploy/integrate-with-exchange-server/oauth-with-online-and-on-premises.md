---
title: Integrazione tra Skype for business online ed Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
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
description: La configurazione dell'autenticazione OAuth tra Exchange in locale e Skype for business online consente le funzionalità di integrazione di Skype for business e Exchange descritte nel supporto delle funzionalità.
ms.openlocfilehash: b673332ea4c4428e68d6434c4638cbc78aa0ba7d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797047"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="75959-103">Configurare l'integrazione e il protocollo OAuth tra Skype for business online ed Exchange Server</span><span class="sxs-lookup"><span data-stu-id="75959-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="75959-104">La configurazione dell'integrazione tra Exchange Server e Skype for business online consente le caratteristiche di integrazione di Skype for business e Exchange descritte nel [supporto delle funzionalità](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="75959-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="75959-105">Questo argomento si applica all'integrazione con Exchange Server 2013 a 2019.</span><span class="sxs-lookup"><span data-stu-id="75959-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="75959-106">Cosa occorre sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="75959-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="75959-107">Tempo stimato per completare l'attività: 15 minuti</span><span class="sxs-lookup"><span data-stu-id="75959-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="75959-108">Per eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate.</span><span class="sxs-lookup"><span data-stu-id="75959-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="75959-109">Per vedere quali autorizzazioni sono necessarie, vedere l'argomento [Autorizzazioni infrastruttura Shell e Exchange](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="75959-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="75959-110">Per informazioni sulle scelte rapide da tastiera che possono essere applicate alle procedure descritte in questo argomento, vedere [scelte rapide da tastiera nell'interfaccia di amministrazione di Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="75959-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="75959-111">Per informazioni sulla compatibilità, vedere [compatibilità con Skype for business con le app di Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span><span class="sxs-lookup"><span data-stu-id="75959-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="75959-112">Configurare l'integrazione tra Exchange Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="75959-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="75959-113">Passaggio 1: configurare l'autenticazione OAuth tra Exchange Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="75959-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="75959-114">Eseguire la procedura descritta nell'articolo seguente:</span><span class="sxs-lookup"><span data-stu-id="75959-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="75959-115">Configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online</span><span class="sxs-lookup"><span data-stu-id="75959-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="75959-116">Passaggio 2: creare un nuovo account utente di posta elettronica per l'applicazione partner di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="75959-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="75959-117">Questo passaggio viene eseguito nel server Exchange.</span><span class="sxs-lookup"><span data-stu-id="75959-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="75959-118">Creerà un utente di posta elettronica e gli assegnerà i diritti appropriati per il ruolo di gestione.</span><span class="sxs-lookup"><span data-stu-id="75959-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="75959-119">Questo account verrà quindi usato nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="75959-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="75959-120">Specificare un dominio verificato per l'organizzazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="75959-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="75959-121">Questo dominio deve essere lo stesso dominio usato come dominio SMTP principale usato per gli account di Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="75959-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="75959-122">Questo dominio viene indicato come \<dominio\> verificato nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="75959-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="75959-123">Inoltre, \<DomainControllerFQDN\> deve essere il nome di dominio completo di un domain controller.</span><span class="sxs-lookup"><span data-stu-id="75959-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="75959-124">Questo comando consente di nascondere il nuovo utente di posta elettronica dagli elenchi di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="75959-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="75959-125">Questi due comandi successivi assegnerà il ruolo di gestione di UserApplication e ArchiveApplication al nuovo account.</span><span class="sxs-lookup"><span data-stu-id="75959-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="75959-126">Passaggio 3: creare e abilitare un'applicazione partner per Skype for business online</span><span class="sxs-lookup"><span data-stu-id="75959-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="75959-127">Crea una nuova applicazione partner e userà l'account appena creato.</span><span class="sxs-lookup"><span data-stu-id="75959-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="75959-128">Eseguire il comando seguente in PowerShell di Exchange nell'organizzazione di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="75959-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="75959-129">Passaggio 4: esportare il certificato di autorizzazione locale</span><span class="sxs-lookup"><span data-stu-id="75959-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="75959-130">Eseguire uno script di PowerShell per esportare il certificato di autorizzazione locale, che verrà importato nell'organizzazione di Skype for business online nel prossimo passaggio.</span><span class="sxs-lookup"><span data-stu-id="75959-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="75959-131">Salvare il testo seguente in un file di script di PowerShell denominato, ad esempio, ExportAuthCert. ps1.</span><span class="sxs-lookup"><span data-stu-id="75959-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

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

<span data-ttu-id="75959-132">In PowerShell di Exchange nell'organizzazione di Exchange locale eseguire lo script di PowerShell appena creato.</span><span class="sxs-lookup"><span data-stu-id="75959-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="75959-133">Ad esempio: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="75959-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="75959-134">Passaggio 5: caricare il certificato di autorizzazione locale in Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="75959-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="75959-135">Utilizzare quindi Windows PowerShell per caricare il certificato di autorizzazione locale esportato nel passaggio precedente in Azure Active Directory Access Control Services (ACS).</span><span class="sxs-lookup"><span data-stu-id="75959-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="75959-136">A questo scopo, è necessario che il modulo Azure Active Directory per i cmdlet di Windows PowerShell sia già installato.</span><span class="sxs-lookup"><span data-stu-id="75959-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="75959-137">Se non è installato, accedere [https://aka.ms/aadposh](https://aka.ms/aadposh) a per installare il modulo di Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75959-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="75959-138">Completare la procedura seguente dopo l'installazione del modulo di Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75959-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="75959-139">Fare clic sul collegamento al **modulo di Azure Active Directory per Windows PowerShell** per aprire un'area di lavoro di Windows PowerShell in cui sono installati i cmdlet di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="75959-139">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed.</span></span> <span data-ttu-id="75959-140">Tutti i comandi in questo passaggio verranno eseguiti usando la console di Windows PowerShell per Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75959-140">All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="75959-141">Salvare il testo seguente in un file di script di PowerShell denominato, ad `UploadAuthCert.ps1`esempio.</span><span class="sxs-lookup"><span data-stu-id="75959-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

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

3. <span data-ttu-id="75959-142">Eseguire lo script di PowerShell creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="75959-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="75959-143">Per esempio:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="75959-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="75959-144">Dopo aver avviato lo script, viene visualizzata una finestra di dialogo credenziali.</span><span class="sxs-lookup"><span data-stu-id="75959-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="75959-145">Immettere le credenziali per l'account di amministratore del tenant dell'organizzazione di Microsoft Online Azure AD.</span><span class="sxs-lookup"><span data-stu-id="75959-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="75959-146">Dopo aver eseguito lo script, lascia aperta la sessione di Windows PowerShell per Azure AD.</span><span class="sxs-lookup"><span data-stu-id="75959-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="75959-147">Verrà usato per eseguire uno script di PowerShell nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="75959-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="75959-148">Passaggio 6: verificare che il certificato sia stato caricato nell'entità del servizio Skype for business</span><span class="sxs-lookup"><span data-stu-id="75959-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="75959-149">In PowerShell aperto e autenticato in Azure Active Directory eseguire le operazioni seguenti</span><span class="sxs-lookup"><span data-stu-id="75959-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="75959-150">Premere INVIO quando richiesto per ReturnKeyValues</span><span class="sxs-lookup"><span data-stu-id="75959-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="75959-151">Confermare la visualizzazione di una chiave elencata con i dati di inizio e di fine corrispondenti alle date di inizio e di fine del certificato OAuth di Exchange</span><span class="sxs-lookup"><span data-stu-id="75959-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="75959-152">Verificare il successo</span><span class="sxs-lookup"><span data-stu-id="75959-152">Verify your success</span></span>

<span data-ttu-id="75959-153">Verificare che la configurazione sia corretta verificando che alcune delle caratteristiche funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="75959-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="75959-154">Verificare che gli utenti di Skype for business con il servizio cloud voicemail, in un'organizzazione con configurazione ibrida di Exchange Server, possano modificare correttamente i messaggi di saluto della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="75959-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="75959-155">Verificare che la cronologia delle conversazioni per i client mobili sia visibile nella cartella Cronologia conversazioni di Outlook.</span><span class="sxs-lookup"><span data-stu-id="75959-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="75959-156">Verificare che i messaggi di chat archiviati vengano depositati nella cassetta postale dell'utente locale nella cartella Purges con [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span><span class="sxs-lookup"><span data-stu-id="75959-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="75959-157">In alternativa, esamina il traffico.</span><span class="sxs-lookup"><span data-stu-id="75959-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="75959-158">Il traffico in un handshake OAuth è davvero distintivo (e non ha l'aspetto dell'autenticazione di base), in particolare intorno ai regni, in cui si inizierà a vedere il traffico dell'emittente che ha un aspetto simile al seguente: 00000004-0000-0FF1-CE00-000000000000 @ (a volte con un/prima del simbolo @), nei token passati.</span><span class="sxs-lookup"><span data-stu-id="75959-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="75959-159">Non verrà visualizzato un nome utente o una password, ovvero il punto di OAuth.</span><span class="sxs-lookup"><span data-stu-id="75959-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="75959-160">Ma vedrai l'emittente "Office", in questo caso "4", Skype for business, e l'ambito dell'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="75959-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="75959-161">Per assicurarsi che si stia usando OAuth, accertarsi di sapere cosa aspettarsi e sapere come dovrebbe essere il traffico.</span><span class="sxs-lookup"><span data-stu-id="75959-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="75959-162">Ecco [cosa aspettarsi](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), ecco un esempio abbastanza standard [di traffico OAuth in un'applicazione Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (molto utile da leggere, anche se non usa i token di aggiornamento) e sono disponibili estensioni di Fiddler che consentono di esaminare il token Web OAuth JWT.</span><span class="sxs-lookup"><span data-stu-id="75959-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="75959-163">Ecco un [esempio di impostazione di uno](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), ma è possibile usare qualsiasi strumento di analisi della rete che si vuole intraprendere in questo processo.</span><span class="sxs-lookup"><span data-stu-id="75959-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="75959-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="75959-164">Related topics</span></span>

[<span data-ttu-id="75959-165">Configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online</span><span class="sxs-lookup"><span data-stu-id="75959-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
