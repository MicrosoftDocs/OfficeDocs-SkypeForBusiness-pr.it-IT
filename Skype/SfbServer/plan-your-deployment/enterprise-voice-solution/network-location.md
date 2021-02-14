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
description: Decisioni necessarie per la pianificazione dei componenti di rete che verranno utilizzati per mappare i chiamanti alle posizioni per la distribuzione del servizio E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813636"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server
 
Decisioni necessarie per la pianificazione dei componenti di rete che verranno utilizzati per mappare i chiamanti alle posizioni per la distribuzione del servizio E9-1-1 in Skype for Business Server VoIP aziendale.
  
Se stai configurando l'infrastruttura di Skype for Business Server per supportare il rilevamento automatico della posizione dei client, devi prima decidere quali elementi di rete userai per mappare i chiamanti alle posizioni. In Skype for Business Server, è possibile associare i seguenti elementi di rete Layer 2 e Layer 3 alle posizioni:
  
- Indirizzi BSSID (Basic Service Set Identification) di punti di accesso wireless (livello 2)
    
- Porta di commutazione LLDP (livello 2)
    
- ID chassis di commutazione LLDP (livello 2)
    
- Subnet IP (livello 3)
    
- Indirizzi MAC dei client (livello 2)
    
Gli elementi di rete sono elencati in ordine di precedenza. Se un client può essere individuato utilizzando più elementi di rete, Skype for Business Server usa l'ordine di precedenza per determinare quale meccanismo utilizzare. 
  
Nelle sezioni seguenti sono disponibili ulteriori dettagli sull'utilizzo di ciascun elemento di rete.
  
> [!IMPORTANT]
> Quando si utilizzano elementi di rete per mappare i chiamanti alle posizioni, è estremamente importante mantenere aggiornato il database del servizio informazioni percorso. Ad esempio, se si aggiunge o modifica un elemento di rete, ad esempio se si aggiunge un punto di accesso wireless, è necessario eliminare la voce esistente e aggiungere la nuova nel database delle località. 
  
## <a name="wireless-access-point"></a>Punto di accesso wireless

Quando un client si connette alla rete in modalità wireless, la richiesta della posizione utilizza l'indirizzo BSSID del punto di accesso wireless per determinarne la posizione. Se il client è in roaming, il punto di accesso wap indicato potrebbe non essere quello più vicino ed è anche possibile prelevare un wap che si trova in un piano diverso dell'edificio. Per indicare che la posizione è approssimativa, è possibile anteporre il valore della posizione con un descrittore **[Near]** o **[Closeto].**
  
Questo metodo presuppone che l'indirizzo BSSID di ogni punto di accesso wireless sia statico. Tuttavia, se il fornitore WAP usa BSSID assegnati dinamicamente, il BSSID ottenuto da un WAP potrebbe cambiare (ciò può accadere in seguito a una modifica della configurazione WAP) e i client wireless potrebbero essere lasciati in una situazione in cui non ricevono una posizione. Per evitare questa possibilità, è necessario popolare il database del servizio informazioni percorso con ERL per tutti i possibili indirizzi BSSID utilizzati da ogni punto di accesso pubblico. 
  
## <a name="lldp-ports-and-switches"></a>Porte e switch LLDP

Switch Ethernet gestiti che supportano LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) possono comunicare informazioni su porta e identità a client compatibili con LLDP-MED, che possono quindi essere soggetti a query sul database delle località per fornire la posizione del dispositivo. È possibile associare ERL unicamente a ID chassis di commutazione oppure è possibile eseguirne il mapping a livello di porta.
  
> [!NOTE]
> Skype for Business Server supporta l'uso di LLDP-MED per determinare le posizioni solo dei dispositivi Lync Phone Edition e dei client Skype for Business in esecuzione su Windows 8. Se è necessario utilizzare dati di livello 2 a livello di commutazione per determinare la posizione di altri client Skype for Business Server basati su PC cablati, è necessario utilizzare il metodo dell'indirizzo MAC client. 
  
## <a name="subnet"></a>Subnet

Le subnet IP di livello 3 forniscono un meccanismo supportato da tutti i client Skype for Business Server che possono essere usati per rilevare automaticamente la posizione dei client. L'utilizzo di subnet IP rappresenta il metodo di individuazione più facile per configurare e gestire client cablati. Prima di scegliere di utilizzare le subnet, tuttavia, è consigliabile rispondere alle domande seguenti per determinare se la specificità di posizione della subnet è sufficiente per individuare accuratamente un client:
  
- Una o più subnet del client occupano più piani?
    
- Una o più subnet occupano più edifici?
    
- Quanto spazio di un piano è occupato da ogni subnet del client?
    
Se la subnet occupa un'area troppo ampia, può essere necessario utilizzare un altro meccanismo per individuare i client. Se si tratta di una scelta pratica, tuttavia, è consigliabile che gli utenti riorganizzino le proprie subnet IP in modo da soddisfare i requisiti di specificità di posizione ERL anziché affrontare i costi e la complessità di soluzioni basate su SNMP di terze parti.
  
## <a name="client-mac-address"></a>Indirizzo MAC del client

Per utilizzare l'indirizzo MAC di un computer client per individuare un chiamante, sono necessari commutatori Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di individuare gli indirizzi MAC dei client Skype for Business connessi a (o tramite) tali commutatori. La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC degli endpoint connessi a ogni porta e ottiene gli ID porta corrispondenti. Durante la richiesta di un client Skype for Business al servizio informazioni percorso, il servizio informazioni percorso esegue una query sull'applicazione di terze parti utilizzando l'indirizzo MAC del client e quindi restituisce eventuali indirizzi IP e ID porta commutatore corrispondenti. Il servizio informazioni sulla posizione utilizza queste informazioni per eseguire una query sulla wiremap di livello 2 pubblicata per trovare un record corrispondente e restituisce la posizione al client. Se si utilizza questa opzione, assicurarsi che gli identificatori di porta degli switch siano coerenti tra l'applicazione SNMP e i record del database delle località pubblicati.
  
> [!NOTE]
> Alcune soluzioni SNMP di terze parti possono supportare opzioni di accesso non gestito. Se il commutatore che servizi il client Skype for Business non è gestito ma dispone di un uplink a un commutatore di distribuzione gestito, il commutatore gestito può segnalare all'applicazione SNMP gli indirizzi MAC dei client connessi al commutatore di accesso. Queste informazioni consentono al servizio informazioni percorso di identificare la posizione dell'utente. Tuttavia, è possibile assegnare un solo elenco di revoche di certificati (ERL) a tutte le porte del commutatore non gestito, in modo che la specificità della posizione sia disponibile solo a livello di chassis del commutatore di accesso e non a livello di porta. 
  

