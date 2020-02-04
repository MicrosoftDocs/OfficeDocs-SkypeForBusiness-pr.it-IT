---
title: 'Lync Server 2013: definizione degli elementi di rete usati per determinare la posizione'
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
ms.openlocfilehash: 4d71d222fd6784c32ecf0228fff2f33188d2afae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Definizione degli elementi di rete usati per determinare la posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Se si sta configurando l'infrastruttura di Lync Server per supportare il rilevamento automatico della posizione del client, è prima di tutto necessario decidere quali elementi di rete usare per eseguire il mapping dei chiamanti alle posizioni. In Lync Server 2013 è possibile associare gli elementi di rete Layer 2 e Layer 3 seguenti con posizioni:

  - Indirizzi di BSSID (Service Set Identification Point) di base (WAP) wireless (Layer 2)

  - LLDP Switch Port (Layer 2)

  - LLDP switch ID chassis (Layer 2)

  - Subnet IP (Layer 3)

  - Indirizzi MAC client (Layer 2)

Gli elementi di rete sono elencati in ordine di precedenza. Se un client può essere individuato usando più elementi di rete, Lync Server usa l'ordine di precedenza per determinare il meccanismo da usare.

Nelle sezioni seguenti sono disponibili altri dettagli per l'uso di ogni elemento di rete.

<div>


> [!IMPORTANT]  
> Quando si usano gli elementi di rete per eseguire il mapping dei chiamanti alle posizioni, è fondamentale che si mantenga aggiornato il database del servizio informazioni sulla posizione. Se ad esempio si aggiunge o si modifica un elemento di rete, come l'aggiunta di un WAP, è necessario eliminare la voce precedente e aggiungere la nuova voce nel database della posizione.



</div>

<div>

## <a name="wireless-access-point"></a>Punto di accesso wireless

Quando un client si connette alla rete in modalità wireless, la richiesta di posizione usa l'indirizzo BSSID del WAP per determinarne la posizione. Se il client è in roaming, il WAP indicato potrebbe non essere quello più vicino ed è anche possibile prendere un WAP che si trova su un piano diverso dell'edificio. Per indicare che la posizione è approssimativa, è possibile anteporre il valore della posizione a un descrittore vicino o vicino a.

Questo metodo di posizione presuppone che il BSSID di ogni WAP sia statico. Tuttavia, se il fornitore WAP usa BSSIDs assegnati in modo dinamico, il BSSID ottenuto da un WAP potrebbe cambiare (ciò può verificarsi dopo una modifica della configurazione WAP) e i client wireless potrebbero essere lasciati in una situazione in cui non ricevono una posizione. Per evitare questa possibilità, è necessario popolare il database del servizio informazioni sulla posizione con posizioni ERL per tutti i possibili indirizzi di BSSID usati da ogni WAP.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>Porte e opzioni di LLDP

Switch Ethernet gestiti che supportano il protocollo di individuazione dei collegamenti Layer-media endpoint Discover (LLDP-MED) è in grado di pubblicizzare le informazioni relative all'identità e alla porta ai client compatibili con LLDP-MED, che possono quindi essere interrogati sul database della posizione per specificare il posizione del dispositivo. Puoi associare posizioni ERL esclusivamente all'ID dello chassis di switch oppure puoi mapparli fino al livello di porta.

<div>


> [!NOTE]  
> Lync Server 2013 supporta l'uso di LLDP-MED per determinare solo le posizioni dei dispositivi Lync Phone Edition e Lync 2013 in uso in Windows 8. Se è necessario usare i dati di livello 2 per determinare la posizione di altri client Lync basati su PC cablati, è necessario usare il metodo per l'indirizzo MAC del client.



</div>

</div>

<div>

## <a name="subnet"></a>Subnet

Le subnet IP di layer 3 includono un meccanismo supportato da tutti i client di Lync Server che possono essere usati per rilevare automaticamente la posizione del client. L'uso delle subnet IP è il metodo di posizione più semplice per configurare e gestire i client cablati. Prima di decidere di usare le subnet, usare tuttavia le seguenti domande per determinare se la specificità della posizione della subnet è sufficiente per individuare accuratamente un client:

  - Una o più subnet client coprono più piani?

  - Una o più subnet coprono più di un edificio?

  - Quanto spazio su piano è coperto da ogni subnet client?

Se la subnet copre un'area troppo ampia, potrebbe essere necessario usare un altro meccanismo per individuare i client. Tuttavia, se possibile, è consigliabile che i clienti riorganizzino il subnetting IP in modo che soddisfino i requisiti di specificità della posizione degli Elfi invece di incorrere nel costo e nella complessità delle soluzioni basate su SNMP di terze parti.

</div>

<div>

## <a name="client-mac-address"></a>Indirizzo MAC client

Per usare l'indirizzo MAC di un computer client per individuare un chiamante, è necessario disporre di switch Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di individuare gli indirizzi MAC dei client Lync connessi (o tramite) a tali opzioni. La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC di endpoint connessi a ogni porta e ottiene gli ID di porta corrispondenti. Durante la richiesta di un client Lync al servizio informazioni sulla posizione, il servizio informazioni sulla posizione esegue una query sull'applicazione di terze parti usando l'indirizzo MAC del client e quindi restituisce gli eventuali indirizzi IP di switch e gli ID di porta corrispondenti. Il servizio informazioni sulla posizione usa queste informazioni per interrogare il wiremap Layer 2 pubblicato per un record corrispondente e restituisce la posizione al client. Se si usa questa opzione, verificare che gli identificatori della porta dello switch siano coerenti tra l'applicazione SNMP e i record di database della posizione pubblicati.

<div>


> [!NOTE]  
> Alcune soluzioni SNMP di terze parti possono supportare switch di Access non gestiti, Se l'opzione che offre servizi al client Lync non è gestita, ma ha un collegamento a un interruttore di distribuzione gestita, lo switch gestito può riferire all'applicazione SNMP gli indirizzi MAC dei client connessi allo switch di Access. Queste informazioni consentono al servizio informazioni sulla posizione di identificare la posizione dell'utente. Tuttavia, è possibile assegnare solo un singolo degli Elfi a tutte le porte dell'interruttore non gestito, quindi la specificità della posizione è disponibile solo a livello di chassis dello switch di Access, non del livello di porta.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

