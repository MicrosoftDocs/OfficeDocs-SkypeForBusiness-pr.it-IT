---
title: Configurare il routing vocale per l'instradamento diretto
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
description: Scopri come configurare il routing vocale con l'instradamento diretto del sistema telefonico Microsoft.
ms.openlocfilehash: e87d7d04f9b2477d65e08f461ac3ff113b4d0e7c
ms.sourcegitcommit: d85425d9e6022d1bf84b877920640f9cbaf8bdce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49530993"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="73bdb-103">Configurare il routing vocale per l'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="73bdb-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="73bdb-104">Questo articolo descrive come configurare il routing vocale per l'instradamento diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="73bdb-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="73bdb-105">Questo è il passaggio 3 della procedura seguente per la configurazione del routing diretto:</span><span class="sxs-lookup"><span data-stu-id="73bdb-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="73bdb-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="73bdb-106">Step 1.</span></span> [<span data-ttu-id="73bdb-107">Collegare il servizio SBC al Sistema telefonico Microsoft e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="73bdb-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="73bdb-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="73bdb-108">Step 2.</span></span> [<span data-ttu-id="73bdb-109">Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="73bdb-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="73bdb-110">**Passaggio 3. Configurare il routing vocale** (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="73bdb-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="73bdb-111">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="73bdb-111">Step 4.</span></span> [<span data-ttu-id="73bdb-112">Convertire i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="73bdb-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="73bdb-113">Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="73bdb-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="73bdb-114">Panoramica del routing vocale</span><span class="sxs-lookup"><span data-stu-id="73bdb-114">Voice routing overview</span></span>

<span data-ttu-id="73bdb-115">Il Sistema telefonico Microsoft dispone di un meccanismo di instradamento che consente l'invio di una chiamata a uno specifico controller dei confini della sessione (SBC) in base a:</span><span class="sxs-lookup"><span data-stu-id="73bdb-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="73bdb-116">Schema numero definito</span><span class="sxs-lookup"><span data-stu-id="73bdb-116">The called number pattern</span></span> 
- <span data-ttu-id="73bdb-117">Lo schema dei numeri più l'utente specifico che effettua la chiamata</span><span class="sxs-lookup"><span data-stu-id="73bdb-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="73bdb-118">I file SBC possono essere designati come attivi e come backup.</span><span class="sxs-lookup"><span data-stu-id="73bdb-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="73bdb-119">Quando il servizio SBC configurato come attivo non è disponibile per un percorso di chiamata specifico, la chiamata verrà instradata a un SBC di backup.</span><span class="sxs-lookup"><span data-stu-id="73bdb-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="73bdb-120">Il routing vocale è costituito da questi elementi:</span><span class="sxs-lookup"><span data-stu-id="73bdb-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="73bdb-121">**Criteri di routing vocale:** contenitore per l'utilizzo di PSTN, che può essere assegnato a un utente o a più utenti.</span><span class="sxs-lookup"><span data-stu-id="73bdb-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="73bdb-122">**Utilizzi di PSTN:** contenitore per i percorsi vocali e l'utilizzo di PSTN, che può essere condiviso in criteri di routing vocale diversi.</span><span class="sxs-lookup"><span data-stu-id="73bdb-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="73bdb-123">**Percorsi vocali:** un modello di numero e un set di gateway PSTN online da usare per le chiamate in cui il numero di chiamata corrisponde a quello specificato.</span><span class="sxs-lookup"><span data-stu-id="73bdb-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="73bdb-124">**Gateway PSTN online:** puntatore a un database SBC che archivia anche la configurazione applicata quando una chiamata viene inserita tramite SBC, ad esempio l'inoltro PAI (Forward P-Asserted-Identity) o Codec preferiti; possono essere aggiunti ai percorsi vocali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="73bdb-125">Considerazioni sui criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="73bdb-125">Voice routing policy considerations</span></span>

<span data-ttu-id="73bdb-126">Se un utente dispone di una licenza per un Piano per chiamate, le chiamate in uscita vengono automaticamente indirizzate attraverso l'infrastruttura PSTN del Piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73bdb-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="73bdb-127">Se si configura e si assegna un criterio di instradamento vocale online a un utente di un Piano per chiamate, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composto corrisponde a uno schema di numero definito nel criterio di routing vocale online.</span><span class="sxs-lookup"><span data-stu-id="73bdb-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="73bdb-128">Se esiste una corrispondenza, la chiamata viene instradata attraverso il trunk di instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="73bdb-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="73bdb-129">Se non ci sono corrispondenze, la chiamata viene instradata attraverso l'infrastruttura PSTN del Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="73bdb-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="73bdb-130">Se si configura e si applica il criterio di routing vocale online globale (impostazione predefinita a livello di organizzazione), tutti gli utenti abilitati alla voce nell'organizzazione erediteranno tale criterio, il che potrebbe comportare l'instradamento accidentale delle chiamate PSTN da parte di utenti del Piano per chiamate a un trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="73bdb-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="73bdb-131">Se non si vuole che tutti gli utenti usino i criteri di routing vocale online globale, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per i comandi vocali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="73bdb-132">Esempio 1: Routing vocale con un utilizzo di PSTN</span><span class="sxs-lookup"><span data-stu-id="73bdb-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="73bdb-133">Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="73bdb-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="73bdb-134">**Flusso delle chiamate 1 (a sinistra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="73bdb-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="73bdb-135">Se non sbc1.contoso.biz né sbc2.contoso.biz disponibili, la chiamata viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="73bdb-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="73bdb-136">**Flusso delle chiamate 2 (a destra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene prima instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="73bdb-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="73bdb-137">Se nessun SBC è disponibile, verrà tentato il percorso con priorità più bassa (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="73bdb-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="73bdb-138">Se nessuno degli SBC è disponibile, la chiamata viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="73bdb-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Mostra esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="73bdb-140">In entrambi gli esempi, mentre alle route vocali sono assegnate priorità, i percorsi vengono provati in ordine casuale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span> <span data-ttu-id="73bdb-141">Quando due SBC sono configurati in un'unica route, il traffico di rete deve essere instradabile tra SBC o il supporto non verrà stabilito sui trasferimenti, perché è possibile che il nuovo invito per il trasferimento sia inviato a un altro SBC della route.</span><span class="sxs-lookup"><span data-stu-id="73bdb-141">When two SBC's are configured in one route, network traffic must be routable between both SBC's or media will fail to be established on transfers as it is possible that the new invite for the transfer will be sent to a different SBC in the route.</span></span>

  > [!NOTE]
  > <span data-ttu-id="73bdb-142">A meno che l'utente non abbia anche una licenza per un Piano per chiamate Microsoft, le chiamate a qualsiasi numero tranne i numeri corrispondenti ai modelli +1 425 XXX XX XX o +1 206 XXX XX XX nella configurazione di esempio vengono eliminate.</span><span class="sxs-lookup"><span data-stu-id="73bdb-142">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="73bdb-143">Se l'utente dispone di una licenza per un Piano per chiamate, la chiamata viene automaticamente instradata in base ai criteri del Piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73bdb-143">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="73bdb-144">Il Piano per chiamate Microsoft si applica automaticamente come ultimo percorso a tutti gli utenti con licenza Piano per chiamate Microsoft e non richiede una configurazione aggiuntiva di instradamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="73bdb-144">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="73bdb-145">Nell'esempio mostrato nella figura seguente viene aggiunto un percorso vocale per inviare chiamate a tutti gli altri numeri degli Stati Uniti e di Canada (chiamate indirizzate al cosiddetto modello di numero +1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="73bdb-145">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra i criteri di instradamento vocale con una terza route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="73bdb-147">Per tutte le altre chiamate, se un utente dispone di entrambe le licenze (Sistema telefonico Microsoft e Piano per chiamate Microsoft), viene utilizzato il percorso automatico.</span><span class="sxs-lookup"><span data-stu-id="73bdb-147">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="73bdb-148">Se nessun elemento corrisponde ai modelli di numerazione nei percorsi vocali online creati dall'amministratore, la chiamata viene instradata attraverso il Piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73bdb-148">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="73bdb-149">Se l'utente ha solo Sistema telefonico Microsoft, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="73bdb-149">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="73bdb-150">Il valore Priorità per la route "Altro +1" non è importante in questo caso perché esiste una sola route che corrisponde al modello +1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="73bdb-150">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="73bdb-151">Se un utente effettua una chiamata a +1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="73bdb-151">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="73bdb-152">La tabella seguente riepiloga la configurazione usando tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-152">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="73bdb-153">In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo di PSTN, "STATI UNITI e Canada".</span><span class="sxs-lookup"><span data-stu-id="73bdb-153">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="73bdb-154">Tutte le route sono associate all'utilizzo di PSTN "Stati Uniti e Canada" e l'utilizzo di PSTN è associato ai criteri di routing vocale "Solo Stati Uniti".</span><span class="sxs-lookup"><span data-stu-id="73bdb-154">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="73bdb-155">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="73bdb-155">**PSTN usage**</span></span>|<span data-ttu-id="73bdb-156">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="73bdb-156">**Voice route**</span></span>|<span data-ttu-id="73bdb-157">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="73bdb-157">**Number pattern**</span></span>|<span data-ttu-id="73bdb-158">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="73bdb-158">**Priority**</span></span>|<span data-ttu-id="73bdb-159">**SBC**</span><span class="sxs-lookup"><span data-stu-id="73bdb-159">**SBC**</span></span>|<span data-ttu-id="73bdb-160">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="73bdb-160">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73bdb-161">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="73bdb-161">US and Canada</span></span>|<span data-ttu-id="73bdb-162">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="73bdb-162">"Redmond 1"</span></span>|<span data-ttu-id="73bdb-163">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="73bdb-163">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="73bdb-164">1</span><span class="sxs-lookup"><span data-stu-id="73bdb-164">1</span></span>|<span data-ttu-id="73bdb-165">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-165">sbc1.contoso.biz</span></span><br/><span data-ttu-id="73bdb-166">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-166">sbc2.contoso.biz</span></span>|<span data-ttu-id="73bdb-167">Percorso attivo per i numeri +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="73bdb-167">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="73bdb-168">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="73bdb-168">US and Canada</span></span>|<span data-ttu-id="73bdb-169">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="73bdb-169">"Redmond 2"</span></span>|<span data-ttu-id="73bdb-170">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="73bdb-170">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="73bdb-171">2</span><span class="sxs-lookup"><span data-stu-id="73bdb-171">2</span></span>|<span data-ttu-id="73bdb-172">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-172">sbc3.contoso.biz</span></span><br/><span data-ttu-id="73bdb-173">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-173">sbc4.contoso.biz</span></span>|<span data-ttu-id="73bdb-174">Percorso di backup per i numeri +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="73bdb-174">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="73bdb-175">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="73bdb-175">US and Canada</span></span>|<span data-ttu-id="73bdb-176">"Altro +1"</span><span class="sxs-lookup"><span data-stu-id="73bdb-176">"Other +1"</span></span>|<span data-ttu-id="73bdb-177">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="73bdb-177">^\\+1(\d{10})$</span></span>|<span data-ttu-id="73bdb-178">3</span><span class="sxs-lookup"><span data-stu-id="73bdb-178">3</span></span>|<span data-ttu-id="73bdb-179">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-179">sbc5.contoso.biz</span></span><br/><span data-ttu-id="73bdb-180">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-180">sbc6.contoso.biz</span></span>|<span data-ttu-id="73bdb-181">Route per i numeri +1 XXX XXX XX XX (eccetto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="73bdb-181">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="73bdb-182">Esempio 1: Passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="73bdb-182">Example 1: Configuration steps</span></span>

<span data-ttu-id="73bdb-183">L'esempio seguente mostra come:</span><span class="sxs-lookup"><span data-stu-id="73bdb-183">The following example shows how to:</span></span>

1. <span data-ttu-id="73bdb-184">Creare un singolo utilizzo di PSTN.</span><span class="sxs-lookup"><span data-stu-id="73bdb-184">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="73bdb-185">Configurare tre percorsi vocali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-185">Configure three voice routes.</span></span>
3. <span data-ttu-id="73bdb-186">Creare un criterio di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-186">Create a voice routing policy.</span></span>
4. <span data-ttu-id="73bdb-187">Assegnare il criterio a un utente denominato Low.</span><span class="sxs-lookup"><span data-stu-id="73bdb-187">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="73bdb-188">Per eseguire queste operazioni, è [possibile usare](#admincenterexample1) l'interfaccia di amministrazione di Microsoft Teams o [PowerShell.](#powershellexample1)</span><span class="sxs-lookup"><span data-stu-id="73bdb-188">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73bdb-189">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73bdb-189">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="73bdb-190">Passaggio 1: Creare l'utilizzo di PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="73bdb-190">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="73bdb-191">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing, quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-191">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="73bdb-192">Fare **clic su** Aggiungi, digitare US e **Canada,** quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-192">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="73bdb-193">Passaggio 2: Creare tre percorsi vocali (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="73bdb-193">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="73bdb-194">I passaggi seguenti descrivono come creare un percorso vocale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-194">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="73bdb-195">Seguire questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e Other +1 per questo esempio usando le impostazioni descritte nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="73bdb-195">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="73bdb-196">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Instradamento diretto  >  **vocale,** quindi seleziona la **scheda Percorsi** vocali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-196">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="73bdb-197">Fare **clic su** Aggiungi, quindi immettere un nome e una descrizione per il percorso vocale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-197">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="73bdb-198">Impostare la priorità e specificare il modello dei numeri componiti.</span><span class="sxs-lookup"><span data-stu-id="73bdb-198">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="73bdb-199">Per registrare un SBC con il percorso vocale, in SBC registrati **(facoltativo)** fare clic su Aggiungi **SBC,** selezionare gli SBC da registrare e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-199">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="73bdb-200">Per aggiungere record di utilizzo PSTN (facoltativo), in Record di utilizzo **PSTN fare** clic su Aggiungi utilizzo **PSTN,** selezionare i record PSTN da aggiungere e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-200">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="73bdb-201">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="73bdb-201">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="73bdb-202">Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo di PSTN "Stati Uniti e Canada" ai criteri</span><span class="sxs-lookup"><span data-stu-id="73bdb-202">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="73bdb-203">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Criteri  >  **di instradamento vocale,** quindi fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-203">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="73bdb-204">Digitare **solo US** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="73bdb-204">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="73bdb-205">In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-205">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="73bdb-206">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="73bdb-206">Click **Save**.</span></span>

<span data-ttu-id="73bdb-207">Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="73bdb-207">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="73bdb-208">Passaggio 4: Assegnare il criterio di instradamento vocale a un utente denominato Basso</span><span class="sxs-lookup"><span data-stu-id="73bdb-208">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="73bdb-209">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="73bdb-209">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="73bdb-210">Fare **clic su** Criteri e quindi su Modifica accanto a **Criteri** **assegnati.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-210">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="73bdb-211">In **Criteri di routing vocale** selezionare il criterio "Solo Stati Uniti" e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-211">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="73bdb-212">Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="73bdb-212">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73bdb-213">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="73bdb-213">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="73bdb-214">Passaggio 1: Creare l'utilizzo di PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="73bdb-214">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="73bdb-215">In una sessione remota di PowerShell in Skype for Business online digita:</span><span class="sxs-lookup"><span data-stu-id="73bdb-215">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="73bdb-216">Verificare che l'utilizzo sia stato creato immettendo:</span><span class="sxs-lookup"><span data-stu-id="73bdb-216">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="73bdb-217">Che restituisce un elenco di nomi che possono essere troncati:</span><span class="sxs-lookup"><span data-stu-id="73bdb-217">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="73bdb-218">L'esempio seguente mostra il risultato dell'esecuzione del comando di Powershell per visualizzare i nomi completi `(Get-CSOnlinePSTNUsage).usage` (non troncati):</span><span class="sxs-lookup"><span data-stu-id="73bdb-218">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` Powershell command to display full names (not truncated):</span></span>

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

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="73bdb-219">Passaggio 2: Creare tre percorsi vocali (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="73bdb-219">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="73bdb-220">Per creare il percorso "Redmond 1", in una sessione di PowerShell in Skype for Business online, immetti:</span><span class="sxs-lookup"><span data-stu-id="73bdb-220">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="73bdb-221">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="73bdb-221">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>

<span data-ttu-id="73bdb-222">Per creare il percorso di Redmond 2, immetti:</span><span class="sxs-lookup"><span data-stu-id="73bdb-222">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="73bdb-223">Per creare il percorso Altro +1, immettere:</span><span class="sxs-lookup"><span data-stu-id="73bdb-223">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="73bdb-224">Verificare che l'espressione regolare nell'attributo NumberAttribute sia un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="73bdb-224">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="73bdb-225">È possibile testarlo usando questo sito Web: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="73bdb-225">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="73bdb-226">In alcuni casi è necessario instradare tutte le chiamate allo stesso SBC; use -NumberNumerazione ".\*"</span><span class="sxs-lookup"><span data-stu-id="73bdb-226">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="73bdb-227">Instradare tutte le chiamate allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="73bdb-227">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="73bdb-228">Verificare di aver configurato correttamente la route eseguendo il comando `Get-CSOnlineVoiceRoute` di PowerShell usando le opzioni indicate:</span><span class="sxs-lookup"><span data-stu-id="73bdb-228">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="73bdb-229">Che dovrebbe restituire:</span><span class="sxs-lookup"><span data-stu-id="73bdb-229">Which should return:</span></span>
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

<span data-ttu-id="73bdb-230">Nell'esempio, al percorso "Altro +1" è stata assegnata automaticamente la priorità 4.</span><span class="sxs-lookup"><span data-stu-id="73bdb-230">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="73bdb-231">Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo di PSTN "Stati Uniti e Canada" ai criteri</span><span class="sxs-lookup"><span data-stu-id="73bdb-231">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="73bdb-232">In una sessione di PowerShell in Skype for Business online digita:</span><span class="sxs-lookup"><span data-stu-id="73bdb-232">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="73bdb-233">Il risultato è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="73bdb-233">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="73bdb-234">Passaggio 4: Assegnare il criterio di instradamento vocale a un utente denominato Basso</span><span class="sxs-lookup"><span data-stu-id="73bdb-234">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="73bdb-235">In una sessione di PowerShell in Skype for Business online digita:</span><span class="sxs-lookup"><span data-stu-id="73bdb-235">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="73bdb-236">Convalidare l'assegnazione dei criteri immettendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="73bdb-236">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="73bdb-237">Il comando restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="73bdb-237">The command returns the following:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="73bdb-238">Esempio 2: Routing vocale con più utilizzi di PSTN</span><span class="sxs-lookup"><span data-stu-id="73bdb-238">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="73bdb-239">Il criterio di instradamento vocale creato nell'esempio 1 consente solo chiamate a numeri di telefono negli Stati Uniti e in Canada, a meno che all'utente non sia assegnata anche la licenza del Piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73bdb-239">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="73bdb-240">Nell'esempio seguente è possibile creare il criterio di routing vocale "Nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="73bdb-240">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="73bdb-241">I criteri riutilizzano l'utilizzo di PSTN "Stati Uniti e Canada" creato nell'esempio 1, nonché il nuovo utilizzo di PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="73bdb-241">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="73bdb-242">Questo criterio indirizza tutte le altre chiamate agli SBC sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="73bdb-242">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="73bdb-243">Gli esempi riportati di seguito assegnano il criterio Solo stati Uniti all'utente Low per gli Stati Uniti e il criterio Nessuna restrizione all'utente John Foresta, in modo che il routing si verifichi nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="73bdb-243">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="73bdb-244">Basso degli Stati Uniti - Politica solo per gli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="73bdb-244">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="73bdb-245">Le chiamate sono consentite solo ai numeri degli Stati Uniti e dei Canada.</span><span class="sxs-lookup"><span data-stu-id="73bdb-245">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="73bdb-246">Quando si chiama all'intervallo dei numeri di Redmond, è necessario utilizzare il set specifico di numeri SBC.</span><span class="sxs-lookup"><span data-stu-id="73bdb-246">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="73bdb-247">I numeri non statunitensi verranno instradati solo se all'utente non viene assegnata la licenza del Piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="73bdb-247">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="73bdb-248">John Rieti - Politica internazionale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-248">John Woods – International policy.</span></span>  <span data-ttu-id="73bdb-249">Le chiamate sono consentite a qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="73bdb-249">Calls are allowed to any number.</span></span> <span data-ttu-id="73bdb-250">Quando si chiama all'intervallo dei numeri di Redmond, è necessario utilizzare il set specifico di numeri SBC.</span><span class="sxs-lookup"><span data-stu-id="73bdb-250">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="73bdb-251">I numeri non statunitensi verranno instradati sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="73bdb-251">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra i criteri di routing vocale assegnati all'utente Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="73bdb-253">Per tutte le altre chiamate, se un utente dispone di entrambe le licenze (Sistema telefonico Microsoft e Piano per chiamate Microsoft), viene utilizzato il percorso automatico.</span><span class="sxs-lookup"><span data-stu-id="73bdb-253">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="73bdb-254">Se nessun elemento corrisponde ai modelli di numerazione nei percorsi vocali online creati dall'amministratore, la chiamata viene instradata utilizzando il Piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73bdb-254">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="73bdb-255">Se l'utente ha solo il Sistema telefonico Microsoft, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="73bdb-255">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra i criteri di instradamento vocale assegnati all'utente John Più di unirsi](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="73bdb-257">La tabella seguente riepiloga le designazioni di utilizzo e i percorsi vocali del criterio di routing "Nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="73bdb-257">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="73bdb-258">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="73bdb-258">**PSTN usage**</span></span>|<span data-ttu-id="73bdb-259">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="73bdb-259">**Voice route**</span></span>|<span data-ttu-id="73bdb-260">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="73bdb-260">**Number pattern**</span></span>|<span data-ttu-id="73bdb-261">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="73bdb-261">**Priority**</span></span>|<span data-ttu-id="73bdb-262">**SBC**</span><span class="sxs-lookup"><span data-stu-id="73bdb-262">**SBC**</span></span>|<span data-ttu-id="73bdb-263">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="73bdb-263">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73bdb-264">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="73bdb-264">US and Canada</span></span>|<span data-ttu-id="73bdb-265">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="73bdb-265">"Redmond 1"</span></span>|<span data-ttu-id="73bdb-266">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="73bdb-266">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="73bdb-267">1</span><span class="sxs-lookup"><span data-stu-id="73bdb-267">1</span></span>|<span data-ttu-id="73bdb-268">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-268">sbc1.contoso.biz</span></span><br/><span data-ttu-id="73bdb-269">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-269">sbc2.contoso.biz</span></span>|<span data-ttu-id="73bdb-270">Percorso attivo per i numeri del chiamato +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="73bdb-270">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="73bdb-271">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="73bdb-271">US and Canada</span></span>|<span data-ttu-id="73bdb-272">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="73bdb-272">"Redmond 2"</span></span>|<span data-ttu-id="73bdb-273">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="73bdb-273">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="73bdb-274">2</span><span class="sxs-lookup"><span data-stu-id="73bdb-274">2</span></span>|<span data-ttu-id="73bdb-275">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-275">sbc3.contoso.biz</span></span><br/><span data-ttu-id="73bdb-276">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-276">sbc4.contoso.biz</span></span>|<span data-ttu-id="73bdb-277">Percorso di backup per i numeri del chiamato +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="73bdb-277">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="73bdb-278">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="73bdb-278">US and Canada</span></span>|<span data-ttu-id="73bdb-279">"Altro +1"</span><span class="sxs-lookup"><span data-stu-id="73bdb-279">"Other +1"</span></span>|<span data-ttu-id="73bdb-280">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="73bdb-280">^\\+1(\d{10})$</span></span>|<span data-ttu-id="73bdb-281">3</span><span class="sxs-lookup"><span data-stu-id="73bdb-281">3</span></span>|<span data-ttu-id="73bdb-282">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-282">sbc5.contoso.biz</span></span><br/><span data-ttu-id="73bdb-283">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-283">sbc6.contoso.biz</span></span>|<span data-ttu-id="73bdb-284">Percorso per i numeri del chiamato +1 XXX XXX XX XX (eccetto +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="73bdb-284">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="73bdb-285">Internazionale</span><span class="sxs-lookup"><span data-stu-id="73bdb-285">International</span></span>|<span data-ttu-id="73bdb-286">Internazionale</span><span class="sxs-lookup"><span data-stu-id="73bdb-286">International</span></span>|<span data-ttu-id="73bdb-287">\d+</span><span class="sxs-lookup"><span data-stu-id="73bdb-287">\d+</span></span>|<span data-ttu-id="73bdb-288">4</span><span class="sxs-lookup"><span data-stu-id="73bdb-288">4</span></span>|<span data-ttu-id="73bdb-289">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-289">sbc2.contoso.biz</span></span><br/><span data-ttu-id="73bdb-290">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="73bdb-290">sbc5.contoso.biz</span></span>|<span data-ttu-id="73bdb-291">Route per qualsiasi schema di numerazione</span><span class="sxs-lookup"><span data-stu-id="73bdb-291">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="73bdb-292">L'ordine di utilizzo di PSTN nei criteri di routing vocale è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-292">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="73bdb-293">Gli utilizzi vengono applicati in ordine e, se viene trovata una corrispondenza nel primo utilizzo, gli altri utilizzi non vengono mai valutati.</span><span class="sxs-lookup"><span data-stu-id="73bdb-293">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="73bdb-294">L'utilizzo di PSTN "internazionale" deve essere posizionato dopo l'utilizzo di PSTN "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="73bdb-294">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="73bdb-295">Per modificare l'ordine di utilizzo di PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="73bdb-295">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="73bdb-296">Ad esempio, per cambiare l'ordine da "Stati Uniti e Canada" per primo e "Internazionale" secondo all'ordine inverso:</span><span class="sxs-lookup"><span data-stu-id="73bdb-296">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="73bdb-297">La priorità per i percorsi vocali "Altri +1" e "Internazionali" viene assegnata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="73bdb-297">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="73bdb-298">Non importa se hanno priorità inferiori rispetto a "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="73bdb-298">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="73bdb-299">Esempio 2: Passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="73bdb-299">Example 2: Configuration steps</span></span>

<span data-ttu-id="73bdb-300">L'esempio seguente mostra come:</span><span class="sxs-lookup"><span data-stu-id="73bdb-300">The following example shows how to:</span></span>

1. <span data-ttu-id="73bdb-301">Creare un nuovo utilizzo di PSTN denominato Internazionale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-301">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="73bdb-302">Creare un nuovo percorso vocale chiamato Internazionale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-302">Create a new voice route called International.</span></span>
3. <span data-ttu-id="73bdb-303">Creare un criterio di routing vocale denominato Nessuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="73bdb-303">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="73bdb-304">Assegnare il criterio all'utente John Piùele.</span><span class="sxs-lookup"><span data-stu-id="73bdb-304">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="73bdb-305">Per eseguire queste operazioni, è [possibile usare](#admincenterexample2) l'interfaccia di amministrazione di Microsoft Teams o [PowerShell.](#powershellexample2)</span><span class="sxs-lookup"><span data-stu-id="73bdb-305">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="73bdb-306">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73bdb-306">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="73bdb-307">Passaggio 1: Creare l'utilizzo di PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="73bdb-307">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="73bdb-308">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing, quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-308">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="73bdb-309">Fare **clic su** Aggiungi, digitare **Internazionale** e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-309">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="73bdb-310">Passaggio 2: Creare il percorso vocale "Internazionale"</span><span class="sxs-lookup"><span data-stu-id="73bdb-310">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="73bdb-311">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a Instradamento diretto  >  **vocale,** quindi seleziona la **scheda Percorsi** vocali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-311">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="73bdb-312">Fare **clic** su Aggiungi, immettere "Internazionale" come nome e quindi aggiungere la descrizione.</span><span class="sxs-lookup"><span data-stu-id="73bdb-312">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="73bdb-313">Impostare la priorità su 4, quindi impostare il modello di numero composto su \d+.</span><span class="sxs-lookup"><span data-stu-id="73bdb-313">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="73bdb-314">In **SBC registrati (facoltativo)** fare clic su Aggiungi **SBC,** selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-314">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="73bdb-315">In **Record di utilizzo PSTN (facoltativo)** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Internazionale" e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-315">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="73bdb-316">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="73bdb-316">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="73bdb-317">Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione" e aggiungere al criterio gli utilizzi di PSTN "Stati Uniti e Canada" e "Internazionali"</span><span class="sxs-lookup"><span data-stu-id="73bdb-317">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="73bdb-318">L'utilizzo di PSTN "STATI UNITI e Canada" viene riutilizzato in questo criterio di routing vocale per mantenere una gestione speciale delle chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-318">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="73bdb-319">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a** Criteri  >  **di instradamento vocale,** quindi fai clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-319">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="73bdb-320">Digitare **No Restrictions** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="73bdb-320">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="73bdb-321">In Record di utilizzo **PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "Internazionale".</span><span class="sxs-lookup"><span data-stu-id="73bdb-321">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="73bdb-322">Fare clic **su Applica.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-322">Click **Apply**.</span></span>

    <span data-ttu-id="73bdb-323">Prendere nota dell'ordine di utilizzo di PSTN:</span><span class="sxs-lookup"><span data-stu-id="73bdb-323">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="73bdb-324">Se viene effettuata una chiamata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come in questo esempio, la chiamata segue il percorso impostato per l'utilizzo in "Stati Uniti e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-324">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="73bdb-325">In altre caso, la chiamata viene instradata usando sbc1.contoso.biz e sbc2.contoso.biz, quindi sbc3.contoso.biz e sbc4.contoso.biz come percorsi di backup.</span><span class="sxs-lookup"><span data-stu-id="73bdb-325">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="73bdb-326">Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="73bdb-326">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="73bdb-327">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="73bdb-327">Click **Save**.</span></span>

<span data-ttu-id="73bdb-328">Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="73bdb-328">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="73bdb-329">Passaggio 4: Assegnare il criterio di routing vocale a un utente di nome Luca Agnesi</span><span class="sxs-lookup"><span data-stu-id="73bdb-329">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="73bdb-330">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="73bdb-330">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="73bdb-331">Fare **clic su** Criteri e quindi su Modifica accanto a **Criteri** **assegnati.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-331">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="73bdb-332">In **Criteri di routing vocale** selezionare il criterio "Nessuna restrizione" e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="73bdb-332">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="73bdb-333">Il risultato è che il criterio vocale applicato alle chiamate di John Eseguo è illimitato e seguirà la logica del routing delle chiamate disponibile per le chiamate negli Stati Uniti, in Canada e all';internazionale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-333">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="73bdb-334">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="73bdb-334">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="73bdb-335">Passaggio 1: Creare l'utilizzo di PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="73bdb-335">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="73bdb-336">In una sessione remota di PowerShell in Skype for Business online, immetti:</span><span class="sxs-lookup"><span data-stu-id="73bdb-336">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="73bdb-337">Passaggio 2: Creare un nuovo percorso vocale denominato "Internazionale"</span><span class="sxs-lookup"><span data-stu-id="73bdb-337">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="73bdb-338">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="73bdb-338">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="73bdb-339">Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione"</span><span class="sxs-lookup"><span data-stu-id="73bdb-339">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="73bdb-340">I servizi PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale delle chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.</span><span class="sxs-lookup"><span data-stu-id="73bdb-340">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="73bdb-341">Prendere nota dell'ordine di utilizzo di PSTN:</span><span class="sxs-lookup"><span data-stu-id="73bdb-341">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="73bdb-342">Se viene effettuata una chiamata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come nell'esempio seguente, la chiamata segue il percorso impostato per l'utilizzo in "Stati Uniti e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-342">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="73bdb-343">In altre caso, la chiamata viene instradata usando sbc1.contoso.biz e sbc2.contoso.biz, quindi sbc3.contoso.biz e sbc4.contoso.biz come percorsi di backup.</span><span class="sxs-lookup"><span data-stu-id="73bdb-343">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="73bdb-344">Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="73bdb-344">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="73bdb-345">Immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="73bdb-345">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="73bdb-346">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="73bdb-346">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
    </pre>

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="73bdb-347">Passaggio 4: Assegnare i criteri di instradamento vocale all'utente John Piùle</span><span class="sxs-lookup"><span data-stu-id="73bdb-347">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="73bdb-348">Verificare quindi l'attività usando il comando:</span><span class="sxs-lookup"><span data-stu-id="73bdb-348">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="73bdb-349">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="73bdb-349">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="73bdb-350">Il risultato è che il criterio vocale applicato alle chiamate di John Eseguo è illimitato e seguirà la logica del routing delle chiamate disponibile per le chiamate negli Stati Uniti, in Canada e all';internazionale.</span><span class="sxs-lookup"><span data-stu-id="73bdb-350">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="73bdb-351">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73bdb-351">See also</span></span>

[<span data-ttu-id="73bdb-352">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="73bdb-352">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="73bdb-353">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="73bdb-353">Configure Direct Routing</span></span>](direct-routing-configure.md)
