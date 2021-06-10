---
title: Audioconferenza con routing diretto, GCCH e DoD
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
description: L'amministratore può imparare a usare le audioconferenze con il routing diretto in ambienti GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262621"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="4d879-103">Audioconferenza con Instradamento diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="4d879-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="4d879-104">Le audioconferenze con routing diretto per GCC High e DoD consentono ai partecipanti di partecipare alle riunioni di Teams nell'organizzazione GCC High o DoD usando un dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="4d879-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="4d879-105">I partecipanti alla riunione potrebbero scegliere di usare un dispositivo telefonico per partecipare Teams riunioni in scenari come quando la connettività Internet è limitata o quando gli utenti sono in viaggio e non hanno accesso Teams.</span><span class="sxs-lookup"><span data-stu-id="4d879-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="4d879-106">I partecipanti possono scegliere di partecipare alle riunioni componendo l'accesso a un numero di telefono esterno per l'organizzazione o facendo in modo che la riunione sia con accesso esterno al dispositivo telefonico.</span><span class="sxs-lookup"><span data-stu-id="4d879-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="4d879-107">Con le audioconferenze con routing diretto per GCC High e DoD, l'organizzazione usa i propri numeri come numeri di telefono per l'accesso esterno e tutte le chiamate in uscita delle riunioni verso i dispositivi telefonici vengono instradati tramite Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="4d879-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="4d879-108">Per abilitare il servizio, le organizzazioni devono configurare Il routing diretto e configurare i numeri di telefono che possono essere usati come numeri di telefono per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="4d879-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="4d879-109">Il requisito per l'uso del routing diretto è diverso dal servizio di audioconferenza offerto alle organizzazioni non GCC High e non DoD in cui i numeri di telefono per l'accesso esterno sono forniti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d879-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="4d879-110">Distribuire audioconferenze con routing diretto per GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="4d879-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="4d879-111">Passaggio 1: Ottenere audioconferenze con routing diretto per le GCC High o DoD</span><span class="sxs-lookup"><span data-stu-id="4d879-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="4d879-112">Per usare le audioconferenze in GCC High o DoD, l'organizzazione e gli utenti dell'organizzazione devono avere una audioconferenza con la licenza Di routing diretto assegnata.</span><span class="sxs-lookup"><span data-stu-id="4d879-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="4d879-113">Ecco le licenze necessarie per abilitare le audioconferenze con routing diretto GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="4d879-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="4d879-114">GCC Alta: una licenza per audioconferenza , GCC High Tenant per l'organizzazione e Audioconferenza, GCC licenze High per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4d879-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="4d879-115">DoD: Audioconferenza - Licenza DoD Tenant per l'organizzazione e Audioconferenza - Licenze DoD per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4d879-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="4d879-116">Per abilitare il servizio sono necessarie una licenza tenant e almeno una licenza utente.</span><span class="sxs-lookup"><span data-stu-id="4d879-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="4d879-117">Non è possibile abilitare il servizio solo con la licenza tenant o con solo licenze utente.</span><span class="sxs-lookup"><span data-stu-id="4d879-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="4d879-118">Per ottenere licenze di servizio per il tenant e gli utenti dell'organizzazione, contattare il team dell'account.</span><span class="sxs-lookup"><span data-stu-id="4d879-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d879-119">Gli utenti non possono essere abilitati per le audioconferenze con routing diretto finché non vengono impostati i numeri di telefono con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="4d879-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="4d879-120">È consigliabile non assegnare audioconferenze con routing diretto per le licenze GCC High o DoD agli utenti fino a quando non si configurano i numeri di telefono per l'accesso esterno come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4d879-120">We recommend that you do not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>  <span data-ttu-id="4d879-121">Se non si seguono queste indicazioni, la tastiera del telefono potrebbe risultare completamente mancante nel client Teams telefono.</span><span class="sxs-lookup"><span data-stu-id="4d879-121">Failure to follow this guidance may cause the dial pad to be completely missing in the Teams client.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="4d879-122">Passaggio 2: Configurare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="4d879-122">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="4d879-123">Per configurare il routing diretto, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d879-123">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="4d879-124">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4d879-124">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="4d879-125">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="4d879-125">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="4d879-126">Quando si configura il routing diretto, ricordarsi di usare i nomi fqdn e le porte GCC High o DoD specifici per le porte descritte in questi due articoli.</span><span class="sxs-lookup"><span data-stu-id="4d879-126">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="4d879-127">Passaggio 3: Configurare i numeri di telefono per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="4d879-127">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="4d879-128">I numeri di telefono per l'accesso esterno sono i numeri di telefono associati al bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="4d879-128">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="4d879-129">Questi numeri vengono usati dai partecipanti per partecipare alle riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d879-129">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="4d879-130">Questi numeri sono inclusi anche negli inviti alle riunioni degli utenti che pianificano le riunioni nell'organizzazione e nella pagina "Trova un numero locale".</span><span class="sxs-lookup"><span data-stu-id="4d879-130">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="4d879-131">Definire i numeri di telefono del servizio nel tenant</span><span class="sxs-lookup"><span data-stu-id="4d879-131">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="4d879-132">È possibile usare il cmdlet di PowerShell New-csHybridTelephoneNumber per definire i numeri di telefono del servizio nel tenant che possono essere usati per instradare le chiamate al servizio di audioconferenza tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="4d879-132">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="4d879-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d879-133">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="4d879-134">Assegnare i numeri di telefono del servizio al bridge di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4d879-134">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="4d879-135">È possibile assegnare numeri di telefono di servizio al bridge di audioconferenza dell'organizzazione usando il cmdlet di PowerShell Register-csOnlineDialInConferencingServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="4d879-135">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="4d879-136">È possibile visualizzare l'ID del bridge di audioconferenza usando Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="4d879-136">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="4d879-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4d879-137">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="4d879-138">Passaggio 4: Definire un criterio di routing vocale globale per abilitare il routing delle chiamate in uscita dalle riunioni</span><span class="sxs-lookup"><span data-stu-id="4d879-138">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="4d879-139">Il routing delle chiamate in uscita effettuate alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione è definito dal criterio di routing vocale globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d879-139">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="4d879-140">Se l'organizzazione ha definito un criterio di routing vocale globale, verificare che il criterio di routing vocale globale consenta le chiamate in uscita verso la rete PSTN che dovrebbero essere avviate da riunioni organizzate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d879-140">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="4d879-141">Se nell'organizzazione non è definito un criterio di routing vocale globale, è necessario definirne uno per abilitare il routing delle chiamate in uscita alla rete PSTN dalle riunioni organizzate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d879-141">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="4d879-142">Tenere presente che il criterio di routing vocale globale dell'organizzazione si applica anche alle chiamate uno-a-uno effettuate alla rete PSTN dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d879-142">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="4d879-143">Se le chiamate uno-a-uno alla rete PSTN sono abilitate per gli utenti dell'organizzazione, assicurarsi che il criterio di routing vocale globale soddisfi le esigenze dell'organizzazione per entrambi i tipi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4d879-143">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="4d879-144">Location-Based routing non è disponibile nelle distribuzioni high Microsoft 365 Government Community Cloud (GCC) High o DoD.</span><span class="sxs-lookup"><span data-stu-id="4d879-144">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="4d879-145">Quando si abilitano le audioconferenze, verificare che non siano abilitati gli utenti di audioconferenza negli ambienti GCC High o DoD per Location-Based Routing.</span><span class="sxs-lookup"><span data-stu-id="4d879-145">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="4d879-146">Definizione di un criterio di routing vocale globale</span><span class="sxs-lookup"><span data-stu-id="4d879-146">Defining a global voice routing policy</span></span>

<span data-ttu-id="4d879-147">È possibile definire un criterio di routing vocale globale definendo un utilizzo PSTN, una route vocale, un criterio di routing vocale e assegnando il nuovo criterio di routing vocale come criterio di routing vocale globale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d879-147">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="4d879-148">La procedura seguente descrive come definire un nuovo criterio di routing vocale globale per un'organizzazione senza uno.</span><span class="sxs-lookup"><span data-stu-id="4d879-148">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="4d879-149">Se l'organizzazione ha già definito criteri di routing vocale, verificare che la configurazione seguente non sia in conflitto con i criteri di routing vocale esistenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d879-149">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="4d879-150">Per creare un nuovo utilizzo PSTN in una sessione remota di PowerShell in Skype for Business Online, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d879-150">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="4d879-151">Per altre informazioni, vedere [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).</span><span class="sxs-lookup"><span data-stu-id="4d879-151">For additional information, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="4d879-152">Per creare una nuova route vocale, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d879-152">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="4d879-153">Quando si definisce una nuova route vocale per l'organizzazione, specificare uno o più gateway PSTN online PSTN definiti per l'organizzazione durante la configurazione del routing diretto.</span><span class="sxs-lookup"><span data-stu-id="4d879-153">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="4d879-154">Lo schema dei numeri specifica quali chiamate verranno instradati attraverso l'elenco specificato di gateway in base al numero di telefono di destinazione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4d879-154">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="4d879-155">Nell'esempio precedente, le chiamate verso qualsiasi destinazione nel mondo corrisponderanno al percorso vocale.</span><span class="sxs-lookup"><span data-stu-id="4d879-155">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="4d879-156">Se si vuole limitare i numeri di telefono che è possibile comporre dalle riunioni degli utenti dell'organizzazione, è possibile modificare lo schema dei numeri in modo che la route vocale corrisponda solo ai modelli di numero delle destinazioni consentite.</span><span class="sxs-lookup"><span data-stu-id="4d879-156">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="4d879-157">Tieni presente che se non ci sono route vocali che corrispondono al modello di numero del numero di telefono di destinazione di una determinata chiamata, la chiamata non verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="4d879-157">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="4d879-158">Per altre informazioni, vedere [New-CsOnlineVoiceRoute.](/powershell/module/skype/new-csonlinevoiceroute)</span><span class="sxs-lookup"><span data-stu-id="4d879-158">For additional information, see [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="4d879-159">Per creare un nuovo criterio di routing vocale, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d879-159">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="4d879-160">Se nel criterio di routing vocale vengono definiti più utilizzi PSTN, questi verranno valutati nell'ordine in cui sono definiti.</span><span class="sxs-lookup"><span data-stu-id="4d879-160">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="4d879-161">È consigliabile che gli utilizzi PSTN siano definiti nell'ordine più specifico di quello più generico in termini di modelli di numero delle route vocali associate agli utilizzi PSTN.</span><span class="sxs-lookup"><span data-stu-id="4d879-161">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="4d879-162">Ad esempio, se è stato definito un utilizzo PSTN per instradare le chiamate verso gli Stati Uniti e un altro utilizzo PSTN è stato definito per instradare le chiamate a qualsiasi altra località del mondo, l'utilizzo PSTN per le chiamate verso gli Stati Uniti dovrebbe essere elencato nei criteri di routing vocale prima dell'utilizzo pstn per instradare le chiamate a qualsiasi altra posizione nel mondo.</span><span class="sxs-lookup"><span data-stu-id="4d879-162">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="4d879-163">Per altre informazioni, vedere [New-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="4d879-163">For additional information, see [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="4d879-164">Per assegnare la nuova route vocale ai criteri globali di routing vocale dell'organizzazione, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d879-164">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="4d879-165">Per altre informazioni, vedere [Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="4d879-165">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="4d879-166">Dopo aver definito il criterio di routing vocale globale, le chiamate in uscita effettuate da riunioni organizzate dagli utenti dell'organizzazione verranno valutate in base alle route vocali associate agli utilizzi PSTN del criterio di routing vocale globale.</span><span class="sxs-lookup"><span data-stu-id="4d879-166">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="4d879-167">Le chiamate in uscita verranno instradate in base alla prima route vocale che corrisponde al modello di numero del numero di telefono composto.</span><span class="sxs-lookup"><span data-stu-id="4d879-167">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="4d879-168">Passaggio 5: Assegnare audioconferenze con routing diretto GCC licenze High o DoD agli utenti</span><span class="sxs-lookup"><span data-stu-id="4d879-168">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="4d879-169">Per assegnare audioconferenze con routing diretto GCC licenze High o DoD all'utente, vedere [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="4d879-169">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="4d879-170">Passaggio 6: (Facoltativo) Vedere un elenco di numeri di audioconferenza in Teams</span><span class="sxs-lookup"><span data-stu-id="4d879-170">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="4d879-171">Per visualizzare l'elenco dei numeri di audioconferenza dell'organizzazione, vedere Visualizzare un elenco di numeri di [audioconferenza in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4d879-171">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="4d879-172">Passaggio 7: (Facoltativo) Impostare le lingue dell'operatore automatico per i numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4d879-172">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="4d879-173">Per cambiare le lingue dei numeri di accesso esterno per i servizi di audioconferenza dell'organizzazione, vedere Impostare le lingue degli operatori automatici per le audioconferenze [in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4d879-173">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="4d879-174">Passaggio 8: (Facoltativo) Modificare le impostazioni del bridge di audioconferenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4d879-174">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="4d879-175">Per modificare le impostazioni del bridge di audioconferenza dell'organizzazione, vedere [Modificare le impostazioni per un bridge di audioconferenza.](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="4d879-175">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="4d879-176">Passaggio 9: (Facoltativo) Impostare i numeri di telefono inclusi negli inviti alla riunione degli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4d879-176">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="4d879-177">Per modificare il set di numeri di telefono inclusi negli inviti alla riunione degli utenti è l'organizzazione, vedere Impostare i numeri di telefono inclusi negli inviti [in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4d879-177">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="4d879-178">Funzionalità di audioconferenza non supportate nelle audioconferenze con routing diretto GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="4d879-178">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="4d879-179">Di seguito sono riportate le funzionalità di audioconferenza non supportate nelle audioconferenze con routing diretto GCC High e DoD:</span><span class="sxs-lookup"><span data-stu-id="4d879-179">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="4d879-180">Notifiche di entrata e uscita con la registrazione del nome.</span><span class="sxs-lookup"><span data-stu-id="4d879-180">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="4d879-181">Per le audioconferenze con routing diretto, le notifiche di entrata e uscita vengono riprodotte nella riunione come toni.</span><span class="sxs-lookup"><span data-stu-id="4d879-181">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="4d879-182">Criteri di restrizione delle chiamate in uscita per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4d879-182">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="4d879-183">I controlli a livello utente per limitare le chiamate in uscita non sono applicabili alle chiamate in uscita instradati tramite Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="4d879-183">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="4d879-184">Disabilitare l'uso di numeri verde per l'organizzatore specifico delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="4d879-184">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="4d879-185">I controlli a livello utente per limitare l'uso di numeri verde per partecipare alle riunioni dell'organizzazione non sono applicabili alle chiamate instradati tramite Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="4d879-185">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="4d879-186">Invio di messaggi di posta elettronica di notifica agli utenti quando le impostazioni cambiano.</span><span class="sxs-lookup"><span data-stu-id="4d879-186">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="4d879-187">I messaggi di posta elettronica di notifica delle audioconferenze non sono supportati per le audioconferenze con routing diretto GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="4d879-187">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>