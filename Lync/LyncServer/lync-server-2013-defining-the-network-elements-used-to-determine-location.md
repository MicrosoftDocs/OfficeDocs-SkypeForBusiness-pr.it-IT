---
title: 'Lync Server 2013: definizione degli elementi di rete usati per determinare la posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572e7e5392390e659b52853cb47e30f696c65e91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="e2ad0-102">Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2ad0-102">Defining the network elements used to determine location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2ad0-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e2ad0-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e2ad0-104">Se si sta configurando l'infrastruttura di Lync Server per supportare il rilevamento automatico della posizione del client, è prima di tutto necessario decidere quali elementi di rete usare per eseguire il mapping dei chiamanti alle posizioni.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-104">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="e2ad0-105">In Lync Server 2013 è possibile associare gli elementi di rete Layer 2 e Layer 3 seguenti con posizioni:</span><span class="sxs-lookup"><span data-stu-id="e2ad0-105">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="e2ad0-106">Indirizzi di BSSID (Service Set Identification Point) di base (WAP) wireless (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e2ad0-106">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="e2ad0-107">LLDP Switch Port (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e2ad0-107">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="e2ad0-108">LLDP switch ID chassis (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e2ad0-108">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="e2ad0-109">Subnet IP (Layer 3)</span><span class="sxs-lookup"><span data-stu-id="e2ad0-109">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="e2ad0-110">Indirizzi MAC client (Layer 2)</span><span class="sxs-lookup"><span data-stu-id="e2ad0-110">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="e2ad0-111">Gli elementi di rete sono elencati in ordine di precedenza.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-111">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="e2ad0-112">Se un client può essere individuato usando più elementi di rete, Lync Server usa l'ordine di precedenza per determinare il meccanismo da usare.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-112">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="e2ad0-113">Nelle sezioni seguenti sono disponibili altri dettagli per l'uso di ogni elemento di rete.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-113">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e2ad0-114">Quando si usano gli elementi di rete per eseguire il mapping dei chiamanti alle posizioni, è fondamentale che si mantenga aggiornato il database del servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-114">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="e2ad0-115">Se ad esempio si aggiunge o si modifica un elemento di rete, come l'aggiunta di un WAP, è necessario eliminare la voce precedente e aggiungere la nuova voce nel database della posizione.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-115">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="e2ad0-116">Punto di accesso wireless</span><span class="sxs-lookup"><span data-stu-id="e2ad0-116">Wireless Access Point</span></span>

<span data-ttu-id="e2ad0-117">Quando un client si connette alla rete in modalità wireless, la richiesta di posizione usa l'indirizzo BSSID del WAP per determinarne la posizione.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-117">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="e2ad0-118">Se il client è in roaming, il WAP indicato potrebbe non essere quello più vicino ed è anche possibile prendere un WAP che si trova su un piano diverso dell'edificio.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-118">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="e2ad0-119">Per indicare che la posizione è approssimativa, è possibile anteporre il valore della posizione a un descrittore vicino o vicino a.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-119">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="e2ad0-120">Questo metodo di posizione presuppone che il BSSID di ogni WAP sia statico.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-120">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="e2ad0-121">Tuttavia, se il fornitore WAP usa BSSIDs assegnati in modo dinamico, il BSSID ottenuto da un WAP potrebbe cambiare (ciò può verificarsi dopo una modifica della configurazione WAP) e i client wireless potrebbero essere lasciati in una situazione in cui non ricevono una posizione.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-121">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="e2ad0-122">Per evitare questa possibilità, è necessario popolare il database del servizio informazioni sulla posizione con posizioni ERL per tutti i possibili indirizzi di BSSID usati da ogni WAP.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-122">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="e2ad0-123">Porte e opzioni di LLDP</span><span class="sxs-lookup"><span data-stu-id="e2ad0-123">LLDP Ports and Switches</span></span>

<span data-ttu-id="e2ad0-124">Switch Ethernet gestiti che supportano il protocollo di individuazione dei collegamenti Layer-media endpoint Discover (LLDP-MED) è in grado di pubblicizzare le informazioni relative all'identità e alla porta ai client compatibili con LLDP-MED, che possono quindi essere interrogati sul database della posizione per specificare il posizione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-124">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device.</span></span> <span data-ttu-id="e2ad0-125">Puoi associare posizioni ERL esclusivamente all'ID dello chassis di switch oppure puoi mapparli fino al livello di porta.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-125">You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2ad0-126">Lync Server 2013 supporta l'uso di LLDP-MED per determinare solo le posizioni dei dispositivi Lync Phone Edition e Lync 2013 in uso in Windows 8.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-126">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="e2ad0-127">Se è necessario usare i dati di livello 2 per determinare la posizione di altri client Lync basati su PC cablati, è necessario usare il metodo per l'indirizzo MAC del client.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-127">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="e2ad0-128">Subnet</span><span class="sxs-lookup"><span data-stu-id="e2ad0-128">Subnet</span></span>

<span data-ttu-id="e2ad0-129">Le subnet IP di layer 3 includono un meccanismo supportato da tutti i client di Lync Server che possono essere usati per rilevare automaticamente la posizione del client.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-129">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="e2ad0-130">L'uso delle subnet IP è il metodo di posizione più semplice per configurare e gestire i client cablati.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-130">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="e2ad0-131">Prima di decidere di usare le subnet, usare tuttavia le seguenti domande per determinare se la specificità della posizione della subnet è sufficiente per individuare accuratamente un client:</span><span class="sxs-lookup"><span data-stu-id="e2ad0-131">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="e2ad0-132">Una o più subnet client coprono più piani?</span><span class="sxs-lookup"><span data-stu-id="e2ad0-132">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="e2ad0-133">Una o più subnet coprono più di un edificio?</span><span class="sxs-lookup"><span data-stu-id="e2ad0-133">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="e2ad0-134">Quanto spazio su piano è coperto da ogni subnet client?</span><span class="sxs-lookup"><span data-stu-id="e2ad0-134">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="e2ad0-135">Se la subnet copre un'area troppo ampia, potrebbe essere necessario usare un altro meccanismo per individuare i client.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-135">If the subnet covers too broad an area, you may need to use another mechanism to locate clients.</span></span> <span data-ttu-id="e2ad0-136">Tuttavia, se possibile, è consigliabile che i clienti riorganizzino il subnetting IP in modo che soddisfino i requisiti di specificità della posizione degli Elfi invece di incorrere nel costo e nella complessità delle soluzioni basate su SNMP di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-136">However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="e2ad0-137">Indirizzo MAC client</span><span class="sxs-lookup"><span data-stu-id="e2ad0-137">Client MAC Address</span></span>

<span data-ttu-id="e2ad0-138">Per usare l'indirizzo MAC di un computer client per individuare un chiamante, è necessario disporre di switch Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di individuare gli indirizzi MAC dei client Lync connessi (o tramite) a tali opzioni.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-138">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="e2ad0-139">La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC di endpoint connessi a ogni porta e ottiene gli ID di porta corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-139">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="e2ad0-140">Durante la richiesta di un client Lync al servizio informazioni sulla posizione, il servizio informazioni sulla posizione esegue una query sull'applicazione di terze parti usando l'indirizzo MAC del client e quindi restituisce gli eventuali indirizzi IP di switch e gli ID di porta corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-140">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="e2ad0-141">Il servizio informazioni sulla posizione usa queste informazioni per interrogare il wiremap Layer 2 pubblicato per un record corrispondente e restituisce la posizione al client.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-141">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="e2ad0-142">Se si usa questa opzione, verificare che gli identificatori della porta dello switch siano coerenti tra l'applicazione SNMP e i record di database della posizione pubblicati.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-142">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2ad0-143">Alcune soluzioni SNMP di terze parti possono supportare switch di Access non gestiti, Se l'opzione che offre servizi al client Lync non è gestita, ma ha un collegamento a un interruttore di distribuzione gestita, lo switch gestito può riferire all'applicazione SNMP gli indirizzi MAC dei client connessi allo switch di Access.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-143">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="e2ad0-144">Queste informazioni consentono al servizio informazioni sulla posizione di identificare la posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-144">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="e2ad0-145">Tuttavia, è possibile assegnare solo un singolo degli Elfi a tutte le porte dell'interruttore non gestito, quindi la specificità della posizione è disponibile solo a livello di chassis dello switch di Access, non del livello di porta.</span><span class="sxs-lookup"><span data-stu-id="e2ad0-145">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

