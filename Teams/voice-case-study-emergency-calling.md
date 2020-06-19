---
title: Case Study di teams Voice contoso
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
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786029"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="9198c-103">Case Study di Contoso: chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="9198c-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="9198c-104">Per comprendere la disponibilità di chiamate di emergenza e la terminologia relativa all'indirizzo di emergenza per le chiamate di emergenza &mdash; , luogo, luogo di emergenza e indirizzo registrato &mdash; Contoso Recensito [Gestisci chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md) e [Pianifica e configura le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="9198c-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="9198c-105">In Office 365 un utente del piano di chiamata viene abilitato automaticamente per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9198c-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="9198c-106">Ma solo gli utenti del piano chiamante negli Stati Uniti possono usare posizioni dinamiche per il routing delle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9198c-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="9198c-107">Per il routing diretto, Contoso ha imparato che è necessaria una configurazione aggiuntiva per il routing delle chiamate di emergenza e possibilmente per la connettività dei partner.</span><span class="sxs-lookup"><span data-stu-id="9198c-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="9198c-108">L'amministratore deve configurare la connessione a un provider di servizi di routing di emergenza (ERSP) (Stati Uniti) o configurare il session border controller (SBC) per un'applicazione ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="9198c-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="9198c-109">Contoso ha uffici negli Stati Uniti ed esterni agli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="9198c-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="9198c-110">Negli Stati Uniti, contoso Calling Plan gli utenti possono usare posizioni dinamiche per il routing delle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9198c-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="9198c-111">Al di fuori degli Stati Uniti, Contoso ha alcuni siti che usano piani di chiamata e alcuni siti connessi al sistema telefonico tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="9198c-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="9198c-112">Casi di utilizzo delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="9198c-112">Emergency calling use cases</span></span>

<span data-ttu-id="9198c-113">Dopo aver deciso in che modo Contoso si connette al sistema telefonico, Contoso ha identificato i casi di utilizzo delle chiamate di emergenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="9198c-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="9198c-114">Utente del piano chiamante negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9198c-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="9198c-115">Utente del piano chiamante al di fuori degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9198c-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="9198c-116">Utente che si connette al sistema telefonico tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="9198c-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="9198c-117">Utente del piano chiamante negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9198c-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="9198c-118">Esistono requisiti per i casi in cui il numero di telefono deve essere associato a una posizione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9198c-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="9198c-119">Per comprendere questi requisiti, Contoso ha esaminato le [considerazioni per i piani di chiamata](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="9198c-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="9198c-120">In base a questi requisiti, Contoso ha deciso di associare la posizione al numero di telefono quando un numero viene assegnato a un utente negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="9198c-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="9198c-121">Utente del piano chiamante al di fuori degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9198c-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="9198c-122">Per capire quando un numero di telefono deve essere associato a una posizione di emergenza, Contoso ha esaminato le [considerazioni per i piani di chiamata](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="9198c-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="9198c-123">In base ai requisiti, Contoso ha deciso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9198c-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="9198c-124">Contoso associa la posizione al numero di telefono quando un numero viene assegnato a un utente in Canada.</span><span class="sxs-lookup"><span data-stu-id="9198c-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="9198c-125">Contoso assegnerà una posizione di emergenza quando il numero di telefono viene acquisito da Office 365 o quando un numero viene trasferito da un altro provider o gestore di servizi.</span><span class="sxs-lookup"><span data-stu-id="9198c-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="9198c-126">Utente che si connette al sistema telefonico tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="9198c-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="9198c-127">Per pianificare il routing delle emergenze per questo caso di utilizzo, Contoso ha esaminato le [considerazioni per il routing diretto](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="9198c-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="9198c-128">Poiché gli utenti del routing diretto non ricevono chiamate di emergenza allo stesso modo degli utenti del piano di chiamata, Contoso ha dovuto decidere come ottenere chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9198c-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="9198c-129">Il routing diretto può essere connesso a un provider di servizi di routing di emergenza (ERSP).</span><span class="sxs-lookup"><span data-stu-id="9198c-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="9198c-130">Il routing diretto può anche avere un SBC che include un numero di identificazione della posizione di emergenza (ELIN).</span><span class="sxs-lookup"><span data-stu-id="9198c-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="9198c-131">Considerazioni sul provider del servizio di routing (ERSP) Emergency</span><span class="sxs-lookup"><span data-stu-id="9198c-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="9198c-132">I provider di servizi di routing di emergenza (ERSPs) possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9198c-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="9198c-133">Se un provider di servizi di routing di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita in modo dinamico verranno indirizzate automaticamente al punto di PSAP (Public Safety Answering Point) che serve tale posizione.</span><span class="sxs-lookup"><span data-stu-id="9198c-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="9198c-134">Le chiamate di emergenza senza una posizione acquisita in modo dinamico vengono prima visualizzate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato in base al percorso aggiornato.</span><span class="sxs-lookup"><span data-stu-id="9198c-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="9198c-135">Considerazioni su ELIN</span><span class="sxs-lookup"><span data-stu-id="9198c-135">ELIN considerations</span></span>

<span data-ttu-id="9198c-136">Se un'applicazione ELIN SBC è integrata in una distribuzione di routing diretto, è necessario che siano presenti ulteriori passaggi di configurazione per associare gli indirizzi di emergenza a numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="9198c-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="9198c-137">Contoso ha deciso di usare i controller di bordo della sessione che includono le applicazioni ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="9198c-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="9198c-138">Notifica di Security desk</span><span class="sxs-lookup"><span data-stu-id="9198c-138">Security desk notification</span></span>

<span data-ttu-id="9198c-139">La possibilità di inviare una notifica al banco di sicurezza quando viene inserita una chiamata di emergenza è disponibile sia per i piani di chiamate Microsoft che per il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="9198c-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="9198c-140">Contoso ha esaminato i dettagli nella notifica di Security desk per determinare se la configurazione deve essere configurata presso gli uffici</span><span class="sxs-lookup"><span data-stu-id="9198c-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="9198c-141">Contoso ha deciso di usare la notifica di Security desk.</span><span class="sxs-lookup"><span data-stu-id="9198c-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="9198c-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="9198c-142">Configuration</span></span> 

<span data-ttu-id="9198c-143">Contoso ha seguito la procedura descritta in [configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md) in:</span><span class="sxs-lookup"><span data-stu-id="9198c-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="9198c-144">Assegnare indirizzi di emergenza</span><span class="sxs-lookup"><span data-stu-id="9198c-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="9198c-145">Configurare le impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9198c-145">Configure network settings</span></span> 

- <span data-ttu-id="9198c-146">Configurare il servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="9198c-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="9198c-147">Configurare i criteri di emergenza</span><span class="sxs-lookup"><span data-stu-id="9198c-147">Configure emergency policies</span></span> 

- <span data-ttu-id="9198c-148">Abilitare utenti e siti</span><span class="sxs-lookup"><span data-stu-id="9198c-148">Enable users and sites</span></span> 

- <span data-ttu-id="9198c-149">Verificare le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="9198c-149">Test emergency calling</span></span> 

<span data-ttu-id="9198c-150">Dopo la configurazione delle chiamate di emergenza dinamiche, contoso doveva assegnare la posizione all'utente appropriato.</span><span class="sxs-lookup"><span data-stu-id="9198c-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="9198c-151">Per aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione, Contoso ha seguito la procedura descritta in [aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="9198c-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="9198c-152">Per creare posizioni per edifici, pavimenti e uffici, Contoso ha seguito la procedura descritta in [aggiungere, modificare o rimuovere una posizione per un luogo di emergenza](add-change-remove-emergency-place-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="9198c-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="9198c-153">Per assegnare una posizione di emergenza, Contoso ha seguito la procedura descritta in [assegnare o modificare una posizione di emergenza per un utente](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="9198c-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 