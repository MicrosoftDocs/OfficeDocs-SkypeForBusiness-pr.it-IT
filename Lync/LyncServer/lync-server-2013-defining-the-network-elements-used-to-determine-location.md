---
title: 'Lync Server 2013: definizione degli elementi di rete utilizzati per determinare la posizione'
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
ms.openlocfilehash: f6578c0cca54c41f079c682862b9e96a54e3d456
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Definizione degli elementi di rete utilizzati per determinare la posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Se si sta configurando l'infrastruttura di Lync Server per il supporto del rilevamento automatico delle posizioni dei client, è necessario prima di tutto decidere quali elementi di rete si intende utilizzare per mappare i chiamanti alle posizioni. In Lync Server 2013, è possibile associare i seguenti elementi di rete Layer 2 e Layer 3 con percorsi:

  - Indirizzi BSSID (Basic Service Set Identification) di punti di accesso wireless (livello 2)

  - Porta di commutazione LLDP (livello 2)

  - ID chassis di commutazione LLDP (livello 2)

  - Subnet IP (livello 3)

  - Indirizzi MAC dei client (livello 2)

Gli elementi di rete sono elencati in ordine di precedenza. Se un client può essere individuato utilizzando più di un elemento di rete, Lync Server utilizza l'ordine di precedenza per determinare il meccanismo da utilizzare.

Nelle sezioni seguenti sono disponibili ulteriori dettagli sull'utilizzo di ciascun elemento di rete.

<div>


> [!IMPORTANT]  
> Quando si utilizzano gli elementi di rete per mappare i chiamanti alle posizioni, è estremamente importante mantenere aggiornati i database del servizio informazioni percorso. Ad esempio, se si aggiunge o modifica un elemento di rete, ad esempio se si aggiunge un punto di accesso wireless, è necessario eliminare la voce esistente e aggiungere la nuova nel database delle località.



</div>

<div>

## <a name="wireless-access-point"></a>Punto di accesso wireless

Quando un client si connette alla rete in modalità wireless, la richiesta della posizione utilizza l'indirizzo BSSID del punto di accesso wireless per determinarne la posizione. Se il client effettua il roaming, il punto di accesso wireless indicato potrebbe non essere quello più vicino ed è anche possibile che venga rilevato un punto di accesso wireless che si trova in un piano diverso dell'edificio. Per indicare che la posizione è approssimativa, è possibile anteporre al valore di posizione un descrittore Near o Close to.

Questo metodo presuppone che l'indirizzo BSSID di ogni punto di accesso wireless sia statico. Se il fornitore del punto di accesso wireless, tuttavia, utilizza BSSID assegnati dinamicamente, l'indirizzo BSSID ottenuto da un punto di accesso wireless può cambiare (ad esempio in seguito a una modifica di configurazione apportata al punto di accesso wireless) e i client wireless possono trovarsi in una situazione in cui non ricevono una posizione. Per evitare questa possibilità, è necessario popolare il database del servizio informazioni percorso con posizioni ERL per tutti i possibili indirizzi di BSSID utilizzati da ogni WAP.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>Porte e switch LLDP

Switch Ethernet gestiti che supportano LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) possono comunicare informazioni su porta e identità a client compatibili con LLDP-MED, che possono quindi essere soggetti a query sul database delle località per fornire la posizione del dispositivo. È possibile associare ERL unicamente a ID chassis di commutazione oppure è possibile eseguirne il mapping a livello di porta.

<div>


> [!NOTE]  
> Lync Server 2013 supporta l'utilizzo di LLDP-MED per determinare solo i percorsi dei dispositivi Lync Phone Edition e Lync 2013 in esecuzione su Windows 8. Se è necessario utilizzare i dati di livello 2 di switch-level per determinare la posizione di altri client Lync basati su PC cablati, è necessario utilizzare il metodo di indirizzo MAC client.



</div>

</div>

<div>

## <a name="subnet"></a>Subnet

Le subnet IP di layer 3 forniscono un meccanismo supportato da tutti i client di Lync Server che possono essere utilizzati per rilevare automaticamente la posizione del client. L'utilizzo di subnet IP rappresenta il metodo di individuazione più facile per configurare e gestire client cablati. Prima di scegliere di utilizzare le subnet, tuttavia, è consigliabile rispondere alle domande seguenti per determinare se la specificità di posizione della subnet è sufficiente per individuare accuratamente un client:

  - Una o più subnet del client occupano più piani?

  - Una o più subnet occupano più edifici?

  - Quanto spazio di un piano è occupato da ogni subnet del client?

Se la subnet occupa un'area troppo ampia, può essere necessario utilizzare un altro meccanismo per individuare i client. Se si tratta di una scelta pratica, tuttavia, è consigliabile che gli utenti riorganizzino le proprie subnet IP in modo da soddisfare i requisiti di specificità di posizione ERL anziché affrontare i costi e la complessità di soluzioni basate su SNMP di terze parti.

</div>

<div>

## <a name="client-mac-address"></a>Indirizzo MAC del client

Per utilizzare l'indirizzo MAC di un computer client per individuare un chiamante, sono necessari switch Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di rilevare gli indirizzi MAC dei client Lync connessi a (o tramite) tali switch. La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC degli endpoint connessi a ogni porta e ottiene gli ID porta corrispondenti. Durante la richiesta di un client di Lync al servizio informazioni percorso, il servizio informazioni percorso esegue una query nell'applicazione di terze parti utilizzando l'indirizzo MAC del client e quindi restituisce gli indirizzi IP e gli ID di porta corrispondenti. Il servizio informazioni percorso utilizza queste informazioni per eseguire una query sul relativo layer 2 wiremap pubblicato per un record corrispondente e restituisce il percorso al client. Se si utilizza questa opzione, assicurarsi che gli identificatori di porta degli switch siano coerenti tra l'applicazione SNMP e i record del database delle località pubblicati.

<div>


> [!NOTE]  
> Alcune soluzioni SNMP di terze parti sono in grado di supportare switch di accesso non gestito. Se l'opzione che gestisce il client Lync non è gestita, ma ha un collegamento a un commutatore di distribuzione gestito, l'opzione Managed Switch può riferire all'applicazione SNMP gli indirizzi MAC dei client connessi al commutatore di accesso. Queste informazioni consentono al servizio informazioni percorso di identificare il percorso dell'utente. Tuttavia, è possibile assegnare solo un singolo gli elfi a tutte le porte sull'opzione non gestita, in modo che la specificità della posizione sia disponibile solo a livello di chassis dell'opzione di accesso, non del livello di porta.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

