---
title: Impostare l'ID chiamante per un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Il sistema telefonico in Office 365 fornisce un ID chiamante predefinito che è il numero di telefono assegnato dell'utente. È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente. È possibile ulteriori informazioni su come utilizzare l'ID del chiamante all'interno dell'organizzazione passando come ID chiamante utilizzare all'interno dell'organizzazione.
ms.openlocfilehash: a48edfd6f0b6967f1f9c628b415f781b8c4832c7
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500854"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="0ad16-105">Impostare l'ID chiamante per un utente</span><span class="sxs-lookup"><span data-stu-id="0ad16-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="0ad16-106">Il sistema telefonico in Office 365 fornisce un ID chiamante predefinito che è il numero di telefono assegnato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0ad16-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="0ad16-107">È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente.</span><span class="sxs-lookup"><span data-stu-id="0ad16-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="0ad16-108">È possibile ulteriori informazioni su come utilizzare l'ID chiamante all'interno dell'organizzazione da utilizzare [come ID chiamante utilizzare all'interno dell'organizzazione](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="0ad16-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="0ad16-109">Non è possibile bloccare le chiamate in arrivo attualmente in Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="0ad16-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="0ad16-110">Ci sono impostazioni che possono essere modificate:</span><span class="sxs-lookup"><span data-stu-id="0ad16-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="0ad16-111">Questa funzione **non** deve essere usata per le organizzazioni in sede con Lync o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0ad16-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="0ad16-p103">**Cambiare l'ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il suo numero di telefono, con un altro numero di telefono. Per esempio, è possibile cambiare l'ID chiamante dell'utente dal suo numero di telefono a un numero principale usato dall'azienda o cambiare l'ID linea chiamante dal suo numero di telefono al numero principale dell'ufficio legale. È possibile cambiare l'ID chiamante in qualsiasi numero di **servizio** online o in sede (a tariffa o numero verde).</span><span class="sxs-lookup"><span data-stu-id="0ad16-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0ad16-115">Se vuoi utilizzare il parametro  _Service_, devi specificare un numero di servizio valido.</span><span class="sxs-lookup"><span data-stu-id="0ad16-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="0ad16-116">**Blocca l'ID chiamante in uscita** È possibile bloccare l'ID chiamante in uscita vengano inviate in chiamate PSTN in uscita dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0ad16-116">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="0ad16-117">In questo modo il suo numero non verrà visualizzato sul telefono di una persona che chiama.</span><span class="sxs-lookup"><span data-stu-id="0ad16-117">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="0ad16-118">**Blocca l'ID chiamante in ingresso** È possibile bloccare un utente di ricevere l'ID chiamante in tutte le chiamate PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="0ad16-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="0ad16-119">Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="0ad16-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="0ad16-p105">Per impostazione predefinita, tutte queste impostazioni dell'ID chiamante sono **disattivate**. Questo significa che il numero di telefono di un utente Skype for Business online è visibile quando un utente effettua una chiamata a un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="0ad16-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="0ad16-122">Per ulteriori informazioni su queste impostazioni e su come usarle, visita [Come usare l'ID chiamante nella tua organizzazione](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="0ad16-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="0ad16-123">Impostare il criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="0ad16-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="0ad16-124">Per tutte le impostazioni di ID chiamante in Skype Business online, è necessario utilizzare Windows PowerShell e non è **possibile utilizzare** **Skype per interfaccia di amministrazione di Business**.</span><span class="sxs-lookup"><span data-stu-id="0ad16-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="0ad16-125">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ad16-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="0ad16-126">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="0ad16-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="0ad16-127">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0ad16-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0ad16-128">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0ad16-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="0ad16-p106">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="0ad16-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="0ad16-p107">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="0ad16-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="0ad16-135">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ad16-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="0ad16-136">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0ad16-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="0ad16-137">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0ad16-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0ad16-138">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="0ad16-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0ad16-139">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="0ad16-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="0ad16-140">Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ad16-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="0ad16-141">Consultare tutte le impostazioni dei criteri ID chiamante nella propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="0ad16-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="0ad16-142">Per visualizzare tutte le impostazioni di criteri di ID chiamante nell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0ad16-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
<span data-ttu-id="0ad16-143">Vedere ulteriori esempi e informazioni dettagliate per [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ad16-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="0ad16-144">Creare un nuovo criterio ID chiamante per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="0ad16-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="0ad16-145">Per creare un nuovo criterio di ID chiamante che imposta l'ID chiamante anonimi, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0ad16-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="0ad16-146">In tutti i casi, il campo "Servizio Number" non dovrebbe includere un iniziale "+".</span><span class="sxs-lookup"><span data-stu-id="0ad16-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="0ad16-147">Vedere ulteriori esempi e informazioni dettagliate per [CsCallingLineIdentity New](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ad16-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="0ad16-148">Per applicare il nuovo criterio creato a Marmo Amos, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0ad16-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="0ad16-149">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ad16-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="0ad16-150">Se è già stato creato un criterio, è possibile utilizzare il cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) per apportare modifiche al criterio esistente e quindi utilizzare il cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) per applicare le impostazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0ad16-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="0ad16-151">Impostare in modo che l'ID chiamante in entrata venga bloccato</span><span class="sxs-lookup"><span data-stu-id="0ad16-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="0ad16-152">Per bloccare l'ID chiamante in arrivo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0ad16-152">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="0ad16-153">Vedere ulteriori esempi e informazioni dettagliate per [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ad16-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="0ad16-154">Per applicare l'impostazione del criterio creato a un utente all'interno dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="0ad16-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="0ad16-155">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ad16-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="0ad16-156">Rimuovere un criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="0ad16-156">Remove a caller ID policy</span></span>

<span data-ttu-id="0ad16-157">Per rimuovere un criterio dalla tua organizzazione, esegui:</span><span class="sxs-lookup"><span data-stu-id="0ad16-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="0ad16-158">Per rimuovere un criterio da un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="0ad16-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0ad16-159">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ad16-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0ad16-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="0ad16-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0ad16-161">È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="0ad16-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0ad16-162">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="0ad16-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0ad16-163">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0ad16-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0ad16-164">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="0ad16-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0ad16-p109">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ad16-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0ad16-167">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="0ad16-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0ad16-168">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0ad16-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0ad16-169">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0ad16-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="0ad16-170">See also</span><span class="sxs-lookup"><span data-stu-id="0ad16-170">Related topics</span></span>
[<span data-ttu-id="0ad16-171">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="0ad16-171">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="0ad16-172">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="0ad16-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="0ad16-173">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="0ad16-173">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="0ad16-174">Ulteriori informazioni su ID linea chiamante e nome del chiamante</span><span class="sxs-lookup"><span data-stu-id="0ad16-174">More about Calling Line ID and Calling Party Name</span></span>](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[<span data-ttu-id="0ad16-175">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="0ad16-175">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="0ad16-176">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0ad16-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
  
 
 
