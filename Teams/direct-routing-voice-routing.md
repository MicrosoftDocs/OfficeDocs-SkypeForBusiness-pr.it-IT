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
ms.openlocfilehash: 37343ad177e3408f94103296509e4b9bfc8ea759
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359412"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="6b2eb-103">Configurare il routing vocale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="6b2eb-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="6b2eb-104">Questo articolo descrive come configurare il routing vocale per il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="6b2eb-105">Questo è il passaggio 3 dei passaggi seguenti per la configurazione del routing diretto:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="6b2eb-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-106">Step 1.</span></span> [<span data-ttu-id="6b2eb-107">Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="6b2eb-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="6b2eb-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-108">Step 2.</span></span> [<span data-ttu-id="6b2eb-109">Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="6b2eb-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="6b2eb-110">**Passaggio 3. Configurare il routing vocale** (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="6b2eb-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="6b2eb-111">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-111">Step 4.</span></span> [<span data-ttu-id="6b2eb-112">Tradurre i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="6b2eb-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="6b2eb-113">Per informazioni su tutti i passaggi necessari per la configurazione del routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="6b2eb-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="6b2eb-114">Panoramica del routing vocale</span><span class="sxs-lookup"><span data-stu-id="6b2eb-114">Voice routing overview</span></span>

<span data-ttu-id="6b2eb-115">Microsoft Phone System include un meccanismo di routing che consente di inviare una chiamata a un SBC (Session Border Controller) specifico basato su:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="6b2eb-116">Modello di numero definito</span><span class="sxs-lookup"><span data-stu-id="6b2eb-116">The called number pattern</span></span> 
- <span data-ttu-id="6b2eb-117">Il modello di numero chiamato più l'utente specifico che effettua la chiamata</span><span class="sxs-lookup"><span data-stu-id="6b2eb-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="6b2eb-118">SBCs può essere designato come attivo e backup.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="6b2eb-119">Quando l'SBC configurato come attivo non è disponibile per una route di chiamata specifica, la chiamata verrà instradata a un SBC di backup.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="6b2eb-120">Il routing vocale è costituito dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="6b2eb-121">**Criteri di routing vocale** : un contenitore per gli usi PSTN, che può essere assegnato a un utente o a più utenti.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="6b2eb-122">**Usi PSTN** : un contenitore per le route vocali e gli usi PSTN, che possono essere condivisi in criteri di routing vocale diversi.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="6b2eb-123">**Route vocali** : uno schema numerico e un set di gateway PSTN online da usare per le chiamate in cui il numero chiamante corrisponde allo schema.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="6b2eb-124">**Gateway PSTN online** : puntatore a un SBC che memorizza anche la configurazione applicata quando viene inserita una chiamata tramite SBC, ad esempio inoltra P-Asserted-Identity (PAI) o codec preferiti; possono essere aggiunte alle route vocali.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="6b2eb-125">Considerazioni sui criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="6b2eb-125">Voice routing policy considerations</span></span>

<span data-ttu-id="6b2eb-126">Se un utente ha una licenza per il piano di chiamata, le chiamate in uscita dell'utente vengono instradate automaticamente tramite l'infrastruttura PSTN del piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="6b2eb-127">Se si configurano e si assegnano criteri di routing vocale online a un utente del piano chiamante, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composto corrisponde a uno schema numerico definito nel criterio di routing vocale online.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="6b2eb-128">Se c'è una corrispondenza, la chiamata viene instradata tramite il trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="6b2eb-129">Se non è presente alcuna corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="6b2eb-130">Se si configurano e si applicano i criteri di routing vocale online globali (a livello di organizzazione), tutti gli utenti abilitati per la voce della società erediteranno tali criteri, che potrebbero causare chiamate PSTN da parte di utenti del piano chiamante inavvertitamente indirizzati a un trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="6b2eb-131">Se non si vuole che tutti gli utenti usino i criteri di routing vocale globale online, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per la voce.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="6b2eb-132">Esempio 1: routing vocale con un solo utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="6b2eb-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="6b2eb-133">Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="6b2eb-134">**Flusso di chiamata 1 (a sinistra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="6b2eb-135">Se non sono disponibili né sbc1.contoso.biz né sbc2.contoso.biz, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="6b2eb-136">**Chiamata flusso 2 (a destra):** Se un utente effettua una chiamata a + 1 425 XXX XX XX o + 1 206 XXX XX XX, la chiamata viene prima indirizzata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="6b2eb-137">Se non è disponibile alcun SBC, verrà provata la route con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="6b2eb-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="6b2eb-138">Se nessuna delle SBCs è disponibile, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="6b2eb-140">In entrambi gli esempi, mentre la route vocale è assegnata alle priorità, il SBCs nelle route viene provato in ordine casuale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6b2eb-141">A meno che l'utente non disponga anche di una licenza per il piano di chiamata Microsoft, le chiamate a qualsiasi numero eccetto i numeri corrispondenti ai pattern + 1 425 XXX XX XX o + 1 206 XXX XX XX nella configurazione di esempio vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="6b2eb-142">Se l'utente ha una licenza per il piano di chiamata, la chiamata viene instradata automaticamente in base ai criteri del piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="6b2eb-143">Il piano di chiamate Microsoft si applica automaticamente come ultima route a tutti gli utenti con la licenza per il piano di chiamata Microsoft e non richiede ulteriori configurazioni di routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="6b2eb-144">Nell'esempio illustrato nel diagramma seguente viene aggiunta una route vocale per inviare chiamate a tutti gli altri numeri di Stati Uniti e canadesi (chiamate che vanno alla sequenza numerica chiamata + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="6b2eb-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra i criteri di routing vocale con una terza Route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="6b2eb-146">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="6b2eb-147">Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="6b2eb-148">Se l'utente ha solo un sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6b2eb-149">Il valore di priorità per la route "altro + 1" non ha importanza in questo caso perché esiste una sola route che corrisponde al modello + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="6b2eb-150">Se un utente effettua una chiamata a + 1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="6b2eb-151">La tabella seguente riepiloga la configurazione usando tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="6b2eb-152">In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo PSTN "USA e Canada".</span><span class="sxs-lookup"><span data-stu-id="6b2eb-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="6b2eb-153">Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo della rete PSTN è associato al criterio di routing vocale "solo USA".</span><span class="sxs-lookup"><span data-stu-id="6b2eb-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="6b2eb-154">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-154">**PSTN usage**</span></span>|<span data-ttu-id="6b2eb-155">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-155">**Voice route**</span></span>|<span data-ttu-id="6b2eb-156">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-156">**Number pattern**</span></span>|<span data-ttu-id="6b2eb-157">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-157">**Priority**</span></span>|<span data-ttu-id="6b2eb-158">**SBC**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-158">**SBC**</span></span>|<span data-ttu-id="6b2eb-159">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b2eb-160">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="6b2eb-160">US and Canada</span></span>|<span data-ttu-id="6b2eb-161">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-161">"Redmond 1"</span></span>|<span data-ttu-id="6b2eb-162">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="6b2eb-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="6b2eb-163">1</span><span class="sxs-lookup"><span data-stu-id="6b2eb-163">1</span></span>|<span data-ttu-id="6b2eb-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="6b2eb-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="6b2eb-166">Route attiva per i numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="6b2eb-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="6b2eb-167">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="6b2eb-167">US and Canada</span></span>|<span data-ttu-id="6b2eb-168">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-168">"Redmond 2"</span></span>|<span data-ttu-id="6b2eb-169">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="6b2eb-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="6b2eb-170">2</span><span class="sxs-lookup"><span data-stu-id="6b2eb-170">2</span></span>|<span data-ttu-id="6b2eb-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="6b2eb-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="6b2eb-173">Percorso di backup per numeri denominati + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="6b2eb-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="6b2eb-174">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="6b2eb-174">US and Canada</span></span>|<span data-ttu-id="6b2eb-175">"Altro + 1"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-175">"Other +1"</span></span>|<span data-ttu-id="6b2eb-176">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="6b2eb-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="6b2eb-177">3</span><span class="sxs-lookup"><span data-stu-id="6b2eb-177">3</span></span>|<span data-ttu-id="6b2eb-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="6b2eb-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="6b2eb-180">Route per i numeri chiamati + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="6b2eb-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="6b2eb-181">Esempio 1: passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="6b2eb-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="6b2eb-182">L'esempio seguente illustra come:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-182">The following example shows how to:</span></span>

1. <span data-ttu-id="6b2eb-183">Creare un singolo utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="6b2eb-184">Configurare tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="6b2eb-185">Creare un criterio di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="6b2eb-186">Assegnare il criterio a un utente di nome Spencer low.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="6b2eb-187">Per eseguire questa procedura, è possibile usare l'interfaccia di [amministrazione di Microsoft teams](#admincenterexample1) o [PowerShell](#powershellexample1) .</span><span class="sxs-lookup"><span data-stu-id="6b2eb-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6b2eb-188">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="6b2eb-189">Passaggio 1: creare l'utilizzo PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="6b2eb-190">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto**vocale e quindi nell'angolo in alto a destra selezionare **Gestisci record utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="6b2eb-191">Fare clic su **Aggiungi**, digitare **Stati Uniti e Canada**e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="6b2eb-192">Passaggio 2: creare tre route vocali (Redmond 1, Redmond 2 e altre + 1)</span><span class="sxs-lookup"><span data-stu-id="6b2eb-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="6b2eb-193">La procedura seguente descrive come creare una route vocale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="6b2eb-194">Seguire questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e altre + 1 per questo esempio usando le impostazioni descritte nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="6b2eb-195">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto**vocale e quindi seleziona la scheda **route vocali** .</span><span class="sxs-lookup"><span data-stu-id="6b2eb-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="6b2eb-196">Fare clic su **Aggiungi**e quindi immettere un nome e una descrizione per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="6b2eb-197">Impostare la priorità e specificare il modello di numero composto.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="6b2eb-198">Per registrare un SBC con la route vocale, in **SBCS registrato (facoltativo)**, fare clic su **Aggiungi SBCS**, selezionare il SBCS che si vuole registrare e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="6b2eb-199">Per aggiungere record di utilizzo PSTN, in **record utilizzo PSTN (facoltativo)**, fare clic su **Aggiungi utilizzo PSTN**, selezionare i record PSTN da aggiungere e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="6b2eb-200">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="6b2eb-201">Passaggio 3: creare un criterio di routing vocale denominato "solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio</span><span class="sxs-lookup"><span data-stu-id="6b2eb-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="6b2eb-202">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing**vocale e quindi fai clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="6b2eb-203">Digitare **US solo** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="6b2eb-204">In **record utilizzo**PSTN fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="6b2eb-205">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-205">Click **Save**.</span></span>

<span data-ttu-id="6b2eb-206">Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6b2eb-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="6b2eb-207">Passaggio 4: assegnare i criteri di routing vocale a un utente di nome Spencer low</span><span class="sxs-lookup"><span data-stu-id="6b2eb-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="6b2eb-208">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6b2eb-209">Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="6b2eb-210">In **criteri di routing vocale**selezionare il criterio "solo Stati Uniti" e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="6b2eb-211">Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6b2eb-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6b2eb-212">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b2eb-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="6b2eb-213">Passaggio 1: creare l'utilizzo PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="6b2eb-214">In una sessione remota di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="6b2eb-215">Verificare che l'utilizzo sia stato creato immettendo:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="6b2eb-216">Che restituisce un elenco di nomi che possono essere troncati:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="6b2eb-217">L'esempio seguente mostra il risultato dell'eseguire il `(Get-CSOnlinePSTNUsage).usage` comando di PowerShell per visualizzare i nomi completi (non troncati):</span><span class="sxs-lookup"><span data-stu-id="6b2eb-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="6b2eb-218">Passaggio 2: creare tre route vocali (Redmond 1, Redmond 2 e altre + 1)</span><span class="sxs-lookup"><span data-stu-id="6b2eb-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="6b2eb-219">Per creare la route "Redmond 1", in una sessione di PowerShell in Skype for business online, immettere:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="6b2eb-220">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-220">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="6b2eb-221">Per creare la route Redmond 2, immettere:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="6b2eb-222">Per creare l'altra route + 1, immettere:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="6b2eb-223">Verificare che l'espressione regolare nell'attributo NumberPattern sia valida.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="6b2eb-224">Puoi testarlo usando questo sito Web: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="6b2eb-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="6b2eb-225">In alcuni casi, è necessario instradare tutte le chiamate allo stesso SBC; usare-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="6b2eb-226">Instradare tutte le chiamate allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="6b2eb-227">Verificare di aver configurato correttamente la route eseguendo il comando di `Get-CSOnlineVoiceRoute` PowerShell usando le opzioni come illustrato:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="6b2eb-228">Che dovrebbe restituire:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-228">Which should return:</span></span>
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

<span data-ttu-id="6b2eb-229">Nell'esempio, la route "altro + 1" è stata assegnata automaticamente la priorità 4.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="6b2eb-230">Passaggio 3: creare un criterio di routing vocale denominato "solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio</span><span class="sxs-lookup"><span data-stu-id="6b2eb-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="6b2eb-231">In una sessione di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="6b2eb-232">Il risultato è illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-232">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="6b2eb-233">Passaggio 4: assegnare i criteri di routing vocale a un utente di nome Spencer low</span><span class="sxs-lookup"><span data-stu-id="6b2eb-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="6b2eb-234">In una sessione di PowerShell in Skype for business online digitare:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="6b2eb-235">Convalidare l'assegnazione dei criteri immettendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="6b2eb-236">Il comando restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-236">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="6b2eb-237">Esempio 2: routing vocale con più usi PSTN</span><span class="sxs-lookup"><span data-stu-id="6b2eb-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="6b2eb-238">Il criterio di routing vocale creato nell'esempio 1 consente solo le chiamate ai numeri di telefono negli Stati Uniti e in Canada, a meno che l'utente non venga assegnato anche alla licenza per il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="6b2eb-239">Nell'esempio seguente puoi creare il criterio di routing vocale "nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="6b2eb-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="6b2eb-240">Il criterio riutilizza l'utilizzo PSTN "Stati Uniti e Canada" creato nell'esempio 1, nonché il nuovo utilizzo PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="6b2eb-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="6b2eb-241">Questo criterio instrada tutte le altre chiamate a SBCs sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="6b2eb-242">Gli esempi illustrati assegnano il criterio solo USA all'utente Spencer low e il criterio nessuna restrizione per l'utente John Woods in modo che il routing si verifichi come segue:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="6b2eb-243">Solo criteri di Spencer low-US.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="6b2eb-244">Le chiamate sono consentite solo ai numeri Stati Uniti e canadesi.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="6b2eb-245">Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBCs.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="6b2eb-246">I numeri non Stati Uniti non verranno instradati, a meno che non venga assegnata all'utente la licenza per il piano chiamante.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="6b2eb-247">John Woods-politica internazionale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-247">John Woods – International policy.</span></span>  <span data-ttu-id="6b2eb-248">Le chiamate sono consentite a qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-248">Calls are allowed to any number.</span></span> <span data-ttu-id="6b2eb-249">Quando si chiama l'intervallo di numeri Redmond, deve essere usato il set specifico di SBCs.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="6b2eb-250">I numeri non Stati Uniti verranno instradati usando sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra il criterio di routing vocale assegnato all'utente Spencer low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="6b2eb-252">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Microsoft Phone System e Microsoft Calling Plan), viene usata la route automatica.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="6b2eb-253">Se non corrisponde agli schemi di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il piano di chiamata Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="6b2eb-254">Se l'utente ha solo sistema telefonico Microsoft, la chiamata viene eliminata perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra il criterio di routing vocale assegnato all'utente John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="6b2eb-256">Nella tabella seguente vengono riepilogati i criteri di routing "nessuna restrizione" denominazioni di utilizzo e route vocali.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="6b2eb-257">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-257">**PSTN usage**</span></span>|<span data-ttu-id="6b2eb-258">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-258">**Voice route**</span></span>|<span data-ttu-id="6b2eb-259">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-259">**Number pattern**</span></span>|<span data-ttu-id="6b2eb-260">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-260">**Priority**</span></span>|<span data-ttu-id="6b2eb-261">**SBC**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-261">**SBC**</span></span>|<span data-ttu-id="6b2eb-262">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6b2eb-262">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b2eb-263">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="6b2eb-263">US and Canada</span></span>|<span data-ttu-id="6b2eb-264">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-264">"Redmond 1"</span></span>|<span data-ttu-id="6b2eb-265">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="6b2eb-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="6b2eb-266">1</span><span class="sxs-lookup"><span data-stu-id="6b2eb-266">1</span></span>|<span data-ttu-id="6b2eb-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="6b2eb-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="6b2eb-269">Route attiva per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="6b2eb-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="6b2eb-270">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="6b2eb-270">US and Canada</span></span>|<span data-ttu-id="6b2eb-271">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-271">"Redmond 2"</span></span>|<span data-ttu-id="6b2eb-272">^\\+ 1 (425 \| 206) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="6b2eb-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="6b2eb-273">2</span><span class="sxs-lookup"><span data-stu-id="6b2eb-273">2</span></span>|<span data-ttu-id="6b2eb-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="6b2eb-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="6b2eb-276">Percorso di backup per i numeri dei chiamanti + 1 425 XXX XX XX o + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="6b2eb-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="6b2eb-277">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="6b2eb-277">US and Canada</span></span>|<span data-ttu-id="6b2eb-278">"Altro + 1"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-278">"Other +1"</span></span>|<span data-ttu-id="6b2eb-279">^\\+ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="6b2eb-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="6b2eb-280">3</span><span class="sxs-lookup"><span data-stu-id="6b2eb-280">3</span></span>|<span data-ttu-id="6b2eb-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="6b2eb-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="6b2eb-283">Route per i numeri dei chiamanti + 1 XXX XXX XX XX (eccetto + 1 425 XXX XX XX o + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="6b2eb-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="6b2eb-284">Internazionale</span><span class="sxs-lookup"><span data-stu-id="6b2eb-284">International</span></span>|<span data-ttu-id="6b2eb-285">Internazionale</span><span class="sxs-lookup"><span data-stu-id="6b2eb-285">International</span></span>|<span data-ttu-id="6b2eb-286">\d +</span><span class="sxs-lookup"><span data-stu-id="6b2eb-286">\d+</span></span>|<span data-ttu-id="6b2eb-287">4</span><span class="sxs-lookup"><span data-stu-id="6b2eb-287">4</span></span>|<span data-ttu-id="6b2eb-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="6b2eb-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="6b2eb-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="6b2eb-290">Route per qualsiasi modello di numero</span><span class="sxs-lookup"><span data-stu-id="6b2eb-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="6b2eb-291">L'ordine degli usi PSTN nei criteri di routing vocale è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="6b2eb-292">Gli usi vengono applicati in ordine e se viene trovata una corrispondenza nel primo utilizzo, gli altri usi non vengono mai valutati.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="6b2eb-293">L'utilizzo PSTN "internazionale" deve essere posizionato dopo l'utilizzo PSTN "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="6b2eb-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="6b2eb-294">Per modificare l'ordine degli usi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="6b2eb-295">Ad esempio, per cambiare l'ordine da "Stati Uniti e Canada" prima e "internazionale" in secondo luogo, eseguire l'ordine inverso:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="6b2eb-296">La priorità per le route vocali "altro + 1" e "internazionale" viene assegnata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="6b2eb-297">Gli utenti non hanno importanza se hanno priorità più basse rispetto a "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="6b2eb-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="6b2eb-298">Esempio 2: passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="6b2eb-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="6b2eb-299">L'esempio seguente illustra come:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-299">The following example shows how to:</span></span>

1. <span data-ttu-id="6b2eb-300">Creare un nuovo utilizzo PSTN denominato internazionale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="6b2eb-301">Creare una nuova route vocale denominata internazionale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="6b2eb-302">Creare un criterio di routing vocale denominato nessuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="6b2eb-303">Assegnare il criterio all'utente John Woods.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="6b2eb-304">Per eseguire questa procedura, è possibile usare l'interfaccia di [amministrazione di Microsoft teams](#admincenterexample2) o [PowerShell](#powershellexample2) .</span><span class="sxs-lookup"><span data-stu-id="6b2eb-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6b2eb-305">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="6b2eb-306">Passaggio 1: creare l'utilizzo PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="6b2eb-307">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto**vocale e quindi nell'angolo in alto a destra selezionare **Gestisci record utilizzo PSTN**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="6b2eb-308">Fare clic su **Aggiungi**, digitare **internazionale**e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="6b2eb-309">Passaggio 2: creare la route vocale "internazionale"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="6b2eb-310">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **routing diretto**vocale e quindi seleziona la scheda **route vocali** .</span><span class="sxs-lookup"><span data-stu-id="6b2eb-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="6b2eb-311">Fare clic su **Aggiungi**, immettere "internazionale" come nome e quindi aggiungere la descrizione.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="6b2eb-312">Imposta la priorità su 4 e quindi imposta il modello di numero composto su \d +.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="6b2eb-313">In **SBCS registrato (facoltativo)** fare clic su **Aggiungi SBCs**, selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="6b2eb-314">In **record utilizzo PSTN (facoltativo)** fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "internazionale" e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="6b2eb-315">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="6b2eb-316">Passaggio 3: creare un criterio di routing vocale denominato "nessuna restrizione" e aggiungere gli utilizzi PSTN "Stati Uniti e Canada" e "internazionale" al criterio</span><span class="sxs-lookup"><span data-stu-id="6b2eb-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="6b2eb-317">Gli usi PSTN "Stati Uniti e Canada" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="6b2eb-318">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, **passa a**  >  **criteri di routing**vocale e quindi fai clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="6b2eb-319">Digitare **Nessuna restrizione** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="6b2eb-320">In **record utilizzo**PSTN fare clic su **Aggiungi utilizzo PSTN**, selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="6b2eb-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="6b2eb-321">Fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-321">Click **Apply**.</span></span>

    <span data-ttu-id="6b2eb-322">Prendere nota dell'ordine degli usi PSTN:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="6b2eb-323">Se una chiamata effettuata al numero "+ 1 425 XXX XX XX" con gli usi configurati come in questo esempio, la chiamata segue la route impostata nell'uso "USA e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="6b2eb-324">La chiamata viene quindi instradata tramite sbc1.contoso.biz e sbc2.contoso.biz prima, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="6b2eb-325">Se l'utilizzo PSTN "internazionale" è prima di "Stati Uniti e Canada", le chiamate a + 1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="6b2eb-326">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-326">Click **Save**.</span></span>

<span data-ttu-id="6b2eb-327">Per altre informazioni, vedere [gestire i criteri di routing vocale](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6b2eb-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="6b2eb-328">Passaggio 4: assegnare i criteri di routing vocale a un utente di nome John Woods</span><span class="sxs-lookup"><span data-stu-id="6b2eb-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="6b2eb-329">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6b2eb-330">Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="6b2eb-331">In **criteri di routing vocale**selezionare il criterio "nessuna restrizione" e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="6b2eb-332">Il risultato è che il criterio vocale applicato alle chiamate di John Woods è senza restrizioni e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6b2eb-333">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b2eb-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="6b2eb-334">Passaggio 1: creare l'utilizzo PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="6b2eb-335">In una sessione remota di PowerShell in Skype for business online, immettere:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="6b2eb-336">Passaggio 2: creare una nuova route vocale denominata "internazionale"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="6b2eb-337">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-337">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="6b2eb-338">Passaggio 3: creare un criterio di routing vocale denominato "nessuna restrizione"</span><span class="sxs-lookup"><span data-stu-id="6b2eb-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="6b2eb-339">L'utilizzo PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+ 1 425 XXX XX XX" e "+ 1 206 XXX XX XX" come chiamate locali o in locale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="6b2eb-340">Prendere nota dell'ordine degli usi PSTN:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="6b2eb-341">Se una chiamata effettuata al numero "+ 1 425 XXX XX XX" con gli usi configurati come nell'esempio seguente, la chiamata segue la route impostata nell'uso "USA e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="6b2eb-342">La chiamata viene quindi instradata tramite sbc1.contoso.biz e sbc2.contoso.biz prima, quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="6b2eb-343">Se l'utilizzo PSTN "internazionale" è prima di "Stati Uniti e Canada", le chiamate a + 1 425 XXX XX XX vengono instradate a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="6b2eb-344">Immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="6b2eb-345">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-345">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="6b2eb-346">Passaggio 4: assegnare i criteri di routing vocale all'utente di nome John Woods</span><span class="sxs-lookup"><span data-stu-id="6b2eb-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="6b2eb-347">Verificare quindi l'assegnazione usando il comando:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="6b2eb-348">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="6b2eb-348">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="6b2eb-349">Il risultato è che il criterio vocale applicato alle chiamate di John Woods è illimitato e seguirà la logica di routing delle chiamate disponibile per gli Stati Uniti, il Canada e la chiamata internazionale.</span><span class="sxs-lookup"><span data-stu-id="6b2eb-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b2eb-350">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b2eb-350">See also</span></span>

[<span data-ttu-id="6b2eb-351">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="6b2eb-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="6b2eb-352">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="6b2eb-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
