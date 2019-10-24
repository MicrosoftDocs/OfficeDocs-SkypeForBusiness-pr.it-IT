---
title: Configurare chiamate di emergenza dinamiche
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurare chiamate di emergenza dinamiche
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "37639484"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="ae608-103">Pianificare e configurare chiamate di emergenza dinamiche per i piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="ae608-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="ae608-104">Le chiamate di emergenza dinamiche per i piani per le chiamate Microsoft offrono la possibilità di configurare e instradare telefonate di emergenza in base alla posizione corrente del client teams.</span><span class="sxs-lookup"><span data-stu-id="ae608-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="ae608-105">La possibilità di eseguire il routing automatico al punto di risposta di sicurezza pubblica appropriato (PSAP) o di informare il personale del servizio di sicurezza varia a seconda del paese di utilizzo dell'utente teams.</span><span class="sxs-lookup"><span data-stu-id="ae608-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="ae608-106">Le chiamate di emergenza dinamiche sono attualmente disponibili solo negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="ae608-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="ae608-107">La notifica di Security desk, tuttavia, è supportata in tutti i confini nazionali.</span><span class="sxs-lookup"><span data-stu-id="ae608-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="ae608-108">**All'interno degli Stati Uniti**è possibile configurare il routing dinamico delle chiamate di emergenza come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ae608-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="ae608-109">Se un client teams si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza provenienti da tale client vengono automaticamente indirizzate al PSAP che serve tale posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="ae608-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="ae608-110">Se un client teams non si trova in una posizione di emergenza dinamica definita dall'inquilino, le chiamate di emergenza provenienti da tale client vengono visualizzate da un Call Center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP al servizio della posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="ae608-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="ae608-111">È possibile configurare la notifica di Security desk come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ae608-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="ae608-112">Se un client teams si trova in un sito di rete definito dal tenant, verranno comunicati i membri del gruppo di sicurezza configurati per il sito.</span><span class="sxs-lookup"><span data-stu-id="ae608-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="ae608-113">Se un client teams non si trova in un sito di rete definito dal tenant, verranno comunicati i membri del gruppo di sicurezza configurati per l'utente.</span><span class="sxs-lookup"><span data-stu-id="ae608-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="ae608-114">Al **di fuori degli Stati Uniti**, le chiamate di emergenza vengono instradate al PSAP mappato al numero di telefono assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="ae608-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="ae608-115">Alcuni paesi, ad esempio la Gran Bretagna e il Canada, schermano le chiamate a livello nazionale prima di trasferire il chiamante all'appropriato PSAP, mentre altri si instradano direttamente al PSAP indipendentemente dalla posizione in cui si trova attualmente l'utente.</span><span class="sxs-lookup"><span data-stu-id="ae608-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="ae608-116">Tieni presente che puoi configurare la notifica di Security desk dinamico per tutti gli utenti del piano chiamante.</span><span class="sxs-lookup"><span data-stu-id="ae608-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="ae608-117">Client supportati</span><span class="sxs-lookup"><span data-stu-id="ae608-117">Supported clients</span></span>

<span data-ttu-id="ae608-118">I client seguenti sono attualmente supportati.</span><span class="sxs-lookup"><span data-stu-id="ae608-118">The following clients are currently supported.</span></span>  <span data-ttu-id="ae608-119">Controlla spesso per vedere gli aggiornamenti di questo elenco.</span><span class="sxs-lookup"><span data-stu-id="ae608-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="ae608-120">Client desktop teams per Windows</span><span class="sxs-lookup"><span data-stu-id="ae608-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="ae608-121">Client desktop teams per Mac</span><span class="sxs-lookup"><span data-stu-id="ae608-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="ae608-122">Configurare chiamate di emergenza dinamiche</span><span class="sxs-lookup"><span data-stu-id="ae608-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="ae608-123">Per configurare le chiamate di emergenza dinamiche, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae608-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="ae608-124">Configurare gli indirizzi di emergenza</span><span class="sxs-lookup"><span data-stu-id="ae608-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="ae608-125">Configurare le impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ae608-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="ae608-126">Configurare il servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="ae608-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="ae608-127">Configurare i criteri di emergenza</span><span class="sxs-lookup"><span data-stu-id="ae608-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="ae608-128">Abilitare utenti e siti</span><span class="sxs-lookup"><span data-stu-id="ae608-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="ae608-129">Verificare le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ae608-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="ae608-130">Configurare gli indirizzi di emergenza</span><span class="sxs-lookup"><span data-stu-id="ae608-130">Configure emergency addresses</span></span>

<span data-ttu-id="ae608-131">Per supportare il routing automatizzato negli Stati Uniti, è necessario configurare completamente l'indirizzo civico che fa parte delle posizioni di emergenza assegnate agli identificatori di rete e includere i codici Geo associati.</span><span class="sxs-lookup"><span data-stu-id="ae608-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="ae608-132">Gli indirizzi di emergenza senza Geo-codici non possono essere assegnati agli identificatori di rete necessari per le posizioni dinamiche.</span><span class="sxs-lookup"><span data-stu-id="ae608-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="ae608-133">Se si immette un indirizzo di emergenza tramite l'interfaccia di amministrazione di Microsoft teams, i codici Geo vengono automaticamente inclusi se viene trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ae608-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="ae608-134">Se non viene trovata automaticamente una corrispondenza, si avrà la possibilità di creare manualmente un indirizzo di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ae608-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="ae608-135">Questo significa che se è configurato un indirizzo di emergenza esistente per le chiamate di emergenza, è necessario ricreare lo stesso indirizzo per includere i codici Geo.</span><span class="sxs-lookup"><span data-stu-id="ae608-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="ae608-136">Per distinguere tra i due indirizzi, è necessario includere una descrizione diversa.</span><span class="sxs-lookup"><span data-stu-id="ae608-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="ae608-137">Il nuovo indirizzo di emergenza può essere assegnato agli utenti che hanno l'indirizzo precedente.</span><span class="sxs-lookup"><span data-stu-id="ae608-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="ae608-138">Quando è stata eseguita la migrazione completa, è possibile eliminare l'indirizzo precedente.</span><span class="sxs-lookup"><span data-stu-id="ae608-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="ae608-139">Per altre informazioni sulla configurazione degli indirizzi di emergenza, vedere [quali sono le posizioni di emergenza, i luoghi e il routing delle chiamate?](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="ae608-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="ae608-140">Configurare le impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ae608-140">Configure network settings</span></span>

<span data-ttu-id="ae608-141">È necessario configurare le impostazioni di rete per ottenere in modo dinamico un percorso di emergenza usato per il routing delle chiamate di emergenza e, facoltativamente, per garantire la configurazione dinamica delle notifiche di Security desk.</span><span class="sxs-lookup"><span data-stu-id="ae608-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="ae608-142">L'esperienza di chiamata in caso di emergenza desiderata indicherà quali impostazioni di rete devono essere configurate.</span><span class="sxs-lookup"><span data-stu-id="ae608-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="ae608-143">Tieni presente le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae608-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="ae608-144">Gli IP attendibili contengono una raccolta di indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="ae608-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="ae608-145">I percorsi dinamici verranno abilitati solo se l'IP esterno dell'utente corrisponde a un IP nella raccolta IP attendibile.</span><span class="sxs-lookup"><span data-stu-id="ae608-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="ae608-146">Una corrispondenza può essere eseguita in base agli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="ae608-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="ae608-147">Un'area di rete contiene una raccolta di siti di rete.</span><span class="sxs-lookup"><span data-stu-id="ae608-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="ae608-148">Un sito di rete rappresenta un percorso in cui l'organizzazione ha un valore fisico, ad esempio un ufficio, un set di edifici o un campus.</span><span class="sxs-lookup"><span data-stu-id="ae608-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="ae608-149">Questi siti sono definiti come una raccolta di subnet IP.</span><span class="sxs-lookup"><span data-stu-id="ae608-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="ae608-150">Una subnet di rete deve essere associata a un sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="ae608-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="ae608-151">La posizione di un cliente viene determinata in base alla subnet della rete e al sito di rete associato.</span><span class="sxs-lookup"><span data-stu-id="ae608-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="ae608-152">Per gli utenti del piano chiamante:</span><span class="sxs-lookup"><span data-stu-id="ae608-152">For Calling Plan users:</span></span>

- <span data-ttu-id="ae608-153">Se è necessaria la configurazione dinamica della notifica del servizio di sicurezza, è necessario configurare sia gli indirizzi IP attendibili che i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="ae608-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="ae608-154">Se sono necessarie solo posizioni dinamiche, è necessario configurare solo gli indirizzi IP attendibili.</span><span class="sxs-lookup"><span data-stu-id="ae608-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="ae608-155">Se non sono necessarie, la configurazione delle impostazioni di rete non è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="ae608-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="ae608-156">Per altre informazioni, vedere [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md), che descrive come configurare le impostazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="ae608-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="ae608-157">Le informazioni contenute in questo articolo sono valide sia per i piani di chiamata che per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="ae608-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="ae608-158">Configurare il servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="ae608-158">Configure Location Information Service</span></span>

<span data-ttu-id="ae608-159">Un client teams ottiene gli indirizzi di emergenza dai percorsi di emergenza associati a identificatori di rete diversi.</span><span class="sxs-lookup"><span data-stu-id="ae608-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="ae608-160">Le subnet e i punti di accesso wireless sono entrambi supportati.</span><span class="sxs-lookup"><span data-stu-id="ae608-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="ae608-161">Il supporto per switch/porta Ethernet è in sospeso.</span><span class="sxs-lookup"><span data-stu-id="ae608-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="ae608-162">Per configurare il servizio LIS (Location Information Service) con gli identificatori di rete e le posizioni di emergenza, usare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae608-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="ae608-163">Ottieni, imposta, Rimuovi-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="ae608-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="ae608-164">Ottieni, imposta, Rimuovi-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="ae608-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="ae608-165">Ottieni, imposta, Rimuovi-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="ae608-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="ae608-166">Ottieni, imposta, Rimuovi-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="ae608-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="ae608-167">Se le subnet vengono usate come parte dei siti di rete, devono essere ridefinite nel servizio informazioni sulla posizione per il rendering di posizioni dinamiche.</span><span class="sxs-lookup"><span data-stu-id="ae608-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="ae608-168">Configurare i criteri di emergenza</span><span class="sxs-lookup"><span data-stu-id="ae608-168">Configure emergency policies</span></span>

<span data-ttu-id="ae608-169">I criteri di emergenza determinano cosa succede quando un utente dell'organizzazione effettua una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ae608-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="ae608-170">Puoi impostare gli utenti che notificano e come vengono informati quando un utente chiama i servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ae608-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="ae608-171">Ad esempio, è possibile configurare le impostazioni dei criteri per comunicare automaticamente al banco di sicurezza dell'organizzazione e farli ascoltare in caso di chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ae608-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="ae608-172">Puoi gestire i criteri di emergenza usando i cmdlet New-, set-e Grant-CsTeamsEmergencyCalling Policy.</span><span class="sxs-lookup"><span data-stu-id="ae608-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="ae608-173">Per altre informazioni, vedere [gestire i criteri per le chiamate di emergenza in teams](manage-emergency-calling-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ae608-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="ae608-174">Abilitare utenti e siti</span><span class="sxs-lookup"><span data-stu-id="ae608-174">Enable users and sites</span></span>

<span data-ttu-id="ae608-175">Quando gli utenti del piano chiamante vengono abilitati automaticamente per le chiamate di emergenza, è necessario abilitare gli utenti per la notifica del servizio di sicurezza configurando il criterio delle chiamate di emergenza, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ae608-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="ae608-176">È anche possibile assegnare i criteri delle chiamate di emergenza a un sito di rete, come illustrato nell'esempio seguente, che assegna un criterio denominato "criteri di chiamata di emergenza contoso 1" al sito 1:</span><span class="sxs-lookup"><span data-stu-id="ae608-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="ae608-177">Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e, se l'utente è in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="ae608-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="ae608-178">Verificare le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ae608-178">Test emergency calling</span></span>

<span data-ttu-id="ae608-179">Per testare le chiamate di emergenza negli Stati Uniti, usare il numero di emergenza predefinito per il test 933.</span><span class="sxs-lookup"><span data-stu-id="ae608-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="ae608-180">Questo numero viene indirizzato a un bot, che riprende il numero di telefono chiamante (ID linea chiamante), l'indirizzo o la posizione di emergenza e se la chiamata viene indirizzata automaticamente al PSAP o prima schermata.</span><span class="sxs-lookup"><span data-stu-id="ae608-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  