---
title: Impostare l'ID chiamante per un utente
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Informazioni sull'ID chiamante predefinito di Microsoft 365 e Office 365 (numero di telefono assegnato da un utente), noto anche come ID linea chiamante. È possibile modificare o bloccare l'ID chiamante di un utente.
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117154"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="d754c-104">Impostare l'ID chiamante per un utente</span><span class="sxs-lookup"><span data-stu-id="d754c-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="d754c-105">Sistema telefonico in Microsoft 365 e Office 365 fornisce un ID chiamante predefinito che è il numero di telefono assegnato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d754c-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="d754c-106">È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente.</span><span class="sxs-lookup"><span data-stu-id="d754c-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="d754c-107">Per altre informazioni su come usare l'ID chiamante nell'organizzazione, vedere Come usare l'ID chiamante [nell'organizzazione.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="d754c-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="d754c-108">Al momento non è possibile bloccare le chiamate in arrivo in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="d754c-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="d754c-109">Ci sono impostazioni che possono essere modificate:</span><span class="sxs-lookup"><span data-stu-id="d754c-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="d754c-110">Questa funzione **non** deve essere usata per le organizzazioni in sede con Lync o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d754c-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="d754c-p103">**Cambiare l'ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il suo numero di telefono, con un altro numero di telefono. Per esempio, è possibile cambiare l'ID chiamante dell'utente dal suo numero di telefono a un numero principale usato dall'azienda o cambiare l'ID linea chiamante dal suo numero di telefono al numero principale dell'ufficio legale. È possibile cambiare l'ID chiamante in qualsiasi numero di **servizio** online o in sede (a tariffa o numero verde).</span><span class="sxs-lookup"><span data-stu-id="d754c-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d754c-114">Se vuoi utilizzare il parametro  _Service_, devi specificare un numero di servizio valido.</span><span class="sxs-lookup"><span data-stu-id="d754c-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="d754c-115">**Bloccare l'ID chiamante in uscita** È possibile bloccare l'invio dell'ID chiamante in uscita nelle chiamate PSTN in uscita di un utente.</span><span class="sxs-lookup"><span data-stu-id="d754c-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="d754c-116">In questo modo il suo numero non verrà visualizzato sul telefono di una persona che chiama.</span><span class="sxs-lookup"><span data-stu-id="d754c-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="d754c-117">**Bloccare l'ID chiamante in arrivo** È possibile impedire a un utente di ricevere l'ID chiamante in qualsiasi chiamata PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d754c-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d754c-118">Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="d754c-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="d754c-p105">Per impostazione predefinita, tutte queste impostazioni dell'ID chiamante sono **disattivate**. Questo significa che il numero di telefono di un utente Skype for Business online è visibile quando un utente effettua una chiamata a un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="d754c-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="d754c-121">Per ulteriori informazioni su queste impostazioni e su come usarle, visita [Come usare l'ID chiamante nella tua organizzazione](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d754c-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="d754c-122">Impostare il criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="d754c-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="d754c-123">Per tutte le impostazioni **dell'ID** chiamante in Skype for Business online, è necessario usare Windows PowerShell e non è possibile usare l'interfaccia di amministrazione **di Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="d754c-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="d754c-124">Avviare PowerShell</span><span class="sxs-lookup"><span data-stu-id="d754c-124">Start PowerShell</span></span>

- <span data-ttu-id="d754c-125">Aprire un Windows PowerShell comando ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d754c-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="d754c-126">Consultare tutte le impostazioni dei criteri ID chiamante nella propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="d754c-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="d754c-127">Per visualizzare tutte le impostazioni dei criteri id chiamante nell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="d754c-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="d754c-128">Vedere altri esempi e dettagli [per Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="d754c-128">See more examples and details for [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="d754c-129">Creare un nuovo criterio ID chiamante per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="d754c-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="d754c-130">Per creare un nuovo criterio id chiamante che imposta l'ID chiamante su anonimo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="d754c-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="d754c-131">In qualsiasi caso, il campo "Numero di servizio" non deve iniziare con un "+".</span><span class="sxs-lookup"><span data-stu-id="d754c-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="d754c-132">Vedere altri esempi e dettagli [per New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="d754c-132">See more examples and details for [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
- <span data-ttu-id="d754c-133">Per applicare il nuovo criterio creato ad Amos Marble, eseguire:</span><span class="sxs-lookup"><span data-stu-id="d754c-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="d754c-134">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="d754c-134">See more on the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    
<span data-ttu-id="d754c-135">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="d754c-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="d754c-136">Impostare in modo che l'ID chiamante in entrata venga bloccato</span><span class="sxs-lookup"><span data-stu-id="d754c-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="d754c-137">Per bloccare l'ID chiamante in arrivo, esegui:</span><span class="sxs-lookup"><span data-stu-id="d754c-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="d754c-138">Vedere altri esempi e dettagli [per Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="d754c-138">See more examples and details for [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
- <span data-ttu-id="d754c-139">Per applicare l'impostazione dei criteri creata a un utente dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="d754c-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="d754c-140">Altre informazioni sul cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="d754c-140">See more on the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="d754c-141">Rimuovere un criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="d754c-141">Remove a caller ID policy</span></span>

<span data-ttu-id="d754c-142">Per rimuovere un criterio dalla tua organizzazione, esegui:</span><span class="sxs-lookup"><span data-stu-id="d754c-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="d754c-143">Per rimuovere un criterio da un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="d754c-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d754c-144">Per saperne di più sulle Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d754c-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d754c-145">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="d754c-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d754c-146">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d754c-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d754c-147">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="d754c-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d754c-148">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d754c-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="d754c-149">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="d754c-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="d754c-150">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d754c-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d754c-151">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="d754c-151">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="d754c-152">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d754c-152">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="d754c-153">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d754c-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="d754c-154">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d754c-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="d754c-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d754c-155">Related topics</span></span>
[<span data-ttu-id="d754c-156">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="d754c-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="d754c-157">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="d754c-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="d754c-158">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="d754c-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d754c-159">Ulteriori informazioni su ID linea chiamante e nome del chiamante</span><span class="sxs-lookup"><span data-stu-id="d754c-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="d754c-160">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="d754c-160">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="d754c-161">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d754c-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
