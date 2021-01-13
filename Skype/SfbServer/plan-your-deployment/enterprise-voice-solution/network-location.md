---
title: Definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Le decisioni necessarie per pianificare i componenti di rete da utilizzare per mappare i chiamanti alle posizioni per la distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813636"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server
 
Le decisioni necessarie per pianificare i componenti di rete da utilizzare per mappare i chiamanti alle posizioni per la distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
  
Se si sta configurando l'infrastruttura di Skype for Business Server per supportare il rilevamento automatico delle posizioni dei client, è innanzitutto necessario decidere quali elementi di rete si intende utilizzare per mappare i chiamanti alle posizioni. In Skype for Business Server, è possibile associare i seguenti elementi di rete Layer 2 e Layer 3 con percorsi:
  
- Indirizzi BSSID (Basic Service Set Identification) di punti di accesso wireless (livello 2)
    
- Porta di commutazione LLDP (livello 2)
    
- ID chassis di commutazione LLDP (livello 2)
    
- Subnet IP (livello 3)
    
- Indirizzi MAC dei client (livello 2)
    
Gli elementi di rete sono elencati in ordine di precedenza. Se un client può essere individuato utilizzando più di un elemento di rete, in Skype for Business Server viene utilizzato l'ordine di precedenza per determinare il meccanismo da utilizzare. 
  
Nelle sezioni seguenti sono disponibili ulteriori dettagli sull'utilizzo di ciascun elemento di rete.
  
> [!IMPORTANT]
> Quando si utilizzano gli elementi di rete per mappare i chiamanti alle posizioni, è estremamente importante mantenere aggiornati i database del servizio informazioni percorso. Ad esempio, se si aggiunge o modifica un elemento di rete, ad esempio se si aggiunge un punto di accesso wireless, è necessario eliminare la voce esistente e aggiungere la nuova nel database delle località. 
  
## <a name="wireless-access-point"></a>Punto di accesso wireless

Quando un client si connette alla rete in modalità wireless, la richiesta della posizione utilizza l'indirizzo BSSID del punto di accesso wireless per determinarne la posizione. Se il client è in roaming, il WAP indicato potrebbe non essere quello più vicino ed è persino possibile ritirare un WAP che si trova su un piano diverso dell'edificio. Per indicare che il percorso è approssimativo, è possibile anteporre il valore location a un descrittore **[near]** o **[closeto]** .
  
Questo metodo presuppone che l'indirizzo BSSID di ogni punto di accesso wireless sia statico. Tuttavia, se il fornitore di WAP utilizza BSSIDs assegnato dinamicamente, il BSSID ottenuto da un WAP potrebbe cambiare (ciò può verificarsi dopo una modifica di configurazione WAP) e i client wireless potrebbero essere lasciati in una situazione in cui non ricevono una posizione. Per evitare questa possibilità, è necessario popolare il database del servizio informazioni percorso con posizioni ERL per tutti i possibili indirizzi di BSSID utilizzati da ogni WAP. 
  
## <a name="lldp-ports-and-switches"></a>Porte e switch LLDP

Switch Ethernet gestiti che supportano LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) possono comunicare informazioni su porta e identità a client compatibili con LLDP-MED, che possono quindi essere soggetti a query sul database delle località per fornire la posizione del dispositivo. È possibile associare ERL unicamente a ID chassis di commutazione oppure è possibile eseguirne il mapping a livello di porta.
  
> [!NOTE]
> Skype for Business Server supporta l'utilizzo di LLDP-MED per determinare solo i percorsi dei dispositivi Lync Phone Edition e i client Skype for business in esecuzione su Windows 8. Se è necessario utilizzare i dati di livello 2 di switch-level per determinare il percorso di altri client Skype for Business Server cablati basati su PC, è necessario utilizzare il metodo di indirizzi MAC client. 
  
## <a name="subnet"></a>Subnet

Le subnet IP di layer 3 forniscono un meccanismo supportato da tutti i client Skype for Business Server che possono essere utilizzati per rilevare automaticamente la posizione del client. L'utilizzo di subnet IP rappresenta il metodo di individuazione più facile per configurare e gestire client cablati. Prima di scegliere di utilizzare le subnet, tuttavia, è consigliabile rispondere alle domande seguenti per determinare se la specificità di posizione della subnet è sufficiente per individuare accuratamente un client:
  
- Una o più subnet del client occupano più piani?
    
- Una o più subnet occupano più edifici?
    
- Quanto spazio di un piano è occupato da ogni subnet del client?
    
Se la subnet occupa un'area troppo ampia, può essere necessario utilizzare un altro meccanismo per individuare i client. Se si tratta di una scelta pratica, tuttavia, è consigliabile che gli utenti riorganizzino le proprie subnet IP in modo da soddisfare i requisiti di specificità di posizione ERL anziché affrontare i costi e la complessità di soluzioni basate su SNMP di terze parti.
  
## <a name="client-mac-address"></a>Indirizzo MAC del client

Per utilizzare l'indirizzo MAC di un computer client per individuare un chiamante, è necessario disporre di commutatori Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di individuare gli indirizzi MAC dei client Skype for business connessi (o tramite) a tali switch. La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC degli endpoint connessi a ogni porta e ottiene gli ID porta corrispondenti. Durante la richiesta di un client Skype for business al servizio informazioni percorso, il servizio informazioni percorso esegue una query nell'applicazione di terze parti utilizzando l'indirizzo MAC del client e quindi restituisce gli indirizzi IP e gli ID di porta corrispondenti. Il servizio informazioni percorso utilizza queste informazioni per eseguire una query sul relativo layer 2 wiremap pubblicato per un record corrispondente e restituisce il percorso al client. Se si utilizza questa opzione, assicurarsi che gli identificatori di porta degli switch siano coerenti tra l'applicazione SNMP e i record del database delle località pubblicati.
  
> [!NOTE]
> Alcune soluzioni SNMP di terze parti sono in grado di supportare switch di accesso non gestito. Se il commutatore che gestisce il client Skype for business non è gestito ma ha un collegamento a un commutatore di distribuzione gestito, l'opzione Managed Switch può riferire all'applicazione SNMP gli indirizzi MAC dei client connessi all'opzione di accesso. Queste informazioni consentono al servizio informazioni percorso di identificare il percorso dell'utente. Tuttavia, è possibile assegnare solo un singolo gli elfi a tutte le porte sull'opzione non gestita, in modo che la specificità della posizione sia disponibile solo a livello di chassis dell'opzione di accesso, non del livello di porta. 
  

