---
title: Configurare il routing vocale per il routing diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare il routing vocale con il routing diretto di Microsoft Phone System.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530993"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="f1bd6-103">Configurare il routing vocale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="f1bd6-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="f1bd6-104">Questo articolo descrive come configurare il routing vocale per il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="f1bd6-105">Questo è il passaggio 3 dei passaggi seguenti per la configurazione del routing diretto:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="f1bd6-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-106">Step 1.</span></span> [<span data-ttu-id="f1bd6-107">Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="f1bd6-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="f1bd6-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-108">Step 2.</span></span> [<span data-ttu-id="f1bd6-109">Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="f1bd6-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="f1bd6-110">**Passaggio 3. Configurare il routing vocale** (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="f1bd6-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="f1bd6-111">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-111">Step 4.</span></span> [<span data-ttu-id="f1bd6-112">Tradurre i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="f1bd6-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="f1bd6-113">Per informazioni su tutti i passaggi necessari per la configurazione del routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="f1bd6-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="f1bd6-114">Panoramica del routing vocale</span><span class="sxs-lookup"><span data-stu-id="f1bd6-114">Voice routing overview</span></span>

<span data-ttu-id="f1bd6-115">Microsoft Phone System include un meccanismo di routing che consente di inviare una chiamata a un SBC (Session Border Controller) specifico basato su:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="f1bd6-116">Modello di numero definito</span><span class="sxs-lookup"><span data-stu-id="f1bd6-116">The called number pattern</span></span> 
- <span data-ttu-id="f1bd6-117">Il modello di numero chiamato più l'utente specifico che effettua la chiamata</span><span class="sxs-lookup"><span data-stu-id="f1bd6-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="f1bd6-118">SBCs può essere designato come attivo e backup.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="f1bd6-119">Quando l'SBC configurato come attivo non è disponibile per una route di chiamata specifica, la chiamata verrà instradata a un SBC di backup.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="f1bd6-120">Il routing vocale è costituito dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="f1bd6-121">**Criteri di routing vocale** : un contenitore per gli usi PSTN, che può essere assegnato a un utente o a più utenti.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="f1bd6-122">**Usi PSTN** : un contenitore per le route vocali e gli usi PSTN, che possono essere condivisi in criteri di routing vocale diversi.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="f1bd6-123">**Route vocali** : uno schema numerico e un set di gateway PSTN online da usare per le chiamate in cui il numero chiamante corrisponde allo schema.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="f1bd6-124">**Gateway PSTN online** : puntatore a un SBC che memorizza anche la configurazione applicata quando viene inserita una chiamata tramite SBC, ad esempio inoltra P-Asserted-Identity (PAI) o codec preferiti; possono essere aggiunte alle route vocali.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="f1bd6-125">Considerazioni sui criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="f1bd6-125">Voice routing policy considerations</span></span>

<span data-ttu-id="f1bd6-126">Se un utente ha una licenza per il piano di chiamata, le chiamate in uscita dell'utente vengono instradate automaticamente tramite l'infrastruttura PSTN del piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="f1bd6-127">Se si configurano e si assegnano criteri di routing vocale online a un utente del piano chiamante, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composto corrisponde a uno schema numerico definito nel criterio di routing vocale online.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="f1bd6-128">Se c'è una corrispondenza, la chiamata viene instradata tramite il trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="f1bd6-129">Se non è presente alcuna corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="f1bd6-130">Se si configurano e si applicano i criteri di routing vocale online globali (a livello di organizzazione), tutti gli utenti abilitati per la voce della società erediteranno tali criteri, che potrebbero causare chiamate PSTN da parte di utenti del piano chiamante inavvertitamente indirizzati a un trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="f1bd6-131">Se non si vuole che tutti gli utenti usino i criteri di routing vocale globale online, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per la voce.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="f1bd6-132">Esempio 1: routing vocale con un solo utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="f1bd6-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="f1bd6-133">Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="f1bd6-134">**Flusso di chiamata 1 (a sinistra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="f1bd6-135">Se non sono disponibili né sbc1.contoso.biz né sbc2.contoso.biz, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="f1bd6-136">**Chiamata flusso 2 (a destra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene prima indirizzata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="f1bd6-137">Se non è disponibile alcun SBC, verrà provata la route con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="f1bd6-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="f1bd6-138">Se nessuna delle SBCs è disponibile, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="f1bd6-140">In entrambi gli esempi, mentre la route vocale è assegnata alle priorità, il SBCs nelle route viene provato in ordine casuale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="f1bd6-141">Quando due SBC sono configurati in una sola route, il traffico di rete deve essere instradabile tra SBC o media non verrà stabilito nei trasferimenti, perché è possibile che il nuovo invito per il trasferimento venga inviato a un altro SBC nella route.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f1bd6-142">A meno che l'utente non disponga anche di una licenza per il piano di chiamata Microsoft, le chiamate a qualsiasi numero eccetto i numeri corrispondenti ai pattern + 1 425 XXX XX XX o + 1 206 XXX XX XX nella configurazione di esempio vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="f1bd6-143">Se l'utente ha una licenza per il piano di chiamata, la chiamata viene instradata automaticamente in base ai criteri del piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="f1bd6-144">Il piano di chiamate Microsoft si applica automaticamente come ultima route a tutti gli utenti con la licenza per il piano di chiamata Microsoft e non richiede ulteriori configurazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="f1bd6-145">Nell'esempio illustrato nel diagramma seguente viene aggiunta una route vocale per inviare chiamate a tutti gli altri numeri di Stati Uniti e canadesi (chiamate che vanno alla sequenza numerica chiamata + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="f1bd6-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra i criteri di routing vocale con una terza Route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="f1bd6-147">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="f1bd6-148">Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="f1bd6-149">Se l'utente ha solo un sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f1bd6-150">Il valore di priorità per la route "altro + 1" non ha importanza in questo caso perché esiste una sola route che corrisponde al modello + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="f1bd6-151">Se un utente effettua una chiamata a + 1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="f1bd6-152">La tabella seguente riepiloga la configurazione usando tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="f1bd6-153">In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo PSTN "USA e Canada".</span><span class="sxs-lookup"><span data-stu-id="f1bd6-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="f1bd6-154">Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo della rete PSTN è associato al criterio di routing vocale "solo USA".</span><span class="sxs-lookup"><span data-stu-id="f1bd6-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="f1bd6-155">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-155">**PSTN usage**</span></span>|<span data-ttu-id="f1bd6-156">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-156">**Voice route**</span></span>|<span data-ttu-id="f1bd6-157">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-157">**Number pattern**</span></span>|<span data-ttu-id="f1bd6-158">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-158">**Priority**</span></span>|<span data-ttu-id="f1bd6-159">**SBC**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-159">**SBC**</span></span>|<span data-ttu-id="f1bd6-160">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f1bd6-161">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="f1bd6-161">US and Canada</span></span>|<span data-ttu-id="f1bd6-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-162">"Redmond 1"</span></span>|<span data-ttu-id="f1bd6-163">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="f1bd6-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f1bd6-164">1</span><span class="sxs-lookup"><span data-stu-id="f1bd6-164">1</span></span>|<span data-ttu-id="f1bd6-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="f1bd6-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="f1bd6-167">Route attiva per i numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="f1bd6-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f1bd6-168">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="f1bd6-168">US and Canada</span></span>|<span data-ttu-id="f1bd6-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-169">"Redmond 2"</span></span>|<span data-ttu-id="f1bd6-170">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="f1bd6-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f1bd6-171">2</span><span class="sxs-lookup"><span data-stu-id="f1bd6-171">2</span></span>|<span data-ttu-id="f1bd6-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="f1bd6-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="f1bd6-174">Percorso di backup per numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="f1bd6-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f1bd6-175">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="f1bd6-175">US and Canada</span></span>|<span data-ttu-id="f1bd6-176">"Altro + 1"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-176">"Other +1"</span></span>|<span data-ttu-id="f1bd6-177">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="f1bd6-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="f1bd6-178">3</span><span class="sxs-lookup"><span data-stu-id="f1bd6-178">3</span></span>|<span data-ttu-id="f1bd6-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="f1bd6-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="f1bd6-181">Route per i numeri chiamati + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="f1bd6-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="f1bd6-182">Esempio 1: passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="f1bd6-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="f1bd6-183">L'esempio seguente illustra come:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-183">The following example shows how to:</span></span>

1. <span data-ttu-id="f1bd6-184">Creare un singolo utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="f1bd6-185">Configurare tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="f1bd6-186">Creare un criterio di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="f1bd6-187">Assegnare il criterio a un utente di nome Spencer low.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="f1bd6-188">Per eseguire questa procedura, è possibile usare l'interfaccia di [amministrazione di Microsoft teams](#admincenterexample1) o [PowerShell](#powershellexample1) .</span><span class="sxs-lookup"><span data-stu-id="f1bd6-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f1bd6-189">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="f1bd6-190">Passaggio 1: creare l'utilizzo PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="f1bd6-191">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi nell'angolo in alto a destra selezionare **Gestisci record utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="f1bd6-192">Fare clic su **Aggiungi**, digitare **Stati Uniti e Canada** e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="f1bd6-193">Passaggio 2: creare tre route vocali (Redmond 1, Redmond 2 e altre + 1)</span><span class="sxs-lookup"><span data-stu-id="f1bd6-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="f1bd6-194">La procedura seguente descrive come creare una route vocale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="f1bd6-195">Seguire questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e altre + 1 per questo esempio usando le impostazioni descritte nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="f1bd6-196">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi seleziona la scheda **route vocali** .</span><span class="sxs-lookup"><span data-stu-id="f1bd6-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="f1bd6-197">Fare clic su **Aggiungi** e quindi immettere un nome e una descrizione per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="f1bd6-198">Impostare la priorità e specificare il modello di numero composto.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="f1bd6-199">Per registrare un SBC con la route vocale, in **SBCS registrato (facoltativo)**, fare clic su **Aggiungi SBCS**, selezionare il SBCS che si vuole registrare e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="f1bd6-200">Per aggiungere record di utilizzo PSTN, in **record utilizzo PSTN (facoltativo)**, fare clic su **Aggiungi utilizzo PSTN**, selezionare i record PSTN da aggiungere e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="f1bd6-201">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="f1bd6-202">Passaggio 3: creare un criterio di routing vocale denominato "solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio</span><span class="sxs-lookup"><span data-stu-id="f1bd6-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="f1bd6-203">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing** vocale e quindi fai clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="f1bd6-204">Digitare **US solo** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="f1bd6-205">In **record utilizzo** PSTN fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="f1bd6-206">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-206">Click **Save**.</span></span>

<span data-ttu-id="f1bd6-207">Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f1bd6-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="f1bd6-208">Passaggio 4: assegnare i criteri di routing vocale a un utente di nome Spencer low</span><span class="sxs-lookup"><span data-stu-id="f1bd6-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="f1bd6-209">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f1bd6-210">Fare clic su **criteri** e quindi fare clic su **modifica** accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="f1bd6-211">In **criteri di routing vocale** selezionare il criterio "solo Stati Uniti" e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="f1bd6-212">Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f1bd6-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f1bd6-213">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1bd6-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="f1bd6-214">Passaggio 1: creare l'utilizzo PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="f1bd6-215">In una sessione remota di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="f1bd6-216">Verificare che l'utilizzo sia stato creato immettendo:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="f1bd6-217">Che restituisce un elenco di nomi che possono essere troncati:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="f1bd6-218">L'esempio seguente mostra il risultato dell'eseguire il `(Get-CSOnlinePSTNUsage).usage` comando di PowerShell per visualizzare i nomi completi (non troncati):</span><span class="sxs-lookup"><span data-stu-id="f1bd6-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="f1bd6-219">Passaggio 2: creare tre route vocali (Redmond 1, Redmond 2 e altre + 1)</span><span class="sxs-lookup"><span data-stu-id="f1bd6-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="f1bd6-220">Per creare la route "Redmond 1", in una sessione di PowerShell in Skype for business online, immettere:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="f1bd6-221">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="f1bd6-222">Per creare la route Redmond 2, immettere:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="f1bd6-223">Per creare l'altra route + 1, immettere:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="f1bd6-224">Verificare che l'espressione regolare nell'attributo NumberPattern sia valida.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="f1bd6-225">Puoi testarlo usando questo sito Web: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="f1bd6-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="f1bd6-226">In alcuni casi, è necessario instradare tutte le chiamate allo stesso SBC; usare-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="f1bd6-227">Instradare tutte le chiamate allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="f1bd6-228">Verificare di aver configurato correttamente la route eseguendo il comando di `Get-CSOnlineVoiceRoute` PowerShell usando le opzioni come illustrato:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="f1bd6-229">Che dovrebbe restituire:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-229">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority               : 1
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc1.contoso.biz, sbc2.contoso.biz}
Name             : Redmond 1
Identity        : Redmond 2 
Priority               : 2
Description         : 
NumberPattern         : ^\+1(425|206) (\d{7})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc3.contoso.biz, sbc4.contoso.biz}
Name             : Redmond 2
    
Identity        : Other +1 
Priority               : 4
Description         : 
NumberPattern         : ^\+1(\d{10})$
OnlinePstnUsages     : {US and Canada}     
OnlinePstnGatewayList    : {sbc5.contoso.biz, sbc6.contoso.biz}
Name             : Other +1
</pre>

<span data-ttu-id="f1bd6-230">Nell'esempio, la route "altro + 1" è stata assegnata automaticamente la priorità 4.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="f1bd6-231">Passaggio 3: creare un criterio di routing vocale denominato "solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio</span><span class="sxs-lookup"><span data-stu-id="f1bd6-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="f1bd6-232">In una sessione di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="f1bd6-233">Il risultato è illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="f1bd6-234">Passaggio 4: assegnare i criteri di routing vocale a un utente di nome Spencer low</span><span class="sxs-lookup"><span data-stu-id="f1bd6-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="f1bd6-235">In una sessione di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="f1bd6-236">Convalidare l'assegnazione dei criteri immettendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="f1bd6-237">Il comando restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="f1bd6-238">Esempio 2: routing vocale con più usi PSTN</span><span class="sxs-lookup"><span data-stu-id="f1bd6-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="f1bd6-239">Il criterio di routing vocale creato nell'esempio 1 consente solo le chiamate ai numeri di telefono negli Stati Uniti e in Canada, a meno che l'utente non venga assegnato anche alla licenza per il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="f1bd6-240">Nell'esempio seguente puoi creare il criterio di routing vocale "nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="f1bd6-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="f1bd6-241">Il criterio riutilizza l'utilizzo PSTN "Stati Uniti e Canada" creato nell'esempio 1, nonché il nuovo utilizzo PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="f1bd6-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="f1bd6-242">Questo criterio instrada tutte le altre chiamate a SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="f1bd6-243">Gli esempi illustrati assegnano il criterio solo USA all'utente Spencer low e il criterio nessuna restrizione per l'utente John Woods in modo che il routing si verifichi come segue:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="f1bd6-244">Solo criteri di Spencer low-US.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="f1bd6-245">Le chiamate sono consentite solo ai numeri Stati Uniti e canadesi.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="f1bd6-246">Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBCs.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="f1bd6-247">I numeri non Stati Uniti non verranno instradati, a meno che non venga assegnata all'utente la licenza per il piano chiamante.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="f1bd6-248">John Woods-politica internazionale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-248">John Woods – International policy.</span></span>  <span data-ttu-id="f1bd6-249">Le chiamate sono consentite a qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-249">Calls are allowed to any number.</span></span> <span data-ttu-id="f1bd6-250">Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBCs.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="f1bd6-251">I numeri non Stati Uniti verranno instradati usando sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra il criterio di routing vocale assegnato all'utente Spencer low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="f1bd6-253">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="f1bd6-254">Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="f1bd6-255">Se l'utente ha solo sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra il criterio di routing vocale assegnato all'utente John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="f1bd6-257">Nella tabella seguente vengono riepilogati i criteri di routing "nessuna restrizione" denominazioni di utilizzo e route vocali.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="f1bd6-258">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-258">**PSTN usage**</span></span>|<span data-ttu-id="f1bd6-259">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-259">**Voice route**</span></span>|<span data-ttu-id="f1bd6-260">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-260">**Number pattern**</span></span>|<span data-ttu-id="f1bd6-261">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-261">**Priority**</span></span>|<span data-ttu-id="f1bd6-262">**SBC**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-262">**SBC**</span></span>|<span data-ttu-id="f1bd6-263">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f1bd6-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f1bd6-264">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="f1bd6-264">US and Canada</span></span>|<span data-ttu-id="f1bd6-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-265">"Redmond 1"</span></span>|<span data-ttu-id="f1bd6-266">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="f1bd6-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f1bd6-267">1</span><span class="sxs-lookup"><span data-stu-id="f1bd6-267">1</span></span>|<span data-ttu-id="f1bd6-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="f1bd6-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="f1bd6-270">Route attiva per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="f1bd6-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f1bd6-271">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="f1bd6-271">US and Canada</span></span>|<span data-ttu-id="f1bd6-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-272">"Redmond 2"</span></span>|<span data-ttu-id="f1bd6-273">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="f1bd6-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f1bd6-274">2</span><span class="sxs-lookup"><span data-stu-id="f1bd6-274">2</span></span>|<span data-ttu-id="f1bd6-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="f1bd6-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="f1bd6-277">Percorso di backup per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="f1bd6-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f1bd6-278">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="f1bd6-278">US and Canada</span></span>|<span data-ttu-id="f1bd6-279">"Altro + 1"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-279">"Other +1"</span></span>|<span data-ttu-id="f1bd6-280">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="f1bd6-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="f1bd6-281">3</span><span class="sxs-lookup"><span data-stu-id="f1bd6-281">3</span></span>|<span data-ttu-id="f1bd6-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="f1bd6-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="f1bd6-284">Route per i numeri dei chiamanti + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="f1bd6-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="f1bd6-285">Internazionale</span><span class="sxs-lookup"><span data-stu-id="f1bd6-285">International</span></span>|<span data-ttu-id="f1bd6-286">Internazionale</span><span class="sxs-lookup"><span data-stu-id="f1bd6-286">International</span></span>|<span data-ttu-id="f1bd6-287">\d +</span><span class="sxs-lookup"><span data-stu-id="f1bd6-287">\d+</span></span>|<span data-ttu-id="f1bd6-288">4</span><span class="sxs-lookup"><span data-stu-id="f1bd6-288">4</span></span>|<span data-ttu-id="f1bd6-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="f1bd6-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f1bd6-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="f1bd6-291">Route per qualsiasi modello di numero</span><span class="sxs-lookup"><span data-stu-id="f1bd6-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="f1bd6-292">L'ordine degli usi PSTN nei criteri di routing vocale è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="f1bd6-293">Gli usi vengono applicati in ordine e se viene trovata una corrispondenza nel primo utilizzo, gli altri usi non vengono mai valutati.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="f1bd6-294">L'utilizzo PSTN "internazionale" deve essere posizionato dopo l'utilizzo PSTN "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="f1bd6-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="f1bd6-295">Per modificare l'ordine degli usi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="f1bd6-296">Ad esempio, per cambiare l'ordine da "Stati Uniti e Canada" prima e "internazionale" in secondo luogo, eseguire l'ordine inverso:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="f1bd6-297">La priorità per le route vocali "altro + 1" e "internazionale" viene assegnata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="f1bd6-298">Gli utenti non hanno importanza se hanno priorità più basse rispetto a "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="f1bd6-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="f1bd6-299">Esempio 2: passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="f1bd6-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="f1bd6-300">L'esempio seguente illustra come:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-300">The following example shows how to:</span></span>

1. <span data-ttu-id="f1bd6-301">Creare un nuovo utilizzo PSTN denominato internazionale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="f1bd6-302">Creare una nuova route vocale denominata internazionale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="f1bd6-303">Creare un criterio di routing vocale denominato nessuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="f1bd6-304">Assegnare il criterio all'utente John Woods.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="f1bd6-305">Per eseguire questa procedura, è possibile usare l'interfaccia di [amministrazione di Microsoft teams](#admincenterexample2) o [PowerShell](#powershellexample2) .</span><span class="sxs-lookup"><span data-stu-id="f1bd6-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f1bd6-306">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="f1bd6-307">Passaggio 1: creare l'utilizzo PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="f1bd6-308">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi nell'angolo in alto a destra selezionare **Gestisci record utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="f1bd6-309">Fare clic su **Aggiungi**, digitare **internazionale** e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="f1bd6-310">Passaggio 2: creare la route vocale "internazionale"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="f1bd6-311">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto** vocale e quindi seleziona la scheda **route vocali** .</span><span class="sxs-lookup"><span data-stu-id="f1bd6-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="f1bd6-312">Fare clic su **Aggiungi**, immettere "internazionale" come nome e quindi aggiungere la descrizione.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="f1bd6-313">Imposta la priorità su 4 e quindi imposta il modello di numero composto su \d +.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="f1bd6-314">In **SBCS registrato (facoltativo)** fare clic su **Aggiungi SBCs**, selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="f1bd6-315">In **record utilizzo PSTN (facoltativo)** fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "internazionale" e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="f1bd6-316">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="f1bd6-317">Passaggio 3: creare un criterio di routing vocale denominato "nessuna restrizione" e aggiungere gli utilizzi PSTN "Stati Uniti e Canada" e "internazionale" al criterio</span><span class="sxs-lookup"><span data-stu-id="f1bd6-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="f1bd6-318">Gli usi PSTN "Stati Uniti e Canada" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="f1bd6-319">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing** vocale e quindi fai clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="f1bd6-320">Digitare **Nessuna restrizione** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="f1bd6-321">In **record utilizzo** PSTN fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="f1bd6-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="f1bd6-322">Fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-322">Click **Apply**.</span></span>

    <span data-ttu-id="f1bd6-323">Prendere nota dell'ordine degli usi PSTN:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="f1bd6-324">Se una chiamata effettuata al numero "+ 1 425 XXX XX XX" con gli usi configurati come in questo esempio, la chiamata segue la route impostata nell'uso "USA e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="f1bd6-325">La chiamata viene quindi instradata tramite sbc1.contoso.biz e sbc2.contoso.biz prima, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="f1bd6-326">Se l'utilizzo PSTN "internazionale" è prima di "Stati Uniti e Canada", le chiamate a + 1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="f1bd6-327">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-327">Click **Save**.</span></span>

<span data-ttu-id="f1bd6-328">Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f1bd6-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="f1bd6-329">Passaggio 4: assegnare i criteri di routing vocale a un utente di nome John Woods</span><span class="sxs-lookup"><span data-stu-id="f1bd6-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="f1bd6-330">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f1bd6-331">Fare clic su **criteri** e quindi fare clic su **modifica** accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="f1bd6-332">In **criteri di routing vocale** selezionare il criterio "nessuna restrizione" e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="f1bd6-333">Il risultato è che il criterio vocale applicato alle chiamate di John Woods è senza restrizioni e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f1bd6-334">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1bd6-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="f1bd6-335">Passaggio 1: creare l'utilizzo PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="f1bd6-336">In una sessione remota di PowerShell in Skype for business online, immettere:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="f1bd6-337">Passaggio 2: creare una nuova route vocale denominata "internazionale"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="f1bd6-338">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="f1bd6-339">Passaggio 3: creare un criterio di routing vocale denominato "nessuna restrizione"</span><span class="sxs-lookup"><span data-stu-id="f1bd6-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="f1bd6-340">L'utilizzo PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="f1bd6-341">Prendere nota dell'ordine degli usi PSTN:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="f1bd6-342">Se una chiamata effettuata al numero "+ 1 425 XXX XX XX" con gli usi configurati come nell'esempio seguente, la chiamata segue la route impostata nell'uso "USA e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="f1bd6-343">La chiamata viene quindi instradata tramite sbc1.contoso.biz e sbc2.contoso.biz prima, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="f1bd6-344">Se l'utilizzo PSTN "internazionale" è prima di "Stati Uniti e Canada", le chiamate a + 1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="f1bd6-345">Immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="f1bd6-346">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="f1bd6-347">Passaggio 4: assegnare i criteri di routing vocale all'utente di nome John Woods</span><span class="sxs-lookup"><span data-stu-id="f1bd6-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="f1bd6-348">Verificare quindi l'assegnazione usando il comando:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="f1bd6-349">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="f1bd6-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="f1bd6-350">Il risultato è che il criterio vocale applicato alle chiamate di John Woods è illimitato e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.</span><span class="sxs-lookup"><span data-stu-id="f1bd6-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1bd6-351">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1bd6-351">See also</span></span>

[<span data-ttu-id="f1bd6-352">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="f1bd6-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="f1bd6-353">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="f1bd6-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
