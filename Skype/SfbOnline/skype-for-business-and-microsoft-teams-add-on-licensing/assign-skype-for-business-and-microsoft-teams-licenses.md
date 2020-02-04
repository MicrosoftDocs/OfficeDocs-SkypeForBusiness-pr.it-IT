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
ms.openlocfilehash: 9aa423683160c064b13be140c4226b2327dd9b69
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692521"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="62aaa-103">Assegnare licenze di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="62aaa-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="62aaa-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="62aaa-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62aaa-106">Vedere [licenze per i componenti aggiuntivi Skype for business](skype-for-business-and-microsoft-teams-add-on-licensing.md) per informazioni sulle licenze che è necessario acquistare e su **come acquistarle** , a seconda del piano di Office 365, in modo che gli utenti ottengano servizi di audioconferenza, numeri verdi e la possibilità di chiamare i numeri di telefono all'esterno della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="62aaa-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="62aaa-107">Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="62aaa-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="62aaa-108">Cosa è necessario sapere prima di assegnare le licenze per i servizi di audioconferenza, il sistema telefonico e il piano di chiamata</span><span class="sxs-lookup"><span data-stu-id="62aaa-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="62aaa-p102">**Usi la connettività PSTN locale per utenti ibridi?** In questo caso, devi assegnare soltanto una licenza **Sistema telefonico**. **NON** dovrai invece assegnare un Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="62aaa-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="62aaa-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="62aaa-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="62aaa-p104">**Messaggi d'errore**: se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze di Piani per chiamate, scegli **Acquista altro**.</span><span class="sxs-lookup"><span data-stu-id="62aaa-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="62aaa-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="62aaa-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="62aaa-118">Come assegnare una licenza Sistema telefonico e Piano per chiamate a un utente</span><span class="sxs-lookup"><span data-stu-id="62aaa-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="62aaa-p106">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="62aaa-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="62aaa-121">Come assegnare licenze Sistema telefonico e Piano per chiamate in massa</span><span class="sxs-lookup"><span data-stu-id="62aaa-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="62aaa-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="62aaa-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="62aaa-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="62aaa-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="62aaa-128">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="62aaa-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="62aaa-129">In questo esempio vengono assegnate una licenza di **Enterprise E3** insieme a una licenza per **Sistema telefonico** e per un **Piano per chiamate nazionali**.</span><span class="sxs-lookup"><span data-stu-id="62aaa-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="62aaa-130">Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo (consulta la sezione **Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script**, dopo l'esempio).</span><span class="sxs-lookup"><span data-stu-id="62aaa-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="62aaa-131">Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="62aaa-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="62aaa-132">**Nome del prodotto**</span><span class="sxs-lookup"><span data-stu-id="62aaa-132">**Product name**</span></span>|<span data-ttu-id="62aaa-133">**Nome parte SKU**</span><span class="sxs-lookup"><span data-stu-id="62aaa-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="62aaa-134">Enterprise E5 (con Sistema telefonico)</span><span class="sxs-lookup"><span data-stu-id="62aaa-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="62aaa-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="62aaa-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="62aaa-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="62aaa-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="62aaa-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="62aaa-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="62aaa-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="62aaa-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="62aaa-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="62aaa-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="62aaa-140">Offerta autonoma Plan 2 di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="62aaa-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="62aaa-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="62aaa-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="62aaa-142">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="62aaa-142">Phone System</span></span>  <br/> |<span data-ttu-id="62aaa-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="62aaa-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="62aaa-144">Piano per chiamate internazionali</span><span class="sxs-lookup"><span data-stu-id="62aaa-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="62aaa-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="62aaa-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="62aaa-146">Piano per chiamate nazionali (3000 min US/1200 min EU plans)</span><span class="sxs-lookup"><span data-stu-id="62aaa-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="62aaa-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="62aaa-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="62aaa-148">Piano per chiamate nazionali (piano per le chiamate di 120 min)</span><span class="sxs-lookup"><span data-stu-id="62aaa-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="62aaa-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="62aaa-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="62aaa-150">Piano per chiamate nazionali (piano per le chiamate di 240 min)</span><span class="sxs-lookup"><span data-stu-id="62aaa-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="62aaa-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="62aaa-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="62aaa-152">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="62aaa-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="62aaa-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="62aaa-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="62aaa-154">Servizi di audioconferenza: suggerimenti e script per l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="62aaa-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="62aaa-155">Ecco cosa devi sapere prima di assegnare le licenze di Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="62aaa-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="62aaa-p109">**Provider di audioconferenze di terze parti**: se per un utente è già stato impostato l'utilizzo di un provider di servizi di audioconferenza di terze parti, quando gli viene assegnata una licenza di **Audioconferenza**, Microsoft diventa il provider di servizi di audioconferenza. Puoi impostare nuovamente il provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="62aaa-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="62aaa-158">Passaggi successivi: dopo aver assegnato le licenze di **audioconferenza** , è necessario assegnare un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="62aaa-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="62aaa-159">Vedi [Assegnare Microsoft come provider di servizi di audioconferenza].</span><span class="sxs-lookup"><span data-stu-id="62aaa-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="62aaa-160">Come assegnare una licenza di Audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="62aaa-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="62aaa-p111">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="62aaa-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="62aaa-163">Come assegnare licenze di Audioconferenza in blocco</span><span class="sxs-lookup"><span data-stu-id="62aaa-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="62aaa-164">Scaricare e installare l' [Assistente per l'accesso ai Microsoft Online Services per professionisti IT-RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="62aaa-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="62aaa-p112">Scarica e installa il **Modulo di Windows Azure Active Directory.** Consulta[Gestire Azure AD tramite Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per ottenere istruzioni per il download e la sintassi del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="62aaa-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="62aaa-167">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="62aaa-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="62aaa-168">Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo.</span><span class="sxs-lookup"><span data-stu-id="62aaa-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="62aaa-169">Vedere [nomi di prodotti per la conferenza audio o SKU usati per gli script](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) per tutti i nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="62aaa-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="62aaa-170">In questo esempio vengono assegnate una licenza di Enterprise E3 e una licenza per i servizi Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="62aaa-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="62aaa-171">Nomi di prodotto delle audioconferenze o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="62aaa-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="62aaa-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="62aaa-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="62aaa-173">**Nome del prodotto**</span><span class="sxs-lookup"><span data-stu-id="62aaa-173">**Product name**</span></span>|<span data-ttu-id="62aaa-174">**Nome parte SKU**</span><span class="sxs-lookup"><span data-stu-id="62aaa-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="62aaa-175">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="62aaa-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="62aaa-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="62aaa-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="62aaa-177">Offerta autonoma Plan 2 di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="62aaa-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="62aaa-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="62aaa-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="62aaa-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="62aaa-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="62aaa-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="62aaa-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="62aaa-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="62aaa-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="62aaa-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="62aaa-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="62aaa-183">Enterprise E5 (senza Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="62aaa-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="62aaa-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="62aaa-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="62aaa-185">Enterprise E5 (con Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="62aaa-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="62aaa-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="62aaa-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="62aaa-187">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="62aaa-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="62aaa-188">Ecco cosa devi sapere prima di assegnare le licenze per i Crediti comunicazioni</span><span class="sxs-lookup"><span data-stu-id="62aaa-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="62aaa-189">**Clienti Enterprise E5**: anche se agli utenti sono assegnate licenze Enterprise E5, è comunque consigliabile assegnare loro licenze per i **crediti per comunicazioni** .</span><span class="sxs-lookup"><span data-stu-id="62aaa-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="62aaa-190">**Passaggi successivi**: dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="62aaa-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="62aaa-191">Per istruzioni dettagliate, vedere [configurare i piani](/microsoftteams/set-up-calling-plans)per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="62aaa-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="62aaa-192">Come assegnare una licenza di Servizi di conferenza PSTN a un utente</span><span class="sxs-lookup"><span data-stu-id="62aaa-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="62aaa-193">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="62aaa-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="62aaa-194">Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="62aaa-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="62aaa-195">Come assegnare licenze per i crediti di comunicazione in blocco</span><span class="sxs-lookup"><span data-stu-id="62aaa-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="62aaa-196">Guarda lo script di esempio per l'assegnazione delle licenze di **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="62aaa-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="62aaa-197">Aggiornalo con le informazioni per l'assegnazione di licenze di **Crediti comunicazioni**.</span><span class="sxs-lookup"><span data-stu-id="62aaa-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="62aaa-198">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="62aaa-198">Related topics</span></span>
  
[<span data-ttu-id="62aaa-199">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="62aaa-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="62aaa-200">Aggiungere fondi e gestire Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="62aaa-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
