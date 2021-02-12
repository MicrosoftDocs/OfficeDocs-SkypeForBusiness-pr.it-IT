---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786029"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="9aa4d-103">Case study Contoso: Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="9aa4d-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="9aa4d-104">Per conoscere la disponibilità delle chiamate di emergenza e la terminologia relativa all'indirizzo di emergenza, al luogo, alla posizione per gli interventi di emergenza e all'indirizzo registrato Contoso ha esaminato Gestisci chiamate di emergenza e Pianifica e configura le chiamate di emergenza &mdash; &mdash; dinamiche. [](what-are-emergency-locations-addresses-and-call-routing.md) [](configure-dynamic-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="9aa4d-105">In Office 365, un utente del Piano per chiamate viene abilitato automaticamente per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="9aa4d-106">Tuttavia, solo gli utenti del Piano per chiamate negli Stati Uniti possono utilizzare posizioni dinamiche per l'instradamento delle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="9aa4d-107">Per l'instradamento diretto, Contoso ha appreso che è necessaria una configurazione aggiuntiva per l'instradamento delle chiamate di emergenza e probabilmente per la connettività del partner.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="9aa4d-108">L'amministratore deve configurare la connessione a un provider del servizio di instradamento di emergenza (ERSP) (Stati Uniti) O configurare il controller dei confini della sessione (SBC) per un'applicazione ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="9aa4d-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="9aa4d-109">Contoso ha uffici negli Stati Uniti e al di fuori degli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="9aa4d-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="9aa4d-110">Negli Stati Uniti, gli utenti del Piano per chiamate Contoso possono utilizzare posizioni dinamiche per l'instradamento delle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="9aa4d-111">Al di fuori degli Stati Uniti, Contoso ha alcuni siti che utilizzano Piani per chiamate e altri sono connessi al Sistema telefonico attraverso l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="9aa4d-112">Casi d'uso per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="9aa4d-112">Emergency calling use cases</span></span>

<span data-ttu-id="9aa4d-113">Dopo aver deciso come Contoso si connetterà al sistema telefonico, Contoso ha identificato i seguenti casi d'uso per le chiamate di emergenza:</span><span class="sxs-lookup"><span data-stu-id="9aa4d-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="9aa4d-114">Utente del Piano per chiamate negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9aa4d-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="9aa4d-115">Utente del Piano per chiamate al di fuori degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9aa4d-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="9aa4d-116">Utente che si connette al Sistema telefonico tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="9aa4d-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="9aa4d-117">Utente del Piano per chiamate negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9aa4d-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="9aa4d-118">Ci sono dei requisiti quando il numero di telefono deve essere associato a una posizione per gli interventi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="9aa4d-119">Per comprendere questi requisiti, Contoso ha esaminato [considerazioni per i piani per chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="9aa4d-120">In base a questi requisiti, Contoso ha deciso di associare la località al numero di telefono quando un numero viene assegnato a un utente negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="9aa4d-121">Utente del Piano per chiamate al di fuori degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="9aa4d-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="9aa4d-122">Per capire quando un numero di telefono deve essere associato a una posizione per gli interventi di emergenza, Contoso ha esaminato [considerazioni per i piani per chiamate.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="9aa4d-123">In base ai requisiti, Contoso ha deciso quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9aa4d-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="9aa4d-124">Contoso associa la località al numero di telefono quando viene assegnato un numero a un utente in Canada.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="9aa4d-125">Contoso assegna una posizione per gli interventi di emergenza quando il numero di telefono viene acquisito da Office 365 o quando un numero viene trasferito da un altro fornitore di servizi o gestore.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="9aa4d-126">Utente che si connette al Sistema telefonico tramite routing diretto</span><span class="sxs-lookup"><span data-stu-id="9aa4d-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="9aa4d-127">Per pianificare l'instradamento di emergenza per questo caso di utilizzo, Contoso ha esaminato [considerazioni per il routing diretto.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="9aa4d-128">Poiché gli utenti con instradamento diretto non ricevono le chiamate di emergenza come gli utenti del Piano per chiamate, Contoso ha dovuto decidere come effettuare le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="9aa4d-129">L'instradamento diretto può essere connesso a un provider di servizi di instradamento di emergenza (ERSP, Emergency Routing Service).</span><span class="sxs-lookup"><span data-stu-id="9aa4d-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="9aa4d-130">L'instradamento diretto può anche avere un SBC che include un numero ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="9aa4d-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="9aa4d-131">Considerazioni sul provider di servizi di emergenza (EERSP, Emergency Routing Service Provider)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="9aa4d-132">Gli operatori del servizio di instradamento di emergenza possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="9aa4d-133">Se un provider di servizi di instradamento di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita dinamicamente verranno automaticamente indirizzate al punto PSAP (Public Safety Answering Point) che serve tale posizione.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="9aa4d-134">Le chiamate di emergenza senza una posizione acquisita dinamicamente vengono innanzitutto schermate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di emergenza appropriato in base alla posizione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="9aa4d-135">Considerazioni sull'ELIN</span><span class="sxs-lookup"><span data-stu-id="9aa4d-135">ELIN considerations</span></span>

<span data-ttu-id="9aa4d-136">Se un'applicazione SBC ELIN è integrata in una distribuzione di routing diretto, è necessario eseguire altri passaggi di configurazione per associare gli indirizzi di emergenza ai numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="9aa4d-137">Contoso ha deciso di usare i controller dei confini della sessione che includono applicazioni ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="9aa4d-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="9aa4d-138">Notifica security desk</span><span class="sxs-lookup"><span data-stu-id="9aa4d-138">Security desk notification</span></span>

<span data-ttu-id="9aa4d-139">La possibilità di avvisare il desk sicurezza durante l'esecuzione di una chiamata di emergenza è disponibile sia per i Piani per chiamate Microsoft che per l'instradamento diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="9aa4d-140">Contoso ha esaminato i dettagli nella notifica security desk per determinare se deve essere configurato negli uffici</span><span class="sxs-lookup"><span data-stu-id="9aa4d-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="9aa4d-141">Contoso ha deciso di usare la notifica del security desk.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="9aa4d-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="9aa4d-142">Configuration</span></span> 

<span data-ttu-id="9aa4d-143">Contoso ha seguito la procedura descritta in [Configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md) per:</span><span class="sxs-lookup"><span data-stu-id="9aa4d-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="9aa4d-144">Assegnare indirizzi per gli interventi di emergenza</span><span class="sxs-lookup"><span data-stu-id="9aa4d-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="9aa4d-145">Configurare le impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9aa4d-145">Configure network settings</span></span> 

- <span data-ttu-id="9aa4d-146">Configurazione del servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="9aa4d-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="9aa4d-147">Configurare i criteri di emergenza</span><span class="sxs-lookup"><span data-stu-id="9aa4d-147">Configure emergency policies</span></span> 

- <span data-ttu-id="9aa4d-148">Abilitare utenti e siti</span><span class="sxs-lookup"><span data-stu-id="9aa4d-148">Enable users and sites</span></span> 

- <span data-ttu-id="9aa4d-149">Testare le chiamate d'emergenza</span><span class="sxs-lookup"><span data-stu-id="9aa4d-149">Test emergency calling</span></span> 

<span data-ttu-id="9aa4d-150">Dopo aver configurato le chiamate di emergenza dinamiche, Contoso deve assegnare la posizione all'utente appropriato.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="9aa4d-151">Per aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione, Contoso ha seguito la procedura aggiunta, modifica o rimozione di una posizione per gli interventi di [emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="9aa4d-152">Per creare luoghi per edifici, piani e uffici, Contoso ha seguito la procedura descritta in Aggiungere, modificare o rimuovere un luogo per una posizione per [gli interventi di emergenza.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="9aa4d-153">Per assegnare una posizione per gli interventi di emergenza, Contoso ha seguito la procedura descritta in Assegnare o modificare una posizione per [gli interventi di emergenza per un utente.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="9aa4d-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 