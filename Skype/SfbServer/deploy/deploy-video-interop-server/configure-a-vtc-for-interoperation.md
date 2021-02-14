---
title: Configurare un VTC per l'interoperabilità con Skype for Business Server
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
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: "Riepilogo: configurare i dispositivi VTC per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802076"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="e480b-103">Configurare un VTC per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e480b-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="e480b-104">**Riepilogo:** Configurare i dispositivi VTC per l'utilizzo con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e480b-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="e480b-105">Dovrai eseguire le seguenti procedure di personalizzazione della configurazione per ogni VTC che si connetterà al server Skype for Business VIS tramite un trunk SIP e un gateway video Cisco Unified Communications Manager (CallManager o CUCM).</span><span class="sxs-lookup"><span data-stu-id="e480b-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="e480b-106">Le impostazioni descritte di seguito sono solo esempi di come è possibile configurare la modalità di configurazione di CUCM per l'utilizzo con un VIS.</span><span class="sxs-lookup"><span data-stu-id="e480b-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="e480b-107">Per ottenere lo stesso risultato, è possibile utilizzare anche altre impostazioni e/o utilizzi di funzionalità DISAS alternative.</span><span class="sxs-lookup"><span data-stu-id="e480b-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="e480b-108">Non è consigliabile utilizzare la configurazione ottimale per uno scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="e480b-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="e480b-109">Configurare un VTC registrato con CUCM</span><span class="sxs-lookup"><span data-stu-id="e480b-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="e480b-110">Accedi al dispositivo VTC Cisco e passa a Configurazione- \> Configurazione del sistema- \> Provisioning.</span><span class="sxs-lookup"><span data-stu-id="e480b-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="e480b-111">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="e480b-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e480b-112">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e480b-112">**Parameter**</span></span>|<span data-ttu-id="e480b-113">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="e480b-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e480b-114">Modalità di provisioning</span><span class="sxs-lookup"><span data-stu-id="e480b-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="e480b-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="e480b-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="e480b-116">Indirizzo ExternalManager</span><span class="sxs-lookup"><span data-stu-id="e480b-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="e480b-117">FQDN di CUCM</span><span class="sxs-lookup"><span data-stu-id="e480b-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="e480b-118">Dominio ExternalManager</span><span class="sxs-lookup"><span data-stu-id="e480b-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="e480b-119">Dominio di CUCM</span><span class="sxs-lookup"><span data-stu-id="e480b-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="e480b-120">Passare a Configurazione- \> Configurazione di sistema- \> Rete.</span><span class="sxs-lookup"><span data-stu-id="e480b-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="e480b-121">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="e480b-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e480b-122">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e480b-122">**Parameter**</span></span>|<span data-ttu-id="e480b-123">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="e480b-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e480b-124">Nome di dominio DNS</span><span class="sxs-lookup"><span data-stu-id="e480b-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="e480b-125">Nome di dominio di CUCM</span><span class="sxs-lookup"><span data-stu-id="e480b-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="e480b-126">Indirizzo server DNS 1</span><span class="sxs-lookup"><span data-stu-id="e480b-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="e480b-127">l'indirizzo del server DNS desiderato</span><span class="sxs-lookup"><span data-stu-id="e480b-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="e480b-128">Passare a Configurazione- \> Configurazione di sistema - Servizi di \> rete.</span><span class="sxs-lookup"><span data-stu-id="e480b-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="e480b-129">Verificare che la modalità H.323 sia disattivata e che la modalità SIP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="e480b-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="e480b-130">Queste opzioni vengono impostate automaticamente quando l'endpoint viene registrato con CUCM.</span><span class="sxs-lookup"><span data-stu-id="e480b-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="e480b-131">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="e480b-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e480b-132">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e480b-132">**Parameter**</span></span>|<span data-ttu-id="e480b-133">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="e480b-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e480b-134">Modalità H.323</span><span class="sxs-lookup"><span data-stu-id="e480b-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="e480b-135">Off</span><span class="sxs-lookup"><span data-stu-id="e480b-135">Off</span></span> <br/> |
   |<span data-ttu-id="e480b-136">Modalità HTTP</span><span class="sxs-lookup"><span data-stu-id="e480b-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="e480b-137">Attivato</span><span class="sxs-lookup"><span data-stu-id="e480b-137">On</span></span> <br/> |
   | <span data-ttu-id="e480b-138">Modalità SIP</span><span class="sxs-lookup"><span data-stu-id="e480b-138">SIP Mode</span></span> <br/> | <span data-ttu-id="e480b-139">Attivato</span><span class="sxs-lookup"><span data-stu-id="e480b-139">On</span></span> <br/> |
   |<span data-ttu-id="e480b-140">Modalità Telnet</span><span class="sxs-lookup"><span data-stu-id="e480b-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="e480b-141">Attivato</span><span class="sxs-lookup"><span data-stu-id="e480b-141">On</span></span> <br/> |
   |<span data-ttu-id="e480b-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="e480b-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="e480b-143">Attivato</span><span class="sxs-lookup"><span data-stu-id="e480b-143">On</span></span> <br/> |
   |<span data-ttu-id="e480b-144">Modalità XMLAPI</span><span class="sxs-lookup"><span data-stu-id="e480b-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="e480b-145">Attivato</span><span class="sxs-lookup"><span data-stu-id="e480b-145">On</span></span> <br/> |
   
7. <span data-ttu-id="e480b-146">Passare a Configurazione- \> Configurazione sistema- \> SIP.</span><span class="sxs-lookup"><span data-stu-id="e480b-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="e480b-147">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="e480b-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e480b-148">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e480b-148">**Parameter**</span></span>|<span data-ttu-id="e480b-149">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="e480b-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e480b-150">Profilo 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="e480b-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="e480b-151">TCP</span><span class="sxs-lookup"><span data-stu-id="e480b-151">TCP</span></span> <br/> |
   |<span data-ttu-id="e480b-152">Profilo 1 - In uscita</span><span class="sxs-lookup"><span data-stu-id="e480b-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="e480b-153">Off</span><span class="sxs-lookup"><span data-stu-id="e480b-153">Off</span></span> <br/> |
   |<span data-ttu-id="e480b-154">Profilo 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="e480b-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="e480b-155">Attivato</span><span class="sxs-lookup"><span data-stu-id="e480b-155">On</span></span> <br/> |
   |<span data-ttu-id="e480b-156">Profilo 1 - Tipo</span><span class="sxs-lookup"><span data-stu-id="e480b-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="e480b-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="e480b-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="e480b-158">Profilo 1 - URI</span><span class="sxs-lookup"><span data-stu-id="e480b-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="e480b-159">Assegnato automaticamente alla registrazione DISAS</span><span class="sxs-lookup"><span data-stu-id="e480b-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="e480b-160">Proxy 1 - Indirizzo</span><span class="sxs-lookup"><span data-stu-id="e480b-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="e480b-161">Il nome host di CUCM</span><span class="sxs-lookup"><span data-stu-id="e480b-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="e480b-162">I VTC sono ora configurati per l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="e480b-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="e480b-163">Prima che il servizio possa iniziare, è necessario eseguire i passaggi finali sul lato DISS.</span><span class="sxs-lookup"><span data-stu-id="e480b-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="e480b-164">Configurare i dispositivi VTC in CUCM</span><span class="sxs-lookup"><span data-stu-id="e480b-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="e480b-165">Accedi a CUCM e passa ad Amministrazione CM unificato Cisco- \> Dispositivo- \> Telefono- \> Trova.</span><span class="sxs-lookup"><span data-stu-id="e480b-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="e480b-166">Seleziona il dispositivo VTC da configurare.</span><span class="sxs-lookup"><span data-stu-id="e480b-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="e480b-167">Verificare le impostazioni seguenti nella schermata Configurazione telefono, correggendo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e480b-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="e480b-168">Dopo aver modificato o verificato queste impostazioni, fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="e480b-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="e480b-169">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e480b-169">**Parameter**</span></span>|<span data-ttu-id="e480b-170">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="e480b-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e480b-171">Device Information - Phone Button Template</span><span class="sxs-lookup"><span data-stu-id="e480b-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="e480b-172">Standard Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="e480b-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e480b-173">Informazioni dispositivo - Profilo telefono comune</span><span class="sxs-lookup"><span data-stu-id="e480b-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="e480b-174">Profilo telefonico comune standard</span><span class="sxs-lookup"><span data-stu-id="e480b-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="e480b-175">Informazioni dispositivo - Spazio di ricerca chiamate</span><span class="sxs-lookup"><span data-stu-id="e480b-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e480b-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e480b-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e480b-177">Informazioni dispositivo - Spazio di ricerca chiamate AAR</span><span class="sxs-lookup"><span data-stu-id="e480b-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="e480b-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e480b-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e480b-179">Informazioni dispositivo - Elenco gruppi di risorse multimediali</span><span class="sxs-lookup"><span data-stu-id="e480b-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="e480b-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e480b-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e480b-181">Informazioni specifiche del protocollo - Profilo di sicurezza del dispositivo</span><span class="sxs-lookup"><span data-stu-id="e480b-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="e480b-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="e480b-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e480b-183">Informazioni specifiche del protocollo - Rerouting Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="e480b-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="e480b-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e480b-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e480b-185">Informazioni specifiche del protocollo - SUBSCRIBE Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="e480b-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="e480b-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e480b-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e480b-187">Informazioni specifiche del protocollo -Profilo SIP</span><span class="sxs-lookup"><span data-stu-id="e480b-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="e480b-188">Profilo SIP standard per endpoint di telepresenza</span><span class="sxs-lookup"><span data-stu-id="e480b-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="e480b-189">Dopo aver salvato la configurazione VTC, torna alla schermata Configurazione telefono per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e480b-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="e480b-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span><span class="sxs-lookup"><span data-stu-id="e480b-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="e480b-191">Verrà visualizzata la schermata Configurazione numero di directory.</span><span class="sxs-lookup"><span data-stu-id="e480b-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="e480b-192">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="e480b-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="e480b-193">Apportare le modifiche appropriate come mostrato in Informazioni numero directory e Impostazioni numero directory.</span><span class="sxs-lookup"><span data-stu-id="e480b-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="e480b-194">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="e480b-194">**Parameter**</span></span>|<span data-ttu-id="e480b-195">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="e480b-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="e480b-196">Informazioni sul numero di directory - Partizione route</span><span class="sxs-lookup"><span data-stu-id="e480b-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="e480b-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="e480b-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="e480b-198">Impostazioni numero directory - Spazio di ricerca chiamante</span><span class="sxs-lookup"><span data-stu-id="e480b-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e480b-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e480b-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e480b-200">Impostazioni del livello di accesso riservato e della parte alternativa MLPP - Spazio di ricerca chiamate MLPP</span><span class="sxs-lookup"><span data-stu-id="e480b-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="e480b-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e480b-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e480b-202">Riga 1 nel dispositivo - Schermo (ID chiamante)</span><span class="sxs-lookup"><span data-stu-id="e480b-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e480b-203">Come desiderato</span><span class="sxs-lookup"><span data-stu-id="e480b-203">As desired</span></span> <br/> |
   |<span data-ttu-id="e480b-204">Riga 1 nel dispositivo - Visualizzazione ASCII (ID chiamante)</span><span class="sxs-lookup"><span data-stu-id="e480b-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e480b-205">Come desiderato</span><span class="sxs-lookup"><span data-stu-id="e480b-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="e480b-206">Al termine, scorrere fino alla parte superiore dello schermo e premere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="e480b-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="e480b-207">La configurazione è ora completa per questo dispositivo VTC.</span><span class="sxs-lookup"><span data-stu-id="e480b-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="e480b-208">Dovrai ripetere questo processo per altri dispositivi VTC nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e480b-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

