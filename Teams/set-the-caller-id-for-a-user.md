---
title: Impostare l'ID chiamante per un utente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Informazioni sul numero Microsoft 365 e Office 365 l'ID chiamante predefinito (il numero di telefono assegnato dall'utente), noto anche come ID linea chiamante. È possibile modificare o bloccare l'ID chiamante di un utente.
ms.openlocfilehash: dbbb48952264d82ca24bdd82dbb45538b0428368
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308335"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="ef05b-104">Impostare l'ID chiamante per un utente</span><span class="sxs-lookup"><span data-stu-id="ef05b-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="ef05b-105">Sistema telefonico in Microsoft 365 fornisce un ID chiamante predefinito che è il numero di telefono assegnato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ef05b-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="ef05b-106">È possibile impostare o bloccare l'ID chiamante (detto anche ID linea chiamante) per un utente.</span><span class="sxs-lookup"><span data-stu-id="ef05b-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="ef05b-107">Per altre informazioni su come usare l'ID chiamante nell'organizzazione, vedere Come usare l'ID chiamante [nell'organizzazione.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="ef05b-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="ef05b-108">Per impostazione predefinita, le impostazioni dell'ID chiamante seguenti **sono disattivate.**</span><span class="sxs-lookup"><span data-stu-id="ef05b-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="ef05b-109">Questo significa che il Teams di telefono dell'utente può essere visualizzato quando l'utente effettua una chiamata a un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="ef05b-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="ef05b-110">È possibile modificare queste impostazioni nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ef05b-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="ef05b-111">**ID chiamante in uscita** È possibile sostituire l'ID chiamante di un utente, che per impostazione predefinita è il numero di telefono, con un altro numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="ef05b-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="ef05b-112">Per esempio, è possibile cambiare l'ID chiamante dell'utente dal suo numero di telefono a un numero principale usato dall'azienda o cambiare l'ID linea chiamante dal suo numero di telefono al numero principale dell'ufficio legale.</span><span class="sxs-lookup"><span data-stu-id="ef05b-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="ef05b-113">È possibile modificare il numero id chiamata in qualsiasi numero di servizio online (numero a pagamento o numero verde).</span><span class="sxs-lookup"><span data-stu-id="ef05b-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="ef05b-114">È anche possibile modificare il numero di ID chiamata in un numero di telefono locale tramite Instradamento diretto assegnato a un account della risorsa usato da un Operatore automatico o coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ef05b-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="ef05b-115">Se si vuole usare il parametro *Service,* è necessario specificare un numero di servizio valido.</span><span class="sxs-lookup"><span data-stu-id="ef05b-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="ef05b-116">**Bloccare l'ID chiamante in uscita.**</span><span class="sxs-lookup"><span data-stu-id="ef05b-116">**Block outbound caller ID.**</span></span> <span data-ttu-id="ef05b-117">È possibile bloccare l'invio dell'ID chiamante in uscita nelle chiamate PSTN in uscita di un utente.</span><span class="sxs-lookup"><span data-stu-id="ef05b-117">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="ef05b-118">In questo modo il suo numero non verrà visualizzato sul telefono di una persona che chiama.</span><span class="sxs-lookup"><span data-stu-id="ef05b-118">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="ef05b-119">**Bloccare l'ID chiamante in arrivo.**</span><span class="sxs-lookup"><span data-stu-id="ef05b-119">**Block incoming caller ID.**</span></span> <span data-ttu-id="ef05b-120">È possibile impedire a un utente di ricevere l'ID chiamante in qualsiasi chiamata PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="ef05b-120">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="ef05b-121">**Impostare il nome della parte chiamante (CNAM).**</span><span class="sxs-lookup"><span data-stu-id="ef05b-121">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="ef05b-122">Per gli Microsoft Teams utenti è possibile inviare un CNAM sulle chiamate PSTN in uscita.</span><span class="sxs-lookup"><span data-stu-id="ef05b-122">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ef05b-123">Le chiamate d'emergenza vedranno sempre il numero di telefono dell'utente (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="ef05b-123">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="ef05b-124">Per altre informazioni su queste impostazioni e su come usarle, vedere Come usare l'ID chiamante [nell'organizzazione.](how-can-caller-id-be-used-in-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="ef05b-124">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="ef05b-125">Impostare il criterio ID chiamante</span><span class="sxs-lookup"><span data-stu-id="ef05b-125">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="ef05b-126">Per impostare l'ID chiamante su un numero di telefono dell'account della risorsa e per impostare il nome della parte chiamante, usare i cmdlet di PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity nel modulo di PowerShell 2.3.1 o versione successiva di Teams.</span><span class="sxs-lookup"><span data-stu-id="ef05b-126">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="ef05b-127">Queste opzioni non sono attualmente disponibili nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ef05b-127">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="ef05b-128">Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef05b-128">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="ef05b-129">Visualizzare, creare e applicare le impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="ef05b-129">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="ef05b-130">Per visualizzare tutte le impostazioni dei criteri id chiamante nell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ef05b-130">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="ef05b-131">Per altre informazioni, vedere [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="ef05b-131">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="ef05b-132">Per creare un nuovo criterio id chiamante per l'organizzazione, usare il cmdlet New-CsCallingIdentity:</span><span class="sxs-lookup"><span data-stu-id="ef05b-132">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="ef05b-133">In qualsiasi caso, il campo "Numero di servizio" non deve iniziare con un "+".</span><span class="sxs-lookup"><span data-stu-id="ef05b-133">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="ef05b-134">Per altre informazioni, vedere [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="ef05b-134">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="ef05b-135">Applicare il nuovo criterio creato usando il cmdlet Grant-CsCallingIdentity.</span><span class="sxs-lookup"><span data-stu-id="ef05b-135">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="ef05b-136">Ad esempio, l'esempio seguente applica il nuovo criterio all'utente Amos Marble.</span><span class="sxs-lookup"><span data-stu-id="ef05b-136">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="ef05b-137">Per altre informazioni, vedere [Cmdlet Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="ef05b-137">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="ef05b-138">Se si vuole bloccare l'ID chiamante in arrivo, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ef05b-138">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="ef05b-139">Per altre informazioni, vedere [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="ef05b-139">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="ef05b-140">Per applicare l'impostazione dei criteri creata a un utente dell'organizzazione, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ef05b-140">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="ef05b-141">Per altre informazioni, vedere [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="ef05b-141">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="ef05b-142">Per creare un nuovo criterio ID chiamante che imposta l'ID chiamante sul numero di telefono dell'account della risorsa specificato e imposta il nome della parte chiamante su Contoso:</span><span class="sxs-lookup"><span data-stu-id="ef05b-142">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="ef05b-143">Se è già stato creato un criterio, è possibile usare il cmdlet [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) per apportare modifiche ai criteri esistenti e quindi usare il cmdlet [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) per applicare le impostazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ef05b-143">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="ef05b-144">Rimuovere un'impostazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="ef05b-144">Remove a policy setting</span></span>

<span data-ttu-id="ef05b-145">Per rimuovere un criterio dalla tua organizzazione, esegui:</span><span class="sxs-lookup"><span data-stu-id="ef05b-145">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="ef05b-146">Per rimuovere un criterio da un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="ef05b-146">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ef05b-147">Vuoi saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ef05b-147">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ef05b-148">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="ef05b-148">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ef05b-149">Con Windows PowerShell, è possibile gestire i Microsoft 365 con un unico punto di amministrazione che semplifica il lavoro quotidiano.</span><span class="sxs-lookup"><span data-stu-id="ef05b-149">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="ef05b-150">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef05b-150">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="ef05b-151">Introduzione alla Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef05b-151">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="ef05b-152">Sei motivi per cui è consigliabile usare Windows PowerShell per gestire Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ef05b-152">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="ef05b-153">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ef05b-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ef05b-154">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="ef05b-154">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="ef05b-155">[Modi migliori per gestire Microsoft 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ef05b-155">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="ef05b-156">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="ef05b-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="ef05b-157">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="ef05b-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="ef05b-158">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ef05b-158">Related topics</span></span>
[<span data-ttu-id="ef05b-159">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="ef05b-159">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="ef05b-160">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="ef05b-160">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="ef05b-161">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="ef05b-161">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="ef05b-162">Ulteriori informazioni su ID linea chiamante e nome del chiamante</span><span class="sxs-lookup"><span data-stu-id="ef05b-162">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="ef05b-163">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="ef05b-163">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="ef05b-164">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ef05b-164">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
