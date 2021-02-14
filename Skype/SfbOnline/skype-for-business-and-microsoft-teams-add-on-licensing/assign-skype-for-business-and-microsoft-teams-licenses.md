---
title: Assegnare licenze di Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Impara come assegnare le licenze di Skype for Business per Sistema telefonico, Audioconferenza, Piani di chiamata e Credito per la comunicazione. '
ms.openlocfilehash: e17050c133643d44cd4811ddc5d70852f1ad50d5
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204847"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="89ffc-103">Assegnare licenze di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="89ffc-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="89ffc-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="89ffc-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89ffc-106">Consulta le licenze per i componenti aggiuntivi [Skype for](skype-for-business-and-microsoft-teams-add-on-licensing.md)  Business per informazioni sulle licenze che devi acquistare e su come acquistarle , a seconda del tuo piano Microsoft 365 o Office 365, in modo che gli utenti osercitino i servizi di audioconferenza, i numeri verde e la possibilità di chiamare numeri esterni alla tua azienda.</span><span class="sxs-lookup"><span data-stu-id="89ffc-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="89ffc-107">Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="89ffc-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="89ffc-108">Cosa devi sapere prima di assegnare le licenze per Audioconferenza, Sistema telefonico e Piano per chiamate</span><span class="sxs-lookup"><span data-stu-id="89ffc-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="89ffc-p102">**Usi la connettività PSTN locale per utenti ibridi?** In questo caso, devi assegnare soltanto una licenza **Sistema telefonico**. **NON** dovrai invece assegnare un Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="89ffc-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="89ffc-p103">**Latenza** dopo l'assegnazione delle licenze: a causa della latenza tra Microsoft 365 o Office 365 e Skype for Business online, l'assegnazione di un Piano per chiamate a un utente dopo l'assegnazione di una licenza può richiedere fino a 24 ore. Se dopo 24 ore all'utente non è assegnato un piano per chiamate, contatta il supporto per i prodotti aziendali [- Guida per gli amministratori.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="89ffc-p103">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="89ffc-p104">**Messaggi d'errore**: se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze di Piani per chiamate, scegli **Acquista altro**.</span><span class="sxs-lookup"><span data-stu-id="89ffc-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="89ffc-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="89ffc-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="89ffc-118">Come assegnare una licenza Sistema telefonico e Piano per chiamate a un utente</span><span class="sxs-lookup"><span data-stu-id="89ffc-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="89ffc-p106">I passaggi sono uguali a quello per l'assegnazione di una licenza di Microsoft 365 o Office 365. Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="89ffc-p106">The steps are the same as assigning a Microsoft 365 or Office 365 license. See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="89ffc-121">Come assegnare licenze Sistema telefonico e Piano per chiamate in massa</span><span class="sxs-lookup"><span data-stu-id="89ffc-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="89ffc-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="89ffc-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="89ffc-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="89ffc-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="89ffc-128">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="89ffc-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="89ffc-129">In questo esempio vengono assegnate una licenza di **Enterprise E3** insieme a una licenza per **Sistema telefonico** e per un **Piano per chiamate nazionali**.</span><span class="sxs-lookup"><span data-stu-id="89ffc-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="89ffc-130">Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo (consulta la sezione **Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script**, dopo l'esempio).</span><span class="sxs-lookup"><span data-stu-id="89ffc-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

   #Example of text file:
   #user1@domain.com
   #user2@domain.com

   #Import Module
   ipmo MSOnline
   #Authenticate to MSOLservice.
   Connect-MSOLService
   #File prompt to select the userlist txt file.
   [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
   $OFD = New-Object System.Windows.Forms.OpenFileDialog
   $OFD.filter = "text files (*.*)| *.txt"
   $OFD.ShowDialog() | Out-Null
   $OFD.filename
   If ($OFD.filename -eq '')
   {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
   }
   #Create a variable of all users.
   $users = Get-Content $OFD.filename
   #License each user in the $users variable.
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="89ffc-131">Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="89ffc-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="89ffc-132">**Nome del prodotto**</span><span class="sxs-lookup"><span data-stu-id="89ffc-132">**Product name**</span></span>|<span data-ttu-id="89ffc-133">**Nome parte SKU**</span><span class="sxs-lookup"><span data-stu-id="89ffc-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89ffc-134">Enterprise E5 (con Sistema telefonico)</span><span class="sxs-lookup"><span data-stu-id="89ffc-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="89ffc-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="89ffc-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="89ffc-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="89ffc-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="89ffc-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="89ffc-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="89ffc-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="89ffc-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="89ffc-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="89ffc-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="89ffc-140">Offerta autonoma Plan 2 di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="89ffc-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="89ffc-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="89ffc-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="89ffc-142">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="89ffc-142">Phone System</span></span>  <br/> |<span data-ttu-id="89ffc-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="89ffc-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="89ffc-144">Piano per chiamate internazionali</span><span class="sxs-lookup"><span data-stu-id="89ffc-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="89ffc-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="89ffc-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="89ffc-146">Piano per chiamate nazionali (piani DA 3000 min USA/1200 min UE)</span><span class="sxs-lookup"><span data-stu-id="89ffc-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="89ffc-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="89ffc-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="89ffc-148">Piano per chiamate nazionali (piano da 120 min)</span><span class="sxs-lookup"><span data-stu-id="89ffc-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="89ffc-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="89ffc-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="89ffc-150">Piano per chiamate nazionali (piano da 240 min)</span><span class="sxs-lookup"><span data-stu-id="89ffc-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="89ffc-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="89ffc-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="89ffc-152">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="89ffc-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="89ffc-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="89ffc-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="89ffc-154">Servizi di audioconferenza: suggerimenti e script per l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="89ffc-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="89ffc-155">Ecco cosa devi sapere prima di assegnare le licenze di Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="89ffc-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="89ffc-p109">**Provider di audioconferenze di terze parti**: se per un utente è già stato impostato l'utilizzo di un provider di servizi di audioconferenza di terze parti, quando gli viene assegnata una licenza di **Audioconferenza**, Microsoft diventa il provider di servizi di audioconferenza. Puoi impostare nuovamente il provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="89ffc-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="89ffc-158">Passaggi successivi: dopo avere assegnato le licenze per i servizi **di audioconferenza,** devi assegnare un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="89ffc-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="89ffc-159">Vedi [Assegnare Microsoft come provider di servizi di audioconferenza].</span><span class="sxs-lookup"><span data-stu-id="89ffc-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="89ffc-160">Come assegnare una licenza di Audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="89ffc-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="89ffc-161">I passaggi sono uguali a quello per l'assegnazione di una licenza di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="89ffc-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="89ffc-162">Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="89ffc-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="89ffc-163">Come assegnare licenze di Audioconferenza in blocco</span><span class="sxs-lookup"><span data-stu-id="89ffc-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="89ffc-164">Scarica e installa [Assistente Microsoft Online Services Sign-In per professionisti IT - RTW.](https://go.microsoft.com/fwlink/?LinkId=625123)</span><span class="sxs-lookup"><span data-stu-id="89ffc-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="89ffc-p112">Scarica e installa il **Modulo di Windows Azure Active Directory.** Consulta [Gestire Azure AD tramite Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per ottenere istruzioni per il download e la sintassi del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="89ffc-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="89ffc-167">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="89ffc-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="89ffc-168">Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo.</span><span class="sxs-lookup"><span data-stu-id="89ffc-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="89ffc-169">Vedi [i nomi di prodotto delle audioconferenze](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) o gli SKU usati per gli script per tutti i nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="89ffc-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="89ffc-170">In questo esempio vengono assegnate una licenza di Enterprise E3 e una licenza per i servizi Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="89ffc-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
    #Example of text file:
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
        }
    ```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="89ffc-171">Nomi di prodotto delle audioconferenze o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="89ffc-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="89ffc-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="89ffc-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="89ffc-173">**Nome del prodotto**</span><span class="sxs-lookup"><span data-stu-id="89ffc-173">**Product name**</span></span>|<span data-ttu-id="89ffc-174">**Nome parte SKU**</span><span class="sxs-lookup"><span data-stu-id="89ffc-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89ffc-175">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="89ffc-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="89ffc-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="89ffc-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="89ffc-177">Offerta autonoma Plan 2 di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="89ffc-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="89ffc-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="89ffc-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="89ffc-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="89ffc-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="89ffc-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="89ffc-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="89ffc-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="89ffc-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="89ffc-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="89ffc-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="89ffc-183">Enterprise E5 (senza Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="89ffc-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="89ffc-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="89ffc-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="89ffc-185">Enterprise E5 (con Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="89ffc-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="89ffc-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="89ffc-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="89ffc-187">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="89ffc-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="89ffc-188">Ecco cosa devi sapere prima di assegnare le licenze per i Crediti comunicazioni</span><span class="sxs-lookup"><span data-stu-id="89ffc-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="89ffc-189">**Clienti Enterprise E5:** anche se agli utenti sono assegnate licenze Enterprise E5, ti consigliamo comunque di assegnare loro **licenze di Crediti** comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="89ffc-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="89ffc-190">**Passaggi successivi**: dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="89ffc-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="89ffc-191">Per istruzioni dettagliate, consulta [Configurare i Piani per chiamate.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="89ffc-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="89ffc-192">Come assegnare una licenza di Servizi di conferenza PSTN a un utente</span><span class="sxs-lookup"><span data-stu-id="89ffc-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="89ffc-193">I passaggi sono uguali a quello per l'assegnazione di una licenza di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="89ffc-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="89ffc-194">Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="89ffc-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="89ffc-195">Come assegnare licenze di Crediti comunicazioni in blocco</span><span class="sxs-lookup"><span data-stu-id="89ffc-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="89ffc-196">Guarda lo script di esempio per l'assegnazione delle licenze di **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="89ffc-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="89ffc-197">Aggiornalo con le informazioni per l'assegnazione di licenze di **Crediti comunicazioni**.</span><span class="sxs-lookup"><span data-stu-id="89ffc-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="89ffc-198">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="89ffc-198">Related topics</span></span>
  
[<span data-ttu-id="89ffc-199">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="89ffc-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="89ffc-200">Aggiungere fondi e gestire Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="89ffc-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
