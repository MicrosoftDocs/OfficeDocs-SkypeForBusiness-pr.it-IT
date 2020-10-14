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
ms.openlocfilehash: 18bd33281379efe7dd2e64019e20a66a2dbec920
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444212"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="f8419-103">Aprire l'anteprima dei servizi di conferenza in rete per l'audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f8419-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="f8419-104">L'anteprima aperta dei servizi di conferenza in rete è disponibile per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="f8419-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="f8419-105">I servizi di conferenza in rete consentono alle organizzazioni di inviare chiamate di audioconferenza in ingresso e in uscita ai numeri di accesso esterno Microsoft tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="f8419-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="f8419-106">Questa funzionalità non è destinata a estendere il supporto dei servizi di audioconferenza ai numeri di accesso esterno di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8419-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="f8419-107">I servizi di conferenza in rete non sono supportati se vengono usati per instradare le chiamate in ingresso al servizio di audioconferenza tramite i numeri di telefono di accesso esterno di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8419-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="f8419-108">In questo articolo vengono illustrati i prerequisiti e i passaggi di configurazione necessari per abilitare i servizi di conferenza in rete per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8419-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8419-109">I servizi di conferenza in rete non devono essere distribuiti con qualsiasi dispositivo di telefonia in India.</span><span class="sxs-lookup"><span data-stu-id="f8419-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="f8419-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f8419-110">Prerequisites</span></span>

<span data-ttu-id="f8419-111">Prima di configurare i servizi di conferenza in rete, verificare che l'organizzazione soddisfi i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8419-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="f8419-112">Assicurarsi che tutti gli utenti dell'organizzazione abilitati o abilitati per i servizi di audioconferenza utilizzino team per tutte le riunioni.</span><span class="sxs-lookup"><span data-stu-id="f8419-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="f8419-113">Il routing delle chiamate di conferenza audio in ingresso e in uscita tramite servizi di conferenza in rete è supportato solo per le riunioni di team.</span><span class="sxs-lookup"><span data-stu-id="f8419-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="f8419-114">Assegnare licenze di audioconferenza a tutti gli utenti che utilizzeranno i servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="f8419-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="f8419-115">Configurare il servizio di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="f8419-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="f8419-116">Per altre informazioni, vedere [configurare le conferenze audio per Microsoft teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f8419-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="f8419-117">Configurare il session border controller (SBC) per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="f8419-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="f8419-118">Per altre informazioni, vedere [pianificare il routing diretto](direct-routing-plan.md) e [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="f8419-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="f8419-119">Se si sta configurando un routing diretto solo per i servizi di audioconferenza, è necessario completare solo il passaggio 1: connettere il SBC per i servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="f8419-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="f8419-120">Abilitare il routing delle chiamate con accesso esterno a Microsoft Audio Conferencing tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="f8419-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="f8419-121">Per instradare le chiamate con accesso esterno effettuate dagli utenti locali al servizio di audioconferenza tramite routing diretto, è necessario configurare le regole di routing appropriate per i sistemi PBX (SBCs e Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="f8419-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="f8419-122">È necessario configurare l'equipaggiamento per la telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del Bridge di conferenza della propria organizzazione tramite un trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="f8419-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="f8419-123">Puoi trovare i numeri di servizio nell'interfaccia di amministrazione di teams in **riunioni-> Bridge per conferenze** o usando il cmdlet di PowerShell per Skype for business online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="f8419-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="f8419-124">Per altre informazioni, vedere un elenco di numeri di servizi di [audioconferenza in Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f8419-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f8419-125">Questa caratteristica non è disponibile per gli utenti con la licenza per i servizi di audioconferenza pay-per-minute.</span><span class="sxs-lookup"><span data-stu-id="f8419-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="f8419-126">Abilitare il routing delle chiamate di chiamata in uscita dei team tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="f8419-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="f8419-127">Le chiamate di chiamata in uscita per le riunioni di team vengono avviate dall'interno di una riunione dell'organizzazione a numeri PSTN, tra cui chiamate e chiamate per trasferire i nuovi partecipanti a una riunione.</span><span class="sxs-lookup"><span data-stu-id="f8419-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="f8419-128">Per abilitare il routing delle chiamate in uscita del team tramite routing diretto, è necessario creare e assegnare un criterio di routing per i servizi di audioconferenza denominato "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="f8419-128">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="f8419-129">Il criterio OnlineAudioConferencingRoutingPolicy equivale alle chiamate PSTN di CsOnlineVoiceRoutingPolicy per 1:1 tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="f8419-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="f8419-130">I criteri di OnlineAudioConferencingRoutingPolicy possono essere gestiti usando i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8419-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="f8419-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f8419-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f8419-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f8419-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f8419-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f8419-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f8419-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f8419-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f8419-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f8419-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="f8419-136">Per altre informazioni sul routing per il routing diretto, vedere [configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f8419-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="f8419-137">Per abilitare il routing delle chiamate di chiamata in uscita tramite routing diretto, è necessario:</span><span class="sxs-lookup"><span data-stu-id="f8419-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="f8419-138">Configurare i criteri di routing per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f8419-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="f8419-139">Configurare il routing nell'attrezzatura per la telefonia dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f8419-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="f8419-140">Opzionale Configurare un dial plan</span><span class="sxs-lookup"><span data-stu-id="f8419-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="f8419-141">Le chiamate in uscita dalle riunioni di team vengono dal numero di servizio predefinito sul Bridge di conferenza.</span><span class="sxs-lookup"><span data-stu-id="f8419-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="f8419-142">Per altre informazioni sul numero di servizio predefinito del Bridge per i servizi di audioconferenza, vedere [modificare i numeri di telefono nel Bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="f8419-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="f8419-143">Configurare i criteri di routing per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f8419-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="f8419-144">Il criterio di routing per i servizi di audioconferenza OnlineAudioConferencingRoutingPolicy determina quali chiamate di chiamata in uscita vengono instradate ai trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="f8419-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="f8419-145">Se si ha familiarità con i criteri di CsOnlineVoiceRoutingPolicy, questo criterio funziona in modo molto simile.</span><span class="sxs-lookup"><span data-stu-id="f8419-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="f8419-146">I passaggi seguenti sono necessari per configurare i criteri di routing per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="f8419-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="f8419-147">Creare usi PSTN</span><span class="sxs-lookup"><span data-stu-id="f8419-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="f8419-148">Configurare le route vocali</span><span class="sxs-lookup"><span data-stu-id="f8419-148">Configure voice routes</span></span>
3.  <span data-ttu-id="f8419-149">Creare criteri di routing vocale per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f8419-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="f8419-150">Assegnare un criterio agli utenti</span><span class="sxs-lookup"><span data-stu-id="f8419-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="f8419-151">Creare usi PSTN</span><span class="sxs-lookup"><span data-stu-id="f8419-151">Create PSTN usages</span></span>

<span data-ttu-id="f8419-152">Gli usi PSTN sono insiemi di route vocali.</span><span class="sxs-lookup"><span data-stu-id="f8419-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="f8419-153">Quando una chiamata in uscita viene avviata dalla riunione di un organizzatore specifico, verranno usate le route vocali per determinare il percorso di routing della chiamata in base agli usi PSTN associati all'utente tramite i criteri di routing vocale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f8419-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="f8419-154">Puoi creare un uso PSTN usando il cmdlet "set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="f8419-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="f8419-155">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f8419-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="f8419-156">Configurare le route vocali</span><span class="sxs-lookup"><span data-stu-id="f8419-156">Configure voice routes</span></span>

<span data-ttu-id="f8419-157">Le route vocali determinano il gateway PSTN che deve essere usato per instradare una chiamata in base al numero di telefono composto da una riunione teams.</span><span class="sxs-lookup"><span data-stu-id="f8419-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="f8419-158">Le route vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata abbinando il numero di telefono composto da una riunione di teams con uno schema Regex.</span><span class="sxs-lookup"><span data-stu-id="f8419-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="f8419-159">Quando si crea una route vocale, la route deve essere associata a uno o più usi PSTN.</span><span class="sxs-lookup"><span data-stu-id="f8419-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="f8419-160">È possibile creare una route vocale e definire le espressioni regolari e i gateway da associare alla route vocale usando il cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="f8419-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="f8419-161">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f8419-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="f8419-162">Creare criteri di routing vocale per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f8419-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="f8419-163">I criteri di routing vocale per i servizi di audioconferenza determinano le possibili route che possono essere usate per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione.</span><span class="sxs-lookup"><span data-stu-id="f8419-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="f8419-164">I criteri di routing vocale per i servizi di audioconferenza sono associati a uno o più usi PSTN, che a loro volta determinano le possibili rotte che verranno usate per le chiamate di chiamata in uscita degli organizzatori associati al criterio.</span><span class="sxs-lookup"><span data-stu-id="f8419-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="f8419-165">Puoi creare un criterio di routing vocale per i servizi di audioconferenza usando il cmdlet "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="f8419-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="f8419-166">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="f8419-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="f8419-167">Dopo che i criteri sono stati assegnati a un utente e quando viene avviata una chiamata esterna a una riunione da una delle riunioni dell'utente, vengono valutate le route vocali negli usi PSTN associati all'organizzatore tramite i criteri di routing vocale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f8419-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="f8419-168">Se la destinazione di chiamata in uscita della riunione corrisponde a una Regex in una delle route vocali associate all'organizzatore, la chiamata di accesso esterno alla riunione verrà instradata al gateway PSTN definito nella route vocale.</span><span class="sxs-lookup"><span data-stu-id="f8419-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="f8419-169">Se la destinazione delle chiamate di chiamata in uscita della riunione non corrisponde a nessuna delle route vocali associate all'organizzatore, la chiamata esterna della riunione verrà instradata da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8419-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="f8419-170">Assegnare un criterio agli utenti</span><span class="sxs-lookup"><span data-stu-id="f8419-170">Assign a policy to your users</span></span>

<span data-ttu-id="f8419-171">Dopo aver definito i criteri di routing per i servizi di audioconferenza, è ora possibile assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f8419-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="f8419-172">Dopo aver assegnato i criteri, le chiamate di chiamata in uscita verranno valutate per determinare il percorso di routing.</span><span class="sxs-lookup"><span data-stu-id="f8419-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="f8419-173">I criteri di routing per i servizi di audioconferenza vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente nella riunione che avvia una chiamata esterna alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f8419-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="f8419-174">Puoi assegnare un criterio di routing vocale per i servizi di audioconferenza a un utente usando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="f8419-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="f8419-175">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f8419-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="f8419-176">Configurare il routing nell'attrezzatura per la telefonia dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f8419-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="f8419-177">Nell'attrezzatura per la telefonia dell'organizzazione devi assicurarti che le chiamate di chiamata in uscita della riunione instradate tramite il routing diretto vengano instradate alla destinazione in rete prevista.</span><span class="sxs-lookup"><span data-stu-id="f8419-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="f8419-178">Opzionale Configurare un dial plan</span><span class="sxs-lookup"><span data-stu-id="f8419-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="f8419-179">Un dial plan è un set di regole di normalizzazione che traducono i numeri di telefono composti da un singolo utente in un formato alternativo (in genere E. 164) ai fini dell'autorizzazione alle chiamate e del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="f8419-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="f8419-180">Per impostazione predefinita, gli utenti del team possono effettuare la chiamata in uscita per i numeri PSTN nel formato E. 164, ovvero + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="f8419-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="f8419-181">Tuttavia, i dial plan possono essere usati per consentire agli utenti di chiamare numeri di telefono in altri formati, ad esempio estensioni a 4 cifre.</span><span class="sxs-lookup"><span data-stu-id="f8419-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="f8419-182">Se si vuole abilitare le chiamate basate su estensioni tramite i servizi di conferenza in rete, è possibile configurare i piani di chiamata in modo che corrispondano al modello di chiamata dell'estensione agli intervalli di numeri di telefono del numero di telefono dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8419-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="f8419-183">Per configurare i dial plan, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f8419-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="f8419-184">Problemi noti nell'anteprima aperta</span><span class="sxs-lookup"><span data-stu-id="f8419-184">Known issues in Open Preview</span></span>

<span data-ttu-id="f8419-185">Di seguito è riportato un elenco dei problemi noti attualmente presenti nella versione Open Preview dei servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="f8419-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="f8419-186">Microsoft sta lavorando per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="f8419-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="f8419-187">Problema</span><span class="sxs-lookup"><span data-stu-id="f8419-187">Issue</span></span> | <span data-ttu-id="f8419-188">Soluzione</span><span class="sxs-lookup"><span data-stu-id="f8419-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="f8419-189">Le chiamate con accesso esterno con ID chiamante anonimo/nascosto instradati attraverso i servizi di conferenza di rete non possono essere connessi alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f8419-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="f8419-190">Se possibile, imposta una configurazione in PBX o SBC per inviare sempre un ID chiamante per le chiamate instradate tramite servizi di conferenza in rete.</span><span class="sxs-lookup"><span data-stu-id="f8419-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="f8419-191">In alcuni casi, il messaggio di benvenuto che viene riprodotto agli utenti quando effettua l'accesso al servizio ("Benvenuto nel servizio di audioconferenza...") viene troncato e gli utenti non sentono la parola "benvenuto".</span><span class="sxs-lookup"><span data-stu-id="f8419-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="f8419-192">Al momento non esistono soluzioni alternative per questo problema.</span><span class="sxs-lookup"><span data-stu-id="f8419-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="f8419-193">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f8419-193">Related topics</span></span>


