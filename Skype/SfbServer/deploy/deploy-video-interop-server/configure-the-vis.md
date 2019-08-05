---
title: Configurare il server di interoperabilità video in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Riepilogo: configurare il ruolo di video Interop Server (VIS) in Skype for Business Server.'
ms.openlocfilehash: 3c0b211897afdde0fc0a01e255cdc14bc466f65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195403"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="39598-103">Configurare il server di interoperabilità video in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="39598-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="39598-104">**Riepilogo:** Configurare il ruolo di video Interop Server (VIS) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="39598-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="39598-105">Configurare le impostazioni che il VIS associerà ai trunk video con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39598-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="39598-106">Viene creata una configurazione trunk video con ambito globale dopo l'installazione del servizio VIS.</span><span class="sxs-lookup"><span data-stu-id="39598-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="39598-107">Questa configurazione del trunk video viene applicata dal VIS a tutti i trunk che non hanno la configurazione del trunk video con un ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="39598-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="39598-108">Tieni presente che la configurazione trunk video è una raccolta di impostazioni applicabili ai trunk video.</span><span class="sxs-lookup"><span data-stu-id="39598-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="39598-109">Configurare il trunk e il dial plan video</span><span class="sxs-lookup"><span data-stu-id="39598-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="39598-110">USA i comandi di Windows PowerShell seguenti per specificare la configurazione del trunk video e il dial plan da associare ai nuovi trunk definiti nel documento di topologia tra il VIS e tutti i gateway video.</span><span class="sxs-lookup"><span data-stu-id="39598-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="39598-111">Tutte queste impostazioni possono essere impostate nei livelli globale, del sito o del servizio (gateway video).</span><span class="sxs-lookup"><span data-stu-id="39598-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="39598-112">Un dial plan con ambito globale viene creato per la distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="39598-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="39598-113">Questo dial plan viene applicato da VIS a tutti i trunk che non hanno un piano di chiamata con un ambito più specifico.</span><span class="sxs-lookup"><span data-stu-id="39598-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="39598-114">Configurare il VIS con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39598-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="39598-115">Creare una nuova configurazione trunk video (una raccolta di impostazioni) da usare nel trunk tra il VIS e Cisco Unified Communications Manager (CallManager o CUCM) usando il cmdlet di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="39598-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="39598-116">Se è presente un trunk video esistente che deve essere modificato, usare il cmdlet di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="39598-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="39598-117">Per visualizzare le impostazioni associate a una particolare configurazione del trunk video, usare il cmdlet di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="39598-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="39598-118">Per rimuovere una particolare configurazione del trunk video, usare il cmdlet di Windows PowerShell seguente (si noti che la configurazione del trunk video con ambito globale verrà applicata se non esiste una configurazione trunk video più specifica per un trunk specifico):</span><span class="sxs-lookup"><span data-stu-id="39598-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="39598-119">Stabilire un dial plan da associare al trunk, usando i cmdlet di Windows PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="39598-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="39598-120">Il comando **Remove-CsVoiceNormalizationRule** è necessario per eseguire l'override di una regola predefinita che interferisce con l'interazione vis e CUCM prevista.</span><span class="sxs-lookup"><span data-stu-id="39598-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="39598-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) può essere usato per rimuovere un dial plan.</span><span class="sxs-lookup"><span data-stu-id="39598-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="39598-122">Per una chiamata trunk SIP video da un gateway video il cui URI di richiesta contiene un numero diverso da E. 164, VIS leggerà il nome del dial plan associato al trunk associato e includerà il nome del dial plan nella parte del contesto telefonico dell'URI della richiesta nell'invito che VI S invia al front-end.</span><span class="sxs-lookup"><span data-stu-id="39598-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="39598-123">L'applicazione di traduzione nel front-end estrae e applica le regole di normalizzazione associate al dial plan all'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="39598-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="39598-124">Opzioni di configurazione trunk</span><span class="sxs-lookup"><span data-stu-id="39598-124">Trunk configuration options</span></span>

<span data-ttu-id="39598-125">I cmdlet di Windows PowerShell per la configurazione del trunk video menzionati in precedenza erano nuovi per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="39598-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="39598-126">Le impostazioni associate alla configurazione del trunk video richiedono una breve spiegazione.</span><span class="sxs-lookup"><span data-stu-id="39598-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="39598-127">**GatewaySendsRtcpForActiveCalls** Questo parametro determina se i pacchetti RTCP vengono inviati da VTC al VIS per le chiamate attive.</span><span class="sxs-lookup"><span data-stu-id="39598-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="39598-128">Una chiamata attiva in questo contesto indica una chiamata in cui è consentito il flusso degli elementi multimediali almeno in una direzione.</span><span class="sxs-lookup"><span data-stu-id="39598-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="39598-129">Se GatewaySendsRtcpForActiveCalls è impostato su true, VIS può terminare una chiamata se non riceve pacchetti RTCP per un periodo che supera i 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="39598-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="39598-130">Il valore predefinito è **true**.</span><span class="sxs-lookup"><span data-stu-id="39598-130">The default is **True**.</span></span>
  
 <span data-ttu-id="39598-131">**GatewaySendsRtcpForCallsOnHold** Questo parametro determina se i pacchetti di RTCP continuano a essere inviati attraverso il trunk per le chiamate che sono state poste in attesa e che non si prevede che il flusso di pacchetti multimediali sia in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="39598-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="39598-132">VIS può terminare la chiamata, se non ci sono pacchetti RTCP che scorrono da VTC a VIS mentre la chiamata è in attesa.</span><span class="sxs-lookup"><span data-stu-id="39598-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="39598-133">Il valore predefinito è **true**.</span><span class="sxs-lookup"><span data-stu-id="39598-133">The default is **True**.</span></span> <span data-ttu-id="39598-134">Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="39598-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="39598-135">**EnableMediaEncryptionForSipOverTls** Questo parametro Abilita o Disabilita SRTP per elementi multimediali quando il protocollo SIPTransport è impostato su TLS.</span><span class="sxs-lookup"><span data-stu-id="39598-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="39598-136">Il valore predefinito è **true**.</span><span class="sxs-lookup"><span data-stu-id="39598-136">The default is **True**.</span></span> <span data-ttu-id="39598-137">Quando il protocollo SIPTransport è impostato su TCP, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="39598-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="39598-138">**EnableSessionTimer** Questo parametro Abilita o Disabilita i timer di sessione sul lato VIS per ogni finestra di dialogo SIP associata al trunk SIP video.</span><span class="sxs-lookup"><span data-stu-id="39598-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="39598-139">Il valore predefinito è **false**.</span><span class="sxs-lookup"><span data-stu-id="39598-139">The default is **False**.</span></span>
  
 <span data-ttu-id="39598-140">**ForwardErrorCorrectionType** Questo parametro viene usato per determinare se la correzione degli errori in avanti (FEC) per i flussi video deve essere applicata alla gamba tra il video Interop server e un gateway video.</span><span class="sxs-lookup"><span data-stu-id="39598-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="39598-141">L'impostazione di ForwardErrorCorrectionType su "None" Disattiva FEC tra VIS e video gateway/VTC.</span><span class="sxs-lookup"><span data-stu-id="39598-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="39598-142">L'impostazione di ForwardErrorCorrectionType su "Cisco" consente la compatibilità con i gateway video per Cisco, ad esempio Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="39598-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="39598-143">Il valore predefinito è **None**.</span><span class="sxs-lookup"><span data-stu-id="39598-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39598-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39598-144">See also</span></span>

[<span data-ttu-id="39598-145">Configurare CUCM per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="39598-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
