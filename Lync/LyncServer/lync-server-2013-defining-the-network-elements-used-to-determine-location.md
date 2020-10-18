---
title: 'Lync Server 2013: definizione degli elementi di rete utilizzati per determinare la posizione'
description: 'Lync Server 2013: definizione degli elementi di rete utilizzati per determinare la posizione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a77ad0a7d704bf2cc43118db45d9bcfb89daa327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576282"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="2cb49-103">Definizione degli elementi di rete utilizzati per determinare la posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb49-103">Defining the network elements used to determine location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cb49-104">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="2cb49-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="2cb49-105">Se si sta configurando l'infrastruttura di Lync Server per il supporto del rilevamento automatico delle posizioni dei client, è necessario prima di tutto decidere quali elementi di rete si intende utilizzare per mappare i chiamanti alle posizioni.</span><span class="sxs-lookup"><span data-stu-id="2cb49-105">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="2cb49-106">In Lync Server 2013, è possibile associare i seguenti elementi di rete Layer 2 e Layer 3 con percorsi:</span><span class="sxs-lookup"><span data-stu-id="2cb49-106">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="2cb49-107">Indirizzi BSSID (Basic Service Set Identification) di punti di accesso wireless (livello 2)</span><span class="sxs-lookup"><span data-stu-id="2cb49-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="2cb49-108">Porta di commutazione LLDP (livello 2)</span><span class="sxs-lookup"><span data-stu-id="2cb49-108">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="2cb49-109">ID chassis di commutazione LLDP (livello 2)</span><span class="sxs-lookup"><span data-stu-id="2cb49-109">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="2cb49-110">Subnet IP (livello 3)</span><span class="sxs-lookup"><span data-stu-id="2cb49-110">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="2cb49-111">Indirizzi MAC dei client (livello 2)</span><span class="sxs-lookup"><span data-stu-id="2cb49-111">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="2cb49-112">Gli elementi di rete sono elencati in ordine di precedenza.</span><span class="sxs-lookup"><span data-stu-id="2cb49-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="2cb49-113">Se un client può essere individuato utilizzando più di un elemento di rete, Lync Server utilizza l'ordine di precedenza per determinare il meccanismo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2cb49-113">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="2cb49-114">Nelle sezioni seguenti sono disponibili ulteriori dettagli sull'utilizzo di ciascun elemento di rete.</span><span class="sxs-lookup"><span data-stu-id="2cb49-114">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cb49-115">Quando si utilizzano gli elementi di rete per mappare i chiamanti alle posizioni, è estremamente importante mantenere aggiornati i database del servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="2cb49-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="2cb49-116">Ad esempio, se si aggiunge o modifica un elemento di rete, ad esempio se si aggiunge un punto di accesso wireless, è necessario eliminare la voce esistente e aggiungere la nuova nel database delle località.</span><span class="sxs-lookup"><span data-stu-id="2cb49-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="2cb49-117">Punto di accesso wireless</span><span class="sxs-lookup"><span data-stu-id="2cb49-117">Wireless Access Point</span></span>

<span data-ttu-id="2cb49-118">Quando un client si connette alla rete in modalità wireless, la richiesta della posizione utilizza l'indirizzo BSSID del punto di accesso wireless per determinarne la posizione.</span><span class="sxs-lookup"><span data-stu-id="2cb49-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="2cb49-119">Se il client effettua il roaming, il punto di accesso wireless indicato potrebbe non essere quello più vicino ed è anche possibile che venga rilevato un punto di accesso wireless che si trova in un piano diverso dell'edificio.</span><span class="sxs-lookup"><span data-stu-id="2cb49-119">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="2cb49-120">Per indicare che la posizione è approssimativa, è possibile anteporre al valore di posizione un descrittore Near o Close to.</span><span class="sxs-lookup"><span data-stu-id="2cb49-120">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="2cb49-121">Questo metodo presuppone che l'indirizzo BSSID di ogni punto di accesso wireless sia statico.</span><span class="sxs-lookup"><span data-stu-id="2cb49-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="2cb49-122">Se il fornitore del punto di accesso wireless, tuttavia, utilizza BSSID assegnati dinamicamente, l'indirizzo BSSID ottenuto da un punto di accesso wireless può cambiare (ad esempio in seguito a una modifica di configurazione apportata al punto di accesso wireless) e i client wireless possono trovarsi in una situazione in cui non ricevono una posizione.</span><span class="sxs-lookup"><span data-stu-id="2cb49-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="2cb49-123">Per evitare questa possibilità, è necessario popolare il database del servizio informazioni percorso con posizioni ERL per tutti i possibili indirizzi di BSSID utilizzati da ogni WAP.</span><span class="sxs-lookup"><span data-stu-id="2cb49-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="2cb49-124">Porte e switch LLDP</span><span class="sxs-lookup"><span data-stu-id="2cb49-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="2cb49-p106">Switch Ethernet gestiti che supportano LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) possono comunicare informazioni su porta e identità a client compatibili con LLDP-MED, che possono quindi essere soggetti a query sul database delle località per fornire la posizione del dispositivo. È possibile associare ERL unicamente a ID chassis di commutazione oppure è possibile eseguirne il mapping a livello di porta.</span><span class="sxs-lookup"><span data-stu-id="2cb49-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cb49-127">Lync Server 2013 supporta l'utilizzo di LLDP-MED per determinare solo i percorsi dei dispositivi Lync Phone Edition e Lync 2013 in esecuzione su Windows 8.</span><span class="sxs-lookup"><span data-stu-id="2cb49-127">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="2cb49-128">Se è necessario utilizzare i dati di livello 2 di switch-level per determinare la posizione di altri client Lync basati su PC cablati, è necessario utilizzare il metodo di indirizzo MAC client.</span><span class="sxs-lookup"><span data-stu-id="2cb49-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="2cb49-129">Subnet</span><span class="sxs-lookup"><span data-stu-id="2cb49-129">Subnet</span></span>

<span data-ttu-id="2cb49-130">Le subnet IP di layer 3 forniscono un meccanismo supportato da tutti i client di Lync Server che possono essere utilizzati per rilevare automaticamente la posizione del client.</span><span class="sxs-lookup"><span data-stu-id="2cb49-130">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="2cb49-131">L'utilizzo di subnet IP rappresenta il metodo di individuazione più facile per configurare e gestire client cablati.</span><span class="sxs-lookup"><span data-stu-id="2cb49-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="2cb49-132">Prima di scegliere di utilizzare le subnet, tuttavia, è consigliabile rispondere alle domande seguenti per determinare se la specificità di posizione della subnet è sufficiente per individuare accuratamente un client:</span><span class="sxs-lookup"><span data-stu-id="2cb49-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="2cb49-133">Una o più subnet del client occupano più piani?</span><span class="sxs-lookup"><span data-stu-id="2cb49-133">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="2cb49-134">Una o più subnet occupano più edifici?</span><span class="sxs-lookup"><span data-stu-id="2cb49-134">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="2cb49-135">Quanto spazio di un piano è occupato da ogni subnet del client?</span><span class="sxs-lookup"><span data-stu-id="2cb49-135">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="2cb49-p109">Se la subnet occupa un'area troppo ampia, può essere necessario utilizzare un altro meccanismo per individuare i client. Se si tratta di una scelta pratica, tuttavia, è consigliabile che gli utenti riorganizzino le proprie subnet IP in modo da soddisfare i requisiti di specificità di posizione ERL anziché affrontare i costi e la complessità di soluzioni basate su SNMP di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2cb49-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="2cb49-138">Indirizzo MAC del client</span><span class="sxs-lookup"><span data-stu-id="2cb49-138">Client MAC Address</span></span>

<span data-ttu-id="2cb49-139">Per utilizzare l'indirizzo MAC di un computer client per individuare un chiamante, sono necessari switch Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di rilevare gli indirizzi MAC dei client Lync connessi a (o tramite) tali switch.</span><span class="sxs-lookup"><span data-stu-id="2cb49-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="2cb49-140">La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC degli endpoint connessi a ogni porta e ottiene gli ID porta corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="2cb49-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="2cb49-141">Durante la richiesta di un client di Lync al servizio informazioni percorso, il servizio informazioni percorso esegue una query nell'applicazione di terze parti utilizzando l'indirizzo MAC del client e quindi restituisce gli indirizzi IP e gli ID di porta corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="2cb49-141">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="2cb49-142">Il servizio informazioni percorso utilizza queste informazioni per eseguire una query sul relativo layer 2 wiremap pubblicato per un record corrispondente e restituisce il percorso al client.</span><span class="sxs-lookup"><span data-stu-id="2cb49-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="2cb49-143">Se si utilizza questa opzione, assicurarsi che gli identificatori di porta degli switch siano coerenti tra l'applicazione SNMP e i record del database delle località pubblicati.</span><span class="sxs-lookup"><span data-stu-id="2cb49-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cb49-144">Alcune soluzioni SNMP di terze parti sono in grado di supportare switch di accesso non gestito. Se l'opzione che gestisce il client Lync non è gestita, ma ha un collegamento a un commutatore di distribuzione gestito, l'opzione Managed Switch può riferire all'applicazione SNMP gli indirizzi MAC dei client connessi al commutatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="2cb49-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="2cb49-145">Queste informazioni consentono al servizio informazioni percorso di identificare il percorso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2cb49-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="2cb49-146">Tuttavia, è possibile assegnare solo un singolo gli elfi a tutte le porte sull'opzione non gestita, in modo che la specificità della posizione sia disponibile solo a livello di chassis dell'opzione di accesso, non del livello di porta.</span><span class="sxs-lookup"><span data-stu-id="2cb49-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

