---
title: Come usare l'ID chiamante nella tua organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
ms.openlocfilehash: c8a823235c3c3fedaf71d42e8482c5f4579b80ef
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958172"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="9f1a5-103">Come usare l'ID chiamante nella tua organizzazione</span><span class="sxs-lookup"><span data-stu-id="9f1a5-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="9f1a5-104">L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="9f1a5-105">La funzionalità ID chiamante è disponibile per tutti gli utenti di Sistema telefonico indipendentemente dalla connettività PSTN:</span><span class="sxs-lookup"><span data-stu-id="9f1a5-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="9f1a5-106">Connettività PSTN in linea</span><span class="sxs-lookup"><span data-stu-id="9f1a5-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="9f1a5-107">Connettività PSTN locale con Skype for Businesss Cloud Connector Edition (richiede Cloud Connector Edition 1.4.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9f1a5-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="9f1a5-108">Connettività PSTN locale con Skype for Businesss Server (richiede Skype for Businesss Server 2015 CU5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9f1a5-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="9f1a5-109">Questo criterio non è disponibile in Skype for Businesss 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="9f1a5-110">ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="9f1a5-110">Outbound caller ID</span></span>

<span data-ttu-id="9f1a5-111">Sono disponibili tre opzioni per l'ID chiamante PSTN in uscita:</span><span class="sxs-lookup"><span data-stu-id="9f1a5-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="9f1a5-112">Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="9f1a5-113">Numero di telefono classificato come *servizio* e *numero verde* nei tuoi Piani chiamata nella rubrica telefonica di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="9f1a5-114">In genere assegnato a una coda di chiamata o operatore automatico dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="9f1a5-115">Impostato su anonimo.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-115">Set to anonymous.</span></span>
    
<span data-ttu-id="9f1a5-116">Tuttavia, non è possibile assegnare questi tipi di numeri di telefono per l'ID chiamante in uscita:</span><span class="sxs-lookup"><span data-stu-id="9f1a5-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="9f1a5-117">I numeri di telefono classificati come *utente* nella rubrica telefonica dei tuoi Piani chiamata</span><span class="sxs-lookup"><span data-stu-id="9f1a5-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="9f1a5-118">Un numero di telefono Skype for Businesss Server locale</span><span class="sxs-lookup"><span data-stu-id="9f1a5-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="9f1a5-119">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9f1a5-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="9f1a5-120">Controllo degli utenti finali dell'ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="9f1a5-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="9f1a5-121">L'attributo EnableUserOverride consente a uno o più utenti di modificare le impostazioni dell'ID chiamante su **Anonimo**.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="9f1a5-122">Ciò è valido solo quando viene configurato un criterio CallingLineIdentity con un parametro CallingIDSubstitute LineURI o sostituto.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="9f1a5-123">Il valore predefinito di EnableUserOverride è False.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="9f1a5-124">Gli utenti finali possono impostare l'ID chiamante su **Anonimo** utilizzando la scheda **Impostazioni inoltro chiamata** nella scrivania cliente di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9f1a5-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9f1a5-125">**Windows**</span></span> <br/> |<span data-ttu-id="9f1a5-126">**Versione**</span><span class="sxs-lookup"><span data-stu-id="9f1a5-126">**Version**</span></span> <br/> |<span data-ttu-id="9f1a5-127">**È supportata**</span><span class="sxs-lookup"><span data-stu-id="9f1a5-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="9f1a5-128">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="9f1a5-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9f1a5-129">Current Channel rilasciato il 6 dicembre 2016 - versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="9f1a5-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="9f1a5-130">Sì</span><span class="sxs-lookup"><span data-stu-id="9f1a5-130">Yes</span></span>  <br/> |
|<span data-ttu-id="9f1a5-131">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="9f1a5-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9f1a5-132">Prima versione per Deferred Channel rilasciata il 22 febbraio 2017 - versione 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="9f1a5-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="9f1a5-133">Sì</span><span class="sxs-lookup"><span data-stu-id="9f1a5-133">Yes</span></span>  <br/> |
|<span data-ttu-id="9f1a5-134">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="9f1a5-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="9f1a5-135">Deferred Channel rilasciato il 13 giugno 2017 - versione 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="9f1a5-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="9f1a5-136">Sì</span><span class="sxs-lookup"><span data-stu-id="9f1a5-136">Yes</span></span>  <br/> |
|<span data-ttu-id="9f1a5-137">MSI</span><span class="sxs-lookup"><span data-stu-id="9f1a5-137">MSI</span></span>  <br/> |<span data-ttu-id="9f1a5-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9f1a5-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="9f1a5-139">No</span><span class="sxs-lookup"><span data-stu-id="9f1a5-139">No</span></span>  <br/> |
|<span data-ttu-id="9f1a5-140">Mac</span><span class="sxs-lookup"><span data-stu-id="9f1a5-140">Mac</span></span>  <br/> |<span data-ttu-id="9f1a5-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9f1a5-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="9f1a5-142">No</span><span class="sxs-lookup"><span data-stu-id="9f1a5-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="9f1a5-143">ID chiamante in ingresso</span><span class="sxs-lookup"><span data-stu-id="9f1a5-143">Inbound Caller ID</span></span>

<span data-ttu-id="9f1a5-144">L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="9f1a5-145">Puoi impostare questo attributo, ma questo non è disponibile per gli utenti finali nella pagina Impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="9f1a5-146">Ed è attualmente disponibile solo con connettività PSTN in linea.</span><span class="sxs-lookup"><span data-stu-id="9f1a5-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="9f1a5-147">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9f1a5-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9f1a5-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9f1a5-148">Related topics</span></span>
[<span data-ttu-id="9f1a5-149">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="9f1a5-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="9f1a5-150">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="9f1a5-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="9f1a5-151">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="9f1a5-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="9f1a5-152">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="9f1a5-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="9f1a5-153">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9f1a5-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 