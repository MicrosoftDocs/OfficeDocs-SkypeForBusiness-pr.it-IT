---
title: Assegnare Teams licenze per i componenti aggiuntivi agli utenti
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Informazioni su come assegnare Teams licenze per i componenti aggiuntivi agli utenti per funzionalità come audioconferenze, Sistema telefonico e piani per chiamate.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116934"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="e528a-103">Assegnare Teams licenze per i componenti aggiuntivi agli utenti</span><span class="sxs-lookup"><span data-stu-id="e528a-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="e528a-104">Le licenze per i componenti aggiuntivi sono licenze per Teams funzionalità di audioconferenza, Sistema telefonico e piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="e528a-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="e528a-105">Questo articolo descrive come assegnare licenze di componenti aggiuntivi a singoli utenti e a set di utenti di grandi dimensioni in blocco.</span><span class="sxs-lookup"><span data-stu-id="e528a-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="e528a-106">Vedere [Teams licenze per i](./microsoft-teams-add-on-licensing.md) componenti aggiuntivi Teams funzionalità disponibili con le licenze per i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e528a-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="e528a-107">Troverai anche informazioni sulle licenze da acquistare e su come acquistarle (a seconda del piano), in modo che gli utenti possano ottenere funzionalità come audioconferenze, numeri a numero verde e la possibilità di chiamare numeri di telefono all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e528a-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="e528a-108">Dopo aver deciso quali funzionalità si vogliono assegnare agli utenti, assegnarle le licenze.</span><span class="sxs-lookup"><span data-stu-id="e528a-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="e528a-109">È possibile usare l'interfaccia Microsoft 365 o PowerShell per assegnare licenze agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e528a-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="e528a-110">Per gestire le licenze, è necessario essere un amministratore globale o un amministratore di gestione utenti.</span><span class="sxs-lookup"><span data-stu-id="e528a-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="e528a-111">Informazioni da sapere prima di assegnare le licenze Sistema telefonico, piano chiamate e crediti comunicazioni</span><span class="sxs-lookup"><span data-stu-id="e528a-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="e528a-112">Prima di iniziare, esaminare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e528a-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="e528a-113">Se si usa la connettività PSTN (Public Switched Telephone Network) locale per gli utenti ibridi, è necessario assegnare una licenza Sistema telefonico locale.</span><span class="sxs-lookup"><span data-stu-id="e528a-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="e528a-114">NON assegnare una licenza per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e528a-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="e528a-115">A causa della latenza tra Microsoft 365 e Microsoft Teams, l'assegnazione di un piano per chiamate a un utente dopo l'assegnazione di una licenza può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="e528a-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="e528a-116">Se all'utente non è assegnato un piano per chiamate dopo 24 ore, contattare il supporto per i prodotti [aziendali - Guida per gli amministratori.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="e528a-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="e528a-117">Se non è stato acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="e528a-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="e528a-118">Se è necessario acquistare altre licenze per il piano per chiamate, scegliere l'opzione per acquistarne altre.</span><span class="sxs-lookup"><span data-stu-id="e528a-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="e528a-119">Anche se agli utenti vengono assegnate Enterprise licenze E5, è comunque necessario assegnare loro le licenze crediti comunicazioni se vogliono effettuare o ricevere chiamate dalla rete PSTN. [](../what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="e528a-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="e528a-120">Dopo aver assegnato licenze per piani per chiamate o crediti comunicazioni agli utenti, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e528a-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="e528a-121">Per istruzioni dettagliate, vedere [Configurare i piani per chiamate.](../set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="e528a-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e528a-122">Uso dell'Microsoft 365 di amministrazione</span><span class="sxs-lookup"><span data-stu-id="e528a-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="e528a-123">Usare l Microsoft 365 di amministrazione per assegnare licenze a singoli utenti o a piccoli set di utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="e528a-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="e528a-124">Le licenze vengono assegnate nella **pagina Licenze** (per un massimo di 20 utenti alla volta) o nella **pagina Utenti** attivi.</span><span class="sxs-lookup"><span data-stu-id="e528a-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="e528a-125">Il metodo scelto varia a seconda che si vogliano gestire licenze di prodotto per utenti specifici o licenze utente per prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="e528a-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="e528a-126">Per istruzioni dettagliate, vedere [Assegnare licenze agli utenti.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="e528a-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="e528a-127">Se è necessario assegnare licenze per un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare Powershell o le licenze basate su gruppo [in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="e528a-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="e528a-128">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e528a-128">Using PowerShell</span></span>

<span data-ttu-id="e528a-129">Usare PowerShell per assegnare licenze agli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="e528a-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="e528a-130">Per altre informazioni, vedere [Assegnare licenze agli account utente con PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e528a-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="e528a-131">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="e528a-131">Example script</span></span>

<span data-ttu-id="e528a-132">Ecco un esempio di come usare uno script per assegnare licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e528a-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="e528a-133">Installare la versione a 64 bit dell'Assistente Microsoft Online Services per i professionisti [IT RTW.](/collaborate/connect-redirect?DownloadID=59185)</span><span class="sxs-lookup"><span data-stu-id="e528a-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="e528a-134">Installare il modulo Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e528a-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="e528a-135">Aprire un prompt dei comandi Windows PowerShell utente con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="e528a-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="e528a-136">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e528a-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="e528a-137">Se viene chiesto di installare il provider di NuGet, digitare **Y** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e528a-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="e528a-138">Se viene chiesto di installare il modulo da PSGallery, digitare **Y** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="e528a-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="e528a-139">Al prompt dei Windows PowerShell eseguire lo script seguente per assegnare licenze agli utenti, dove è il nome dell'organizzazione e l'identificatore della licenza da \<CompanyName:License> assegnare.</span><span class="sxs-lookup"><span data-stu-id="e528a-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="e528a-140">Ad esempio, litwareinc:MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="e528a-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="e528a-141">L'identificatore è diverso dal nome descrittivo della licenza.</span><span class="sxs-lookup"><span data-stu-id="e528a-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="e528a-142">Ad esempio, l'identificatore per le audioconferenze è MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="e528a-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="e528a-143">Per altre informazioni, vedere [Nomi dei prodotti e identificatori SKU per le licenze.](#product-names-and-sku-identifiers-for-licensing)</span><span class="sxs-lookup"><span data-stu-id="e528a-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="e528a-144">Ad esempio, per assegnare Microsoft 365 Enterprise 1 e le licenze di audioconferenza, usare la sintassi seguente nello script:</span><span class="sxs-lookup"><span data-stu-id="e528a-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="e528a-145">Per assegnare una licenza Microsoft Business Voice (senza piano di chiamata), usare la sintassi seguente nello script:</span><span class="sxs-lookup"><span data-stu-id="e528a-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="e528a-146">Nomi di prodotto e identificatori SKU per le licenze</span><span class="sxs-lookup"><span data-stu-id="e528a-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="e528a-147">Ecco un elenco parziale dei nomi di prodotto e dei nomi delle parti SKU corrispondenti che è possibile usare come riferimento quando si usa PowerShell per gestire le licenze in Teams.</span><span class="sxs-lookup"><span data-stu-id="e528a-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="e528a-148">Per altre informazioni, vedere Visualizzare licenze [](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)e servizi [con PowerShell,](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)Nomi dei prodotti e identificatori del piano di servizio per le licenze e Informazioni di riferimento [su SKU education.](../sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="e528a-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="e528a-149">Nome del prodotto</span><span class="sxs-lookup"><span data-stu-id="e528a-149">Product name</span></span>| <span data-ttu-id="e528a-150">Nome parte SKU</span><span class="sxs-lookup"><span data-stu-id="e528a-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="e528a-151">Microsoft Enterprise E5 (con Sistema telefonico)</span><span class="sxs-lookup"><span data-stu-id="e528a-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="e528a-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e528a-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="e528a-153">Microsoft Enterprise E5 (senza audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="e528a-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="e528a-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="e528a-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="e528a-155">Microsoft Enterprise E5 (con audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="e528a-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="e528a-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e528a-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="e528a-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e528a-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="e528a-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e528a-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="e528a-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e528a-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="e528a-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e528a-160">STANDARDPACK</span></span> |
| <span data-ttu-id="e528a-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="e528a-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="e528a-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="e528a-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="e528a-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="e528a-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="e528a-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="e528a-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="e528a-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e528a-165">Microsoft 365 Business</span></span> | <span data-ttu-id="e528a-166">SPB</span><span class="sxs-lookup"><span data-stu-id="e528a-166">SPB</span></span>|
| <span data-ttu-id="e528a-167">Microsoft Business Voice (Canada)</span><span class="sxs-lookup"><span data-stu-id="e528a-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="e528a-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="e528a-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="e528a-169">Microsoft Business Voice (Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="e528a-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="e528a-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="e528a-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="e528a-171">Microsoft Business Voice (Stati Uniti)</span><span class="sxs-lookup"><span data-stu-id="e528a-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="e528a-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="e528a-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="e528a-173">Microsoft Business Voice (senza piano chiamate)</span><span class="sxs-lookup"><span data-stu-id="e528a-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="e528a-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="e528a-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="e528a-175">Microsoft Business Voice (senza piano chiamate) per gli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="e528a-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="e528a-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="e528a-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="e528a-177">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e528a-177">Audio Conferencing</span></span> | <span data-ttu-id="e528a-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="e528a-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="e528a-179">Pagamento per audioconferenza al minuto (pagamento al minuto)</span><span class="sxs-lookup"><span data-stu-id="e528a-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="e528a-180">*Richiede che i Crediti comunicazioni siano impostati e abilitati.*</span><span class="sxs-lookup"><span data-stu-id="e528a-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="e528a-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="e528a-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="e528a-182">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="e528a-182">Phone System</span></span> | <span data-ttu-id="e528a-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="e528a-183">MCOEV</span></span> |
| <span data-ttu-id="e528a-184">Piano per chiamate nazionali e internazionali</span><span class="sxs-lookup"><span data-stu-id="e528a-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="e528a-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="e528a-185">MCOPSTN2</span></span> |
| <span data-ttu-id="e528a-186">Piano per chiamate nazionali (3000 minuti per utente/mese per STATI UNITI/PR/CA, 1200 minuti per utente/mese per i paesi dell'UE)</span><span class="sxs-lookup"><span data-stu-id="e528a-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="e528a-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="e528a-187">MCOPSTN1</span></span> |
| <span data-ttu-id="e528a-188">Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese)</span><span class="sxs-lookup"><span data-stu-id="e528a-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="e528a-189">*Questo piano non è disponibile negli Stati Uniti.*</span><span class="sxs-lookup"><span data-stu-id="e528a-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="e528a-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="e528a-190">MCOPSTN5</span></span> |
| <span data-ttu-id="e528a-191">Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese)</span><span class="sxs-lookup"><span data-stu-id="e528a-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="e528a-192">*Questo piano non è disponibile negli Stati Uniti.*</span><span class="sxs-lookup"><span data-stu-id="e528a-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="e528a-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="e528a-193">MCOPSTN6</span></span> |
| <span data-ttu-id="e528a-194">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="e528a-194">Communications Credits</span></span> | <span data-ttu-id="e528a-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="e528a-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e528a-196">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e528a-196">Related topics</span></span>

- [<span data-ttu-id="e528a-197">Gestione delle licenze per i componenti aggiuntivi di Teams</span><span class="sxs-lookup"><span data-stu-id="e528a-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="e528a-198">Gestire l'accesso degli utenti a Teams</span><span class="sxs-lookup"><span data-stu-id="e528a-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="e528a-199">Visualizzare licenze e servizi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e528a-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="e528a-200">Nomi dei prodotti e identificatori dei piani di servizio per le licenze</span><span class="sxs-lookup"><span data-stu-id="e528a-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="e528a-201">Informazioni di riferimento su SKU education</span><span class="sxs-lookup"><span data-stu-id="e528a-201">Education SKU reference</span></span>](../sku-reference-edu.md)