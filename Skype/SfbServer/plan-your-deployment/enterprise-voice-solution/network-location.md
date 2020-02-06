---
title: Definire gli elementi di rete usati per determinare la posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisioni necessarie per pianificare i componenti di rete da usare per eseguire il mapping dei chiamanti alle posizioni per la distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 404ac2d151f367ad391e4d5426090f20448cc383
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802666"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definire gli elementi di rete usati per determinare la posizione in Skype for Business Server
 
Decisioni necessarie per pianificare i componenti di rete da usare per eseguire il mapping dei chiamanti alle posizioni per la distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
  
Se si sta configurando l'infrastruttura di Skype for Business Server per supportare il rilevamento automatico della posizione del client, è prima di tutto necessario decidere quali elementi di rete usare per eseguire il mapping dei chiamanti alle posizioni. In Skype for Business Server è possibile associare gli elementi di rete Layer 2 e Layer 3 seguenti con posizioni:
  
- Indirizzi di BSSID (Service Set Identification Point) di base (WAP) wireless (Layer 2)
    
- LLDP Switch Port (Layer 2)
    
- LLDP switch ID chassis (Layer 2)
    
- Subnet IP (Layer 3)
    
- Indirizzi MAC client (Layer 2)
    
Gli elementi di rete sono elencati in ordine di precedenza. Se un client può essere individuato usando più elementi di rete, Skype for Business Server usa l'ordine di precedenza per determinare il meccanismo da usare. 
  
Nelle sezioni seguenti sono disponibili altri dettagli per l'uso di ogni elemento di rete.
  
> [!IMPORTANT]
> Quando si usano gli elementi di rete per eseguire il mapping dei chiamanti alle posizioni, è fondamentale che si mantenga aggiornato il database del servizio informazioni sulla posizione. Se ad esempio si aggiunge o si modifica un elemento di rete, come l'aggiunta di un WAP, è necessario eliminare la voce precedente e aggiungere la nuova voce nel database della posizione. 
  
## <a name="wireless-access-point"></a>Punto di accesso wireless

Quando un client si connette alla rete in modalità wireless, la richiesta di posizione usa l'indirizzo BSSID del WAP per determinarne la posizione. Se il client è in roaming, il WAP indicato potrebbe non essere quello più vicino ed è anche possibile prendere un WAP che si trova su un piano diverso dell'edificio. Per indicare che la posizione è approssimativa, è possibile anteporre il valore della posizione a un descrittore **[near]** o **[closeto]** .
  
Questo metodo di posizione presuppone che il BSSID di ogni WAP sia statico. Tuttavia, se il fornitore WAP usa BSSIDs assegnati in modo dinamico, il BSSID ottenuto da un WAP potrebbe cambiare (ciò può verificarsi dopo una modifica della configurazione WAP) e i client wireless potrebbero essere lasciati in una situazione in cui non ricevono una posizione. Per evitare questa possibilità, è necessario popolare il database del servizio informazioni sulla posizione con posizioni ERL per tutti i possibili indirizzi di BSSID usati da ogni WAP. 
  
## <a name="lldp-ports-and-switches"></a>Porte e opzioni di LLDP

Switch Ethernet gestiti che supportano il protocollo di individuazione dei collegamenti Layer-media endpoint Discover (LLDP-MED) è in grado di pubblicizzare le informazioni relative all'identità e alla porta ai client compatibili con LLDP-MED, che possono quindi essere interrogati sul database della posizione per specificare il posizione del dispositivo. Puoi associare posizioni ERL esclusivamente all'ID dello chassis di switch oppure puoi mapparli fino al livello di porta.
  
> [!NOTE]
> Skype for Business Server supporta l'uso di LLDP-MED per determinare solo le posizioni dei dispositivi Lync Phone Edition e i client Skype for business in uso in Windows 8. Se è necessario usare i dati di livello 2 per determinare la posizione di altri client di Skype for Business Server cablati basati su PC, è necessario usare il metodo per l'indirizzo MAC del client. 
  
## <a name="subnet"></a>Subnet

Le subnet IP Layer 3 includono un meccanismo supportato da tutti i client di Skype for Business Server che possono essere usati per rilevare automaticamente la posizione del client. L'uso delle subnet IP è il metodo di posizione più semplice per configurare e gestire i client cablati. Prima di decidere di usare le subnet, usare tuttavia le seguenti domande per determinare se la specificità della posizione della subnet è sufficiente per individuare accuratamente un client:
  
- Una o più subnet client coprono più piani?
    
- Una o più subnet coprono più di un edificio?
    
- Quanto spazio su piano è coperto da ogni subnet client?
    
Se la subnet copre un'area troppo ampia, potrebbe essere necessario usare un altro meccanismo per individuare i client. Tuttavia, se possibile, è consigliabile che i clienti riorganizzino il subnetting IP in modo che soddisfino i requisiti di specificità della posizione degli Elfi invece di incorrere nel costo e nella complessità delle soluzioni basate su SNMP di terze parti.
  
## <a name="client-mac-address"></a>Indirizzo MAC client

Per usare l'indirizzo MAC di un computer client per individuare un chiamante, è necessario disporre di switch Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di individuare gli indirizzi MAC dei client Skype for business connessi (o tramite) a tali opzioni. La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC di endpoint connessi a ogni porta e ottiene gli ID di porta corrispondenti. Durante una richiesta di un client Skype for business al servizio informazioni sulla posizione, il servizio informazioni sulla posizione esegue una query sull'applicazione di terze parti usando l'indirizzo MAC del client e quindi restituisce gli eventuali indirizzi IP di switch e gli ID di porta corrispondenti. Il servizio informazioni sulla posizione usa queste informazioni per interrogare il wiremap Layer 2 pubblicato per un record corrispondente e restituisce la posizione al client. Se si usa questa opzione, verificare che gli identificatori della porta dello switch siano coerenti tra l'applicazione SNMP e i record di database della posizione pubblicati.
  
> [!NOTE]
> Alcune soluzioni SNMP di terze parti possono supportare switch di Access non gestiti, Se l'opzione che offre servizi al client Skype for business non è gestita, ma ha un collegamento a un interruttore di distribuzione gestita, lo switch gestito può riferire all'applicazione SNMP gli indirizzi MAC dei client connessi allo switch di Access. Queste informazioni consentono al servizio informazioni sulla posizione di identificare la posizione dell'utente. Tuttavia, è possibile assegnare solo un singolo degli Elfi a tutte le porte dell'interruttore non gestito, quindi la specificità della posizione è disponibile solo a livello di chassis dello switch di Access, non del livello di porta. 
  

