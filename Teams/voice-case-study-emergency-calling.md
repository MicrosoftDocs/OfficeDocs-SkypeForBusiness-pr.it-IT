---
title: Teams caso di studio contoso vocale
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams caso di studio vocale per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786029"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="29eb5-103">Caso di studio Contoso: Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="29eb5-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="29eb5-104">Per comprendere la disponibilità delle chiamate di emergenza e la terminologia relativa alle chiamate di emergenza, l'indirizzo, il luogo, la posizione per gli interventi di emergenza e l'indirizzo registrato Contoso ha esaminato Gestire le chiamate di emergenza e Pianificare e configurare le chiamate di emergenza &mdash; &mdash; [dinamiche.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="29eb5-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="29eb5-105">In Office 365, un utente del Piano chiamate viene abilitato automaticamente per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="29eb5-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="29eb5-106">Ma solo gli utenti del Piano chiamate negli Stati Uniti possono usare posizioni dinamiche per instradamento delle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="29eb5-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="29eb5-107">Per il routing diretto, Contoso ha appreso che è necessaria una configurazione aggiuntiva per il routing delle chiamate di emergenza e, eventualmente, per la connettività dei partner.</span><span class="sxs-lookup"><span data-stu-id="29eb5-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="29eb5-108">L'amministratore deve configurare la connessione a un provider di servizi di routing per gli interventi di emergenza (ERSP) (Stati Uniti) O configurare il Session Border Controller (SBC) per un'applicazione Emergency Location Identification Number (ELIN).</span><span class="sxs-lookup"><span data-stu-id="29eb5-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="29eb5-109">Contoso ha uffici negli Stati Uniti e all'esterno degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="29eb5-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="29eb5-110">Negli Stati Uniti, gli utenti del piano chiamate Contoso possono usare posizioni dinamiche per instradamento delle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="29eb5-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="29eb5-111">Al di fuori degli Stati Uniti, Contoso ha alcuni siti che usano piani per chiamate e alcuni siti connessi a Sistema telefonico tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="29eb5-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="29eb5-112">Casi d'uso per chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="29eb5-112">Emergency calling use cases</span></span>

<span data-ttu-id="29eb5-113">Dopo aver deciso in che modo Contoso si connetterà Telefono sistema, Contoso ha identificato i casi d'uso per le chiamate di emergenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="29eb5-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="29eb5-114">Utente del piano di chiamata negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="29eb5-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="29eb5-115">Utente del piano di chiamata al di fuori degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="29eb5-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="29eb5-116">Utente che si connette a Sistema telefonico tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="29eb5-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="29eb5-117">Utente del piano di chiamata negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="29eb5-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="29eb5-118">Ci sono requisiti per quando il numero di telefono deve essere associato a una posizione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="29eb5-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="29eb5-119">Per comprendere questi requisiti, Contoso ha esaminato [Considerazioni per i piani per chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="29eb5-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="29eb5-120">In base a questi requisiti, Contoso ha deciso di associare la località al numero di telefono quando un numero viene assegnato a un utente negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="29eb5-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="29eb5-121">Utente del piano di chiamata al di fuori degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="29eb5-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="29eb5-122">Per capire quando un numero di telefono deve essere associato a una località di emergenza, Contoso ha esaminato [Considerazioni per i piani per le chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="29eb5-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="29eb5-123">In base ai requisiti, Contoso ha deciso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="29eb5-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="29eb5-124">Contoso associerà la località al numero di telefono quando un numero viene assegnato a un utente in Canada.</span><span class="sxs-lookup"><span data-stu-id="29eb5-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="29eb5-125">Contoso assegna una posizione di emergenza quando il numero di telefono viene acquistato da Office 365 o quando un numero viene trasferito da un altro provider di servizi o gestore.</span><span class="sxs-lookup"><span data-stu-id="29eb5-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="29eb5-126">Utente che si connette a Sistema telefonico tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="29eb5-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="29eb5-127">Per pianificare il routing di emergenza per questo caso d'uso, Contoso ha esaminato [Considerazioni per il routing diretto.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="29eb5-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="29eb5-128">Poiché gli utenti di Routing diretto non ricevono chiamate di emergenza allo stesso modo degli utenti del piano di chiamata, Contoso ha dovuto decidere come fornire le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="29eb5-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="29eb5-129">Il routing diretto può essere connesso a un provider di servizi di routing di emergenza (ERSP).</span><span class="sxs-lookup"><span data-stu-id="29eb5-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="29eb5-130">Il routing diretto può anche avere un SBC che include un codice ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="29eb5-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="29eb5-131">Considerazioni sul provider di servizi di routing di emergenza (ERSP)</span><span class="sxs-lookup"><span data-stu-id="29eb5-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="29eb5-132">I provider di servizi di routing di emergenza (ESP) possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="29eb5-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="29eb5-133">Se un provider di servizi di routing per gli interventi di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita dinamicamente verranno automaticamente instradati al Punto di risposta per la sicurezza pubblica (PSAP) che serve tale posizione.</span><span class="sxs-lookup"><span data-stu-id="29eb5-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="29eb5-134">Le chiamate di emergenza senza una posizione acquisita dinamicamente vengono prima schermate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato in base alla posizione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="29eb5-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="29eb5-135">Considerazioni sull'ELIN</span><span class="sxs-lookup"><span data-stu-id="29eb5-135">ELIN considerations</span></span>

<span data-ttu-id="29eb5-136">Se un'applicazione SBC ELIN è integrata in una distribuzione di Routing diretto, è necessario eseguire altri passaggi di configurazione per associare gli indirizzi di emergenza ai numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="29eb5-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="29eb5-137">Contoso ha deciso di usare i session border controller che includono applicazioni ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="29eb5-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="29eb5-138">Notifica di Security Desk</span><span class="sxs-lookup"><span data-stu-id="29eb5-138">Security desk notification</span></span>

<span data-ttu-id="29eb5-139">La possibilità di inviare una notifica al desk di sicurezza quando viene effettuato un intervento di emergenza è disponibile sia per i piani per chiamate Microsoft che per Sistema telefonico Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="29eb5-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="29eb5-140">Contoso ha esaminato i dettagli nella notifica di Security desk per determinare se deve essere configurato nei propri uffici</span><span class="sxs-lookup"><span data-stu-id="29eb5-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="29eb5-141">Contoso ha deciso di usare la notifica del security desk.</span><span class="sxs-lookup"><span data-stu-id="29eb5-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="29eb5-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="29eb5-142">Configuration</span></span> 

<span data-ttu-id="29eb5-143">Contoso ha seguito la procedura descritta in [Configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md) per:</span><span class="sxs-lookup"><span data-stu-id="29eb5-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="29eb5-144">Assegnare indirizzi di emergenza</span><span class="sxs-lookup"><span data-stu-id="29eb5-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="29eb5-145">Configurare le impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="29eb5-145">Configure network settings</span></span> 

- <span data-ttu-id="29eb5-146">Configurare il servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="29eb5-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="29eb5-147">Configurare i criteri di emergenza</span><span class="sxs-lookup"><span data-stu-id="29eb5-147">Configure emergency policies</span></span> 

- <span data-ttu-id="29eb5-148">Abilitare utenti e siti</span><span class="sxs-lookup"><span data-stu-id="29eb5-148">Enable users and sites</span></span> 

- <span data-ttu-id="29eb5-149">Testare le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="29eb5-149">Test emergency calling</span></span> 

<span data-ttu-id="29eb5-150">Dopo aver configurato le chiamate di emergenza dinamiche, Contoso doveva assegnare la posizione all'utente appropriato.</span><span class="sxs-lookup"><span data-stu-id="29eb5-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="29eb5-151">Per aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione, Contoso ha seguito la procedura descritta in Aggiungere, modificare o rimuovere una posizione per gli interventi di [emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="29eb5-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="29eb5-152">Per creare luoghi per edifici, piani e uffici, Contoso ha seguito la procedura descritta in Aggiungere, modificare o rimuovere un luogo per un [luogo per gli interventi di emergenza.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="29eb5-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="29eb5-153">Per assegnare una posizione per gli interventi di emergenza, Contoso ha seguito la procedura descritta in Assegnare o modificare una posizione per [gli interventi di emergenza per un utente.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="29eb5-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 