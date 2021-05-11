---
title: Come usare l'ID chiamante nella tua organizzazione
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
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
ms.openlocfilehash: 2a104679be84dfdaa4574353ccc79142d8a82284
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308345"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="d9f8b-103">Come usare l'ID chiamante nella tua organizzazione</span><span class="sxs-lookup"><span data-stu-id="d9f8b-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="d9f8b-104">L'ID chiamante è costituito da due informazioni identificabili dall'utente:</span><span class="sxs-lookup"><span data-stu-id="d9f8b-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="d9f8b-105">Un numero di telefono (in genere definito CLID o ID della linea telefonica).</span><span class="sxs-lookup"><span data-stu-id="d9f8b-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="d9f8b-106">Si tratta del numero pstn (Public Switched Telephone Number) presentato come identificativo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="d9f8b-107">Nome di una parte chiamante(in genere denominata CNAM).</span><span class="sxs-lookup"><span data-stu-id="d9f8b-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="d9f8b-108">La funzionalità ID chiamante è disponibile per tutti Sistema telefonico utenti indipendentemente dall'opzione di connettività PSTN:</span><span class="sxs-lookup"><span data-stu-id="d9f8b-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="d9f8b-109">Piani per chiamate Microsoft</span><span class="sxs-lookup"><span data-stu-id="d9f8b-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="d9f8b-110">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="d9f8b-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="d9f8b-111">È possibile controllare l'ID chiamante per le chiamate in ingresso e in uscita usando un criterio denominato CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="d9f8b-112">Per altre informazioni, vedere [Altre informazioni su ID linea chiamante e Nome della parte chiamante.](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="d9f8b-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="d9f8b-113">ID chiamante PSTN in uscita</span><span class="sxs-lookup"><span data-stu-id="d9f8b-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="d9f8b-114">Per l'ID chiamante PSTN in uscita, sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-114">For the outbound PSTN caller ID, the following options are available.</span></span> 

> [!NOTE]
> <span data-ttu-id="d9f8b-115">Alcune opzioni, indicate di seguito, sono disponibili nella versione di anteprima.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-115">Some options, indicated below, are in preview release.</span></span>
  
- <span data-ttu-id="d9f8b-116">Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-116">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="d9f8b-117">Anonimo, che è disponibile rimuovendo la presentazione del numero PSTN dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-117">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="d9f8b-118">Un numero di telefono sostitutivo, che può essere:</span><span class="sxs-lookup"><span data-stu-id="d9f8b-118">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="d9f8b-119">Numero di telefono classificato come servizio e numero verde nell'inventario dei numeri di telefono dei Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-119">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="d9f8b-120">In genere viene assegnato a una Teams Operatore automatico o coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-120">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="d9f8b-121">**Versione di anteprima.**</span><span class="sxs-lookup"><span data-stu-id="d9f8b-121">**Preview release.**</span></span> <span data-ttu-id="d9f8b-122">Numero di telefono locale tramite Routing diretto assegnato a un account di risorsa usato da un Teams Operatore automatico o coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-122">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="d9f8b-123">**Versione di anteprima.**</span><span class="sxs-lookup"><span data-stu-id="d9f8b-123">**Preview release.**</span></span> <span data-ttu-id="d9f8b-124">Nome della parte chiamante o CNAM impostato sulla chiamata PSTN in uscita.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-124">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="d9f8b-125">Per altre informazioni, vedere [Impostare l'ID chiamante per un utente.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="d9f8b-125">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="d9f8b-126">Controllo utente finale dell'ID chiamante in uscita</span><span class="sxs-lookup"><span data-stu-id="d9f8b-126">End user control of outbound caller ID</span></span>

<span data-ttu-id="d9f8b-127">Gli utenti possono modificare l'impostazione dell'ID chiamante **su Anonimo** impostando l'attributo EnableUserOverride.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-127">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="d9f8b-128">Se l'ID chiamante in uscita è impostato su Anonimo, EnableUserOverride non ha alcun effetto e l'ID chiamante è sempre impostato su Anonimo.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-128">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="d9f8b-129">Il valore predefinito di EnableUserOverride è False.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-129">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="d9f8b-130">Gli utenti finali possono impostare l'ID chiamante su Anonimo selezionando **Impostazioni > Chiamate** e quindi in **ID** chiamante selezionare Nascondi il numero di telefono e le informazioni del profilo per tutte **le chiamate.**</span><span class="sxs-lookup"><span data-stu-id="d9f8b-130">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="d9f8b-131">Note</span><span class="sxs-lookup"><span data-stu-id="d9f8b-131">Notes</span></span>

<span data-ttu-id="d9f8b-132">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d9f8b-132">Keep the following in mind:</span></span>

- <span data-ttu-id="d9f8b-133">Non è possibile assegnare i tipi di numeri di telefono seguenti per l'ID chiamante in uscita:</span><span class="sxs-lookup"><span data-stu-id="d9f8b-133">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="d9f8b-134">Tutti i numeri di telefono classificati come utente nell'inventario dei numeri di telefono dei Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-134">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="d9f8b-135">Qualsiasi numero di telefono locale tramite Routing diretto assegnato a un utente.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-135">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="d9f8b-136">Un Skype for Business Server di telefono locale.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-136">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="d9f8b-137">L'uso della sostituzione del numero di telefono dell'account della risorsa funziona solo per Teams utenti.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-137">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="d9f8b-138">La sostituzione del numero di telefono del servizio funziona sia per Skype for Business online che per Teams utenti.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-138">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="d9f8b-139">Il nome della parte chiamante viene inviato solo sulle chiamate in cui l'ID chiamante viene sostituito con LineUri, un numero di telefono dell'account di servizio o della risorsa e quando il chiamante è un Teams utente.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-139">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="d9f8b-140">Nome parte chiamante può contenere un massimo di 200 caratteri, ma i sistemi a valle potrebbero supportare un numero inferiore di caratteri.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-140">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="d9f8b-141">Per l'instradamento diretto, la sostituzione del numero di telefono e il nome della parte chiamante vengono inviati nell'intestazione SIP FROM.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-141">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="d9f8b-142">Se il corrispondente OnlinePstnGateway è configurato con ForwardPai = True, l'intestazione SIP P-ASSERTED-IDENTITY conterrà l'utente chiamante reale.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-142">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="d9f8b-143">EnableUserOverride ha la precedenza sulle altre impostazioni del criterio, a meno che la sostituzione non sia impostata su Anonimo.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-143">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="d9f8b-144">Si supponga, ad esempio, che l'istanza dei criteri abbia la sostituzione con un account di risorsa e che EnableUserOverride sia impostato e abilitato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-144">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="d9f8b-145">In questo caso, l'ID chiamante in uscita verrà bloccato e verrà usato Anonimo.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-145">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="d9f8b-146">Se un'istanza dei criteri ha la sostituzione impostata su Anonimo e EnableUserOverride è impostato, l'ID chiamante in uscita sarà sempre Anonimo, indipendentemente dall'impostazione dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-146">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="d9f8b-147">ID chiamante in ingresso</span><span class="sxs-lookup"><span data-stu-id="d9f8b-147">Inbound caller ID</span></span>

<span data-ttu-id="d9f8b-148">Sistema telefonico il numero di telefono esterno in arrivo come ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-148">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="d9f8b-149">Se il numero è associato a un utente o un contatto in Azure AD o a un contatto personale, i client Skype for Business e Teams mostreranno l'ID chiamante in base a queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-149">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="d9f8b-150">Se il numero di telefono non si trova in Azure AD o in un contatto personale, se disponibile verrà visualizzato il nome visualizzato fornito da telco.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-150">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="d9f8b-151">L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-151">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="d9f8b-152">Puoi impostare questo attributo, ma questo non è disponibile per gli utenti finali nella pagina Impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-152">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="d9f8b-153">Quando questa impostazione è abilitata, il chiamante PSTN in arrivo verrà visualizzato come proveniente da Anonimo.</span><span class="sxs-lookup"><span data-stu-id="d9f8b-153">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="d9f8b-154">Per bloccare l'ID chiamante in ingresso, vedere [Impostare l'ID chiamante per un utente.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="d9f8b-154">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d9f8b-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d9f8b-155">Related topics</span></span>
[<span data-ttu-id="d9f8b-156">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="d9f8b-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="d9f8b-157">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="d9f8b-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="d9f8b-158">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="d9f8b-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d9f8b-159">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="d9f8b-159">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="d9f8b-160">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d9f8b-160">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
