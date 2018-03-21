---
title: Come ID chiamante utilizzare all'interno dell'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
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
description: "ID chiamante può essere controllato per le chiamate in ingresso e in uscita per gli utenti di sistema telefonico utilizzando un criterio denominato CallingLineIdentity."
ms.openlocfilehash: e68b9c2130f5cfc8a054e485367351eccbffc93c
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="9d0c1-103">Come ID chiamante utilizzare all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="9d0c1-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="9d0c1-104">ID chiamante può essere controllato per le chiamate in ingresso e in uscita per gli utenti di sistema telefonico utilizzando un criterio denominato CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="9d0c1-105">La funzionalità ID chiamante è disponibile per tutti gli utenti di sistema telefonico indipendentemente dalla connettività PSTN:</span><span class="sxs-lookup"><span data-stu-id="9d0c1-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="9d0c1-106">Connettività PSTN in linea</span><span class="sxs-lookup"><span data-stu-id="9d0c1-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="9d0c1-107">Connettività PSTN locale con Skype per Business Cloud connettore Edition (richiede Cloud connettore Edition 1.4.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9d0c1-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="9d0c1-108">Connettività PSTN locale con Skype per Business Server (è richiesto Skype per Business Server 2015 CU5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9d0c1-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d0c1-109">Questo criterio non è disponibile in Skype per Business 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="9d0c1-110">ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="9d0c1-110">Outbound caller ID</span></span>

<span data-ttu-id="9d0c1-111">Sono disponibili tre opzioni per l'ID chiamante PSTN in uscita:</span><span class="sxs-lookup"><span data-stu-id="9d0c1-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="9d0c1-112">Numero di telefono assegnato all'utente, ovvero il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="9d0c1-113">Inventario dei numeri di un numero di telefono che verrà classificato come un *servizio* e il *numero verde* numero nei piani di chiamata in Office 365 telefono.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="9d0c1-114">In genere assegnata a una coda di chiamata o operatore automatico dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="9d0c1-115">Impostare su anonimo.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-115">Set to anonymous.</span></span>
    
<span data-ttu-id="9d0c1-116">Tuttavia, è possibile assegnare questi tipi di numeri di telefono per l'ID chiamante in uscita:</span><span class="sxs-lookup"><span data-stu-id="9d0c1-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="9d0c1-117">Inventario dei numeri dei numeri di telefono che classificati come *utente* nel proprio telefono tariffe di chiamate</span><span class="sxs-lookup"><span data-stu-id="9d0c1-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="9d0c1-118">Skype per numero di telefono locale Business Server</span><span class="sxs-lookup"><span data-stu-id="9d0c1-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="9d0c1-119">Per impostare l'ID chiamante in uscita, vedere [impostazione dell'ID chiamante per un utente](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9d0c1-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="9d0c1-120">Controllo degli utenti finali dell'ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="9d0c1-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="9d0c1-121">L'attributo EnableUserOverride consente agli utenti di un o più modificare le impostazioni di ID chiamante su **anonimo**.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="9d0c1-122">Ciò è valido solo quando viene configurato un criterio CallingLineIdentity con un parametro CallingIDSubstitute LineURI o sostituto.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="9d0c1-123">Il valore predefinito di EnableUserOverride è False.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="9d0c1-124">Gli utenti finali possono impostare ID chiamante su **anonimo** utilizzando la scheda **Chiama impostazioni** nel Skype per client desktop aziendali.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9d0c1-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9d0c1-125">**Windows**</span></span> <br/> |<span data-ttu-id="9d0c1-126">**Versione**</span><span class="sxs-lookup"><span data-stu-id="9d0c1-126">**Version**</span></span> <br/> |<span data-ttu-id="9d0c1-127">**È supportata**</span><span class="sxs-lookup"><span data-stu-id="9d0c1-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="9d0c1-128">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="9d0c1-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9d0c1-129">Canale corrente su 6 dicembre 2016 - versione completa 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="9d0c1-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="9d0c1-130">Sì</span><span class="sxs-lookup"><span data-stu-id="9d0c1-130">Yes</span></span>  <br/> |
|<span data-ttu-id="9d0c1-131">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="9d0c1-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9d0c1-132">Prima versione per il canale rinviata rilasciato il 22 febbraio 2017 - versione 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="9d0c1-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="9d0c1-133">Sì</span><span class="sxs-lookup"><span data-stu-id="9d0c1-133">Yes</span></span>  <br/> |
|<span data-ttu-id="9d0c1-134">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="9d0c1-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9d0c1-135">Rinviato canale rilasciato il 13 giugno 2017 - versione 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="9d0c1-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="9d0c1-136">Sì</span><span class="sxs-lookup"><span data-stu-id="9d0c1-136">Yes</span></span>  <br/> |
|<span data-ttu-id="9d0c1-137">MSI</span><span class="sxs-lookup"><span data-stu-id="9d0c1-137">MSI</span></span>  <br/> |<span data-ttu-id="9d0c1-138">Skype per le aziende</span><span class="sxs-lookup"><span data-stu-id="9d0c1-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="9d0c1-139">No</span><span class="sxs-lookup"><span data-stu-id="9d0c1-139">No</span></span>  <br/> |
|<span data-ttu-id="9d0c1-140">Mac</span><span class="sxs-lookup"><span data-stu-id="9d0c1-140">Mac</span></span>  <br/> |<span data-ttu-id="9d0c1-141">Skype per le aziende</span><span class="sxs-lookup"><span data-stu-id="9d0c1-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="9d0c1-142">No</span><span class="sxs-lookup"><span data-stu-id="9d0c1-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="9d0c1-143">ID chiamante in ingresso</span><span class="sxs-lookup"><span data-stu-id="9d0c1-143">Inbound Caller ID</span></span>

<span data-ttu-id="9d0c1-144">L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="9d0c1-145">È possibile impostare questo attributo, ma non è disponibile per gli utenti finali nella pagina Impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="9d0c1-146">Ed è attualmente disponibile solo con connettività PSTN in linea.</span><span class="sxs-lookup"><span data-stu-id="9d0c1-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="9d0c1-147">Per impostare l'ID chiamante in uscita, vedere [impostazione dell'ID chiamante per un utente](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9d0c1-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9d0c1-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9d0c1-148">Related topics</span></span>
[<span data-ttu-id="9d0c1-149">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="9d0c1-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="9d0c1-150">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="9d0c1-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="9d0c1-151">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="9d0c1-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="9d0c1-152">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="9d0c1-152">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="9d0c1-153">Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="9d0c1-153">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a><span data-ttu-id="9d0c1-154">Commenti e suggerimenti?</span><span class="sxs-lookup"><span data-stu-id="9d0c1-154">Feedback?</span></span>
<span data-ttu-id="9d0c1-155">Per inviare commenti e suggerimenti prodotto o per consentire us sapere come ci si limita, vedere [Skype per commenti e suggerimenti Business](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="9d0c1-155">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>