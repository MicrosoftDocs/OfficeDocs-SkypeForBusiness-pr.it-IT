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
- ms.teamsadmincenter.voice.callerid.overview
description: L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224209"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="a75a6-103">Come usare l'ID chiamante nella tua organizzazione</span><span class="sxs-lookup"><span data-stu-id="a75a6-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="a75a6-104">L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="a75a6-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="a75a6-105">La funzionalità ID chiamante è disponibile per tutti gli utenti del sistema telefonico indipendentemente dalla connettività PSTN:</span><span class="sxs-lookup"><span data-stu-id="a75a6-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="a75a6-106">Connettività PSTN in linea</span><span class="sxs-lookup"><span data-stu-id="a75a6-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="a75a6-107">Connettività PSTN locale con Skype for Businesss Cloud Connector Edition (richiede Cloud Connector Edition 1.4.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a75a6-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="a75a6-108">Connettività PSTN locale con Skype for Businesss Server (richiede Skype for Businesss Server 2015 CU5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="a75a6-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="a75a6-109">Questo criterio non è disponibile in Skype for Businesss 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="a75a6-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="a75a6-110">ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="a75a6-110">Outbound caller ID</span></span>

<span data-ttu-id="a75a6-111">Sono disponibili tre opzioni per l'ID chiamante PSTN in uscita:</span><span class="sxs-lookup"><span data-stu-id="a75a6-111">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="a75a6-112">Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a75a6-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="a75a6-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="a75a6-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="a75a6-115">Impostato su anonimo.</span><span class="sxs-lookup"><span data-stu-id="a75a6-115">Set to anonymous.</span></span>
    
<span data-ttu-id="a75a6-116">Tuttavia, non è possibile assegnare questi tipi di numeri di telefono per l'ID chiamante in uscita:</span><span class="sxs-lookup"><span data-stu-id="a75a6-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="a75a6-117">I numeri di telefono classificati come *utente* nella rubrica telefonica dei tuoi Piani chiamata</span><span class="sxs-lookup"><span data-stu-id="a75a6-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="a75a6-118">Un numero di telefono Skype for Businesss Server locale</span><span class="sxs-lookup"><span data-stu-id="a75a6-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="a75a6-119">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="a75a6-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="a75a6-120">Controllo utente finale dell'ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="a75a6-120">End user control of outbound caller ID</span></span>

<span data-ttu-id="a75a6-p102">L'attributo EnableUserOverride consente a singoli o più utenti di modificare l'impostazione dell'ID chiamante in **Anonymous**. Questo problema si applica solo quando un criterio CallingLineIdentity è configurato con un parametro CallingIDSubstitute di LineURI o sostituto. Il valore predefinito di EnableUserOverride è false.</span><span class="sxs-lookup"><span data-stu-id="a75a6-p102">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="a75a6-124">Gli utenti finali possono impostare l'ID chiamante su **Anonimo** usando la scheda **Impostazioni** nel client desktop Skype for business, selezionare **chiama un utente finale** (se abilitato dall'amministratore) e quindi selezionare **Nascondi il numero di telefono e le informazioni del profilo per tutte le chiamate**.</span><span class="sxs-lookup"><span data-stu-id="a75a6-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="a75a6-125">In teams gli utenti possono accedere all'immagine del profilo nell'angolo in alto a destra, selezionare **le**  >  **chiamate**di impostazioni e quindi in **ID chiamante**selezionare **Nascondi il numero di telefono e le informazioni del profilo per tutte le chiamate**.</span><span class="sxs-lookup"><span data-stu-id="a75a6-125">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a75a6-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="a75a6-126">**Windows**</span></span> <br/> |<span data-ttu-id="a75a6-127">**Versione**</span><span class="sxs-lookup"><span data-stu-id="a75a6-127">**Version**</span></span> <br/> |<span data-ttu-id="a75a6-128">**Supportati**</span><span class="sxs-lookup"><span data-stu-id="a75a6-128">**Supported**</span></span> <br/> |
|<span data-ttu-id="a75a6-129">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="a75a6-129">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a75a6-130">Current Channel rilasciato il 6 dicembre 2016 - versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="a75a6-130">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="a75a6-131">Sì</span><span class="sxs-lookup"><span data-stu-id="a75a6-131">Yes</span></span>  <br/> |
|<span data-ttu-id="a75a6-132">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="a75a6-132">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a75a6-133">Prima versione per Deferred Channel rilasciata il 22 febbraio 2017 - versione 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="a75a6-133">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="a75a6-134">Sì</span><span class="sxs-lookup"><span data-stu-id="a75a6-134">Yes</span></span>  <br/> |
|<span data-ttu-id="a75a6-135">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="a75a6-135">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a75a6-136">Deferred Channel rilasciato il 13 giugno 2017 - versione 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="a75a6-136">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="a75a6-137">Sì</span><span class="sxs-lookup"><span data-stu-id="a75a6-137">Yes</span></span>  <br/> |
|<span data-ttu-id="a75a6-138">MSI</span><span class="sxs-lookup"><span data-stu-id="a75a6-138">MSI</span></span>  <br/> |<span data-ttu-id="a75a6-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a75a6-139">Skype for Business</span></span>  <br/> |<span data-ttu-id="a75a6-140">No</span><span class="sxs-lookup"><span data-stu-id="a75a6-140">No</span></span>  <br/> |
|<span data-ttu-id="a75a6-141">Mac</span><span class="sxs-lookup"><span data-stu-id="a75a6-141">Mac</span></span>  <br/> |<span data-ttu-id="a75a6-142">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a75a6-142">Skype for Business</span></span>  <br/> |<span data-ttu-id="a75a6-143">No</span><span class="sxs-lookup"><span data-stu-id="a75a6-143">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="a75a6-144">ID chiamante in ingresso</span><span class="sxs-lookup"><span data-stu-id="a75a6-144">Inbound caller ID</span></span>

<span data-ttu-id="a75a6-145">Il sistema telefonico mostrerà l'ID denominato per un numero di telefono esterno se il numero è associato a un utente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a75a6-145">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="a75a6-146">Se il numero di telefono non è in Azure AD, verrà visualizzato il nome visualizzato di Telco, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="a75a6-146">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="a75a6-147">L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="a75a6-147">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="a75a6-148">Puoi impostare questo attributo, ma questo non è disponibile per gli utenti finali nella pagina Impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="a75a6-148">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="a75a6-149">Ed è attualmente disponibile solo con connettività PSTN in linea.</span><span class="sxs-lookup"><span data-stu-id="a75a6-149">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="a75a6-150">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="a75a6-150">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a75a6-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a75a6-151">Related topics</span></span>
[<span data-ttu-id="a75a6-152">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="a75a6-152">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="a75a6-153">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="a75a6-153">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="a75a6-154">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="a75a6-154">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a75a6-155">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="a75a6-155">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a75a6-156">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a75a6-156">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
