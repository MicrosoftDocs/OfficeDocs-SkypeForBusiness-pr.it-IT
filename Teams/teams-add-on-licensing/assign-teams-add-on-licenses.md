---
title: Assegnare licenze per i componenti aggiuntivi per i team agli utenti
author: LanaChin
ms.author: v-lanac
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
description: Informazioni su come assegnare licenze per i componenti aggiuntivi per i team agli utenti per le caratteristiche come l'audioconferenza, il sistema telefonico e i piani di chiamata.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868583"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="c115e-103">Assegnare licenze per i componenti aggiuntivi per i team agli utenti</span><span class="sxs-lookup"><span data-stu-id="c115e-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="c115e-104">Le licenze per i componenti aggiuntivi sono licenze per specifiche caratteristiche dei team, ad esempio servizi di audioconferenza, sistema telefonico e piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="c115e-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="c115e-105">Questo articolo descrive come assegnare licenze per i componenti aggiuntivi a singoli utenti e a set di utenti di grandi dimensioni in blocco.</span><span class="sxs-lookup"><span data-stu-id="c115e-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="c115e-106">Vedere [licenze per i componenti aggiuntivi teams](microsoft-teams-add-on-licensing.md) per le funzionalità Team disponibili con le licenze per i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c115e-106">See [Teams add-on licensing](microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="c115e-107">Sono disponibili anche informazioni sulle licenze che è necessario acquistare e su come acquistarle (a seconda del piano), in modo che gli utenti possano ottenere funzionalità come i servizi di audioconferenza, i numeri verdi e la possibilità di chiamare i numeri di telefono all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c115e-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="c115e-108">Dopo aver deciso le caratteristiche desiderate per gli utenti, assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="c115e-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="c115e-109">È possibile usare l'interfaccia di amministrazione di Microsoft 365 o PowerShell per assegnare licenze agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c115e-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="c115e-110">Per gestire le licenze, è necessario essere un amministratore globale o un amministratore di gestione utenti.</span><span class="sxs-lookup"><span data-stu-id="c115e-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="c115e-111">Cosa è necessario sapere prima di assegnare le licenze per il sistema telefonico, il piano di chiamata e i crediti di comunicazione</span><span class="sxs-lookup"><span data-stu-id="c115e-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="c115e-112">Prima di iniziare, esaminare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c115e-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="c115e-113">Se si usa la connettività PSTN (Public Switched Telephone Network) locale per gli utenti ibridi, è sufficiente assegnare una licenza per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="c115e-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="c115e-114">Non assegnare una licenza per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c115e-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="c115e-115">Data la latenza tra Microsoft 365 e Microsoft teams, possono essere necessarie fino a 24 ore per consentire a un utente di assegnare un piano di chiamata dopo l'assegnazione di una licenza.</span><span class="sxs-lookup"><span data-stu-id="c115e-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="c115e-116">Se dopo 24 ore non viene assegnato un piano per le chiamate, [contattare il supporto per i prodotti business-Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="c115e-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="c115e-117">Se non è stato acquistato il numero di licenze corretto, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c115e-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="c115e-118">Se è necessario acquistare più licenze per il piano di chiamata, scegliere l'opzione per acquistare altro.</span><span class="sxs-lookup"><span data-stu-id="c115e-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="c115e-119">Anche se agli utenti sono assegnate licenze Enterprise E5, è comunque necessario assegnare loro le licenze per i [crediti di comunicazione](../what-are-communications-credits.md) , se vogliono effettuare o ricevere chiamate dalla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="c115e-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="c115e-120">Dopo aver assegnato le licenze per il piano di chiamata o per i crediti di comunicazione agli utenti, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnare tali numeri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c115e-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="c115e-121">Per istruzioni dettagliate, vedere [configurare i piani](../set-up-calling-plans.md)per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="c115e-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="c115e-122">Uso dell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c115e-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="c115e-123">Usare l'interfaccia di amministrazione di Microsoft 365 per assegnare licenze a singoli utenti o a piccoli gruppi di utenti alla volta.</span><span class="sxs-lookup"><span data-stu-id="c115e-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="c115e-124">È possibile assegnare licenze nella pagina **licenze** (per un massimo di 20 utenti alla volta) o nella pagina **utenti attivi** .</span><span class="sxs-lookup"><span data-stu-id="c115e-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="c115e-125">Il metodo scelto varia a seconda che si vogliano gestire le licenze di prodotto per utenti specifici o gestire le licenze utente per prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="c115e-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="c115e-126">Per istruzioni dettagliate, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="c115e-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="c115e-127">Se è necessario assegnare licenze per un numero elevato di utenti, ad esempio centinaia o migliaia di utenti, usare PowerShell o le [licenze basate su gruppo in Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="c115e-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="c115e-128">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c115e-128">Using PowerShell</span></span>

<span data-ttu-id="c115e-129">Usare PowerShell per assegnare licenze agli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="c115e-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="c115e-130">Per altre informazioni, vedere [assegnare licenze agli account utente con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c115e-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="c115e-131">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="c115e-131">Example script</span></span>

<span data-ttu-id="c115e-132">Ecco un esempio di come usare uno script per assegnare licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c115e-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="c115e-133">Installare la versione a 64 bit dell' [Assistente per l'accesso ai Microsoft Online Services per professionisti IT-RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="c115e-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="c115e-134">Installare il modulo di Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c115e-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="c115e-135">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="c115e-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="c115e-136">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c115e-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="c115e-137">Se viene richiesto di installare il provider NuGet, digitare **Y**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="c115e-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="c115e-138">Se viene richiesto di installare il modulo da PSGallery, digitare **Y**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="c115e-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="c115e-139">Al prompt dei comandi di Windows PowerShell eseguire lo script seguente per assegnare licenze agli utenti, dove \<CompanyName:License> si trova il nome dell'organizzazione e l'identificatore per la licenza che si vuole assegnare.</span><span class="sxs-lookup"><span data-stu-id="c115e-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="c115e-140">Ad esempio, litwareinc: MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="c115e-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="c115e-141">L'identificatore è diverso dal nome descrittivo della licenza.</span><span class="sxs-lookup"><span data-stu-id="c115e-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="c115e-142">Ad esempio, l'identificatore per i servizi di audioconferenza è MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="c115e-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="c115e-143">Per altre informazioni, vedere [nomi di prodotti e identificatori SKU per le licenze](#product-names-and-sku-identifiers-for-licensing).</span><span class="sxs-lookup"><span data-stu-id="c115e-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="c115e-144">Ad esempio, per assegnare licenze Microsoft 365 Enterprise 1 e servizi di audioconferenza, usare la sintassi seguente nello script:</span><span class="sxs-lookup"><span data-stu-id="c115e-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="c115e-145">Per assegnare una licenza di Microsoft Business Voice (senza il piano chiamante), usare la sintassi seguente nello script:</span><span class="sxs-lookup"><span data-stu-id="c115e-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="c115e-146">Nomi di prodotto e identificatori SKU per le licenze</span><span class="sxs-lookup"><span data-stu-id="c115e-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="c115e-147">Ecco un elenco parziale di nomi di prodotto e i relativi nomi di parti SKU che puoi usare come riferimento quando usi PowerShell per gestire le licenze in teams.</span><span class="sxs-lookup"><span data-stu-id="c115e-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="c115e-148">Per altre informazioni, vedere [visualizzare licenze e servizi con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nomi di prodotto e identificatori del piano di servizio per le licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)e [riferimento per SKU per l'istruzione](../sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="c115e-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="c115e-149">Nome del prodotto</span><span class="sxs-lookup"><span data-stu-id="c115e-149">Product name</span></span>| <span data-ttu-id="c115e-150">Nome parte SKU</span><span class="sxs-lookup"><span data-stu-id="c115e-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="c115e-151">Microsoft Enterprise E5 (con sistema telefonico)</span><span class="sxs-lookup"><span data-stu-id="c115e-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="c115e-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c115e-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="c115e-153">Microsoft Enterprise E5 (senza servizi di audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="c115e-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="c115e-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="c115e-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="c115e-155">Microsoft Enterprise E5 (con servizi di audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="c115e-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="c115e-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c115e-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="c115e-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c115e-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="c115e-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c115e-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="c115e-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c115e-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="c115e-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c115e-160">STANDARDPACK</span></span> |
| <span data-ttu-id="c115e-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="c115e-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="c115e-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="c115e-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="c115e-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="c115e-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="c115e-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="c115e-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="c115e-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="c115e-165">Microsoft 365 Business</span></span> | <span data-ttu-id="c115e-166">SPB</span><span class="sxs-lookup"><span data-stu-id="c115e-166">SPB</span></span>|
| <span data-ttu-id="c115e-167">Microsoft Business Voice (Canada)</span><span class="sxs-lookup"><span data-stu-id="c115e-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="c115e-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="c115e-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="c115e-169">Microsoft Business Voice (Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="c115e-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="c115e-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="c115e-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="c115e-171">Microsoft Business Voice (Stati Uniti)</span><span class="sxs-lookup"><span data-stu-id="c115e-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="c115e-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="c115e-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="c115e-173">Microsoft Business Voice (senza piano chiamante)</span><span class="sxs-lookup"><span data-stu-id="c115e-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="c115e-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="c115e-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="c115e-175">Microsoft Business Voice (senza piano chiamante) per gli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="c115e-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="c115e-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="c115e-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="c115e-177">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="c115e-177">Audio Conferencing</span></span> | <span data-ttu-id="c115e-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="c115e-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="c115e-179">Pay-in per i servizi di audioconferenza per minuto (pay-in-go)</span><span class="sxs-lookup"><span data-stu-id="c115e-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="c115e-180">*Richiede che i crediti di comunicazione siano configurati e abilitati.*</span><span class="sxs-lookup"><span data-stu-id="c115e-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="c115e-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="c115e-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="c115e-182">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="c115e-182">Phone System</span></span> | <span data-ttu-id="c115e-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="c115e-183">MCOEV</span></span> |
| <span data-ttu-id="c115e-184">Piano per chiamate nazionali e internazionali</span><span class="sxs-lookup"><span data-stu-id="c115e-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="c115e-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="c115e-185">MCOPSTN2</span></span> |
| <span data-ttu-id="c115e-186">Piano per chiamate nazionali (3000 minuti per utente/mese per US/PR/CA, 1200 minuti per utente/mese per i paesi dell'UE)</span><span class="sxs-lookup"><span data-stu-id="c115e-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="c115e-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="c115e-187">MCOPSTN1</span></span> |
| <span data-ttu-id="c115e-188">Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese)</span><span class="sxs-lookup"><span data-stu-id="c115e-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="c115e-189">*Questo piano non è disponibile negli Stati Uniti.*</span><span class="sxs-lookup"><span data-stu-id="c115e-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="c115e-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="c115e-190">MCOPSTN5</span></span> |
| <span data-ttu-id="c115e-191">Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese)</span><span class="sxs-lookup"><span data-stu-id="c115e-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="c115e-192">*Questo piano non è disponibile negli Stati Uniti.*</span><span class="sxs-lookup"><span data-stu-id="c115e-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="c115e-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="c115e-193">MCOPSTN6</span></span> |
| <span data-ttu-id="c115e-194">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="c115e-194">Communications Credits</span></span> | <span data-ttu-id="c115e-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="c115e-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c115e-196">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c115e-196">Related topics</span></span>

- [<span data-ttu-id="c115e-197">Gestione delle licenze per i componenti aggiuntivi di Teams</span><span class="sxs-lookup"><span data-stu-id="c115e-197">Teams add-on licensing</span></span>](microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="c115e-198">Gestire l'accesso degli utenti a Teams</span><span class="sxs-lookup"><span data-stu-id="c115e-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="c115e-199">Visualizzare licenze e servizi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c115e-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="c115e-200">Nomi dei prodotti e identificatori dei piani di servizio per le licenze</span><span class="sxs-lookup"><span data-stu-id="c115e-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="c115e-201">Riferimento SKU per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="c115e-201">Education SKU reference</span></span>](../sku-reference-edu.md)