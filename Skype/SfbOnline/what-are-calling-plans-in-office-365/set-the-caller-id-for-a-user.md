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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente. You can learn more about how to use caller ID in your organization by going How can caller ID be used in your organization.
ms.openlocfilehash: ac3732be84d44b7f42c8a76c51dd1aeb72b7cac3
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="ca67d-105">Impostare l'ID chiamante per un utente</span><span class="sxs-lookup"><span data-stu-id="ca67d-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="ca67d-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span><span class="sxs-lookup"><span data-stu-id="ca67d-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="ca67d-107">È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente.</span><span class="sxs-lookup"><span data-stu-id="ca67d-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="ca67d-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ca67d-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="ca67d-109">You can't block incoming calls currently in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ca67d-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="ca67d-110">Ci sono impostazioni che possono essere modificate:</span><span class="sxs-lookup"><span data-stu-id="ca67d-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca67d-111">Questa funzione **non** deve essere usata per le organizzazioni in sede con Lync o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ca67d-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="ca67d-p103">**Cambiare l'ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il suo numero di telefono, con un altro numero di telefono. Per esempio, è possibile cambiare l'ID chiamante dell'utente dal suo numero di telefono a un numero principale usato dall'azienda o cambiare l'ID linea chiamante dal suo numero di telefono al numero principale dell'ufficio legale. È possibile cambiare l'ID chiamante in qualsiasi numero di **servizio** online o in sede (a tariffa o numero verde).</span><span class="sxs-lookup"><span data-stu-id="ca67d-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ca67d-115">Se vuoi utilizzare il parametro  _Service_, devi specificare un numero di servizio valido.</span><span class="sxs-lookup"><span data-stu-id="ca67d-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="ca67d-116">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span><span class="sxs-lookup"><span data-stu-id="ca67d-116">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="ca67d-117">In questo modo il suo numero non verrà visualizzato sul telefono di una persona che chiama.</span><span class="sxs-lookup"><span data-stu-id="ca67d-117">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="ca67d-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span><span class="sxs-lookup"><span data-stu-id="ca67d-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ca67d-119">Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="ca67d-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="ca67d-p105">Per impostazione predefinita, tutte queste impostazioni dell'ID chiamante sono **disattivate**. Questo significa che il numero di telefono di un utente Skype for Business online è visibile quando un utente effettua una chiamata a un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca67d-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="ca67d-122">Per ulteriori informazioni su queste impostazioni e su come usarle, visita [Come usare l'ID chiamante nella tua organizzazione](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ca67d-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="ca67d-123">Impostare il criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="ca67d-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="ca67d-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span><span class="sxs-lookup"><span data-stu-id="ca67d-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ca67d-125">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca67d-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ca67d-126">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="ca67d-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ca67d-127">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ca67d-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ca67d-128">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ca67d-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ca67d-p106">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="ca67d-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ca67d-p107">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="ca67d-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="ca67d-135">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca67d-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ca67d-136">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ca67d-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ca67d-137">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ca67d-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ca67d-138">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="ca67d-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ca67d-139">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="ca67d-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
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

<span data-ttu-id="ca67d-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca67d-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="ca67d-141">Consultare tutte le impostazioni dei criteri ID chiamante nella propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="ca67d-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="ca67d-142">To view all of the caller ID policy settings in your organization, run:</span><span class="sxs-lookup"><span data-stu-id="ca67d-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
<span data-ttu-id="ca67d-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca67d-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="ca67d-144">Creare un nuovo criterio ID chiamante per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="ca67d-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="ca67d-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span><span class="sxs-lookup"><span data-stu-id="ca67d-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

  > [!NOTE]  
  > <span data-ttu-id="ca67d-146">In all cases, the "Service Number" field should not include an initial "+".</span><span class="sxs-lookup"><span data-stu-id="ca67d-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="ca67d-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca67d-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="ca67d-148">To apply the new policy you created to Amos Marble, run:</span><span class="sxs-lookup"><span data-stu-id="ca67d-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="ca67d-149">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca67d-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="ca67d-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span><span class="sxs-lookup"><span data-stu-id="ca67d-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="ca67d-151">Impostare in modo che l'ID chiamante in entrata venga bloccato</span><span class="sxs-lookup"><span data-stu-id="ca67d-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="ca67d-152">To block the incoming caller ID, run:</span><span class="sxs-lookup"><span data-stu-id="ca67d-152">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="ca67d-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca67d-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="ca67d-154">To apply the policy setting you created to a user in your organization, run:</span><span class="sxs-lookup"><span data-stu-id="ca67d-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="ca67d-155">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="ca67d-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="ca67d-156">Rimuovere un criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="ca67d-156">Remove a caller ID policy</span></span>

<span data-ttu-id="ca67d-157">Per rimuovere un criterio dalla tua organizzazione, esegui:</span><span class="sxs-lookup"><span data-stu-id="ca67d-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="ca67d-158">Per rimuovere un criterio da un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="ca67d-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ca67d-159">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca67d-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ca67d-p108">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="ca67d-p108">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ca67d-163">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ca67d-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ca67d-164">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="ca67d-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ca67d-p109">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca67d-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ca67d-167">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="ca67d-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ca67d-168">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ca67d-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ca67d-169">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ca67d-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ca67d-170">See also</span><span class="sxs-lookup"><span data-stu-id="ca67d-170">Related topics</span></span>
[<span data-ttu-id="ca67d-171">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="ca67d-171">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="ca67d-172">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="ca67d-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="ca67d-173">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="ca67d-173">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="ca67d-174">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="ca67d-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="ca67d-175">Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ca67d-175">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
  
  
 
