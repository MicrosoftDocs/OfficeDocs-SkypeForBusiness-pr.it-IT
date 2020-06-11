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
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Informazioni sull'ID chiamante predefinito di Microsoft 365 e Office 365 (numero di telefono assegnato dall'utente), noto anche come ID linea chiamante. È possibile modificare o bloccare l'ID chiamante di un utente.
ms.openlocfilehash: 059e92f04f3d4a5df73ed9201f1f784f2bd01f30
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691122"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="20dbf-104">Impostare l'ID chiamante per un utente</span><span class="sxs-lookup"><span data-stu-id="20dbf-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="20dbf-105">Il sistema telefonico in Microsoft 365 e Office 365 fornisce un ID chiamante predefinito che corrisponde al numero di telefono assegnato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="20dbf-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="20dbf-106">È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente.</span><span class="sxs-lookup"><span data-stu-id="20dbf-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="20dbf-107">Per altre informazioni sull'uso dell'ID chiamante nell'organizzazione, è [possibile usare l'ID chiamante nell'organizzazione](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="20dbf-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="20dbf-108">Al momento non è possibile bloccare le chiamate in arrivo in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="20dbf-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="20dbf-109">Ci sono impostazioni che possono essere modificate:</span><span class="sxs-lookup"><span data-stu-id="20dbf-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="20dbf-110">Questa funzione **non** deve essere usata per le organizzazioni in sede con Lync o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="20dbf-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="20dbf-p103">**Cambiare l'ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il suo numero di telefono, con un altro numero di telefono. Per esempio, è possibile cambiare l'ID chiamante dell'utente dal suo numero di telefono a un numero principale usato dall'azienda o cambiare l'ID linea chiamante dal suo numero di telefono al numero principale dell'ufficio legale. È possibile cambiare l'ID chiamante in qualsiasi numero di **servizio** online o in sede (a tariffa o numero verde).</span><span class="sxs-lookup"><span data-stu-id="20dbf-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="20dbf-114">Se vuoi utilizzare il parametro  _Service_, devi specificare un numero di servizio valido.</span><span class="sxs-lookup"><span data-stu-id="20dbf-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="20dbf-115">**Bloccare l'ID chiamante in uscita** È possibile bloccare l'ID chiamante in uscita dall'invio alle chiamate PSTN in uscita di un utente.</span><span class="sxs-lookup"><span data-stu-id="20dbf-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="20dbf-116">In questo modo il suo numero non verrà visualizzato sul telefono di una persona che chiama.</span><span class="sxs-lookup"><span data-stu-id="20dbf-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="20dbf-117">**Bloccare l'ID chiamante in entrata** È possibile impedire a un utente di ricevere l'ID chiamante in qualsiasi chiamata PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="20dbf-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="20dbf-118">Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="20dbf-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="20dbf-p105">Per impostazione predefinita, tutte queste impostazioni dell'ID chiamante sono **disattivate**. Questo significa che il numero di telefono di un utente Skype for Business online è visibile quando un utente effettua una chiamata a un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="20dbf-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="20dbf-121">Per ulteriori informazioni su queste impostazioni e su come usarle, visita [Come usare l'ID chiamante nella tua organizzazione](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="20dbf-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="20dbf-122">Impostare il criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="20dbf-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="20dbf-123">Per tutte le impostazioni dell'ID chiamante in Skype for business online, è necessario usare Windows PowerShell e non è possibile **usare** l'interfaccia di **amministrazione di Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="20dbf-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="20dbf-124">Verificare e avviare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20dbf-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="20dbf-125">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="20dbf-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="20dbf-126">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="20dbf-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="20dbf-127">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="20dbf-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="20dbf-128">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20dbf-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="20dbf-129">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="20dbf-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="20dbf-130">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="20dbf-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="20dbf-p107">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="20dbf-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="20dbf-134">Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="20dbf-134">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="20dbf-135">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="20dbf-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="20dbf-136">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="20dbf-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="20dbf-137">Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="20dbf-137">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="20dbf-138">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="20dbf-138">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="20dbf-139">Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="20dbf-139">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="20dbf-140">Consultare tutte le impostazioni dei criteri ID chiamante nella propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="20dbf-140">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="20dbf-141">Per visualizzare tutte le impostazioni dei criteri ID chiamante nell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="20dbf-141">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="20dbf-142">Vedere altri esempi e dettagli per [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="20dbf-142">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="20dbf-143">Creare un nuovo criterio ID chiamante per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="20dbf-143">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="20dbf-144">Per creare un nuovo criterio ID chiamante che imposta l'ID chiamante su Anonimo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="20dbf-144">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="20dbf-145">In qualsiasi caso, il campo "Numero di servizio" non deve iniziare con un "+".</span><span class="sxs-lookup"><span data-stu-id="20dbf-145">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="20dbf-146">Vedere altri esempi e dettagli per [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="20dbf-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="20dbf-147">Per applicare il nuovo criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="20dbf-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="20dbf-148">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="20dbf-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="20dbf-149">Se è già stato creato un criterio, è possibile usare il cmdlet [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) per apportare modifiche ai criteri esistenti e quindi utilizzare il cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="20dbf-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="20dbf-150">Impostare in modo che l'ID chiamante in entrata venga bloccato</span><span class="sxs-lookup"><span data-stu-id="20dbf-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="20dbf-151">Per bloccare l'ID chiamante in arrivo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="20dbf-151">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="20dbf-152">Vedere altri esempi e dettagli per [set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="20dbf-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="20dbf-153">Per applicare l'impostazione dei criteri creata a un utente dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="20dbf-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="20dbf-154">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="20dbf-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="20dbf-155">Rimuovere un criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="20dbf-155">Remove a caller ID policy</span></span>

<span data-ttu-id="20dbf-156">Per rimuovere un criterio dalla tua organizzazione, esegui:</span><span class="sxs-lookup"><span data-stu-id="20dbf-156">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="20dbf-157">Per rimuovere un criterio da un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="20dbf-157">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="20dbf-158">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20dbf-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="20dbf-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="20dbf-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="20dbf-160">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere.</span><span class="sxs-lookup"><span data-stu-id="20dbf-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="20dbf-161">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="20dbf-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="20dbf-162">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="20dbf-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="20dbf-163">Sei motivi per cui potresti voler usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="20dbf-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="20dbf-164">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="20dbf-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="20dbf-165">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="20dbf-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="20dbf-166">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20dbf-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="20dbf-167">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="20dbf-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="20dbf-168">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="20dbf-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="20dbf-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="20dbf-169">Related topics</span></span>
[<span data-ttu-id="20dbf-170">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="20dbf-170">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="20dbf-171">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="20dbf-171">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="20dbf-172">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="20dbf-172">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="20dbf-173">Ulteriori informazioni su ID linea chiamante e nome del chiamante</span><span class="sxs-lookup"><span data-stu-id="20dbf-173">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="20dbf-174">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="20dbf-174">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="20dbf-175">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="20dbf-175">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
