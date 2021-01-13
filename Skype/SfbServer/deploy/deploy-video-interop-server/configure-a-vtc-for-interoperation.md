---
title: Configurare un videoconferenza per l'interoperabilità con Skype for Business Server
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
description: "Riepilogo: configurare i dispositivi di videoconferenza per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802076"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="b23f9-103">Configurare un videoconferenza per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b23f9-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="b23f9-104">**Riepilogo:** Configurare i dispositivi di videoconferenza per l'utilizzo con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b23f9-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="b23f9-105">Sarà necessario eseguire le procedure di personalizzazione di configurazione seguenti per ogni videoconferenza che si connette a Skype for Business Server tramite un trunk SIP e un gateway video di Cisco Unified Communications Manager (CallManager o un CUCM).</span><span class="sxs-lookup"><span data-stu-id="b23f9-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="b23f9-106">Le impostazioni descritte in questa sezione sono intese solo come esempi di come un CUCM può essere configurato per l'utilizzo con un VIS.</span><span class="sxs-lookup"><span data-stu-id="b23f9-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="b23f9-107">È inoltre possibile utilizzare altre impostazioni e/o usi della funzionalità un CUCM alternativa per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="b23f9-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="b23f9-108">Nessuna raccomandazione è implicita sulla configurazione ottimale per uno scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="b23f9-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="b23f9-109">Configurare un videoconferenza registrato con un CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="b23f9-110">Accedere al dispositivo Cisco videoconferenza e passare a configurazione-sistema di configurazione \> - \> provisioning.</span><span class="sxs-lookup"><span data-stu-id="b23f9-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="b23f9-111">Verificare le impostazioni seguenti, correggendo i valori necessari:</span><span class="sxs-lookup"><span data-stu-id="b23f9-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b23f9-112">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="b23f9-112">**Parameter**</span></span>|<span data-ttu-id="b23f9-113">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="b23f9-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b23f9-114">Modalità di provisioning</span><span class="sxs-lookup"><span data-stu-id="b23f9-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="b23f9-115">UN CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="b23f9-116">Indirizzo ExternalManager</span><span class="sxs-lookup"><span data-stu-id="b23f9-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="b23f9-117">FQDN di un CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="b23f9-118">Dominio ExternalManager</span><span class="sxs-lookup"><span data-stu-id="b23f9-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="b23f9-119">Dominio di un CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="b23f9-120">Accedere a configurazione- \> sistema di configurazione- \> rete.</span><span class="sxs-lookup"><span data-stu-id="b23f9-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="b23f9-121">Verificare le impostazioni seguenti, correggendo i valori necessari:</span><span class="sxs-lookup"><span data-stu-id="b23f9-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b23f9-122">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="b23f9-122">**Parameter**</span></span>|<span data-ttu-id="b23f9-123">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="b23f9-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b23f9-124">Nome di dominio DNS</span><span class="sxs-lookup"><span data-stu-id="b23f9-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="b23f9-125">Nome di dominio di un CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="b23f9-126">Indirizzo del server DNS 1</span><span class="sxs-lookup"><span data-stu-id="b23f9-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="b23f9-127">l'indirizzo del server DNS desiderato</span><span class="sxs-lookup"><span data-stu-id="b23f9-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="b23f9-128">Accedere a configurazione- \> sistema di configurazione- \> servizi di rete.</span><span class="sxs-lookup"><span data-stu-id="b23f9-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="b23f9-129">Verificare che la modalità H. 323 sia disattivata e che la modalità SIP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="b23f9-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="b23f9-130">Queste opzioni vengono impostate automaticamente quando l'endpoint è registrato con un CUCM.</span><span class="sxs-lookup"><span data-stu-id="b23f9-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="b23f9-131">Verificare le impostazioni seguenti, correggendo i valori necessari:</span><span class="sxs-lookup"><span data-stu-id="b23f9-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b23f9-132">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="b23f9-132">**Parameter**</span></span>|<span data-ttu-id="b23f9-133">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="b23f9-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b23f9-134">Modalità H. 323</span><span class="sxs-lookup"><span data-stu-id="b23f9-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="b23f9-135">Off</span><span class="sxs-lookup"><span data-stu-id="b23f9-135">Off</span></span> <br/> |
   |<span data-ttu-id="b23f9-136">Modalità HTTP</span><span class="sxs-lookup"><span data-stu-id="b23f9-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="b23f9-137">Attivato</span><span class="sxs-lookup"><span data-stu-id="b23f9-137">On</span></span> <br/> |
   | <span data-ttu-id="b23f9-138">Modalità SIP</span><span class="sxs-lookup"><span data-stu-id="b23f9-138">SIP Mode</span></span> <br/> | <span data-ttu-id="b23f9-139">Attivato</span><span class="sxs-lookup"><span data-stu-id="b23f9-139">On</span></span> <br/> |
   |<span data-ttu-id="b23f9-140">Modalità Telnet</span><span class="sxs-lookup"><span data-stu-id="b23f9-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="b23f9-141">Attivato</span><span class="sxs-lookup"><span data-stu-id="b23f9-141">On</span></span> <br/> |
   |<span data-ttu-id="b23f9-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="b23f9-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="b23f9-143">Attivato</span><span class="sxs-lookup"><span data-stu-id="b23f9-143">On</span></span> <br/> |
   |<span data-ttu-id="b23f9-144">Modalità XMLAPI</span><span class="sxs-lookup"><span data-stu-id="b23f9-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="b23f9-145">Attivato</span><span class="sxs-lookup"><span data-stu-id="b23f9-145">On</span></span> <br/> |
   
7. <span data-ttu-id="b23f9-146">Passare a configurazione- \> sistema di configurazione- \> SIP.</span><span class="sxs-lookup"><span data-stu-id="b23f9-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="b23f9-147">Verificare le impostazioni seguenti, correggendo i valori necessari:</span><span class="sxs-lookup"><span data-stu-id="b23f9-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b23f9-148">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="b23f9-148">**Parameter**</span></span>|<span data-ttu-id="b23f9-149">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="b23f9-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b23f9-150">Profile 1-DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="b23f9-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="b23f9-151">TCP</span><span class="sxs-lookup"><span data-stu-id="b23f9-151">TCP</span></span> <br/> |
   |<span data-ttu-id="b23f9-152">Profilo 1-in uscita</span><span class="sxs-lookup"><span data-stu-id="b23f9-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="b23f9-153">Off</span><span class="sxs-lookup"><span data-stu-id="b23f9-153">Off</span></span> <br/> |
   |<span data-ttu-id="b23f9-154">Profile 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="b23f9-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="b23f9-155">Attivato</span><span class="sxs-lookup"><span data-stu-id="b23f9-155">On</span></span> <br/> |
   |<span data-ttu-id="b23f9-156">Profilo 1-tipo</span><span class="sxs-lookup"><span data-stu-id="b23f9-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="b23f9-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="b23f9-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="b23f9-158">Profilo 1-URI</span><span class="sxs-lookup"><span data-stu-id="b23f9-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="b23f9-159">Assegnato automaticamente alla registrazione di un CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="b23f9-160">Proxy 1-indirizzo</span><span class="sxs-lookup"><span data-stu-id="b23f9-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="b23f9-161">Il nome host del un CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="b23f9-162">La videoconferenza è ora configurata per l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b23f9-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="b23f9-163">Prima dell'inizio del servizio, è possibile eseguire le operazioni finali sul un CUCM.</span><span class="sxs-lookup"><span data-stu-id="b23f9-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="b23f9-164">Configurare i dispositivi di videoconferenza in un CUCM</span><span class="sxs-lookup"><span data-stu-id="b23f9-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="b23f9-165">Accedere a un CUCM e accedere a Cisco Unified CM Administration- \> Device- \> Phone- \> Find.</span><span class="sxs-lookup"><span data-stu-id="b23f9-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="b23f9-166">Selezionare il dispositivo di videoconferenza da configurare.</span><span class="sxs-lookup"><span data-stu-id="b23f9-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="b23f9-167">Verificare le impostazioni seguenti nella schermata Configurazione Telefono, correggendo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b23f9-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="b23f9-168">Dopo aver modificato o verificato queste impostazioni, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b23f9-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="b23f9-169">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="b23f9-169">**Parameter**</span></span>|<span data-ttu-id="b23f9-170">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="b23f9-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b23f9-171">Informazioni sul dispositivo-modello di pulsante del telefono</span><span class="sxs-lookup"><span data-stu-id="b23f9-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="b23f9-172">Codec di telepresenza Cisco standard C40</span><span class="sxs-lookup"><span data-stu-id="b23f9-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="b23f9-173">Informazioni sul dispositivo-profilo comune del telefono</span><span class="sxs-lookup"><span data-stu-id="b23f9-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="b23f9-174">Profilo standard per i telefoni comuni</span><span class="sxs-lookup"><span data-stu-id="b23f9-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="b23f9-175">Informazioni sul dispositivo-spazio di ricerca di chiamata</span><span class="sxs-lookup"><span data-stu-id="b23f9-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="b23f9-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b23f9-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b23f9-177">Informazioni sui dispositivi-AAR che chiama lo spazio di ricerca</span><span class="sxs-lookup"><span data-stu-id="b23f9-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="b23f9-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b23f9-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b23f9-179">Informazioni sul dispositivo-elenco dei gruppi di risorse multimediali</span><span class="sxs-lookup"><span data-stu-id="b23f9-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="b23f9-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b23f9-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b23f9-181">Informazioni specifiche del protocollo-profilo di sicurezza del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b23f9-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="b23f9-182">Codec di telepresenza Cisco C40</span><span class="sxs-lookup"><span data-stu-id="b23f9-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="b23f9-183">Informazioni specifiche del protocollo-rerouting delle chiamate nello spazio di ricerca</span><span class="sxs-lookup"><span data-stu-id="b23f9-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="b23f9-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b23f9-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b23f9-185">Informazioni specifiche del protocollo-SUBSCRIBE Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="b23f9-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="b23f9-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b23f9-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b23f9-187">Informazioni specifiche del protocollo-profilo SIP</span><span class="sxs-lookup"><span data-stu-id="b23f9-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="b23f9-188">Profilo SIP standard per endpoint di telepresenza</span><span class="sxs-lookup"><span data-stu-id="b23f9-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="b23f9-189">Dopo aver salvato la configurazione di videoconferenza, passare alla schermata di configurazione del telefono per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b23f9-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="b23f9-190">Nella parte superiore dello schermo del gruppo di associazione fare clic sull'associazione per l'interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="b23f9-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="b23f9-191">Viene visualizzata la schermata di configurazione del numero di directory.</span><span class="sxs-lookup"><span data-stu-id="b23f9-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="b23f9-192">Verificare le impostazioni seguenti, correggendo i valori necessari:</span><span class="sxs-lookup"><span data-stu-id="b23f9-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="b23f9-193">Apportare le modifiche appropriate come mostrato alle informazioni sul numero di directory e le impostazioni dei numeri di directory.</span><span class="sxs-lookup"><span data-stu-id="b23f9-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="b23f9-194">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="b23f9-194">**Parameter**</span></span>|<span data-ttu-id="b23f9-195">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="b23f9-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="b23f9-196">Informazioni sul numero di directory-route Partition</span><span class="sxs-lookup"><span data-stu-id="b23f9-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="b23f9-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="b23f9-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="b23f9-198">Impostazioni del numero di directory-chiamata dello spazio di ricerca</span><span class="sxs-lookup"><span data-stu-id="b23f9-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="b23f9-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b23f9-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b23f9-200">Impostazioni di MLPP Party alternativo e livello di accesso riservato-MLPP Calling Search Space</span><span class="sxs-lookup"><span data-stu-id="b23f9-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="b23f9-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b23f9-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b23f9-202">Riga 1 del dispositivo-visualizzazione (ID chiamante)</span><span class="sxs-lookup"><span data-stu-id="b23f9-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="b23f9-203">Come desiderato</span><span class="sxs-lookup"><span data-stu-id="b23f9-203">As desired</span></span> <br/> |
   |<span data-ttu-id="b23f9-204">Riga 1 del dispositivo-visualizzazione ASCII (ID chiamante)</span><span class="sxs-lookup"><span data-stu-id="b23f9-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="b23f9-205">Come desiderato</span><span class="sxs-lookup"><span data-stu-id="b23f9-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="b23f9-206">Al termine, scorrere fino alla parte superiore dello schermo e premere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b23f9-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="b23f9-207">La configurazione è ora completata per il dispositivo videoconferenza.</span><span class="sxs-lookup"><span data-stu-id="b23f9-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="b23f9-208">Sarà necessario ripetere questa procedura per gli altri dispositivi di videoconferenza nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b23f9-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

