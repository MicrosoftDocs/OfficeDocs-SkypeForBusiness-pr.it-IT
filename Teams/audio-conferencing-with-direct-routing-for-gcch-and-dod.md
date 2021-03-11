---
title: Audioconferenza con instradamento diretto, MCCH e DoD
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
description: L'amministratore può imparare a usare le audioconferenze con il routing diretto in ambienti MCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 84f2789c6d4f4e9c5446ad39d6f2d50d842b92a6
ms.sourcegitcommit: 0a7c1f52484452f66f678b0feca1455bade4fcf3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50716932"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="fa496-103">Audioconferenza con Instradamento diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="fa496-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="fa496-104">Le audioconferenze con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare alle riunioni di Teams nell'organizzazione GCC High o DoD usando un dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="fa496-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="fa496-105">I partecipanti alla riunione potrebbero preferire usare un dispositivo telefonico per partecipare alle riunioni di Teams in scenari come quando la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso a Teams.</span><span class="sxs-lookup"><span data-stu-id="fa496-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="fa496-106">I partecipanti possono scegliere di partecipare alle riunioni componendo un numero di telefono per l'organizzazione o facendo in modo che la riunione sia chiamata in uscita al proprio dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="fa496-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="fa496-107">Con le audioconferenze con routing diretto per GCC High e DoD, l'organizzazione usa i propri numeri come numeri di telefono per l'accesso esterno e tutte le chiamate in uscita per le riunioni verso i dispositivi telefonici vengono instradati tramite l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="fa496-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="fa496-108">Per abilitare il servizio, le organizzazioni devono configurare l'instradamento diretto e configurare i numeri di telefono che possono essere utilizzati come numeri di telefono per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="fa496-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="fa496-109">Il requisito di usare l'instradamento diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non GCC High e non DoD in cui i numeri di telefono per l'accesso esterno sono forniti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa496-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="fa496-110">Distribuire le audioconferenze con l'instradamento diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="fa496-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="fa496-111">Passaggio 1: Ottenere l'audioconferenza con l'instradamento diretto per le licenze GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="fa496-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="fa496-112">Per utilizzare le audioconferenze in GCC High o DoD, è necessario che all'organizzazione e agli utenti dell'organizzazione sia assegnata una licenza per l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="fa496-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="fa496-113">Ecco le licenze necessarie per abilitare l'audioconferenza con l'instradamento diretto per GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="fa496-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="fa496-114">GCC High: un'audioconferenza - licenza GCC High Tenant per l'organizzazione e Audioconferenza - Licenze GCC High per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="fa496-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="fa496-115">DoD: una licenza Di conferenza - DoD Tenant per l'organizzazione e Audioconferenza - Licenze DoD per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="fa496-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="fa496-116">Per abilitare il servizio è necessaria una licenza tenant e almeno una licenza utente.</span><span class="sxs-lookup"><span data-stu-id="fa496-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="fa496-117">Non è possibile abilitare il servizio solo con la licenza tenant o solo con licenze utente.</span><span class="sxs-lookup"><span data-stu-id="fa496-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="fa496-118">Per ottenere licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team dell'account.</span><span class="sxs-lookup"><span data-stu-id="fa496-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa496-119">Gli utenti non possono essere abilitati per le audioconferenze con instradamento diretto finché non vengono impostati i numeri di telefono per l'accesso esterno e gli utenti non hanno una tastiera funzionante nel client di Teams.</span><span class="sxs-lookup"><span data-stu-id="fa496-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up and users have a working dial pad in their Teams client.</span></span> <span data-ttu-id="fa496-120">È consigliabile non assegnare agli utenti le audioconferenze con routing diretto per le licenze GCC High o DoD fino a quando non si configurano i numeri di telefono per l'accesso esterno, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="fa496-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="fa496-121">Passaggio 2: Configurare l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="fa496-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="fa496-122">Per configurare l'instradamento diretto, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa496-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="fa496-123">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="fa496-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="fa496-124">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="fa496-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="fa496-125">Quando si configura il routing diretto, ricordarsi di usare gli FQDN e le porte GCC High o DoD specifici, descritti in questi due articoli.</span><span class="sxs-lookup"><span data-stu-id="fa496-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="fa496-126">Passaggio 3: Configurare i numeri di telefono per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="fa496-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="fa496-127">I numeri di telefono per l'accesso esterno sono i numeri di telefono associati al bridge per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="fa496-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="fa496-128">Questi numeri vengono utilizzati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa496-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="fa496-129">Questi numeri sono inclusi anche negli inviti alle riunioni degli utenti che pianificano le riunioni nell'organizzazione e nella pagina "Trova un numero locale".</span><span class="sxs-lookup"><span data-stu-id="fa496-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="fa496-130">Definire i numeri di telefono di servizio nel tenant</span><span class="sxs-lookup"><span data-stu-id="fa496-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="fa496-131">Puoi usare il cmdlet PowerShell New-csHybridTelephoneNumber per definire i numeri di servizio del tuo tenant che possono essere usati per instradare le chiamate al servizio Audioconferenza tramite l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="fa496-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="fa496-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fa496-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="fa496-133">Assegnare i numeri di servizio al bridge per i servizi di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fa496-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="fa496-134">Puoi assegnare numeri di servizio al bridge di audioconferenza della tua organizzazione utilizzando il cmdlet di PowerShell Register-csOnlineDialInConferencingServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="fa496-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="fa496-135">Puoi visualizzare l'ID del bridge di audioconferenza utilizzando Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="fa496-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="fa496-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fa496-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="fa496-137">Passaggio 4: Definire un criterio di routing vocale globale per abilitare il routing delle chiamate in uscita dalle riunioni</span><span class="sxs-lookup"><span data-stu-id="fa496-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="fa496-138">Il routing delle chiamate in uscita effettuate alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione è definito dai criteri di routing vocale globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa496-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="fa496-139">Se la tua organizzazione ha definito un criterio di routing vocale globale, verifica che il criterio di routing vocale globale consenta le chiamate in uscita alla rete PSTN che dovrebbero essere avviate da riunioni organizzate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa496-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="fa496-140">Se l'organizzazione non ha definito un criterio di routing vocale globale, è necessario definirne uno per abilitare l'instradamento delle chiamate in uscita alla rete PSTN da riunioni organizzate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa496-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="fa496-141">I criteri di routing vocale globale dell'organizzazione si applicano anche alle chiamate uno-a-uno effettuate alla rete PSTN dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa496-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="fa496-142">Se le chiamate uno-a-uno alla rete PSTN sono abilitate per gli utenti dell'organizzazione, assicurati che il criterio di routing vocale globale soddisfi le esigenze dell'organizzazione per entrambi i tipi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa496-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa496-143">Location-Based routing delle chiamate non è disponibile nelle distribuzioni High o DoD di Microsoft 365 Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="fa496-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="fa496-144">Quando si abilitano le audioconferenze, verificare che gli utenti di Audioconferenza nell'ambiente GCC High o DoD non siano abilitati per il routing Location-Based audio.</span><span class="sxs-lookup"><span data-stu-id="fa496-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="fa496-145">Definizione di un criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="fa496-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="fa496-146">Un criterio di routing vocale globale può essere definito definendo l'utilizzo di PSTN, un percorso vocale, un criterio di routing vocale e assegnando il nuovo criterio di routing vocale come criterio di routing vocale globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa496-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="fa496-147">La procedura seguente descrive come definire un nuovo criterio di routing vocale globale per un'organizzazione senza criteri.</span><span class="sxs-lookup"><span data-stu-id="fa496-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="fa496-148">Se l'organizzazione ha già definito criteri di routing vocale, verificare che la configurazione seguente non sia in conflitto con i criteri di routing vocale esistenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa496-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="fa496-149">Per creare un nuovo utilizzo di PSTN in una sessione remota di PowerShell in Skype for Business online, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fa496-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="fa496-150">Per ulteriori informazioni, consulta [Set-CsOnlinePstnUsage.](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)</span><span class="sxs-lookup"><span data-stu-id="fa496-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="fa496-151">Per creare una nuova route vocale, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fa496-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="fa496-152">Quando si definisce una nuova route vocale per l'organizzazione, specificare uno o più gateway PSTN online PSTN definiti per l'organizzazione durante la configurazione del routing diretto.</span><span class="sxs-lookup"><span data-stu-id="fa496-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="fa496-153">Il modello di numero specifica quali chiamate verranno instradati attraverso l'elenco specificato di gateway in base al numero di telefono di destinazione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fa496-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="fa496-154">Nell'esempio precedente, le chiamate verso tutte le destinazioni nel mondo corrisponderanno al percorso vocale.</span><span class="sxs-lookup"><span data-stu-id="fa496-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="fa496-155">Se si desidera limitare i numeri di telefono che è possibile comporre dalle riunioni degli utenti dell'organizzazione, è possibile modificare il modello di numero in modo che il percorso vocale corrisponda solo ai modelli di numero delle destinazioni consentite.</span><span class="sxs-lookup"><span data-stu-id="fa496-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="fa496-156">Tenere presente che se non sono presenti percorsi vocali che corrispondono al modello di numero del numero di telefono di destinazione di una determinata chiamata, la chiamata non verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="fa496-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="fa496-157">Per ulteriori informazioni, consulta [New-CsOnlineVoiceRoute.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)</span><span class="sxs-lookup"><span data-stu-id="fa496-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="fa496-158">Per creare un nuovo criterio di routing vocale, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fa496-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="fa496-159">Se nel criterio di routing vocale vengono definiti più utilizzi di PSTN, questi vengono valutati nell'ordine in cui sono stati definiti.</span><span class="sxs-lookup"><span data-stu-id="fa496-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="fa496-160">È consigliabile che gli utilizzi di PSTN siano definiti nell'ordine dei più specifici per i più generici in termini di modelli numerici delle route vocali associate agli utilizzi PSTN.</span><span class="sxs-lookup"><span data-stu-id="fa496-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="fa496-161">Ad esempio, se un utilizzo PSTN è stato definito per instradare le chiamate verso gli Stati Uniti e un altro utilizzo PSTN è stato definito per instradare le chiamate a qualsiasi altra località del mondo, l'utilizzo di PSTN per le chiamate verso gli Stati Uniti dovrebbe essere elencato nei criteri di routing vocale in anticipo rispetto all'utilizzo di PSTN per instradare le chiamate verso qualsiasi altra località del mondo.</span><span class="sxs-lookup"><span data-stu-id="fa496-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="fa496-162">Per ulteriori informazioni, consulta [New-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="fa496-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="fa496-163">Per assegnare il nuovo percorso vocale al criterio di routing vocale globale dell'organizzazione, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fa496-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="fa496-164">Per ulteriori informazioni, consulta [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="fa496-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="fa496-165">Una volta definito il criterio di routing vocale globale, le chiamate in uscita effettuate dalle riunioni organizzate dagli utenti dell'organizzazione verranno valutate rispetto ai percorsi vocali associati agli utilizzi PSTN del criterio di routing vocale globale.</span><span class="sxs-lookup"><span data-stu-id="fa496-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="fa496-166">Le chiamate in uscita verranno instradate in base al primo percorso vocale che corrisponde al modello di numero del numero di telefono composto.</span><span class="sxs-lookup"><span data-stu-id="fa496-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="fa496-167">Passaggio 5: Assegnare audioconferenze con routing diretto per le licenze GCC High o DoD agli utenti</span><span class="sxs-lookup"><span data-stu-id="fa496-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="fa496-168">Per assegnare le audioconferenze con routing diretto per le licenze GCC High o DoD all'utente, vedi Assegnare [licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="fa496-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="fa496-169">Passaggio 6: (facoltativo) Visualizzare un elenco di numeri per i servizi di audioconferenza in Teams</span><span class="sxs-lookup"><span data-stu-id="fa496-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="fa496-170">Per visualizzare l'elenco dei numeri dei servizi di audioconferenza dell'organizzazione, vedere l'elenco dei numeri dei servizi di [audioconferenza in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="fa496-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="fa496-171">Passaggio 7: (Facoltativo) Impostare le lingue dell'operatore automatico per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fa496-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="fa496-172">Per cambiare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, consulta Impostare le lingue dell'operatore automatico per le audioconferenze [in Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="fa496-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="fa496-173">Passaggio 8: (Facoltativo) Modificare le impostazioni del bridge di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fa496-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="fa496-174">Per modificare le impostazioni del bridge di audioconferenza dell'organizzazione, vedi Modificare le impostazioni [per un bridge per audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="fa496-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="fa496-175">Passaggio 9 : (Facoltativo) Impostare i numeri di telefono inclusi negli inviti alle riunioni degli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fa496-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="fa496-176">Per modificare il set di numeri di telefono inclusi negli inviti alle riunioni degli utenti è la tua organizzazione, vedi Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="fa496-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="fa496-177">Le funzionalità di audioconferenza non sono supportate nelle audioconferenze con routing diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="fa496-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="fa496-178">Di seguito sono riportate le funzionalità di audioconferenza non supportate nelle audioconferenze con instradamento diretto per GCC High e DoD:</span><span class="sxs-lookup"><span data-stu-id="fa496-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="fa496-179">Notifiche di accesso e uscita tramite registrazione del nome.</span><span class="sxs-lookup"><span data-stu-id="fa496-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="fa496-180">Per le audioconferenze con instradamento diretto, le notifiche di accesso e uscita vengono riprodotte nella riunione come toni.</span><span class="sxs-lookup"><span data-stu-id="fa496-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="fa496-181">Criteri di restrizione delle chiamate in uscita per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="fa496-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="fa496-182">I controlli a livello utente per limitare le chiamate in uscita non sono applicabili alle chiamate in uscita instradati tramite instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="fa496-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="fa496-183">Disabilita l'uso dei numeri verde per le riunioni con l'organizzatore specifico.</span><span class="sxs-lookup"><span data-stu-id="fa496-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="fa496-184">I controlli a livello utente che limitano l'utilizzo dei numeri verde per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradati tramite instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="fa496-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="fa496-185">Invio di messaggi di posta elettronica di notifica agli utenti quando le impostazioni vengono modificate.</span><span class="sxs-lookup"><span data-stu-id="fa496-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="fa496-186">I messaggi di posta elettronica di notifica per le audioconferenze non sono supportati per le audioconferenze con instradamento diretto per GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="fa496-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
