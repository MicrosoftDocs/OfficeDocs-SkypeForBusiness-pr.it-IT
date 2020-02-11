---
title: Assegnare licenze di Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Informazioni su come assegnare licenze per funzionalità come audioconferenza, sistema telefonico e piani di chiamata.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46ae5952d79f3f0ef0a6137b240661550ecead00
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888685"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="6cb3a-103">Assegnare licenze di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cb3a-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="6cb3a-104">È possibile assegnare licenze agli utenti per funzionalità come i piani di audioconferenza, sistema telefonico e chiamate.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="6cb3a-105">Questo articolo illustra come aggiungere queste licenze in blocco e per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6cb3a-106">Vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per informazioni sulle licenze che è necessario acquistare e su come acquistarle, a seconda del piano di Office 365, in modo che gli utenti ottengano servizi di audioconferenza, numeri verdi e la possibilità di chiamare i numeri di telefono all'esterno della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="6cb3a-107">Sistema telefonico e Piani per chiamate: suggerimenti e script per l'assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="6cb3a-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="6cb3a-108">Ecco cosa è necessario sapere prima di assegnare le licenze per i servizi di audioconferenza, il sistema telefonico e il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="6cb3a-109">**Usi la connettività PSTN locale per utenti ibridi?**</span><span class="sxs-lookup"><span data-stu-id="6cb3a-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="6cb3a-110">In questo caso, devi assegnare soltanto una licenza Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="6cb3a-111">NON dovrai invece assegnare un Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="6cb3a-112">**Latenza dopo l'assegnazione delle licenze**: a causa della latenza tra Office 365 e Microsoft teams, possono essere necessarie fino a 24 ore per consentire a un utente di assegnare un piano di chiamata dopo l'assegnazione di una licenza.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="6cb3a-113">Se dopo 24 ore non è stato assegnato un piano per le chiamate, [contattare il supporto per i prodotti business-Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="6cb3a-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="6cb3a-p104">**Messaggi d'errore**: se non hai acquistato il numero corretto di licenze, verrà visualizzato un messaggio di errore. Se è necessario acquistare altre licenze di Piani per chiamate, scegli **Acquista altro**.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="6cb3a-116">**Passaggi successivi**: dopo avere assegnato le licenze per il Piano per chiamate agli utenti, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="6cb3a-117">Per istruzioni dettagliate, vedere [configurare i piani](set-up-calling-plans.md)per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="6cb3a-118">Assegnare un sistema telefonico e una licenza per un piano di chiamata a un utente</span><span class="sxs-lookup"><span data-stu-id="6cb3a-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="6cb3a-119">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="6cb3a-120">Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="6cb3a-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="6cb3a-121">Assegnare licenze per il sistema telefonico e il piano di chiamata in blocco</span><span class="sxs-lookup"><span data-stu-id="6cb3a-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="6cb3a-122">Installa Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="6cb3a-123">Cosa fare se il modulo non è installato?</span><span class="sxs-lookup"><span data-stu-id="6cb3a-123">Don't have the module installed?</span></span> <span data-ttu-id="6cb3a-124">Per scaricarlo, vedere [Assistente per l'accesso ai Microsoft Online Services per professionisti IT-RTW](https://go.microsoft.com/fwlink/?LinkId=625123) .</span><span class="sxs-lookup"><span data-stu-id="6cb3a-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="6cb3a-125">Installa il Modulo di Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="6cb3a-126">Cosa fare se il modulo non è installato?</span><span class="sxs-lookup"><span data-stu-id="6cb3a-126">Don't have the module installed?</span></span> <span data-ttu-id="6cb3a-127">Vedere [gestire Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per le istruzioni per il download e la sintassi dei cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="6cb3a-128">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="6cb3a-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="6cb3a-129">In questo esempio vengono assegnate una licenza di Enterprise E3 insieme a una licenza per Sistema telefonico e per un Piano per chiamate nazionali.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="6cb3a-130">Il nome delle licenze o dei nomi di prodotto nello script è elencato in corsivo (Vedi il [sistema telefonico e i piani di chiamata per i nomi dei prodotti o gli SKU usati per gli script](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), dopo l'esempio).</span><span class="sxs-lookup"><span data-stu-id="6cb3a-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```powershell
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

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="6cb3a-131">Nomi di prodotto di Sistema telefonico e Piani per chiamate o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="6cb3a-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="6cb3a-132">Nome del prodotto</span><span class="sxs-lookup"><span data-stu-id="6cb3a-132">Product name</span></span> | <span data-ttu-id="6cb3a-133">Nome parte SKU</span><span class="sxs-lookup"><span data-stu-id="6cb3a-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="6cb3a-134">Enterprise E5 (con Sistema telefonico)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="6cb3a-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="6cb3a-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="6cb3a-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="6cb3a-136">Enterprise E3</span></span> | <span data-ttu-id="6cb3a-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="6cb3a-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="6cb3a-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="6cb3a-138">Enterprise E1</span></span> | <span data-ttu-id="6cb3a-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="6cb3a-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="6cb3a-140">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="6cb3a-140">Phone System</span></span> | <span data-ttu-id="6cb3a-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="6cb3a-141">MCOEV</span></span> |
| <span data-ttu-id="6cb3a-142">Piano di chiamate internazionali & nazionali</span><span class="sxs-lookup"><span data-stu-id="6cb3a-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="6cb3a-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="6cb3a-143">MCOPSTN2</span></span> |
| <span data-ttu-id="6cb3a-144">Piano per chiamate nazionali (3000 minuti per utente/mese per US/PR/CA, 1200 minuti per utente/mese per i paesi dell'UE)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="6cb3a-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="6cb3a-145">MCOPSTN1</span></span> |
| <span data-ttu-id="6cb3a-146">Piano per chiamate nazionali (120 minuti per utente/mese per ogni paese)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="6cb3a-147">*Nota: questo piano non è disponibile negli Stati Uniti*.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="6cb3a-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="6cb3a-148">MCOPSTN5</span></span> |
| <span data-ttu-id="6cb3a-149">Piano per chiamate nazionali (240 minuti per utente/mese per ogni paese)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="6cb3a-150">*Nota: questo piano non è disponibile negli Stati Uniti*.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="6cb3a-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="6cb3a-151">MCOPSTN6</span></span> |
| <span data-ttu-id="6cb3a-152">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="6cb3a-152">Communications Credits</span></span> | <span data-ttu-id="6cb3a-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="6cb3a-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="6cb3a-154">Servizi di conferenza audio: suggerimenti e script per l'assegnazione di licenze</span><span class="sxs-lookup"><span data-stu-id="6cb3a-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="6cb3a-155">Ecco cosa devi sapere prima di assegnare le licenze per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="6cb3a-156">**Provider di audioconferenze di terze parti**: se per un utente è già stato impostato l'utilizzo di un provider di servizi di audioconferenza di terze parti, quando gli viene assegnata una licenza di Audioconferenza, Microsoft diventa il provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="6cb3a-157">Puoi impostare nuovamente il provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="6cb3a-158">**Passaggi successivi**: dopo aver assegnato le licenze di audioconferenza, è necessario assegnare un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="6cb3a-159">Vedere [assegnare Microsoft come provider di servizi di audioconferenza](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="6cb3a-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="6cb3a-160">Assegnare una licenza di audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="6cb3a-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="6cb3a-161">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="6cb3a-162">Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="6cb3a-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="6cb3a-163">Assegnare licenze per servizi di audioconferenza in blocco</span><span class="sxs-lookup"><span data-stu-id="6cb3a-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="6cb3a-164">Scaricare e installare l' [Assistente per l'accesso ai Microsoft Online Services per professionisti IT-RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="6cb3a-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="6cb3a-165">Scarica e installa il Modulo di Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="6cb3a-166">Vedere [gestire Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) per le istruzioni per il download e la sintassi dei cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="6cb3a-167">Una volta installati i moduli, usa il prompt dei comandi di Windows PowerShell e la seguente sintassi per assegnare le licenze agli utenti:</span><span class="sxs-lookup"><span data-stu-id="6cb3a-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="6cb3a-168">Il nome delle licenze o dei nomi di prodotto nello script è elencato in corsivo.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="6cb3a-169">Vedere [nomi di prodotti per la conferenza audio o SKU usati per gli script](#audio-conferencing-product-names-or-skus-used-for-scripting) per tutti i nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="6cb3a-170">In questo esempio vengono assegnate una licenza di Enterprise E3 e una licenza per i servizi Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```powershell
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

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="6cb3a-171">Nomi dei prodotti per la conferenza audio o SKU usati per gli script</span><span class="sxs-lookup"><span data-stu-id="6cb3a-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="6cb3a-172">Nome del prodotto</span><span class="sxs-lookup"><span data-stu-id="6cb3a-172">Product name</span></span> | <span data-ttu-id="6cb3a-173">Nome parte SKU</span><span class="sxs-lookup"><span data-stu-id="6cb3a-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="6cb3a-174">Servizi di audioconferenza (abbonamento)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="6cb3a-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="6cb3a-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="6cb3a-176">Pay-in per i servizi di audioconferenza per minuto (pay-in-go)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="6cb3a-177">*Nota: richiede che i crediti di comunicazione siano configurati e abilitati*.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="6cb3a-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="6cb3a-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="6cb3a-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="6cb3a-179">Enterprise E1</span></span> | <span data-ttu-id="6cb3a-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="6cb3a-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="6cb3a-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="6cb3a-181">Enterprise E3</span></span> | <span data-ttu-id="6cb3a-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="6cb3a-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="6cb3a-183">Enterprise E5 (senza Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="6cb3a-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="6cb3a-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="6cb3a-185">Enterprise E5 (con Audioconferenza)</span><span class="sxs-lookup"><span data-stu-id="6cb3a-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="6cb3a-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="6cb3a-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="6cb3a-187">Credito per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="6cb3a-187">Communications Credits</span></span>

<span data-ttu-id="6cb3a-188">Ecco cosa è necessario sapere prima di assegnare le licenze per i crediti di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="6cb3a-189">**Clienti Enterprise E5**: anche se agli utenti sono assegnate licenze Enterprise E5, è comunque consigliabile assegnare loro licenze per i crediti per comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="6cb3a-190">**Passaggi successivi**: dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="6cb3a-191">Per istruzioni dettagliate, vedere [configurare i piani](set-up-calling-plans.md)per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="6cb3a-192">Assegnare una licenza per i crediti di comunicazione a un utente</span><span class="sxs-lookup"><span data-stu-id="6cb3a-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="6cb3a-193">I passaggi sono uguali a quelli seguiti per l'assegnazione di una licenza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="6cb3a-194">Consulta la sezione [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="6cb3a-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="6cb3a-195">Assegnare licenze per i crediti di comunicazione in blocco</span><span class="sxs-lookup"><span data-stu-id="6cb3a-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="6cb3a-196">Guarda lo script di esempio per l'assegnazione delle licenze di Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="6cb3a-197">Aggiornalo con le informazioni per l'assegnazione di licenze di Crediti comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="6cb3a-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6cb3a-198">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6cb3a-198">Related topics</span></span>

[<span data-ttu-id="6cb3a-199">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="6cb3a-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="6cb3a-200">Aggiungere fondi e gestire i crediti per la comunicazione</span><span class="sxs-lookup"><span data-stu-id="6cb3a-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
