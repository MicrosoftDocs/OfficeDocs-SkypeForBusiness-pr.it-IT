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
description: Informazioni su come configurare il routing vocale con Telefono Microsoft routing diretto di sistema.
ms.openlocfilehash: 9330c3bf8200ed84fa9f7c534e794af887097b8d
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383980"
---
# <a name="configure-voice-routing-for-direct-routing"></a><span data-ttu-id="81798-103">Configurare il routing vocale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="81798-103">Configure voice routing for Direct Routing</span></span>

<span data-ttu-id="81798-104">Questo articolo descrive come configurare il routing vocale per Sistema telefonico routing diretto.</span><span class="sxs-lookup"><span data-stu-id="81798-104">This article describes how to configure voice routing for Phone System Direct Routing.</span></span>  <span data-ttu-id="81798-105">Questo è il passaggio 3 della procedura seguente per la configurazione del routing diretto:</span><span class="sxs-lookup"><span data-stu-id="81798-105">This is step 3 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="81798-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="81798-106">Step 1.</span></span> [<span data-ttu-id="81798-107">Connessione SBC con Telefono Microsoft sistema e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="81798-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="81798-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="81798-108">Step 2.</span></span> [<span data-ttu-id="81798-109">Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="81798-109">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="81798-110">**Passaggio 3. Configurare il routing vocale** (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="81798-110">**Step 3. Configure voice routing** (This article)</span></span>
- <span data-ttu-id="81798-111">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="81798-111">Step 4.</span></span> [<span data-ttu-id="81798-112">Tradurre i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="81798-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="81798-113">Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="81798-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="voice-routing-overview"></a><span data-ttu-id="81798-114">Panoramica del routing vocale</span><span class="sxs-lookup"><span data-stu-id="81798-114">Voice routing overview</span></span>

<span data-ttu-id="81798-115">Telefono Microsoft Il sistema ha un meccanismo di routing che consente di inviare una chiamata a uno specifico Session Border Controller (SBC) in base a:</span><span class="sxs-lookup"><span data-stu-id="81798-115">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific Session Border Controller (SBC) based on:</span></span> 

- <span data-ttu-id="81798-116">Il modello di numero chiamato</span><span class="sxs-lookup"><span data-stu-id="81798-116">The called number pattern</span></span> 
- <span data-ttu-id="81798-117">Il modello di numero chiamato più l'utente specifico che effettua la chiamata</span><span class="sxs-lookup"><span data-stu-id="81798-117">The called number pattern plus the specific user who makes the call</span></span>
 
<span data-ttu-id="81798-118">Gli SBC possono essere designati come attivi e di backup.</span><span class="sxs-lookup"><span data-stu-id="81798-118">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="81798-119">Quando la SBC configurata come attiva non è disponibile per un percorso di chiamata specifico, la chiamata verrà instradata a un SBC di backup.</span><span class="sxs-lookup"><span data-stu-id="81798-119">When the SBC that is configured as active is not available for a specific call route, then the call will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="81798-120">Il routing vocale è costituito da elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="81798-120">Voice routing is made up of the following elements:</span></span> 

- <span data-ttu-id="81798-121">**Criteri di routing vocale:** contenitore per gli utilizzi PSTN, che può essere assegnato a un utente o a più utenti.</span><span class="sxs-lookup"><span data-stu-id="81798-121">**Voice routing policy** – A container for PSTN usages, which can be assigned to a user or to multiple users.</span></span> 

- <span data-ttu-id="81798-122">**Utilizzi PSTN:** contenitore per route vocali e utilizzi PSTN, che può essere condiviso in criteri di routing vocale diversi.</span><span class="sxs-lookup"><span data-stu-id="81798-122">**PSTN usages** – A container for voice routes and PSTN usages, which can be shared in different voice routing policies.</span></span> 

- <span data-ttu-id="81798-123">**Route vocali:** uno schema di numeri e un set di gateway PSTN online da usare per le chiamate in cui il numero di chiamata corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="81798-123">**Voice routes** – A number pattern and set of online PSTN gateways to use for calls where the calling number matches the pattern.</span></span>

- <span data-ttu-id="81798-124">**Gateway PSTN online:** puntatore a un SBC in cui viene archiviata anche la configurazione applicata quando una chiamata viene inoltrata tramite SBC, ad esempio l'inoltro P-Asserted-Identity (PAI) o i codec preferiti. può essere aggiunto alle route vocali.</span><span class="sxs-lookup"><span data-stu-id="81798-124">**Online PSTN gateway** - A pointer to an SBC that also stores the configuration that is applied when a call is placed through the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to voice routes.</span></span>

## <a name="voice-routing-policy-considerations"></a><span data-ttu-id="81798-125">Considerazioni sui criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="81798-125">Voice routing policy considerations</span></span>

<span data-ttu-id="81798-126">Se un utente ha una licenza per il piano di chiamata, le chiamate in uscita dell'utente vengono automaticamente instradati tramite l'infrastruttura PSTN del piano chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81798-126">If a user has a Calling Plan license, that user’s outgoing calls are automatically routed through the Microsoft Calling Plan PSTN infrastructure.</span></span> <span data-ttu-id="81798-127">Se si configurano e si assegnano criteri di routing vocale online a un utente del piano di chiamata, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composto corrisponde a uno schema di numeri definito nel criterio di routing vocale online.</span><span class="sxs-lookup"><span data-stu-id="81798-127">If you configure and assign an online voice routing policy to a Calling Plan user, that user’s outgoing calls are checked to determine whether the dialed number matches a number pattern defined in the online voice routing policy.</span></span> <span data-ttu-id="81798-128">Se c'è una corrispondenza, la chiamata viene instradata attraverso il trunk direct routing.</span><span class="sxs-lookup"><span data-stu-id="81798-128">If there’s a match, the call is routed through the Direct Routing trunk.</span></span> <span data-ttu-id="81798-129">Se non c'è corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano per chiamate.</span><span class="sxs-lookup"><span data-stu-id="81798-129">If there’s no match, the call is routed through the Calling Plan PSTN infrastructure.</span></span>

> [!CAUTION]
> <span data-ttu-id="81798-130">Se si configura e si applica il criterio di routing vocale online globale (predefinito a livello di organizzazione), tutti gli utenti abilitati per la voce dell'organizzazione erediteranno tale criterio, il che potrebbe comportare l'instradamento involontario delle chiamate PSTN degli utenti del piano di chiamata a un trunk di routing diretto.</span><span class="sxs-lookup"><span data-stu-id="81798-130">If you configure and apply the global (Org-wide default) online voice routing policy, all voice-enabled users in your organization will inherit that policy, which may result in PSTN calls from Calling Plan users being inadvertently routed to a Direct Routing trunk.</span></span> <span data-ttu-id="81798-131">Se non si vuole che tutti gli utenti usino il criterio di routing vocale online globale, configurare un criterio di routing vocale online personalizzato e assegnarlo ai singoli utenti abilitati per la voce.</span><span class="sxs-lookup"><span data-stu-id="81798-131">If you don't want all users to use the global online voice routing policy, configure a custom online voice routing policy and assign it to individual voice-enabled users.</span></span>

## <a name="example-1-voice-routing-with-one-pstn-usage"></a><span data-ttu-id="81798-132">Esempio 1: Routing vocale con un solo utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="81798-132">Example 1: Voice routing with one PSTN usage</span></span>

<span data-ttu-id="81798-133">Il diagramma seguente mostra due esempi di criteri di routing vocale in un flusso di chiamate.</span><span class="sxs-lookup"><span data-stu-id="81798-133">The following diagram shows two examples of voice routing policies in a call flow.</span></span>

<span data-ttu-id="81798-134">**Chiama Flow 1 (a sinistra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="81798-134">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="81798-135">Se non sbc1.contoso.biz né sbc2.contoso.biz disponibili, la chiamata viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="81798-135">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="81798-136">**Chiama Flow 2 (a destra):** Se un utente effettua una chiamata a +1 425 XXX XX XX o +1 206 XXX XX XX, la chiamata viene prima instradata a SBC sbc1.contoso.biz o sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="81798-136">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="81798-137">Se nessuno dei due SBC è disponibile, verrà provato il percorso con priorità inferiore (sbc3.contoso.biz e sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="81798-137">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="81798-138">Se nessuno dei SBC è disponibile, la chiamata viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="81798-138">If none of the SBCs are available, the call is dropped.</span></span> 

![Esempi di criteri di routing vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="81798-140">In entrambi gli esempi, mentre alla route vocale sono assegnate priorità, i SBC nelle route vengono provati in ordine casuale.</span><span class="sxs-lookup"><span data-stu-id="81798-140">In both examples, while the voice route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="81798-141">A meno che l'utente non abbia anche una licenza per il piano per chiamate Microsoft, le chiamate a qualsiasi numero tranne i numeri che corrispondono ai modelli +1 425 XXX XX XX o +1 206 XXX XX XX nella configurazione di esempio vengono eliminate.</span><span class="sxs-lookup"><span data-stu-id="81798-141">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="81798-142">Se l'utente ha una licenza per il piano di chiamata, la chiamata viene instradata automaticamente in base ai criteri del Piano chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81798-142">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> <span data-ttu-id="81798-143">Il Piano chiamate Microsoft si applica automaticamente come ultimo percorso a tutti gli utenti con la licenza Microsoft Calling Plan e non richiede una configurazione aggiuntiva del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="81798-143">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="81798-144">Nell'esempio illustrato nel diagramma seguente viene aggiunta una route vocale per inviare chiamate a tutti gli altri numeri statunitensi e canadesi (chiamate che vengono chiamate con schema di numeri +1 XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="81798-144">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian numbers (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Mostra i criteri di routing vocale con una terza route](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="81798-146">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Telefono Microsoft Sistema e Piano chiamate Microsoft), viene usato il percorso automatico.</span><span class="sxs-lookup"><span data-stu-id="81798-146">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), the automatic route is used.</span></span> <span data-ttu-id="81798-147">Se nulla corrisponde ai modelli di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata tramite il Piano chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81798-147">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed through Microsoft Calling Plan.</span></span> <span data-ttu-id="81798-148">Se l'utente ha solo Telefono Microsoft sistema, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="81798-148">If the user only has Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="81798-149">Il valore Priority per la route "Other +1" non è importante in questo caso perché esiste una sola route che corrisponde al modello +1 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="81798-149">The Priority value for route "Other +1" doesn't matter in this case because there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="81798-150">Se un utente effettua una chiamata a +1 324 567 89 89 e sia sbc5.contoso.biz che sbc6.contoso.biz non sono disponibili, la chiamata viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="81798-150">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="81798-151">La tabella seguente riepiloga la configurazione usando tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="81798-151">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="81798-152">In questo esempio, tutte e tre le route fanno parte dello stesso utilizzo PSTN, "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="81798-152">In this example, all three routes are part of the same PSTN usage, "US and Canada".</span></span>  <span data-ttu-id="81798-153">Tutte le route sono associate all'utilizzo PSTN "Stati Uniti e Canada" e l'utilizzo PSTN è associato al criterio di routing vocale "Solo stati Uniti".</span><span class="sxs-lookup"><span data-stu-id="81798-153">All routes are associated with the "US and Canada" PSTN usage  and the PSTN usage is associated with the "US Only" voice routing policy.</span></span>

|<span data-ttu-id="81798-154">**Utilizzo PSTN**</span><span class="sxs-lookup"><span data-stu-id="81798-154">**PSTN usage**</span></span>|<span data-ttu-id="81798-155">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="81798-155">**Voice route**</span></span>|<span data-ttu-id="81798-156">**Schema numerico**</span><span class="sxs-lookup"><span data-stu-id="81798-156">**Number pattern**</span></span>|<span data-ttu-id="81798-157">**Priority**</span><span class="sxs-lookup"><span data-stu-id="81798-157">**Priority**</span></span>|<span data-ttu-id="81798-158">**SBC**</span><span class="sxs-lookup"><span data-stu-id="81798-158">**SBC**</span></span>|<span data-ttu-id="81798-159">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="81798-159">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81798-160">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="81798-160">US and Canada</span></span>|<span data-ttu-id="81798-161">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="81798-161">"Redmond 1"</span></span>|<span data-ttu-id="81798-162">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="81798-162">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="81798-163">1</span><span class="sxs-lookup"><span data-stu-id="81798-163">1</span></span>|<span data-ttu-id="81798-164">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-164">sbc1.contoso.biz</span></span><br/><span data-ttu-id="81798-165">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-165">sbc2.contoso.biz</span></span>|<span data-ttu-id="81798-166">Percorso attivo per i numeri chiamati +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="81798-166">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="81798-167">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="81798-167">US and Canada</span></span>|<span data-ttu-id="81798-168">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="81798-168">"Redmond 2"</span></span>|<span data-ttu-id="81798-169">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="81798-169">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="81798-170">2</span><span class="sxs-lookup"><span data-stu-id="81798-170">2</span></span>|<span data-ttu-id="81798-171">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-171">sbc3.contoso.biz</span></span><br/><span data-ttu-id="81798-172">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-172">sbc4.contoso.biz</span></span>|<span data-ttu-id="81798-173">Percorso di backup per i numeri denominati +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="81798-173">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="81798-174">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="81798-174">US and Canada</span></span>|<span data-ttu-id="81798-175">"Altro +1"</span><span class="sxs-lookup"><span data-stu-id="81798-175">"Other +1"</span></span>|<span data-ttu-id="81798-176">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="81798-176">^\\+1(\d{10})$</span></span>|<span data-ttu-id="81798-177">3</span><span class="sxs-lookup"><span data-stu-id="81798-177">3</span></span>|<span data-ttu-id="81798-178">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-178">sbc5.contoso.biz</span></span><br/><span data-ttu-id="81798-179">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-179">sbc6.contoso.biz</span></span>|<span data-ttu-id="81798-180">Percorso per i numeri chiamati +1 XXX XXX XX XX (tranne +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="81798-180">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

## <a name="example-1-configuration-steps"></a><span data-ttu-id="81798-181">Esempio 1: Passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="81798-181">Example 1: Configuration steps</span></span>

<span data-ttu-id="81798-182">L'esempio seguente mostra come:</span><span class="sxs-lookup"><span data-stu-id="81798-182">The following example shows how to:</span></span>

1. <span data-ttu-id="81798-183">Creare un singolo utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="81798-183">Create a single PSTN usage.</span></span>
2. <span data-ttu-id="81798-184">Configurare tre route vocali.</span><span class="sxs-lookup"><span data-stu-id="81798-184">Configure three voice routes.</span></span>
3. <span data-ttu-id="81798-185">Creare un criterio di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="81798-185">Create a voice routing policy.</span></span>
4. <span data-ttu-id="81798-186">Assegnare il criterio a un utente denominato Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="81798-186">Assign the policy to a user named Spencer Low.</span></span>

<span data-ttu-id="81798-187">È possibile usare [l'Microsoft Teams di amministrazione o](#admincenterexample1) [PowerShell](#powershellexample1) per eseguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="81798-187">You can use the [Microsoft Teams admin center](#admincenterexample1) or [PowerShell](#powershellexample1) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="81798-188">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81798-188">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample1"></a>

#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="81798-189">Passaggio 1: Creare l'utilizzo PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="81798-189">Step 1: Create the "US and Canada" PSTN usage</span></span>

1. <span data-ttu-id="81798-190">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing e quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**</span><span class="sxs-lookup"><span data-stu-id="81798-190">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="81798-191">Fare **clic su** Aggiungi , digitare Stati Uniti e **Canada** e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="81798-191">Click **Add**, type **US and Canada**, and then click **Apply**.</span></span>

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="81798-192">Passaggio 2: Creare tre route vocali (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="81798-192">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="81798-193">La procedura seguente descrive come creare una route vocale.</span><span class="sxs-lookup"><span data-stu-id="81798-193">The following steps describe how to create a voice route.</span></span> <span data-ttu-id="81798-194">Usare questa procedura per creare le tre route vocali denominate Redmond 1, Redmond 2 e Other +1 per questo esempio usando le impostazioni descritte nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="81798-194">Use these steps to create the three voice routes named Redmond 1, Redmond 2, and Other +1 for this example by using the settings outlined in the earlier table.</span></span>

1. <span data-ttu-id="81798-195">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Routing** vocale diretto e quindi  >  selezionare la **scheda Route** vocali.</span><span class="sxs-lookup"><span data-stu-id="81798-195">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="81798-196">Fare **clic su** Aggiungi e quindi immettere un nome e una descrizione per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="81798-196">Click **Add**, and then enter a name and description for the voice route.</span></span>
3. <span data-ttu-id="81798-197">Impostare la priorità e specificare il modello di numero composto.</span><span class="sxs-lookup"><span data-stu-id="81798-197">Set the priority and specify the dialed number pattern.</span></span>
4. <span data-ttu-id="81798-198">Per registrare un SBC con la route vocale, in SBC registrati **(facoltativo)** fare clic su Aggiungi **SBC,** selezionare gli SBC da registrare e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="81798-198">To enroll an SBC with the voice route, under **SBCs enrolled (optional)**, click **Add SBCs**, select the SBCs you want to enroll, and then click **Apply**.</span></span>
5. <span data-ttu-id="81798-199">Per aggiungere record di utilizzo PSTN, in Record di utilizzo **PSTN (facoltativo)** fare clic su Aggiungi utilizzo **PSTN,** selezionare i record PSTN da aggiungere e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="81798-199">To add PSTN usage records, under **PSTN usage records (optional)**, click **Add PSTN usage**, select the PSTN records you want to add, and then click **Apply**.</span></span>
6. <span data-ttu-id="81798-200">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81798-200">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="81798-201">Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio</span><span class="sxs-lookup"><span data-stu-id="81798-201">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

1. <span data-ttu-id="81798-202">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare **a** Criteri di  >  **routing vocale** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="81798-202">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="81798-203">Digitare **Solo stati Uniti** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="81798-203">Type **US Only** as the name and add a description.</span></span>
3. <span data-ttu-id="81798-204">In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="81798-204">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then click **Apply**.</span></span>
4. <span data-ttu-id="81798-205">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81798-205">Click **Save**.</span></span>

<span data-ttu-id="81798-206">Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="81798-206">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="81798-207">Passaggio 4: Assegnare i criteri di routing vocale a un utente denominato Spencer Low</span><span class="sxs-lookup"><span data-stu-id="81798-207">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

1. <span data-ttu-id="81798-208">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="81798-208">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="81798-209">Fare **clic su** Criteri e quindi accanto a Criteri **assegnati** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="81798-209">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="81798-210">In **Criteri routing vocale** selezionare il criterio "Solo stati Uniti" e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="81798-210">Under **Voice routing policy**, select the "US Only" policy, and then click **Save**.</span></span>

<span data-ttu-id="81798-211">Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="81798-211">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="81798-212">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="81798-212">Using PowerShell</span></span>
<a name="powershellexample1"></a>


#### <a name="step-1-create-the-us-and-canada-pstn-usage"></a><span data-ttu-id="81798-213">Passaggio 1: Creare l'utilizzo PSTN "Stati Uniti e Canada"</span><span class="sxs-lookup"><span data-stu-id="81798-213">Step 1: Create the "US and Canada" PSTN usage</span></span>

<span data-ttu-id="81798-214">In una sessione remota di PowerShell in Skype for Business Online digitare:</span><span class="sxs-lookup"><span data-stu-id="81798-214">In a remote PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="81798-215">Verificare che l'utilizzo sia stato creato immettendo:</span><span class="sxs-lookup"><span data-stu-id="81798-215">Verify that the usage was created by entering:</span></span>

```PowerShell
Get-CSOnlinePSTNUsage
``` 

<span data-ttu-id="81798-216">Che restituisce un elenco di nomi che potrebbero essere troncati:</span><span class="sxs-lookup"><span data-stu-id="81798-216">Which returns a list of names that may be truncated:</span></span>

```console
Identity    : Global
Usage        : {testusage, US and Canada, International, karlUsage. . .}
```

<span data-ttu-id="81798-217">L'esempio seguente mostra il risultato dell'esecuzione del comando `(Get-CSOnlinePSTNUsage).usage` PowerShell per visualizzare i nomi completi (non troncati):</span><span class="sxs-lookup"><span data-stu-id="81798-217">The following example shows the result of running the `(Get-CSOnlinePSTNUsage).usage` PowerShell command to display full names (not truncated):</span></span>

```console
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
```

#### <a name="step-2-create-three-voice-routes-redmond-1-redmond-2-and-other-1"></a><span data-ttu-id="81798-218">Passaggio 2: Creare tre route vocali (Redmond 1, Redmond 2 e Other +1)</span><span class="sxs-lookup"><span data-stu-id="81798-218">Step 2: Create three voice routes (Redmond 1, Redmond 2, and Other +1)</span></span>

<span data-ttu-id="81798-219">Per creare il percorso "Redmond 1", in una sessione di PowerShell in Skype for Business Online, immettere:</span><span class="sxs-lookup"><span data-stu-id="81798-219">To create the "Redmond 1" route, in a PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="81798-220">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="81798-220">Which returns:</span></span>

```console
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
```

<span data-ttu-id="81798-221">Per creare il percorso di Redmond 2, immettere:</span><span class="sxs-lookup"><span data-stu-id="81798-221">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="81798-222">Per creare il percorso Altro +1, immettere:</span><span class="sxs-lookup"><span data-stu-id="81798-222">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="81798-223">Assicurarsi che l'espressione regolare nell'attributo NumberPattern sia un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="81798-223">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="81798-224">È possibile testarlo usando questo sito Web: [https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="81798-224">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="81798-225">In alcuni casi, è necessario instradare tutte le chiamate allo stesso SBC; use -NumberPattern ".\*"</span><span class="sxs-lookup"><span data-stu-id="81798-225">In some cases, there is a need to route all calls to the same SBC; use -NumberPattern ".\*"</span></span>

<span data-ttu-id="81798-226">Instradare tutte le chiamate allo stesso SBC.</span><span class="sxs-lookup"><span data-stu-id="81798-226">Route all calls to the same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="81798-227">Verificare di aver configurato correttamente la route eseguendo il comando `Get-CSOnlineVoiceRoute` di PowerShell usando le opzioni come illustrato:</span><span class="sxs-lookup"><span data-stu-id="81798-227">Verify that you've correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="81798-228">Che dovrebbe restituire:</span><span class="sxs-lookup"><span data-stu-id="81798-228">Which should return:</span></span>

```console
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
```

<span data-ttu-id="81798-229">Nell'esempio, alla route "Altro +1" è stata assegnata automaticamente la priorità 4.</span><span class="sxs-lookup"><span data-stu-id="81798-229">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

#### <a name="step-3-create-a-voice-routing-policy-named-us-only-and-add-the-us-and-canada-pstn-usage-to-the-policy"></a><span data-ttu-id="81798-230">Passaggio 3: Creare un criterio di routing vocale denominato "Solo Stati Uniti" e aggiungere l'utilizzo PSTN "Stati Uniti e Canada" al criterio</span><span class="sxs-lookup"><span data-stu-id="81798-230">Step 3: Create a voice routing policy named "US Only" and add the "US and Canada" PSTN usage to the policy</span></span>

<span data-ttu-id="81798-231">In una sessione di PowerShell in Skype for Business Online digitare:</span><span class="sxs-lookup"><span data-stu-id="81798-231">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="81798-232">Il risultato è illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="81798-232">The result is shown in this example:</span></span>

```console
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-spencer-low"></a><span data-ttu-id="81798-233">Passaggio 4: Assegnare i criteri di routing vocale a un utente denominato Spencer Low</span><span class="sxs-lookup"><span data-stu-id="81798-233">Step 4: Assign the voice routing policy to a user named Spencer Low</span></span>

<span data-ttu-id="81798-234">In una sessione di PowerShell in Skype for Business Online digitare:</span><span class="sxs-lookup"><span data-stu-id="81798-234">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="81798-235">Convalidare l'assegnazione dei criteri immettendo questo comando:</span><span class="sxs-lookup"><span data-stu-id="81798-235">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="81798-236">Il comando restituisce quanto segue:</span><span class="sxs-lookup"><span data-stu-id="81798-236">The command returns the following:</span></span>

```console
OnlineVoiceRoutingPolicy
---------------------
US Only
```

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a><span data-ttu-id="81798-237">Esempio 2: Routing vocale con più utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="81798-237">Example 2: Voice routing with multiple PSTN usages</span></span>

<span data-ttu-id="81798-238">Il criterio di routing vocale creato nell'esempio 1 consente solo le chiamate a numeri di telefono negli Stati Uniti e in Canada, a meno che all'utente non sia assegnata anche la licenza Del piano per chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81798-238">The voice routing policy created in Example 1 only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="81798-239">Nell'esempio seguente è possibile creare il criterio di routing vocale "Nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="81798-239">In the example that follows, you can create the "No Restrictions" voice routing policy.</span></span> <span data-ttu-id="81798-240">Il criterio riutilizza l'utilizzo PSTN "Stati Uniti e Canada" creato nell'esempio 1, oltre al nuovo utilizzo PSTN "internazionale".</span><span class="sxs-lookup"><span data-stu-id="81798-240">The policy reuses the "US and Canada" PSTN usage created in Example 1, as well as the new "International" PSTN usage.</span></span> <span data-ttu-id="81798-241">Questo criterio indirizza tutte le altre chiamate agli SBC sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="81798-241">This policy routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

<span data-ttu-id="81798-242">Gli esempi illustrati assegnano il criterio Solo stati Uniti all'utente Spencer Low e il criterio Nessuna restrizione all'utente John Woods in modo che il routing si verifichi come segue:</span><span class="sxs-lookup"><span data-stu-id="81798-242">The examples that are shown assign the US Only policy to user Spencer Low, and the No Restrictions policy to the user John Woods so that routing occurs as follows:</span></span>

- <span data-ttu-id="81798-243">Politica di Spencer Low - Solo stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="81798-243">Spencer Low – US Only policy.</span></span>  <span data-ttu-id="81798-244">Le chiamate sono consentite solo a numeri statunitensi e canadesi.</span><span class="sxs-lookup"><span data-stu-id="81798-244">Calls are allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="81798-245">Quando si chiama l'intervallo di numeri di Redmond, è necessario usare il set specifico di SBC.</span><span class="sxs-lookup"><span data-stu-id="81798-245">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="81798-246">I numeri non statunitensi non verranno instradati a meno che all'utente non sia assegnata la licenza per il piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="81798-246">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

- <span data-ttu-id="81798-247">John Woods - Politica internazionale.</span><span class="sxs-lookup"><span data-stu-id="81798-247">John Woods – International policy.</span></span>  <span data-ttu-id="81798-248">Le chiamate sono consentite a qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="81798-248">Calls are allowed to any number.</span></span> <span data-ttu-id="81798-249">Quando si chiama l'intervallo di numeri di Redmond, è necessario usare il set specifico di SBC.</span><span class="sxs-lookup"><span data-stu-id="81798-249">When calling to the Redmond number range, the specific set of SBCs must be used.</span></span> <span data-ttu-id="81798-250">I numeri non statunitensi verranno instradati usando sbc2.contoso.biz e sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="81798-250">Non-US numbers will be routed using sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Mostra i criteri di routing vocale assegnati all'utente Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="81798-252">Per tutte le altre chiamate, se un utente ha entrambe le licenze (Telefono Microsoft Sistema e Piano chiamate Microsoft), viene usato il percorso automatico.</span><span class="sxs-lookup"><span data-stu-id="81798-252">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), automatic route is used.</span></span> <span data-ttu-id="81798-253">Se nulla corrisponde ai modelli di numero nelle route vocali online create dall'amministratore, la chiamata viene instradata usando il Piano chiamate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81798-253">If nothing matches the number patterns in the administrator-created online voice routes, then the call is routed using Microsoft Calling Plan.</span></span>  <span data-ttu-id="81798-254">Se l'utente ha Telefono Microsoft sistema, la chiamata viene interrotta perché non sono disponibili regole di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="81798-254">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Mostra i criteri di routing vocale assegnati all'utente John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="81798-256">La tabella seguente riepiloga le designazioni di utilizzo e le route vocali dei criteri di routing "Nessuna restrizione".</span><span class="sxs-lookup"><span data-stu-id="81798-256">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

| <span data-ttu-id="81798-257">Utilizzo PSTN</span><span class="sxs-lookup"><span data-stu-id="81798-257">PSTN usage</span></span> | <span data-ttu-id="81798-258">Route vocale</span><span class="sxs-lookup"><span data-stu-id="81798-258">Voice route</span></span> | <span data-ttu-id="81798-259">Schema numerico</span><span class="sxs-lookup"><span data-stu-id="81798-259">Number pattern</span></span> | <span data-ttu-id="81798-260">Priority</span><span class="sxs-lookup"><span data-stu-id="81798-260">Priority</span></span> | <span data-ttu-id="81798-261">SBC</span><span class="sxs-lookup"><span data-stu-id="81798-261">SBC</span></span> | <span data-ttu-id="81798-262">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81798-262">Description</span></span> |
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81798-263">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="81798-263">US and Canada</span></span>|<span data-ttu-id="81798-264">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="81798-264">"Redmond 1"</span></span>|<span data-ttu-id="81798-265">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="81798-265">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="81798-266">1</span><span class="sxs-lookup"><span data-stu-id="81798-266">1</span></span>|<span data-ttu-id="81798-267">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-267">sbc1.contoso.biz</span></span><br/><span data-ttu-id="81798-268">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-268">sbc2.contoso.biz</span></span>|<span data-ttu-id="81798-269">Percorso attivo per i numeri dei callee +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="81798-269">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="81798-270">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="81798-270">US and Canada</span></span>|<span data-ttu-id="81798-271">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="81798-271">"Redmond 2"</span></span>|<span data-ttu-id="81798-272">^\\+1(425 \| 206)(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="81798-272">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="81798-273">2</span><span class="sxs-lookup"><span data-stu-id="81798-273">2</span></span>|<span data-ttu-id="81798-274">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-274">sbc3.contoso.biz</span></span><br/><span data-ttu-id="81798-275">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-275">sbc4.contoso.biz</span></span>|<span data-ttu-id="81798-276">Percorso di backup per i numeri dei callee +1 425 XXX XX XX o +1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="81798-276">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="81798-277">Stati Uniti e Canada</span><span class="sxs-lookup"><span data-stu-id="81798-277">US and Canada</span></span>|<span data-ttu-id="81798-278">"Altro +1"</span><span class="sxs-lookup"><span data-stu-id="81798-278">"Other +1"</span></span>|<span data-ttu-id="81798-279">^\\+1(\d {10} )$</span><span class="sxs-lookup"><span data-stu-id="81798-279">^\\+1(\d{10})$</span></span>|<span data-ttu-id="81798-280">3</span><span class="sxs-lookup"><span data-stu-id="81798-280">3</span></span>|<span data-ttu-id="81798-281">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-281">sbc5.contoso.biz</span></span><br/><span data-ttu-id="81798-282">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-282">sbc6.contoso.biz</span></span>|<span data-ttu-id="81798-283">Percorso per i numeri dei callee +1 XXX XXX XX XX (ad eccezione di +1 425 XXX XX XX o +1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="81798-283">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="81798-284">Internazionale</span><span class="sxs-lookup"><span data-stu-id="81798-284">International</span></span>|<span data-ttu-id="81798-285">Internazionale</span><span class="sxs-lookup"><span data-stu-id="81798-285">International</span></span>|<span data-ttu-id="81798-286">\d+</span><span class="sxs-lookup"><span data-stu-id="81798-286">\d+</span></span>|<span data-ttu-id="81798-287">4</span><span class="sxs-lookup"><span data-stu-id="81798-287">4</span></span>|<span data-ttu-id="81798-288">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-288">sbc2.contoso.biz</span></span><br/><span data-ttu-id="81798-289">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="81798-289">sbc5.contoso.biz</span></span>|<span data-ttu-id="81798-290">Percorso per qualsiasi schema di numeri</span><span class="sxs-lookup"><span data-stu-id="81798-290">Route for any number pattern</span></span> |

  > [!NOTE]
  > - <span data-ttu-id="81798-291">L'ordine di utilizzo di PSTN nei criteri di routing vocale è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="81798-291">The order of PSTN usages in voice routing policies is critical.</span></span> <span data-ttu-id="81798-292">Gli utilizzi vengono applicati nell'ordine e, se viene trovata una corrispondenza nel primo utilizzo, gli altri utilizzi non vengono mai valutati.</span><span class="sxs-lookup"><span data-stu-id="81798-292">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="81798-293">L'utilizzo PSTN "internazionale" deve essere inserito dopo l'utilizzo PSTN "Stati Uniti e Canada".</span><span class="sxs-lookup"><span data-stu-id="81798-293">The "International" PSTN usage must be placed after the  "US and Canada" PSTN usage.</span></span> <span data-ttu-id="81798-294">Per modificare l'ordine degli utilizzi PSTN, eseguire il `Set-CSOnlineVoiceRoutingPolicy` comando.</span><span class="sxs-lookup"><span data-stu-id="81798-294">To change the order of the PSTN usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="81798-295">Ad esempio, per modificare l'ordine da "Stati Uniti e Canada" prima e "Internazionale" secondo all'ordine inverso:</span><span class="sxs-lookup"><span data-stu-id="81798-295">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="81798-296">La priorità per le route vocali "Altre +1" e "Internazionali" viene assegnata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="81798-296">The priority for "Other +1" and "International" voice routes are assigned automatically.</span></span> <span data-ttu-id="81798-297">Non hanno importanza se hanno priorità inferiori rispetto a "Redmond 1" e "Redmond 2".</span><span class="sxs-lookup"><span data-stu-id="81798-297">They don't matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

## <a name="example-2-configuration-steps"></a><span data-ttu-id="81798-298">Esempio 2: Passaggi di configurazione</span><span class="sxs-lookup"><span data-stu-id="81798-298">Example 2: Configuration steps</span></span>

<span data-ttu-id="81798-299">L'esempio seguente mostra come:</span><span class="sxs-lookup"><span data-stu-id="81798-299">The following example shows how to:</span></span>

1. <span data-ttu-id="81798-300">Creare un nuovo utilizzo PSTN denominato Internazionale.</span><span class="sxs-lookup"><span data-stu-id="81798-300">Create a new PSTN usage called International.</span></span>
2. <span data-ttu-id="81798-301">Creare una nuova route vocale denominata Internazionale.</span><span class="sxs-lookup"><span data-stu-id="81798-301">Create a new voice route called International.</span></span>
3. <span data-ttu-id="81798-302">Creare un criterio di routing vocale denominato Nessuna restrizione.</span><span class="sxs-lookup"><span data-stu-id="81798-302">Create a voice routing policy called No Restrictions.</span></span>
4. <span data-ttu-id="81798-303">Assegnare il criterio all'utente John Woods.</span><span class="sxs-lookup"><span data-stu-id="81798-303">Assign the policy to user John Woods.</span></span>

<span data-ttu-id="81798-304">È possibile usare [l'Microsoft Teams di amministrazione o](#admincenterexample2) [PowerShell](#powershellexample2) per eseguire questa procedura.</span><span class="sxs-lookup"><span data-stu-id="81798-304">You can use the [Microsoft Teams admin center](#admincenterexample2) or [PowerShell](#powershellexample2) to perform these steps.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="81798-305">Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81798-305">Using the Microsoft Teams admin center</span></span>
<a name="admincenterexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="81798-306">Passaggio 1: Creare l'utilizzo PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="81798-306">Step 1: Create the "International" PSTN usage</span></span>

1. <span data-ttu-id="81798-307">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **Voice** Direct Routing e quindi nell'angolo in alto a destra selezionare Gestisci record di utilizzo  >   **PSTN.**</span><span class="sxs-lookup"><span data-stu-id="81798-307">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then in the upper-right corner, select **Manage PSTN usage records**.</span></span>
2. <span data-ttu-id="81798-308">Fare **clic su Aggiungi**, digitare **Internazionale** e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="81798-308">Click **Add**, type **International**, and then click **Apply**.</span></span>

#### <a name="step-2-create-the-international-voice-route"></a><span data-ttu-id="81798-309">Passaggio 2: Creare la route vocale "Internazionale"</span><span class="sxs-lookup"><span data-stu-id="81798-309">Step 2: Create the "International" voice route</span></span>

1. <span data-ttu-id="81798-310">Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Routing** vocale diretto e quindi  >  selezionare la **scheda Route** vocali.</span><span class="sxs-lookup"><span data-stu-id="81798-310">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Direct Routing**, and then select the **Voice routes** tab.</span></span>
2. <span data-ttu-id="81798-311">Fare **clic su** Aggiungi, immettere "Internazionale" come nome e quindi aggiungere la descrizione.</span><span class="sxs-lookup"><span data-stu-id="81798-311">Click **Add**, enter "International" as the name, and then add the description.</span></span>
3. <span data-ttu-id="81798-312">Impostare la priorità su 4 e quindi impostare lo schema di numeri composto su \d+.</span><span class="sxs-lookup"><span data-stu-id="81798-312">Set the priority to 4, and then set the dialed number pattern to \d+.</span></span>
4. <span data-ttu-id="81798-313">In **SBC registrati (facoltativo)** fare clic su **Aggiungi SBC,** selezionare sbc2.contoso.biz e sbc5.contoso.biz e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="81798-313">Under **SBCs enrolled (optional)**, click **Add SBCs**, select sbc2.contoso.biz and sbc5.contoso.biz, and then click **Apply**.</span></span>
5. <span data-ttu-id="81798-314">In **Record di utilizzo PSTN (facoltativo)** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Internazionale" e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="81798-314">Under **PSTN usage records (optional)**, click **Add PSTN usage**, select the "International" PSTN usage record, and then click **Apply**.</span></span>
6. <span data-ttu-id="81798-315">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81798-315">Click **Save**.</span></span>

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions-and-add-the-us-and-canada-and-international-pstn-usages-to-the-policy"></a><span data-ttu-id="81798-316">Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione" e aggiungere al criterio gli utilizzi PSTN "Stati Uniti e Canada" e "Internazionali"</span><span class="sxs-lookup"><span data-stu-id="81798-316">Step 3: Create a voice routing policy named "No Restrictions" and add the "US and Canada" and "International" PSTN usages to the policy</span></span>

<span data-ttu-id="81798-317">L'utilizzo PSTN "Stati Uniti e Canada" viene riutilizzato in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate al numero "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.</span><span class="sxs-lookup"><span data-stu-id="81798-317">The PSTN usage "US and Canada" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

1. <span data-ttu-id="81798-318">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione, passare **a** Criteri di  >  **routing vocale** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="81798-318">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span>
2. <span data-ttu-id="81798-319">Digitare **No Restrictions** come nome e aggiungere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="81798-319">Type **No Restrictions** as the name and add a description.</span></span>
3. <span data-ttu-id="81798-320">In **Record di utilizzo PSTN** fare clic su Aggiungi utilizzo **PSTN,** selezionare il record di utilizzo PSTN "Stati Uniti e Canada" e quindi selezionare il record di utilizzo PSTN "Internazionale".</span><span class="sxs-lookup"><span data-stu-id="81798-320">Under **PSTN usage records**, click **Add PSTN usage**, select the "US and Canada" PSTN usage record, and then select the "International" PSTN usage record.</span></span> <span data-ttu-id="81798-321">Fare clic **su Applica**.</span><span class="sxs-lookup"><span data-stu-id="81798-321">Click **Apply**.</span></span>

    <span data-ttu-id="81798-322">Prendere nota dell'ordine di utilizzo pstn:</span><span class="sxs-lookup"><span data-stu-id="81798-322">Take note of the order of PSTN usages:</span></span>

    - <span data-ttu-id="81798-323">Se una chiamata effettuata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come in questo esempio, la chiamata segue il percorso impostato nell'utilizzo "Stati Uniti e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="81798-323">If a call made to number "+1 425 XXX XX XX" with the usages configured as in this example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="81798-324">In altre informazioni, la chiamata viene instradata sbc1.contoso.biz e sbc2.contoso.biz e quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.</span><span class="sxs-lookup"><span data-stu-id="81798-324">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

    - <span data-ttu-id="81798-325">Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="81798-325">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span>

4. <span data-ttu-id="81798-326">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81798-326">Click **Save**.</span></span>

<span data-ttu-id="81798-327">Per altre informazioni, vedere [Gestire i criteri di routing vocale.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="81798-327">To learn more, see [Manage voice routing policies](manage-voice-routing-policies.md).</span></span>

#### <a name="step-4-assign-the-voice-routing-policy-to-a-user-named-john-woods"></a><span data-ttu-id="81798-328">Passaggio 4: Assegnare i criteri di routing vocale a un utente denominato John Woods</span><span class="sxs-lookup"><span data-stu-id="81798-328">Step 4: Assign the voice routing policy to a user named John Woods</span></span>

1. <span data-ttu-id="81798-329">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="81798-329">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="81798-330">Fare **clic su** Criteri e quindi accanto a Criteri **assegnati** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="81798-330">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="81798-331">In **Criteri routing vocale** selezionare il criterio "Nessuna restrizione" e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="81798-331">Under **Voice routing policy**, select the "No Restrictions" policy, and then click **Save**.</span></span>

<span data-ttu-id="81798-332">Il risultato è che i criteri vocali applicati alle chiamate di John Woods sono senza restrizioni e seguiranno la logica del routing delle chiamate disponibile per le chiamate usa, canada e internazionali.</span><span class="sxs-lookup"><span data-stu-id="81798-332">The result is that the voice policy applied to John Woods' calls is unrestricted and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="81798-333">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="81798-333">Using PowerShell</span></span>
<a name="powershellexample2"></a>

#### <a name="step-1-create-the-international-pstn-usage"></a><span data-ttu-id="81798-334">Passaggio 1: Creare l'utilizzo PSTN "internazionale"</span><span class="sxs-lookup"><span data-stu-id="81798-334">Step 1: Create the "International" PSTN usage</span></span>

<span data-ttu-id="81798-335">In una sessione remota di PowerShell in Skype for Business Online immettere:</span><span class="sxs-lookup"><span data-stu-id="81798-335">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

#### <a name="step-2--create-a-new-voice-route-named-international"></a><span data-ttu-id="81798-336">Passaggio 2: Creare una nuova route vocale denominata "Internazionale"</span><span class="sxs-lookup"><span data-stu-id="81798-336">Step 2:  Create a new voice route named "International"</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```

<span data-ttu-id="81798-337">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="81798-337">Which returns:</span></span>

```console
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
```

#### <a name="step-3-create-a-voice-routing-policy-named-no-restrictions"></a><span data-ttu-id="81798-338">Passaggio 3: Creare un criterio di routing vocale denominato "Nessuna restrizione"</span><span class="sxs-lookup"><span data-stu-id="81798-338">Step 3: Create a voice routing policy named "No Restrictions"</span></span>

<span data-ttu-id="81798-339">L'utilizzo PSTN "Redmond 1" e "Redmond" vengono riutilizzati in questo criterio di routing vocale per mantenere una gestione speciale per le chiamate ai numeri "+1 425 XXX XX XX" e "+1 206 XXX XX XX" come chiamate locali o locali.</span><span class="sxs-lookup"><span data-stu-id="81798-339">The PSTN usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="81798-340">Prendere nota dell'ordine di utilizzo pstn:</span><span class="sxs-lookup"><span data-stu-id="81798-340">Take note of the order of PSTN usages:</span></span>

  - <span data-ttu-id="81798-341">Se una chiamata effettuata al numero "+1 425 XXX XX XX" con gli utilizzi configurati come nell'esempio seguente, la chiamata segue la route impostata nell'utilizzo "Stati Uniti e Canada" e viene applicata la logica di routing speciale.</span><span class="sxs-lookup"><span data-stu-id="81798-341">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="81798-342">In altre informazioni, la chiamata viene instradata sbc1.contoso.biz e sbc2.contoso.biz e quindi sbc3.contoso.biz e sbc4.contoso.biz come route di backup.</span><span class="sxs-lookup"><span data-stu-id="81798-342">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  - <span data-ttu-id="81798-343">Se l'utilizzo PSTN "internazionale" è precedente a "Stati Uniti e Canada", le chiamate a +1 425 XXX XX XX vengono instradati a sbc2.contoso.biz e sbc5.contoso.biz come parte della logica di routing.</span><span class="sxs-lookup"><span data-stu-id="81798-343">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="81798-344">Immettere il comando:</span><span class="sxs-lookup"><span data-stu-id="81798-344">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="81798-345">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="81798-345">Which returns:</span></span>

```console
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}     
    Description         :  
    RouteType               : BYOT
```

#### <a name="step-4-assign-the-voice-routing-policy-to-the-user-named-john-woods"></a><span data-ttu-id="81798-346">Passaggio 4: Assegnare i criteri di routing vocale all'utente denominato John Woods</span><span class="sxs-lookup"><span data-stu-id="81798-346">Step 4: Assign the voice routing policy to the user named John Woods</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions"
```

<span data-ttu-id="81798-347">Verificare quindi l'attività usando il comando:</span><span class="sxs-lookup"><span data-stu-id="81798-347">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="81798-348">Che restituisce:</span><span class="sxs-lookup"><span data-stu-id="81798-348">Which returns:</span></span>

```console
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
```

<span data-ttu-id="81798-349">Il risultato è che il criterio vocale applicato alle chiamate di John Woods è senza restrizioni e seguirà la logica del routing delle chiamate disponibile per le chiamate negli Stati Uniti, in Canada e in Internazionali.</span><span class="sxs-lookup"><span data-stu-id="81798-349">The result is that the voice policy applied to John Woods' calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="see-also"></a><span data-ttu-id="81798-350">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81798-350">See also</span></span>

[<span data-ttu-id="81798-351">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="81798-351">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="81798-352">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="81798-352">Configure Direct Routing</span></span>](direct-routing-configure.md)
