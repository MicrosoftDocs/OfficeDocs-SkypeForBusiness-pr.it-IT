---
title: Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: 'Informazioni su come assegnare Skype per le licenze Business per sistema telefonico, conferenze Audio, la chiamata a piani e avere comunicazioni. '
ms.openlocfilehash: d60d637d3b904b98ee8600647c57062927fe9afc
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="8718e-103">Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8718e-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="8718e-104">In questo articolo vengono forniti suggerimenti sull'assegnazione delle licenze agli utenti di funzionalità come audioconferenze, sistema telefonico e la chiamata dei piani.</span><span class="sxs-lookup"><span data-stu-id="8718e-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="8718e-105">Inoltre, sono disponibili gli script per l'assegnazione delle licenze in blocco.</span><span class="sxs-lookup"><span data-stu-id="8718e-105">It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="8718e-106">**Importante**: vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) per sapere quali concede in licenza è necessario acquistare e su **come acquistare** li - a seconda del piano di Office 365 - in modo che gli utenti ottengono audioconferenze, numeri verdi, e la possibilità di chiamare i numeri di telefono all'esterno dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="8718e-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="8718e-107">Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="8718e-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="8718e-108">Che cosa è necessario sapere prima di assegnare i servizi di conferenza Audio, sistema telefonico e la chiamata a pianificare licenze</span><span class="sxs-lookup"><span data-stu-id="8718e-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="8718e-p102">**Usi la connettività PSTN locale per utenti ibridi?** In questo caso, devi assegnare soltanto una licenza **Sistema telefonico**. **NON** dovrai invece assegnare un Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="8718e-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="8718e-112">**Latenza dopo l'assegnazione delle licenze**: a causa della latenza tra Office 365 e Skype Business online, talvolta può richiedere fino a 24 ore per un utente da assegnare a Plan la chiamata dopo che si assegna una licenza.</span><span class="sxs-lookup"><span data-stu-id="8718e-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="8718e-113">Se dopo 24 ore all'utente non è assegnato a una chiamata a pianificare, [contattare il supporto per i prodotti di business - della Guida di amministrazione](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="8718e-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="8718e-p104">**Messaggi d'errore**: se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze di Piani per chiamate, scegli **Acquista altro**.</span><span class="sxs-lookup"><span data-stu-id="8718e-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="8718e-116">**Passaggi successivi**: dopo aver assegnato la chiamata a pianificare le licenze agli utenti, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegna tali numeri per le persone all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8718e-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="8718e-117">Per istruzioni dettagliate, vedere [impostare le tariffe di chiamate](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="8718e-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="8718e-118">Come assegnare una licenza Sistema telefonico e Piano per chiamate a un utente</span><span class="sxs-lookup"><span data-stu-id="8718e-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="8718e-p106">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="8718e-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="8718e-121">Come assegnare licenze Sistema telefonico e Piano per chiamate in massa</span><span class="sxs-lookup"><span data-stu-id="8718e-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="8718e-122">Installare **Microsoft Online Services Assistente per l'accesso per i professionisti IT RTW**.</span><span class="sxs-lookup"><span data-stu-id="8718e-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="8718e-123">Non è installato il modulo?</span><span class="sxs-lookup"><span data-stu-id="8718e-123">Don't have the module installed?</span></span> <span data-ttu-id="8718e-124">Vedere [Assistente Microsoft Online Services accesso per RTW i professionisti IT](https://go.microsoft.com/fwlink/?LinkId=625123) per scaricarlo.</span><span class="sxs-lookup"><span data-stu-id="8718e-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="8718e-125">Installare il **modulo Windows Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="8718e-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="8718e-126">Non è installato il modulo?</span><span class="sxs-lookup"><span data-stu-id="8718e-126">Don't have the module installed?</span></span> <span data-ttu-id="8718e-127">Per istruzioni sul download e la sintassi cmdlet, vedere [Gestione Azure AD tramite Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="8718e-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="8718e-128">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="8718e-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="8718e-129">In questo esempio vengono assegnate una licenza di **Enterprise E3** insieme a una licenza per **Sistema telefonico** e per un **Piano per chiamate nazionali**.</span><span class="sxs-lookup"><span data-stu-id="8718e-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="8718e-130">Il nome delle licenze o i nomi dei prodotti nello script sono elencati in corsivo (consulta la sezione **Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script**, dopo l'esempio).</span><span class="sxs-lookup"><span data-stu-id="8718e-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="8718e-131">Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="8718e-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="8718e-132">**Nome del prodotto**</span><span class="sxs-lookup"><span data-stu-id="8718e-132">**Product name**</span></span>|<span data-ttu-id="8718e-133">**Nome parte SKU**</span><span class="sxs-lookup"><span data-stu-id="8718e-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8718e-134">Enterprise E5 (con Sistema telefonico)</span><span class="sxs-lookup"><span data-stu-id="8718e-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="8718e-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="8718e-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="8718e-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="8718e-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="8718e-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="8718e-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="8718e-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="8718e-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="8718e-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="8718e-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="8718e-140">Offerta autonoma Plan 2 di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="8718e-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="8718e-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="8718e-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="8718e-142">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="8718e-142">Phone System</span></span>  <br/> |<span data-ttu-id="8718e-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="8718e-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="8718e-144">Piano per chiamate internazionali</span><span class="sxs-lookup"><span data-stu-id="8718e-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="8718e-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="8718e-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="8718e-146">Piano per chiamate nazionali</span><span class="sxs-lookup"><span data-stu-id="8718e-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="8718e-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="8718e-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="8718e-148">Crediti comunicazioni</span><span class="sxs-lookup"><span data-stu-id="8718e-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="8718e-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="8718e-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="8718e-150">Servizi di audioconferenza: suggerimenti e script per l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="8718e-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="8718e-151">Ecco cosa devi sapere prima di assegnare le licenze di Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="8718e-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="8718e-p109">**Provider di audioconferenze di terze parti**: se per un utente è già stato impostato l'utilizzo di un provider di servizi di audioconferenza di terze parti, quando gli viene assegnata una licenza di **Audioconferenza**, Microsoft diventa il provider di servizi di audioconferenza. Puoi impostare nuovamente il provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="8718e-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="8718e-154">Passaggi successivi: dopo l'assegnazione delle licenze di **Audioconferenza** , è necessario assegnare un provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="8718e-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="8718e-155">Effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8718e-155">Do one of the following:</span></span>
    
  - [<span data-ttu-id="8718e-156">Assegnare Microsoft come provider di servizi di conferenza audio</span><span class="sxs-lookup"><span data-stu-id="8718e-156">Assign Microsoft as the audio conferencing provider</span></span>](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - <span data-ttu-id="8718e-157">In alternativa, [Assegnare una terza parte come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="8718e-157">Or, [Assign a third-party as the audio conferencing provider](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="8718e-158">Come assegnare una licenza di Audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="8718e-158">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="8718e-p111">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="8718e-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="8718e-161">Come assegnare licenze di Audioconferenza in blocco</span><span class="sxs-lookup"><span data-stu-id="8718e-161">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="8718e-162">Scaricare e installare [Microsoft Online Services Assistente per l'accesso per RTW i professionisti IT](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="8718e-162">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="8718e-p112">Scarica e installa il **Modulo di Windows Azure Active Directory.** Consulta[Gestire Azure AD tramite Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per ottenere istruzioni per il download e la sintassi del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8718e-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="8718e-165">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="8718e-165">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="8718e-166">Il nome delle licenze o i nomi dei prodotti nello script sono elencati in testo in corsivo.</span><span class="sxs-lookup"><span data-stu-id="8718e-166">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="8718e-167">Vedere [i nomi dei prodotti di conferenze Audio o SKU utilizzati per la creazione di script](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) per tutti i nomi dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="8718e-167">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="8718e-168">In questo esempio vengono assegnate una licenza di Enterprise E3 e una licenza per i servizi Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="8718e-168">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="8718e-169">Nomi di prodotto delle audioconferenze o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="8718e-169">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="8718e-170"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="8718e-170"></span></span>

|<span data-ttu-id="8718e-171">**Nome del prodotto**</span><span class="sxs-lookup"><span data-stu-id="8718e-171">**Product name**</span></span>|<span data-ttu-id="8718e-172">**Nome parte SKU**</span><span class="sxs-lookup"><span data-stu-id="8718e-172">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8718e-173">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="8718e-173">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="8718e-174">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="8718e-174">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="8718e-175">Offerta autonoma Plan 2 di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="8718e-175">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="8718e-176">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="8718e-176">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="8718e-177">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="8718e-177">Enterprise E1</span></span>  <br/> |<span data-ttu-id="8718e-178">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="8718e-178">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="8718e-179">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="8718e-179">Enterprise E3</span></span>  <br/> |<span data-ttu-id="8718e-180">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="8718e-180">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="8718e-181">Enterprise E5 (senza Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="8718e-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="8718e-182">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="8718e-182">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="8718e-183">Enterprise E5 (con Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="8718e-183">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="8718e-184">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="8718e-184">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="8718e-185">Crediti comunicazioni</span><span class="sxs-lookup"><span data-stu-id="8718e-185">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="8718e-186">Ecco cosa devi sapere prima di assegnare le licenze per i Crediti comunicazioni</span><span class="sxs-lookup"><span data-stu-id="8718e-186">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="8718e-187">**I clienti Enterprise E5**: anche se gli utenti vengono assegnati licenze E5 Enterprise, è comunque consigliabile che assegnare loro le licenze **Crediti Communications** .</span><span class="sxs-lookup"><span data-stu-id="8718e-187">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="8718e-188">**Passaggi successivi**: dopo aver assegnato questi licenze, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegna tali numeri per le persone all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8718e-188">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="8718e-189">Per istruzioni dettagliate, vedere [impostare le tariffe di chiamate](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="8718e-189">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="8718e-190">Come assegnare una licenza di Servizi di conferenza PSTN a un utente</span><span class="sxs-lookup"><span data-stu-id="8718e-190">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="8718e-p115">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365. Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="8718e-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="8718e-193">Come assegnare licenze Communications crediti in blocco</span><span class="sxs-lookup"><span data-stu-id="8718e-193">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="8718e-p116">Guarda lo script di esempio per l'assegnazione delle licenze di **Audioconferenza**. Aggiornalo con le informazioni per l'assegnazione di licenze di **Crediti comunicazioni**.</span><span class="sxs-lookup"><span data-stu-id="8718e-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8718e-196">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8718e-196">Related topics</span></span>

[<span data-ttu-id="8718e-197">Configurare le audioconferenze per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8718e-197">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[<span data-ttu-id="8718e-198">Impostare le tariffe di chiamate</span><span class="sxs-lookup"><span data-stu-id="8718e-198">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="8718e-199">Aggiungere i fondi e gestire Communications titoli di coda</span><span class="sxs-lookup"><span data-stu-id="8718e-199">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  