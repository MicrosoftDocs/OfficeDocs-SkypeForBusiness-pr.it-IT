---
title: Come usare l'ID chiamante nella tua organizzazione
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: cd2074fec3027f1172b6ea681013f53994963cb5
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255449"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="30153-103">Come usare l'ID chiamante nella tua organizzazione</span><span class="sxs-lookup"><span data-stu-id="30153-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="30153-104">L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="30153-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="30153-105">La funzionalità ID chiamante è disponibile per tutti gli utenti del Sistema telefonico, indipendentemente dalla connettività PSTN:</span><span class="sxs-lookup"><span data-stu-id="30153-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="30153-106">Piani per chiamate Microsoft</span><span class="sxs-lookup"><span data-stu-id="30153-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="30153-107">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="30153-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="30153-108">Connettività PSTN in linea</span><span class="sxs-lookup"><span data-stu-id="30153-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="30153-109">Connettività PSTN locale con Skype for Businesss Cloud Connector Edition (richiede Cloud Connector Edition 1.4.2 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="30153-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="30153-110">Connettività PSTN locale con Skype for Businesss Server (richiede Skype for Businesss Server 2015 CU5 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="30153-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="30153-111">Questo criterio non è disponibile in Skype for Businesss 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="30153-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="30153-112">ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="30153-112">Outbound caller ID</span></span>

<span data-ttu-id="30153-113">Sono disponibili tre opzioni per l'ID chiamante PSTN in uscita:</span><span class="sxs-lookup"><span data-stu-id="30153-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="30153-114">Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30153-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="30153-115">Un numero di telefono classificato  come *servizio* e numero verde nell'inventario dei numeri di telefono dei Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="30153-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="30153-116">In genere assegnato a una coda di chiamata o operatore automatico dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30153-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="30153-117">Impostato su anonimo.</span><span class="sxs-lookup"><span data-stu-id="30153-117">Set to anonymous.</span></span>
    
<span data-ttu-id="30153-118">Tuttavia, non è possibile assegnare questi tipi di numeri di telefono per l'ID chiamante in uscita:</span><span class="sxs-lookup"><span data-stu-id="30153-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="30153-119">I numeri di telefono classificati come *utente* nella rubrica telefonica dei tuoi Piani chiamata</span><span class="sxs-lookup"><span data-stu-id="30153-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="30153-120">Un numero di telefono Skype for Businesss Server locale</span><span class="sxs-lookup"><span data-stu-id="30153-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="30153-121">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="30153-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="30153-122">Controllo dell'ID chiamante in uscita da parte dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="30153-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="30153-123">L'attributo EnableUserOverride consente a uno o più utenti di modificare l'impostazione dell'ID chiamante su **Anonimo.**</span><span class="sxs-lookup"><span data-stu-id="30153-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="30153-124">Ciò è valido solo quando viene configurato un criterio CallingLineIdentity con un parametro CallingIDSubstitute LineURI o sostituto.</span><span class="sxs-lookup"><span data-stu-id="30153-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="30153-125">Il valore predefinito di EnableUserOverride è False.</span><span class="sxs-lookup"><span data-stu-id="30153-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="30153-126">Gli utenti finali possono impostare  l'ID  chiamante su Anonimo utilizzando la scheda Impostazioni nel client desktop di Skype for Business, seleziona Chiama un utente finale **(se** abilitato dall'amministratore), quindi seleziona Nascondi il mio numero di telefono e le informazioni del profilo per tutte le **chiamate.**</span><span class="sxs-lookup"><span data-stu-id="30153-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="30153-127">In Teams, gli utenti possono accedere all'immagine del profilo nell'angolo in alto a destra, selezionare Impostazioni chiamate, quindi in ID chiamante selezionare Nascondi il mio numero di telefono e le informazioni del profilo per tutte le  >   **chiamate.** </span><span class="sxs-lookup"><span data-stu-id="30153-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="30153-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="30153-128">**Windows**</span></span> <br/> |<span data-ttu-id="30153-129">**Versione**</span><span class="sxs-lookup"><span data-stu-id="30153-129">**Version**</span></span> <br/> |<span data-ttu-id="30153-130">**Supportata**</span><span class="sxs-lookup"><span data-stu-id="30153-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="30153-131">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="30153-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="30153-132">Current Channel rilasciato il 6 dicembre 2016 - versione 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="30153-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="30153-133">Sì</span><span class="sxs-lookup"><span data-stu-id="30153-133">Yes</span></span>  <br/> |
|<span data-ttu-id="30153-134">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="30153-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="30153-135">Prima versione per Deferred Channel rilasciata il 22 febbraio 2017 - versione 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="30153-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="30153-136">Sì</span><span class="sxs-lookup"><span data-stu-id="30153-136">Yes</span></span>  <br/> |
|<span data-ttu-id="30153-137">A portata di clic</span><span class="sxs-lookup"><span data-stu-id="30153-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="30153-138">Deferred Channel rilasciato il 13 giugno 2017 - versione 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="30153-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="30153-139">Sì</span><span class="sxs-lookup"><span data-stu-id="30153-139">Yes</span></span>  <br/> |
|<span data-ttu-id="30153-140">MSI</span><span class="sxs-lookup"><span data-stu-id="30153-140">MSI</span></span>  <br/> |<span data-ttu-id="30153-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="30153-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="30153-142">No</span><span class="sxs-lookup"><span data-stu-id="30153-142">No</span></span>  <br/> |
|<span data-ttu-id="30153-143">Mac</span><span class="sxs-lookup"><span data-stu-id="30153-143">Mac</span></span>  <br/> |<span data-ttu-id="30153-144">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="30153-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="30153-145">No</span><span class="sxs-lookup"><span data-stu-id="30153-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="30153-146">ID chiamante in ingresso</span><span class="sxs-lookup"><span data-stu-id="30153-146">Inbound caller ID</span></span>

<span data-ttu-id="30153-147">Sistema telefonico mostrerà l'ID di un numero di telefono esterno se è associato a un utente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="30153-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="30153-148">Se il numero di telefono non è presente in Azure AD, verrà visualizzato il nome visualizzato fornito con telco, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="30153-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="30153-149">L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="30153-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="30153-150">Puoi impostare questo attributo, ma questo non è disponibile per gli utenti finali nella pagina Impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="30153-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="30153-151">Ed è attualmente disponibile solo con connettività PSTN in linea.</span><span class="sxs-lookup"><span data-stu-id="30153-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="30153-152">Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="30153-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="30153-153">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="30153-153">Related topics</span></span>
[<span data-ttu-id="30153-154">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="30153-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="30153-155">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="30153-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="30153-156">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="30153-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="30153-157">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="30153-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="30153-158">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="30153-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
