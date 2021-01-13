---
title: Servizi di conferenza audio con routing diretto, GCCH e DoD
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: L'amministratore può trovare informazioni su come usare i servizi di audioconferenza con routing diretto in ambienti GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 818b36e379532e361fd3991b002bc899156af056
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812916"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="94c96-103">Audioconferenza con Instradamento diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="94c96-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="94c96-104">I servizi di audioconferenza con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare a riunioni di teams nell'organizzazione GCC High o DoD usando un dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="94c96-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="94c96-105">I partecipanti alla riunione possono preferire l'uso di un dispositivo telefonico per partecipare a riunioni di team in scenari come la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso ai team.</span><span class="sxs-lookup"><span data-stu-id="94c96-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="94c96-106">I partecipanti possono scegliere di partecipare alle riunioni effettuando la chiamata in un numero di telefono di accesso esterno per l'organizzazione oppure effettuando la chiamata della riunione al dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="94c96-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="94c96-107">Con i servizi di audioconferenza con routing diretto per GCC High e DoD, l'organizzazione usa i propri numeri come numeri di telefono di accesso esterno e tutti i dial-out per le riunioni vengono instradati tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="94c96-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="94c96-108">Per abilitare il servizio, le organizzazioni devono impostare il routing diretto e configurare i numeri di telefono che possono essere usati come numeri di telefono di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="94c96-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="94c96-109">Il requisito di usare il routing diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non-GCC High e non-DoD in cui i numeri di telefono di accesso esterno sono forniti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94c96-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="94c96-110">Distribuire servizi di audioconferenza con routing diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="94c96-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="94c96-111">Passaggio 1: ottenere servizi di audioconferenza con routing diretto per le licenze GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="94c96-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="94c96-112">Per usare le conferenze audio in GCC High o DoD, l'organizzazione e gli utenti dell'organizzazione devono avere un servizio di audioconferenza con licenza di routing diretta assegnata.</span><span class="sxs-lookup"><span data-stu-id="94c96-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="94c96-113">Ecco le licenze necessarie per abilitare i servizi di audioconferenza con routing diretto per GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="94c96-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="94c96-114">GCC High: una licenza per i servizi di audioconferenza per l'organizzazione e l'audioconferenza-licenze GCC High per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="94c96-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="94c96-115">DoD: una licenza per i servizi di audioconferenza-DoD tenant per l'organizzazione e le licenze per i servizi di audioconferenza per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="94c96-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="94c96-116">Per abilitare il servizio, è necessaria una licenza tenant e almeno una licenza per l'utente.</span><span class="sxs-lookup"><span data-stu-id="94c96-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="94c96-117">Non è possibile abilitare il servizio con solo la licenza tenant o solo con le licenze utente.</span><span class="sxs-lookup"><span data-stu-id="94c96-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="94c96-118">Per ottenere le licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team dell'account.</span><span class="sxs-lookup"><span data-stu-id="94c96-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94c96-119">Gli utenti non possono essere abilitati per i servizi di audioconferenza con routing diretto fino alla configurazione dei numeri di telefono di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="94c96-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="94c96-120">È consigliabile non assegnare servizi di audioconferenza con routing diretto per le licenze GCC High o DoD agli utenti fino a quando non si configurano i numeri di telefono con accesso esterno come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="94c96-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="94c96-121">Passaggio 2: configurare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="94c96-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="94c96-122">Per configurare il routing diretto, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="94c96-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="94c96-123">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="94c96-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="94c96-124">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="94c96-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="94c96-125">Quando configuri il routing diretto, ricordati di usare gli FQDN e le porte di dominio elevato o specifico del DoD che sono descritti in questi due articoli.</span><span class="sxs-lookup"><span data-stu-id="94c96-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="94c96-126">Passaggio 3: configurare i numeri di telefono con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="94c96-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="94c96-127">I numeri di telefono di accesso esterno sono i numeri di telefono associati al Bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="94c96-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="94c96-128">Questi numeri vengono usati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94c96-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="94c96-129">Questi numeri sono inclusi anche negli inviti alla riunione degli utenti che pianificano le riunioni nell'organizzazione e nella pagina "trova un numero locale".</span><span class="sxs-lookup"><span data-stu-id="94c96-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="94c96-130">Definire i numeri di telefono del servizio nel tenant</span><span class="sxs-lookup"><span data-stu-id="94c96-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="94c96-131">Puoi usare il cmdlet di PowerShell New-csHybridTelephoneNumber per definire i numeri di telefono del servizio nel tenant che possono essere usati per instradare le chiamate al servizio di audioconferenza tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="94c96-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="94c96-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="94c96-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="94c96-133">Assegnare i numeri di telefono del servizio al Bridge di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="94c96-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="94c96-134">È possibile assegnare numeri di telefono del servizio al Bridge di audioconferenza dell'organizzazione usando il cmdlet Register-csOnlineDialInConferencingServiceNumber di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94c96-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="94c96-135">Puoi vedere l'ID del Bridge di audioconferenza usando Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="94c96-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="94c96-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="94c96-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="94c96-137">Passaggio 4: definire un criterio di routing vocale globale per consentire il routing delle chiamate in uscita dalle riunioni</span><span class="sxs-lookup"><span data-stu-id="94c96-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="94c96-138">Il routing delle chiamate in uscita effettuate alla rete PSTN da riunioni organizzate dagli utenti dell'organizzazione è definito dal criterio di routing vocale globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94c96-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="94c96-139">Se l'organizzazione ha un criterio di routing vocale globale definito, verificare che i criteri di routing vocale globale consentano alle chiamate in uscita alla rete PSTN che dovrebbero essere avviate da riunioni organizzate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94c96-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="94c96-140">Se l'organizzazione non ha un criterio di routing vocale globale definito, sarà necessario definirne uno per consentire il routing delle chiamate in uscita alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94c96-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="94c96-141">Tieni presente che il criterio di routing vocale globale dell'organizzazione si applica anche alle chiamate uno-a-uno effettuate alla rete PSTN dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94c96-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="94c96-142">Se le chiamate uno-a-uno alla rete PSTN sono abilitate per gli utenti dell'organizzazione, verificare che il criterio di routing vocale globale soddisfi le esigenze dell'organizzazione per entrambi i tipi di chiamate.</span><span class="sxs-lookup"><span data-stu-id="94c96-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="94c96-143">Location-Based routing non è disponibile nelle distribuzioni di Microsoft 365 Government community Cloud (GCC) High o DoD.</span><span class="sxs-lookup"><span data-stu-id="94c96-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="94c96-144">Quando si Abilita la conferenza audio, verificare che non siano abilitati utenti di servizi di audioconferenza nell'ambiente GCC High o DoD per Location-Based routing.</span><span class="sxs-lookup"><span data-stu-id="94c96-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="94c96-145">Definizione di un criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="94c96-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="94c96-146">Un criterio di routing vocale globale può essere definito definendo un uso PSTN, una route vocale, un criterio di routing vocale e assegnando i nuovi criteri di routing vocale come criterio di routing vocale globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94c96-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="94c96-147">I passaggi seguenti descrivono come definire un nuovo criterio di routing vocale globale per un'organizzazione senza una.</span><span class="sxs-lookup"><span data-stu-id="94c96-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="94c96-148">Se l'organizzazione dispone già di criteri di routing vocale definiti, verificare che la configurazione seguente non sia in conflitto con i criteri di routing vocale esistenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94c96-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="94c96-149">Per creare un nuovo utilizzo PSTN in una sessione remota di PowerShell in Skype for business online, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="94c96-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="94c96-150">Per altre informazioni, vedere [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span><span class="sxs-lookup"><span data-stu-id="94c96-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="94c96-151">Per creare una nuova route vocale, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="94c96-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="94c96-152">Quando si definisce una nuova route vocale per l'organizzazione, specificare uno o più gateway PSTN online PSTN definiti per l'organizzazione durante la configurazione del routing diretto.</span><span class="sxs-lookup"><span data-stu-id="94c96-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="94c96-153">Il modello di numero specifica le chiamate che verranno instradate tramite l'elenco di gateway specificato in base al numero di telefono di destinazione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="94c96-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="94c96-154">Nell'esempio precedente le chiamate a qualsiasi destinazione nel mondo corrisponderanno alla route vocale.</span><span class="sxs-lookup"><span data-stu-id="94c96-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="94c96-155">Per limitare i numeri di telefono che possono essere comunicati dalle riunioni degli utenti dell'organizzazione, è possibile modificare il modello di numero in modo che la route vocale corrisponda solo agli schemi di numero delle destinazioni consentite.</span><span class="sxs-lookup"><span data-stu-id="94c96-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="94c96-156">Tieni presente che se non ci sono route vocali che corrispondono al modello numerico del numero di telefono di destinazione di una determinata chiamata, la chiamata non verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="94c96-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="94c96-157">Per altre informazioni, vedere [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span><span class="sxs-lookup"><span data-stu-id="94c96-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="94c96-158">Per creare un nuovo criterio di routing vocale, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="94c96-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="94c96-159">Se nel criterio di routing vocale vengono definiti più usi PSTN, questi verranno valutati nell'ordine in cui sono definiti.</span><span class="sxs-lookup"><span data-stu-id="94c96-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="94c96-160">È consigliabile che gli usi PSTN siano definiti nell'ordine più specifico per il più generico in termini di pattern di numero delle route vocali associate agli usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="94c96-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="94c96-161">Ad esempio, se è stato definito un uso PSTN per instradare le chiamate agli Stati Uniti e un altro utilizzo PSTN è stato definito per instradare le chiamate a qualsiasi altra posizione nel mondo, l'utilizzo PSTN per le chiamate agli Stati Uniti deve essere elencato nei criteri di routing vocale prima dell'uso PSTN per instradare le chiamate a qualsiasi altra posizione nel mondo.</span><span class="sxs-lookup"><span data-stu-id="94c96-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="94c96-162">Per altre informazioni, vedere [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="94c96-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="94c96-163">Per assegnare la nuova route vocale al criterio di routing vocale globale dell'organizzazione, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="94c96-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="94c96-164">Per altre informazioni, vedere [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="94c96-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="94c96-165">Una volta definiti i criteri di routing vocale globale, le chiamate in uscita effettuate dalle riunioni organizzate dagli utenti dell'organizzazione verranno valutate in base alle route vocali associate agli usi PSTN del criterio di routing vocale globale.</span><span class="sxs-lookup"><span data-stu-id="94c96-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="94c96-166">Le chiamate in uscita verranno instradate in base alla prima route vocale che corrisponde al modello numerico del numero di telefono chiamato.</span><span class="sxs-lookup"><span data-stu-id="94c96-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="94c96-167">Passaggio 5: assegnare servizi di audioconferenza con routing diretto per le licenze GCC High o DoD agli utenti</span><span class="sxs-lookup"><span data-stu-id="94c96-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="94c96-168">Per assegnare i servizi di audioconferenza con routing diretto per le licenze GCC High o DoD all'utente, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="94c96-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="94c96-169">Passaggio 6: (facoltativo) visualizzare un elenco di numeri di conferenza audio in teams</span><span class="sxs-lookup"><span data-stu-id="94c96-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="94c96-170">Per visualizzare l'elenco dei numeri di servizi di audioconferenza dell'organizzazione, [vedere un elenco di numeri di conferenza audio in Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="94c96-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="94c96-171">Passaggio 7: (facoltativo) impostare le lingue per gli operatori automatici per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="94c96-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="94c96-172">Per modificare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, vedere [impostare le lingue per l'operatore automatico per i servizi di audioconferenza in Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="94c96-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="94c96-173">Passaggio 8: (facoltativo) modificare le impostazioni del Bridge di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="94c96-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="94c96-174">Per modificare le impostazioni del Bridge di audioconferenza dell'organizzazione, vedere [modificare le impostazioni per un Bridge di audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="94c96-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="94c96-175">Passaggio 9: (facoltativo) impostare i numeri di telefono inclusi negli inviti alla riunione degli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="94c96-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="94c96-176">Per modificare il set di numeri di telefono inclusi negli inviti alla riunione degli utenti è la propria organizzazione, vedere [impostare i numeri di telefono inclusi negli inviti in Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="94c96-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="94c96-177">Funzionalità di conferenza audio non supportate in servizi di audioconferenza con routing diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="94c96-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="94c96-178">Di seguito sono riportate funzionalità di conferenza audio non supportate in servizi di audioconferenza con routing diretto per GCC High e DoD:</span><span class="sxs-lookup"><span data-stu-id="94c96-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="94c96-179">Notifiche di entrata e uscita tramite registrazione nomi.</span><span class="sxs-lookup"><span data-stu-id="94c96-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="94c96-180">Per i servizi di audioconferenza con routing diretto, le notifiche di entrata e uscita vengono riprodotte nella riunione come toni.</span><span class="sxs-lookup"><span data-stu-id="94c96-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="94c96-181">Criteri di restrizione delle chiamate in uscita per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="94c96-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="94c96-182">I controlli a livello utente per limitare le chiamate in uscita non sono applicabili alle chiamate di chiamata in uscita per le riunioni instradate tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="94c96-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="94c96-183">Disabilitare l'uso di numeri verdi per l'organizzatore di riunioni specifico.</span><span class="sxs-lookup"><span data-stu-id="94c96-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="94c96-184">I controlli a livello di utente per limitare l'uso di numeri verdi per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradate tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="94c96-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="94c96-185">Invio di messaggi di notifica agli utenti quando cambiano le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="94c96-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="94c96-186">I messaggi di notifica per i servizi di audioconferenza non sono supportati per le conferenze audio con routing diretto per GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="94c96-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
