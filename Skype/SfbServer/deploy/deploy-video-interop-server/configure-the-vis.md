---
title: Configurare Video Interop Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Riepilogo: configurare il ruolo Video Interop Server (VIS) in Skype for Business Server.'
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120305"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="b7ea4-103">Configurare Video Interop Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b7ea4-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="b7ea4-104">**Riepilogo:** Configurare il ruolo Video Interop Server (VIS) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="b7ea4-105">Configurare le impostazioni che il VIS associerà ai trunk video usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="b7ea4-106">Una configurazione trunk video con ambito globale viene creata dopo l'installazione del servizio VIS.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="b7ea4-107">Questa configurazione trunk video viene applicata dal VIS a tutti i trunk che non dispongono di una configurazione trunk video con un ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="b7ea4-108">Si noti che la configurazione del trunk video è una raccolta di impostazioni applicabili ai trunk video.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="b7ea4-109">Configurare trunk video e dial plan</span><span class="sxs-lookup"><span data-stu-id="b7ea4-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="b7ea4-110">Utilizzare i seguenti comandi Windows PowerShell per specificare la configurazione del trunk video e il dial plan da associare ai nuovi trunk definiti nel Documento di topologia tra il VIS e tutti i gateway video.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="b7ea4-111">Tutte queste impostazioni possono essere impostate a livello globale, sito o servizio (gateway video).</span><span class="sxs-lookup"><span data-stu-id="b7ea4-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="b7ea4-112">Viene creato un dial plan con ambito globale per ogni distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="b7ea4-113">Questo dial plan viene applicato da VIS a tutti i trunk che non dispongono di dial plan con ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="b7ea4-114">Configurare il sistema VIS utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7ea4-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="b7ea4-115">Creare una nuova configurazione trunk video (una raccolta di impostazioni) da utilizzare nel trunk tra VIS e Cisco Unified Communications Manager (CallManager o CUCM), utilizzando il cmdlet Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="b7ea4-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="b7ea4-116">Se è necessario modificare un trunk video esistente, utilizzare il cmdlet Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="b7ea4-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="b7ea4-117">Per visualizzare le impostazioni associate a una particolare configurazione trunk video, utilizzare il cmdlet Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="b7ea4-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="b7ea4-118">Per rimuovere una particolare configurazione trunk video, utilizzare il cmdlet Windows PowerShell seguente (si noti che la configurazione trunk video con ambito globale verrà applicata se non esiste una configurazione trunk video con ambito più specifico per un determinato trunk):</span><span class="sxs-lookup"><span data-stu-id="b7ea4-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="b7ea4-119">Stabilire un dial plan da associare al trunk, utilizzando i cmdlet Windows PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7ea4-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="b7ea4-120">Il **comando Remove-CsVoiceNormalizationRule** è necessario per ignorare una regola predefinita che interferirà con l'interazione VIS e CUCM prevista.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="b7ea4-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) può essere utilizzato per rimuovere un dial plan.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="b7ea4-122">Per una chiamata trunk SIP video da un gateway video il cui URI di richiesta contiene un numero non E.164, VIS leggerà il nome del dial plan associato al trunk associato e includerà il nome del dial plan nella parte del contesto telefonico dell'URI richiesta nell'invito inviato da VIS al Front End.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="b7ea4-123">L'applicazione di traduzione nel Front End estrae e applica le regole di normalizzazione associate al dial plan all'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="b7ea4-124">Opzioni di configurazione trunk</span><span class="sxs-lookup"><span data-stu-id="b7ea4-124">Trunk configuration options</span></span>

<span data-ttu-id="b7ea4-125">I Windows PowerShell per la configurazione dei trunk video menzionati in precedenza erano nuovi di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="b7ea4-126">Le impostazioni associate alla configurazione del trunk video richiedono una breve spiegazione.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="b7ea4-127">**GatewaySendsRtcpForActiveCalls** Questo parametro determina se i pacchetti RTCP vengono inviati dal VTC al VIS per le chiamate attive.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="b7ea4-128">Una chiamata attiva in questo contesto è una chiamata in cui il flusso dei supporti è consentito almeno in una direzione.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="b7ea4-129">Se GatewaySendsRtcpForActiveCalls è impostato su True, VIS può terminare una chiamata se non riceve pacchetti RTCP per un periodo superiore a 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="b7ea4-130">L'impostazione predefinita è **True**.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-130">The default is **True**.</span></span>
  
 <span data-ttu-id="b7ea4-131">**GatewaySendsRtcpForCallsOnHold** Questo parametro determina se i pacchetti RTCP continuano a essere inviati attraverso il trunk per le chiamate che sono state poste in attesa e non si prevede che i pacchetti multimediali scorrono in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="b7ea4-132">VIS può terminare la chiamata, se non ci sono pacchetti RTCP che fluino dal VTC al VIS mentre la chiamata è in attesa.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="b7ea4-133">L'impostazione predefinita è **True**.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-133">The default is **True**.</span></span> <span data-ttu-id="b7ea4-134">Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="b7ea4-135">**EnableMediaEncryptionForSipOverTls** Questo parametro abilita o disabilita SRTP per i supporti quando il protocollo SIPTransport è impostato su TLS.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="b7ea4-136">L'impostazione predefinita è **True**.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-136">The default is **True**.</span></span> <span data-ttu-id="b7ea4-137">Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="b7ea4-138">**EnableSessionTimer** Questo parametro abilita o disabilita i timer di sessione sul lato VIS per ogni finestra di dialogo SIP associata al trunk SIP video.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="b7ea4-139">Il valore predefinito è **False**.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-139">The default is **False**.</span></span>
  
 <span data-ttu-id="b7ea4-140">**ForwardErrorCorrectionType** Questo parametro viene utilizzato per determinare se la correzione degli errori di inoltro (FEC, Forward Error Correction) per i flussi video deve essere applicata sulla parte tra Video Interop Server e un gateway video.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="b7ea4-141">L'impostazione di ForwardErrorCorrectionType su "None" disattiva FEC tra VIS e Video Gateway/VTC.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="b7ea4-142">L'impostazione di ForwardErrorCorrectionType su "Cisco" abilita FEC compatibile con i gateway video di Cisco, ad esempio Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="b7ea4-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="b7ea4-143">Il valore predefinito **è None.**</span><span class="sxs-lookup"><span data-stu-id="b7ea4-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b7ea4-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7ea4-144">See also</span></span>

[<span data-ttu-id="b7ea4-145">Configurare CUCM per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b7ea4-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)