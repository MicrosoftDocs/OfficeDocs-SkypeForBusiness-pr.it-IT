---
title: Conferenze in rete per servizi di audioconferenza
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Di seguito vengono illustrate le funzionalità di anteprima aperta per la rete per i servizi di audioconferenza.
ms.openlocfilehash: 3b33c67cc79f79d36cf2a11213dc934103b026fb
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321801"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="b1e3a-103">Aprire l'anteprima dei servizi di conferenza in rete per l'audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b1e3a-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="b1e3a-104">L'anteprima aperta dei servizi di conferenza in rete è disponibile per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="b1e3a-105">I servizi di conferenza in rete consentono alle organizzazioni di inviare chiamate di audioconferenza in ingresso e in uscita ai numeri di accesso esterno Microsoft tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="b1e3a-106">Questa funzionalità non è destinata a estendere il supporto dei servizi di audioconferenza ai numeri di accesso esterno di terze parti.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="b1e3a-107">I servizi di conferenza in rete non sono supportati se vengono usati per instradare le chiamate in ingresso al servizio di audioconferenza tramite i numeri di telefono di accesso esterno di terze parti.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="b1e3a-108">In questo articolo vengono illustrati i prerequisiti e i passaggi di configurazione necessari per abilitare i servizi di conferenza in rete per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1e3a-109">I servizi di conferenza in rete non devono essere distribuiti con qualsiasi dispositivo di telefonia in India.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="b1e3a-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b1e3a-110">Prerequisites</span></span>

<span data-ttu-id="b1e3a-111">Prima di configurare i servizi di conferenza in rete, verificare che l'organizzazione soddisfi i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="b1e3a-112">Assicurarsi che tutti gli utenti dell'organizzazione abilitati o vengano abilitati per i servizi di audioconferenza siano in modalità solo teams.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are in Teams Only mode.</span></span> <span data-ttu-id="b1e3a-113">Il routing delle chiamate di conferenza audio in ingresso e Outboud tramite servizi di conferenza in rete è supportato solo per le riunioni di team.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-113">The routing of inbound and outboud Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="b1e3a-114">Assegnare licenze di audioconferenza a tutti gli utenti che utilizzeranno i servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="b1e3a-115">Configurare il servizio di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="b1e3a-116">Per altre informazioni, vedere [configurare le conferenze audio per Microsoft teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b1e3a-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="b1e3a-117">Configurare il session border controller (SBC) per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="b1e3a-118">Per altre informazioni, vedere [pianificare il routing diretto](direct-routing-plan.md) e [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b1e3a-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="b1e3a-119">Se si sta configurando un routing diretto solo per i servizi di audioconferenza, è necessario completare solo il passaggio 1: connettere il SBC per i servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="b1e3a-120">Abilitare il routing delle chiamate con accesso esterno a Microsoft Audio Conferencing tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="b1e3a-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="b1e3a-121">Per instradare le chiamate con accesso esterno effettuate dagli utenti locali al servizio di audioconferenza tramite routing diretto, è necessario configurare le regole di routing appropriate per i sistemi PBX (SBCs e Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="b1e3a-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="b1e3a-122">È necessario configurare l'equipaggiamento per la telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del Bridge di conferenza della propria organizzazione tramite un trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="b1e3a-123">Puoi trovare i numeri di servizio nell'interfaccia di amministrazione di teams in **riunioni-> Bridge per conferenze** o usando il cmdlet di PowerShell per Skype for business online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="b1e3a-124">Per altre informazioni, vedere un elenco di numeri di servizi di [audioconferenza in Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b1e3a-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>


## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="b1e3a-125">Abilitare il routing delle chiamate di chiamata in uscita dei team tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="b1e3a-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="b1e3a-126">Le chiamate di chiamata in uscita per le riunioni di team vengono avviate dall'interno di una riunione dell'organizzazione a numeri PSTN, tra cui chiamate e chiamate per trasferire i nuovi partecipanti a una riunione.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="b1e3a-127">Per abilitare il routing delle chiamate in uscita del team tramite routing diretto, è necessario creare e assegnare un criterio di routing per i servizi di audioconferenza denominato "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="b1e3a-127">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="b1e3a-128">Il criterio OnlineAudioConferencingRoutingPolicy equivale alle chiamate PSTN di CsOnlineVoiceRoutingPolicy per 1:1 tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="b1e3a-129">I criteri di OnlineAudioConferencingRoutingPolicy possono essere gestiti usando i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="b1e3a-130">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b1e3a-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b1e3a-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b1e3a-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b1e3a-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b1e3a-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b1e3a-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b1e3a-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="b1e3a-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="b1e3a-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="b1e3a-135">Per altre informazioni sul routing per il routing diretto, vedere [configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="b1e3a-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="b1e3a-136">Per abilitare il routing delle chiamate di chiamata in uscita tramite routing diretto, è necessario:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="b1e3a-137">Configurare i criteri di routing per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b1e3a-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="b1e3a-138">Configurare il routing nell'attrezzatura per la telefonia dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b1e3a-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="b1e3a-139">Opzionale Configurare un dial plan</span><span class="sxs-lookup"><span data-stu-id="b1e3a-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b1e3a-140">Le chiamate in uscita dalle riunioni di team vengono dal numero di servizio predefinito sul Bridge di conferenza.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="b1e3a-141">Per altre informazioni sul numero di servizio predefinito del Bridge per i servizi di audioconferenza, vedere [modificare i numeri di telefono nel Bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="b1e3a-142">Configurare i criteri di routing per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b1e3a-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="b1e3a-143">Il criterio di routing per i servizi di audioconferenza OnlineAudioConferencingRoutingPolicy determina quali chiamate di chiamata in uscita vengono instradate ai trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="b1e3a-144">Se si ha familiarità con i criteri di CsOnlineVoiceRoutingPolicy, questo criterio funziona in modo molto simile.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="b1e3a-145">I passaggi seguenti sono necessari per configurare i criteri di routing per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="b1e3a-146">Creare usi PSTN</span><span class="sxs-lookup"><span data-stu-id="b1e3a-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="b1e3a-147">Configurare le route vocali</span><span class="sxs-lookup"><span data-stu-id="b1e3a-147">Configure voice routes</span></span>
3.  <span data-ttu-id="b1e3a-148">Creare criteri di routing vocale per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b1e3a-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="b1e3a-149">Assegnare un criterio agli utenti</span><span class="sxs-lookup"><span data-stu-id="b1e3a-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="b1e3a-150">Creare usi PSTN</span><span class="sxs-lookup"><span data-stu-id="b1e3a-150">Create PSTN usages</span></span>

<span data-ttu-id="b1e3a-151">Gli usi PSTN sono insiemi di route vocali.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="b1e3a-152">Quando una chiamata in uscita viene avviata dalla riunione di un organizzatore specifico, verranno usate le route vocali per determinare il percorso di routing della chiamata in base agli usi PSTN associati all'utente tramite i criteri di routing vocale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="b1e3a-153">Puoi creare un uso PSTN usando il cmdlet "set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="b1e3a-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="b1e3a-154">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-154">For Example:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="b1e3a-155">Configurare le route vocali</span><span class="sxs-lookup"><span data-stu-id="b1e3a-155">Configure voice routes</span></span>

<span data-ttu-id="b1e3a-156">Le route vocali determinano il gateway PSTN che deve essere usato per instradare una chiamata in base al numero di telefono composto da una riunione teams.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="b1e3a-157">Le route vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata abbinando il numero di telefono composto da una riunione di teams con uno schema Regex.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="b1e3a-158">Quando si crea una route vocale, la route deve essere associata a uno o più usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="b1e3a-159">È possibile creare una route vocale e definire le espressioni regolari e i gateway da associare alla route vocale usando il cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="b1e3a-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="b1e3a-160">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-160">For Example:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="b1e3a-161">Creare criteri di routing vocale per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b1e3a-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="b1e3a-162">I criteri di routing vocale per i servizi di audioconferenza determinano le possibili route che possono essere usate per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="b1e3a-163">I criteri di routing vocale per i servizi di audioconferenza sono associati a uno o più usi PSTN, che a loro volta determinano le possibili rotte che verranno usate per le chiamate di chiamata in uscita degli organizzatori associati al criterio.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="b1e3a-164">Puoi creare un criterio di routing vocale per i servizi di audioconferenza usando il cmdlet "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="b1e3a-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b1e3a-165">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-165">For Example:</span></span>

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b1e3a-166">Dopo che i criteri sono stati assegnati a un utente e quando viene avviata una chiamata esterna a una riunione da una delle riunioni dell'utente, vengono valutate le route vocali negli usi PSTN associati all'organizzatore tramite i criteri di routing vocale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="b1e3a-167">Se la destinazione di chiamata in uscita della riunione corrisponde a una Regex in una delle route vocali associate all'organizzatore, la chiamata di accesso esterno alla riunione verrà instradata al gateway PSTN definito nella route vocale.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="b1e3a-168">Se la destinazione delle chiamate di chiamata in uscita della riunione non corrisponde a nessuna delle route vocali associate all'organizzatore, la chiamata esterna della riunione verrà instradata da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="b1e3a-169">Assegnare un criterio agli utenti</span><span class="sxs-lookup"><span data-stu-id="b1e3a-169">Assign a policy to your users</span></span>

<span data-ttu-id="b1e3a-170">Dopo aver definito i criteri di routing per i servizi di audioconferenza, è ora possibile assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="b1e3a-171">Dopo aver assegnato i criteri, le chiamate di chiamata in uscita verranno valutate per determinare il percorso di routing.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="b1e3a-172">I criteri di routing per i servizi di audioconferenza vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente nella riunione che avvia una chiamata esterna alla riunione.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="b1e3a-173">Puoi assegnare un criterio di routing vocale per i servizi di audioconferenza a un utente usando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="b1e3a-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="b1e3a-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b1e3a-174">For example:</span></span>

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="b1e3a-175">Configurare il routing nell'attrezzatura per la telefonia dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b1e3a-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="b1e3a-176">Nell'attrezzatura per la telefonia dell'organizzazione devi assicurarti che le chiamate di chiamata in uscita della riunione instradate tramite il routing diretto vengano indirizzate alla destinazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="b1e3a-177">Opzionale Configurare un dial plan</span><span class="sxs-lookup"><span data-stu-id="b1e3a-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="b1e3a-178">Un dial plan è un set di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E. 164) ai fini dell'autorizzazione alle chiamate e del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="b1e3a-179">Per impostazione predefinita, gli utenti del team possono effettuare la chiamata in uscita per i numeri PSTN nel formato E. 164, ovvero + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="b1e3a-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="b1e3a-180">Tuttavia, i dial plan possono essere usati per consentire agli utenti di chiamare numeri di telefono in altri formati, ad esempio estensioni a 4 cifre.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="b1e3a-181">Se si vuole abilitare le chiamate basate su estensioni tramite i servizi di conferenza in rete, è possibile configurare i piani di chiamata in modo che corrispondano al modello di chiamata dell'estensione agli intervalli di numeri di telefono del numero di telefono dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="b1e3a-182">Per configurare i dial plan, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="b1e3a-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="b1e3a-183">Problemi noti nell'anteprima aperta</span><span class="sxs-lookup"><span data-stu-id="b1e3a-183">Known issues in Open Preview</span></span>

<span data-ttu-id="b1e3a-184">Di seguito è riportato un elenco dei problemi noti attualmente presenti nella versione Open Preview dei servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-184">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="b1e3a-185">Microsoft sta lavorando per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-185">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="b1e3a-186">Problema</span><span class="sxs-lookup"><span data-stu-id="b1e3a-186">Issue</span></span> | <span data-ttu-id="b1e3a-187">Soluzione</span><span class="sxs-lookup"><span data-stu-id="b1e3a-187">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="b1e3a-188">Le chiamate con accesso esterno con ID chiamante anonimo/nascosto instradati attraverso i servizi di conferenza di rete non possono essere connessi alla riunione.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-188">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="b1e3a-189">Se possibile, imposta una configurazione in PBX o SBC per inviare sempre un ID chiamante per le chiamate instradate tramite servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-189">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="b1e3a-190">In alcuni casi, il messaggio di benvenuto che viene riprodotto agli utenti quando effettua l'accesso al servizio ("Benvenuto nel servizio di audioconferenza...") viene troncato e gli utenti non sentono la parola "benvenuto".</span><span class="sxs-lookup"><span data-stu-id="b1e3a-190">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="b1e3a-191">Al momento non esistono soluzioni alternative per questo problema.</span><span class="sxs-lookup"><span data-stu-id="b1e3a-191">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="b1e3a-192">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b1e3a-192">Related topics</span></span>


