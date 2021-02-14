---
title: Servizi di conferenza in rete per audioconferenze
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
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Di seguito viene descritta la funzionalità Open Preview per le audioconferenze in rete.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031862"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="78545-103">Anteprima delle conferenze in rete aperte per le audioconferenze</span><span class="sxs-lookup"><span data-stu-id="78545-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="78545-104">L'anteprima aperta delle conferenze in rete è disponibile per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="78545-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="78545-105">Le conferenze in rete consentono alle organizzazioni di inviare chiamate in ingresso e in uscita ai numeri di accesso esterno Microsoft tramite l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="78545-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="78545-106">Questa funzionalità non ha lo scopo di estendere il supporto dei servizi di audioconferenza ai numeri di accesso esterno di terze parti.</span><span class="sxs-lookup"><span data-stu-id="78545-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="78545-107">Le conferenze in rete non sono supportate se vengono utilizzate per instradare le chiamate in ingresso al servizio di audioconferenza attraverso numeri di telefono di accesso esterno di terze parti.</span><span class="sxs-lookup"><span data-stu-id="78545-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="78545-108">Questo articolo descrive i prerequisiti e i passaggi di configurazione necessari per abilitare le conferenze in rete per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78545-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78545-109">LE conferenze in rete NON devono essere distribuite con dispositivi di telefonia in India.</span><span class="sxs-lookup"><span data-stu-id="78545-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="78545-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="78545-110">Prerequisites</span></span>

<span data-ttu-id="78545-111">Prima di configurare le conferenze in rete, verificare che l'organizzazione soddisfi i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="78545-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="78545-112">Assicurarsi che tutti gli utenti dell'organizzazione abilitati o abilitati per le audioconferenze utilizzino Teams per tutte le riunioni.</span><span class="sxs-lookup"><span data-stu-id="78545-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="78545-113">Il routing delle chiamate in ingresso e in uscita delle audioconferenze tramite le conferenze in rete è supportato solo per le riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="78545-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="78545-114">Assegnare licenze per i servizi di audioconferenza a tutti gli utenti che utilizzano le conferenze in rete.</span><span class="sxs-lookup"><span data-stu-id="78545-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="78545-115">Configurare il servizio di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="78545-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="78545-116">Per altre informazioni, vedere [Configurare le audioconferenze per Microsoft Teams.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="78545-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="78545-117">Configurare il controller dei confini della sessione (SBC) per l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="78545-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="78545-118">Per altre informazioni, vedere [Pianificare l'instradamento diretto](direct-routing-plan.md) [e configurare l'instradamento diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="78545-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="78545-119">Se si sta configurando l'instradamento diretto solo ai fini delle audioconferenze, è necessario completare solo il "Passaggio 1: Connettere il proprio SBC" per le conferenze in rete.</span><span class="sxs-lookup"><span data-stu-id="78545-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="78545-120">Abilitare l'instradamento delle chiamate con accesso esterno ai servizi di audioconferenza Microsoft tramite l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="78545-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="78545-121">Per instradare le chiamate con accesso esterno effettuate dagli utenti locali al servizio di audioconferenza tramite l'instradamento diretto, è necessario configurare le regole di routing appropriate per i provider di servizi di audioconferenza e IBC (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="78545-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="78545-122">È necessario configurare le apparecchiature di telefonia dei siti per instradare le chiamate a qualsiasi numero di servizio del bridge di conferenza dell'organizzazione tramite un trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="78545-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="78545-123">Puoi trovare i numeri di servizio nell'interfaccia di amministrazione di Teams in Riunioni **-> Conferencing Bridges** o utilizzando il cmdlet PowerShell di Skype for Business Online Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="78545-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="78545-124">Per ulteriori informazioni, consulta un elenco di numeri per [i servizi di audioconferenza in Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="78545-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="78545-125">Questa funzionalità non è disponibile per gli utenti con licenza di audioconferenza con pagamento al minuto.</span><span class="sxs-lookup"><span data-stu-id="78545-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="78545-126">Abilitare l'instradamento delle chiamate in uscita delle riunioni di Teams tramite l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="78545-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="78545-127">Le chiamate in uscita delle riunioni di Teams vengono avviate dall'interno di una riunione dell'organizzazione a numeri PSTN, tra cui chiamate con accesso esterno e chiamate per portare i nuovi partecipanti a una riunione.</span><span class="sxs-lookup"><span data-stu-id="78545-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="78545-128">Per abilitare il routing in uscita delle riunioni di Teams tramite l'instradamento diretto agli utenti di rete, è necessario creare e assegnare un criterio di routing dei servizi di audioconferenza denominato "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="78545-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="78545-129">Il criterio OnlineAudioConferencingRoutingPolicy è equivalente al criterio CsOnlineVoiceRoutingPolicy per le chiamate PSTN 1:1 tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="78545-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="78545-130">Il criterio OnlineAudioConferencingRoutingPolicy può essere gestito usando i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="78545-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="78545-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="78545-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="78545-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="78545-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="78545-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="78545-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="78545-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="78545-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="78545-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="78545-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="78545-136">Per altre informazioni sul routing per il routing diretto, vedere [Configurare il routing vocale per l'instradamento diretto.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="78545-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="78545-137">Per abilitare l'instradamento delle chiamate in uscita tramite l'instradamento diretto, è necessario:</span><span class="sxs-lookup"><span data-stu-id="78545-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="78545-138">Configurare i criteri di routing delle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="78545-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="78545-139">Configurare il routing sui dispositivi di telefonia dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="78545-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="78545-140">(Facoltativo) Configurare un piano di chiamata</span><span class="sxs-lookup"><span data-stu-id="78545-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="78545-141">Le chiamate in uscita dalle riunioni di Teams sono provenienti dal numero di servizio predefinito nel bridge di conferenza.</span><span class="sxs-lookup"><span data-stu-id="78545-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="78545-142">Per ulteriori informazioni sul numero di servizio predefinito del bridge di audioconferenza, consulta Modificare i numeri di [telefono nel bridge di audioconferenza.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="78545-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="78545-143">Configurare i criteri di routing delle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="78545-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="78545-144">Il criterio di routing onlineAudioConferencingRoutingPolicy per le audioconferenze determina quali chiamate in uscita vengono instradati ai trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="78545-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="78545-145">Se si ha familiarità con il criterio CsOnlineVoiceRoutingPolicy, il funzionamento di questo criterio è molto simile.</span><span class="sxs-lookup"><span data-stu-id="78545-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="78545-146">Per configurare i criteri di routing delle audioconferenze, sono necessari i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="78545-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="78545-147">Creare utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="78545-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="78545-148">Configurare i percorsi vocali</span><span class="sxs-lookup"><span data-stu-id="78545-148">Configure voice routes</span></span>
3.  <span data-ttu-id="78545-149">Creare criteri di routing vocale per le audioconferenze</span><span class="sxs-lookup"><span data-stu-id="78545-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="78545-150">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="78545-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="78545-151">Creare utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="78545-151">Create PSTN usages</span></span>

<span data-ttu-id="78545-152">L'utilizzo di PSTN è una raccolta di route vocali.</span><span class="sxs-lookup"><span data-stu-id="78545-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="78545-153">Quando viene avviata una chiamata in uscita dalla riunione di un determinato organizzatore, i percorsi vocali vengono utilizzati per determinare il percorso di instradamento della chiamata in base agli utilizzi PSTN associati all'utente tramite il criterio di instradamento vocale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="78545-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="78545-154">Puoi creare un utilizzo PSTN utilizzando il cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="78545-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="78545-155">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="78545-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="78545-156">Configurare i percorsi vocali</span><span class="sxs-lookup"><span data-stu-id="78545-156">Configure voice routes</span></span>

<span data-ttu-id="78545-157">I percorsi vocali determinano il gateway PSTN da usare per instradare una chiamata in base al numero di telefono composto da una riunione di Teams.</span><span class="sxs-lookup"><span data-stu-id="78545-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="78545-158">I percorsi vocali determinano il gateway PSTN che deve essere usato per instradare una determinata chiamata abbinando il numero di telefono composto da una riunione di Teams a un modello di regex.</span><span class="sxs-lookup"><span data-stu-id="78545-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="78545-159">Quando si crea un percorso vocale, la route deve essere associata a uno o più utilizzi di PSTN.</span><span class="sxs-lookup"><span data-stu-id="78545-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="78545-160">Puoi creare un percorso vocale e definire il regex e i gateway da associare al percorso vocale usando il cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="78545-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="78545-161">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="78545-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="78545-162">Creare criteri di routing vocale per le audioconferenze</span><span class="sxs-lookup"><span data-stu-id="78545-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="78545-163">I criteri di routing vocale delle audioconferenze determinano i possibili percorsi che possono essere utilizzati per instradare una chiamata proveniente dalle riunioni di un organizzatore in base al numero di telefono di destinazione della chiamata in uscita della riunione.</span><span class="sxs-lookup"><span data-stu-id="78545-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="78545-164">I criteri di routing vocale delle audioconferenze sono associati a uno o più utilizzi di PSTN, che a loro volta determinano i possibili percorsi che verranno tentati di utilizzare per le chiamate in uscita della riunione degli organizzatori associati al criterio.</span><span class="sxs-lookup"><span data-stu-id="78545-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="78545-165">Puoi creare un criterio di routing vocale per i servizi di audioconferenza utilizzando il cmdlet "New- CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="78545-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="78545-166">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="78545-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="78545-167">Dopo l'assegnazione del criterio a un utente e l'avvio di una chiamata in uscita da una delle riunioni dell'utente, vengono valutati i percorsi vocali negli utilizzi PSTN associati all'organizzatore attraverso il criterio di instradamento vocale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="78545-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="78545-168">Se la destinazione della chiamata in uscita della riunione corrisponde a un regex in uno dei percorsi vocali associati all'organizzatore, la chiamata in uscita della riunione verrà instradata al gateway PSTN definito nel percorso vocale.</span><span class="sxs-lookup"><span data-stu-id="78545-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="78545-169">Se la destinazione della chiamata in uscita della riunione non corrisponde a nessuno dei percorsi vocali associati all'organizzatore, la chiamata in uscita della riunione verrà instradata da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78545-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="78545-170">Assegnare criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="78545-170">Assign a policy to your users</span></span>

<span data-ttu-id="78545-171">Dopo aver definito i criteri di routing delle audioconferenze, è possibile assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="78545-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="78545-172">Dopo l'assegnazione dei criteri, le chiamate in uscita della riunione verranno valutate per determinare il percorso di routing.</span><span class="sxs-lookup"><span data-stu-id="78545-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="78545-173">I criteri di routing delle audioconferenze vengono sempre valutati in base all'organizzatore della riunione, indipendentemente dall'utente che avvia una chiamata in uscita per una riunione.</span><span class="sxs-lookup"><span data-stu-id="78545-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="78545-174">Puoi assegnare criteri di routing vocale per i servizi di audioconferenza a un utente utilizzando il cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="78545-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="78545-175">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="78545-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="78545-176">Configurare il routing sui dispositivi di telefonia dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="78545-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="78545-177">Sui dispositivi di telefonia dell'organizzazione, è necessario assicurarsi che le chiamate in uscita della riunione instradati attraverso l'instradamento diretto siano indirizzate alla destinazione prevista in rete.</span><span class="sxs-lookup"><span data-stu-id="78545-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="78545-178">(Facoltativo) Configurare un piano di chiamata</span><span class="sxs-lookup"><span data-stu-id="78545-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="78545-179">Un piano di chiamata è un insieme di regole di normalizzazione che traducono i numeri di telefono composto da un singolo utente in un formato alternativo (in genere E.164) ai fini dell'autorizzazione delle chiamate e dell'instradamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="78545-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="78545-180">Per impostazione predefinita, gli utenti di Teams possono effettuare chiamate in uscita ai numeri PSTN in formato E.164, cioò + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="78545-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="78545-181">Tuttavia, i piani di chiamata possono essere utilizzati per consentire agli utenti di comporre numeri di telefono in altri formati, ad esempio estensioni a 4 cifre.</span><span class="sxs-lookup"><span data-stu-id="78545-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="78545-182">Per abilitare la composizione basata su interno tramite conferenza telefonica in rete, è possibile configurare piani di chiamata in modo che corrispondano al modello di composizione dell'interno agli intervalli di numeri di telefono del numero di telefono dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78545-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="78545-183">Per configurare piani di chiamata, vedere [Creare e gestire piani di chiamata.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="78545-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="78545-184">Problemi noti in Open Preview</span><span class="sxs-lookup"><span data-stu-id="78545-184">Known issues in Open Preview</span></span>

<span data-ttu-id="78545-185">Di seguito è riportato un elenco dei problemi noti attualmente presenti nella versione Open Preview delle conferenze in rete.</span><span class="sxs-lookup"><span data-stu-id="78545-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="78545-186">Microsoft sta lavorando alla risoluzione di questi problemi.</span><span class="sxs-lookup"><span data-stu-id="78545-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="78545-187">Problema</span><span class="sxs-lookup"><span data-stu-id="78545-187">Issue</span></span> | <span data-ttu-id="78545-188">Soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="78545-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="78545-189">Le chiamate con accesso esterno con ID chiamante anonimi/nascosti che vengono instradati tramite conferenze in rete non possono essere connesse alla riunione.</span><span class="sxs-lookup"><span data-stu-id="78545-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="78545-190">Se possibile, imposta una configurazione nel sistema PBX o SBC in modo da inviare sempre un ID chiamante per le chiamate instradati tramite conferenze in rete.</span><span class="sxs-lookup"><span data-stu-id="78545-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="78545-191">In alcuni casi, il messaggio di benvenuto che viene riprodotto agli utenti quando accondono al servizio ("Benvenuto nel servizio di audioconferenza...") viene troncato e gli utenti non sentono la parola "Benvenuto".</span><span class="sxs-lookup"><span data-stu-id="78545-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="78545-192">Al momento non ci sono soluzioni alternative per questo problema.</span><span class="sxs-lookup"><span data-stu-id="78545-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="78545-193">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="78545-193">Related topics</span></span>


