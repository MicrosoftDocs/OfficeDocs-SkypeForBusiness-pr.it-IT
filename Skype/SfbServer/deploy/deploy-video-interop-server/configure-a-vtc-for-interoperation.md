---
title: Configurare un VTC per l'interoperabilità con Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: "Riepilogo: configurare i dispositivi VTC per l'utilizzo con Skype for Business Server."
ms.openlocfilehash: 460ac0a301ee9c9b2cb5bb1b4ca4c1aaf6ee4825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195409"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="69c57-103">Configurare un VTC per l'interoperabilità con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="69c57-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="69c57-104">**Riepilogo:** Configurare i dispositivi VTC per l'utilizzo con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="69c57-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="69c57-105">Dovrai eseguire le procedure di personalizzazione di configurazione seguenti per ogni VTC che si connette al server VIS Skype for business tramite un trunk SIP e un gateway video Cisco Unified Communications Manager (CallManager o CUCM).</span><span class="sxs-lookup"><span data-stu-id="69c57-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="69c57-106">Le impostazioni descritte in questo articolo sono intese solo come esempi di come CUCM può essere configurato per l'utilizzo con un VIS.</span><span class="sxs-lookup"><span data-stu-id="69c57-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="69c57-107">Altre impostazioni e/o usi della funzionalità CUCM alternativa possono essere usati anche per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="69c57-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="69c57-108">Nessuna raccomandazione è implicita sulla configurazione ottimale per uno scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="69c57-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="69c57-109">Configurare un VTC registrato con CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="69c57-110">Accedere al dispositivo Cisco VTC e passare a configurazione-\>configurazione di sistema-\>provisioning.</span><span class="sxs-lookup"><span data-stu-id="69c57-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="69c57-111">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="69c57-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="69c57-112">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="69c57-112">**Parameter**</span></span>|<span data-ttu-id="69c57-113">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="69c57-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="69c57-114">Modalità di provisioning</span><span class="sxs-lookup"><span data-stu-id="69c57-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="69c57-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="69c57-116">Indirizzo ExternalManager</span><span class="sxs-lookup"><span data-stu-id="69c57-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="69c57-117">Nome di dominio completo di CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="69c57-118">Dominio ExternalManager</span><span class="sxs-lookup"><span data-stu-id="69c57-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="69c57-119">Dominio di CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="69c57-120">Passare a configurazione-\>configurazione di sistema\>-rete.</span><span class="sxs-lookup"><span data-stu-id="69c57-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="69c57-121">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="69c57-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="69c57-122">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="69c57-122">**Parameter**</span></span>|<span data-ttu-id="69c57-123">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="69c57-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="69c57-124">Nome di dominio DNS</span><span class="sxs-lookup"><span data-stu-id="69c57-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="69c57-125">Nome di dominio di CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="69c57-126">Indirizzo del server DNS 1</span><span class="sxs-lookup"><span data-stu-id="69c57-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="69c57-127">Indirizzo del server DNS desiderato</span><span class="sxs-lookup"><span data-stu-id="69c57-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="69c57-128">Passare a configurazione-\>configurazione di sistema\>-servizi di rete.</span><span class="sxs-lookup"><span data-stu-id="69c57-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="69c57-129">Verificare che la modalità H. 323 sia disattivata e che la modalità SIP sia attivata.</span><span class="sxs-lookup"><span data-stu-id="69c57-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="69c57-130">Queste opzioni vengono impostate automaticamente quando l'endpoint viene registrato con CUCM.</span><span class="sxs-lookup"><span data-stu-id="69c57-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="69c57-131">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="69c57-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="69c57-132">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="69c57-132">**Parameter**</span></span>|<span data-ttu-id="69c57-133">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="69c57-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="69c57-134">Modalità H. 323</span><span class="sxs-lookup"><span data-stu-id="69c57-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="69c57-135">Disattivare</span><span class="sxs-lookup"><span data-stu-id="69c57-135">Off</span></span> <br/> |
   |<span data-ttu-id="69c57-136">Modalità HTTP</span><span class="sxs-lookup"><span data-stu-id="69c57-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="69c57-137">Nella</span><span class="sxs-lookup"><span data-stu-id="69c57-137">On</span></span> <br/> |
   | <span data-ttu-id="69c57-138">Modalità SIP</span><span class="sxs-lookup"><span data-stu-id="69c57-138">SIP Mode</span></span> <br/> | <span data-ttu-id="69c57-139">Nella</span><span class="sxs-lookup"><span data-stu-id="69c57-139">On</span></span> <br/> |
   |<span data-ttu-id="69c57-140">Modalità Telnet</span><span class="sxs-lookup"><span data-stu-id="69c57-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="69c57-141">Nella</span><span class="sxs-lookup"><span data-stu-id="69c57-141">On</span></span> <br/> |
   |<span data-ttu-id="69c57-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="69c57-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="69c57-143">Nella</span><span class="sxs-lookup"><span data-stu-id="69c57-143">On</span></span> <br/> |
   |<span data-ttu-id="69c57-144">Modalità XMLAPI</span><span class="sxs-lookup"><span data-stu-id="69c57-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="69c57-145">Nella</span><span class="sxs-lookup"><span data-stu-id="69c57-145">On</span></span> <br/> |
   
7. <span data-ttu-id="69c57-146">Passare a configurazione-\>configurazione di sistema\>-SIP.</span><span class="sxs-lookup"><span data-stu-id="69c57-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="69c57-147">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="69c57-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="69c57-148">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="69c57-148">**Parameter**</span></span>|<span data-ttu-id="69c57-149">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="69c57-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="69c57-150">Profilo 1-DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="69c57-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="69c57-151">TCP</span><span class="sxs-lookup"><span data-stu-id="69c57-151">TCP</span></span> <br/> |
   |<span data-ttu-id="69c57-152">Profilo 1-in uscita</span><span class="sxs-lookup"><span data-stu-id="69c57-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="69c57-153">Disattivare</span><span class="sxs-lookup"><span data-stu-id="69c57-153">Off</span></span> <br/> |
   |<span data-ttu-id="69c57-154">Profilo 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="69c57-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="69c57-155">Nella</span><span class="sxs-lookup"><span data-stu-id="69c57-155">On</span></span> <br/> |
   |<span data-ttu-id="69c57-156">Profilo 1-tipo</span><span class="sxs-lookup"><span data-stu-id="69c57-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="69c57-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="69c57-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="69c57-158">Profilo 1-URI</span><span class="sxs-lookup"><span data-stu-id="69c57-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="69c57-159">Assegnato automaticamente alla registrazione di CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="69c57-160">Indirizzo proxy 1</span><span class="sxs-lookup"><span data-stu-id="69c57-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="69c57-161">Nome host della CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="69c57-162">VTC è ora configurato per l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="69c57-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="69c57-163">Prima che il servizio possa iniziare, ci sono passaggi finali da eseguire sul lato CUCM.</span><span class="sxs-lookup"><span data-stu-id="69c57-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="69c57-164">Configurare i dispositivi VTC in CUCM</span><span class="sxs-lookup"><span data-stu-id="69c57-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="69c57-165">Accedere a CUCM e passare a Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span><span class="sxs-lookup"><span data-stu-id="69c57-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="69c57-166">Selezionare il dispositivo VTC da configurare.</span><span class="sxs-lookup"><span data-stu-id="69c57-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="69c57-167">Verificare le impostazioni seguenti nella schermata Configurazione Telefono, correggendo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="69c57-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="69c57-168">Dopo aver modificato o verificato le impostazioni, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="69c57-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="69c57-169">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="69c57-169">**Parameter**</span></span>|<span data-ttu-id="69c57-170">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="69c57-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="69c57-171">Informazioni sul dispositivo-modello di pulsante telefono</span><span class="sxs-lookup"><span data-stu-id="69c57-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="69c57-172">Standard Cisco TelePresence codec C40</span><span class="sxs-lookup"><span data-stu-id="69c57-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="69c57-173">Informazioni sul dispositivo-profilo del telefono comune</span><span class="sxs-lookup"><span data-stu-id="69c57-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="69c57-174">Profilo di telefono comune standard</span><span class="sxs-lookup"><span data-stu-id="69c57-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="69c57-175">Informazioni sul dispositivo: spazio di ricerca chiamante</span><span class="sxs-lookup"><span data-stu-id="69c57-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="69c57-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="69c57-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="69c57-177">Informazioni sul dispositivo-area di ricerca chiamata AAR</span><span class="sxs-lookup"><span data-stu-id="69c57-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="69c57-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="69c57-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="69c57-179">Informazioni sul dispositivo-elenco gruppi risorse multimediali</span><span class="sxs-lookup"><span data-stu-id="69c57-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="69c57-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="69c57-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="69c57-181">Informazioni specifiche sul protocollo-profilo di sicurezza del dispositivo</span><span class="sxs-lookup"><span data-stu-id="69c57-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="69c57-182">Cisco telepresenza codec C40</span><span class="sxs-lookup"><span data-stu-id="69c57-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="69c57-183">Informazioni specifiche del protocollo-reinstradamento delle chiamate nello spazio di ricerca</span><span class="sxs-lookup"><span data-stu-id="69c57-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="69c57-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="69c57-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="69c57-185">Informazioni specifiche per il protocollo-sottoscrivere lo spazio di ricerca</span><span class="sxs-lookup"><span data-stu-id="69c57-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="69c57-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="69c57-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="69c57-187">Informazioni specifiche sul protocollo-profilo SIP</span><span class="sxs-lookup"><span data-stu-id="69c57-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="69c57-188">Profilo SIP standard per endpoint telepresenza</span><span class="sxs-lookup"><span data-stu-id="69c57-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="69c57-189">Dopo aver salvato la configurazione di VTC, passare di nuovo alla schermata di configurazione del telefono per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="69c57-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="69c57-190">Nella parte superiore della schermata del gruppo associazione fare clic sull'associazione per l'interoperabilità video.</span><span class="sxs-lookup"><span data-stu-id="69c57-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="69c57-191">Viene visualizzata la schermata di configurazione del numero di directory.</span><span class="sxs-lookup"><span data-stu-id="69c57-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="69c57-192">Verificare le impostazioni seguenti, correggendo in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="69c57-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="69c57-193">Apportare le modifiche appropriate come mostrato alle informazioni relative al numero di directory e alle impostazioni del numero di directory.</span><span class="sxs-lookup"><span data-stu-id="69c57-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="69c57-194">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="69c57-194">**Parameter**</span></span>|<span data-ttu-id="69c57-195">**Impostazione consigliata**</span><span class="sxs-lookup"><span data-stu-id="69c57-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="69c57-196">Informazioni sul numero di directory-route Partition</span><span class="sxs-lookup"><span data-stu-id="69c57-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="69c57-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="69c57-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="69c57-198">Impostazioni numero directory-chiamata dello spazio di ricerca</span><span class="sxs-lookup"><span data-stu-id="69c57-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="69c57-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="69c57-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="69c57-200">Impostazioni del livello di accesso riservato e del partito alternativo MLPP-MLPP chiamata dello spazio di ricerca</span><span class="sxs-lookup"><span data-stu-id="69c57-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="69c57-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="69c57-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="69c57-202">Linea 1 su Device-display (ID chiamante)</span><span class="sxs-lookup"><span data-stu-id="69c57-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="69c57-203">Come desiderato</span><span class="sxs-lookup"><span data-stu-id="69c57-203">As desired</span></span> <br/> |
   |<span data-ttu-id="69c57-204">Riga 1 sul dispositivo-visualizzazione ASCII (ID chiamante)</span><span class="sxs-lookup"><span data-stu-id="69c57-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="69c57-205">Come desiderato</span><span class="sxs-lookup"><span data-stu-id="69c57-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="69c57-206">Al termine, scorrere fino all'inizio dello schermo e premere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="69c57-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="69c57-207">La configurazione è ora completa per questo dispositivo VTC.</span><span class="sxs-lookup"><span data-stu-id="69c57-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="69c57-208">Sarà necessario ripetere questa procedura per gli altri dispositivi VTC dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="69c57-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

