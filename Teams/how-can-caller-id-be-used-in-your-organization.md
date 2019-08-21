---
title: Come usare l'ID chiamante nella tua organizzazione
author: CarolynRowe
ms.author: crowe
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.callerid.overview
ms.custom:
- Calling Plans
description: L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
ms.openlocfilehash: 31948a8361d8ae5a15ce84549d982d0c7f9adf1b
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484038"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="a4030-103">Come usare l'ID chiamante nella tua organizzazione</span><span class="sxs-lookup"><span data-stu-id="a4030-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="a4030-104">L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="a4030-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="a4030-105">La funzionalità ID chiamante è disponibile per tutti gli utenti di Sistema telefonico indipendentemente dalla connettività PSTN:</span><span class="sxs-lookup"><span data-stu-id="a4030-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="a4030-106">Connettività PSTN in linea</span><span class="sxs-lookup"><span data-stu-id="a4030-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="a4030-107">Connettività PSTN locale con Skype for Businesss Cloud Connector Edition (richiede Cloud Connector Edition 1.4.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a4030-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="a4030-108">Connettività PSTN locale con Skype for Businesss Server (richiede Skype for Businesss Server 2015 CU5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a4030-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="a4030-109">Questo criterio non è disponibile in Skype for Businesss 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="a4030-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="a4030-110">ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="a4030-110">Outbound caller ID</span></span>

<span data-ttu-id="a4030-111">Sono disponibili tre opzioni per l'ID chiamante PSTN in uscita:</span><span class="sxs-lookup"><span data-stu-id="a4030-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="a4030-112">Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a4030-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="a4030-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="a4030-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="a4030-115">Impostato su anonimo.</span><span class="sxs-lookup"><span data-stu-id="a4030-115">Set to anonymous.</span></span>
    
<span data-ttu-id="a4030-116">Tuttavia, non è possibile assegnare questi tipi di numeri di telefono per l'ID chiamante in uscita:</span><span class="sxs-lookup"><span data-stu-id="a4030-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="a4030-117">I numeri di telefono classificati come *utente* nella rubrica telefonica dei tuoi Piani chiamata</span><span class="sxs-lookup"><span data-stu-id="a4030-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="a4030-118">Un numero di telefono Skype for Businesss Server locale</span><span class="sxs-lookup"><span data-stu-id="a4030-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="a4030-119">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="a4030-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="a4030-120">Controllo degli utenti finali dell'ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="a4030-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="a4030-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="a4030-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="a4030-124">Gli utenti finali possono impostare l'ID chiamante su **Anonimo** usando la scheda **Impostazioni** nel client desktop Skype for business, selezionare **chiama un utente finale** (se abilitato dall'amministratore), selezionare Nascondi il \*\*numero di telefono e le informazioni del profilo per tutte le chiamate \*\*.</span><span class="sxs-lookup"><span data-stu-id="a4030-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a4030-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="a4030-125">**Windows**</span></span> <br/> |<span data-ttu-id="a4030-126">**Versione**</span><span class="sxs-lookup"><span data-stu-id="a4030-126">**Version**</span></span> <br/> |<span data-ttu-id="a4030-127">**Supportati**</span><span class="sxs-lookup"><span data-stu-id="a4030-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="a4030-128">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="a4030-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a4030-129">Current Channel rilasciato il 6 dicembre 2016 - versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="a4030-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="a4030-130">Sì</span><span class="sxs-lookup"><span data-stu-id="a4030-130">Yes</span></span>  <br/> |
|<span data-ttu-id="a4030-131">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="a4030-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a4030-132">Prima versione per Deferred Channel rilasciata il 22 febbraio 2017 - versione 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="a4030-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="a4030-133">Sì</span><span class="sxs-lookup"><span data-stu-id="a4030-133">Yes</span></span>  <br/> |
|<span data-ttu-id="a4030-134">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="a4030-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a4030-135">Deferred Channel rilasciato il 13 giugno 2017 - versione 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="a4030-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="a4030-136">Sì</span><span class="sxs-lookup"><span data-stu-id="a4030-136">Yes</span></span>  <br/> |
|<span data-ttu-id="a4030-137">MSI</span><span class="sxs-lookup"><span data-stu-id="a4030-137">MSI</span></span>  <br/> |<span data-ttu-id="a4030-138">Skype for business</span><span class="sxs-lookup"><span data-stu-id="a4030-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="a4030-139">No</span><span class="sxs-lookup"><span data-stu-id="a4030-139">No</span></span>  <br/> |
|<span data-ttu-id="a4030-140">Mac</span><span class="sxs-lookup"><span data-stu-id="a4030-140">Mac</span></span>  <br/> |<span data-ttu-id="a4030-141">Skype for business</span><span class="sxs-lookup"><span data-stu-id="a4030-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="a4030-142">No</span><span class="sxs-lookup"><span data-stu-id="a4030-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="a4030-143">ID chiamante in ingresso</span><span class="sxs-lookup"><span data-stu-id="a4030-143">Inbound Caller ID</span></span>

<span data-ttu-id="a4030-p103">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.</span><span class="sxs-lookup"><span data-stu-id="a4030-p103">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="a4030-147">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="a4030-147">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a4030-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a4030-148">Related topics</span></span>
[<span data-ttu-id="a4030-149">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="a4030-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="a4030-150">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="a4030-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="a4030-151">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="a4030-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a4030-152">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="a4030-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a4030-153">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a4030-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
