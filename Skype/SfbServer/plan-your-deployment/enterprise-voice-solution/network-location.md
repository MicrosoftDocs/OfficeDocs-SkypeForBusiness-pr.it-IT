---
title: Definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisioni necessarie per la pianificazione dei componenti di rete che verranno utilizzati per mappare i chiamanti alle posizioni per la distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
---

# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server
 
Decisioni necessarie per la pianificazione dei componenti di rete che verranno utilizzati per mappare i chiamanti alle posizioni per la distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
  
Se si configura l'infrastruttura Skype for Business Server per supportare il rilevamento automatico delle posizioni dei client, è innanzitutto necessario decidere quali elementi di rete si utilizzerà per mappare i chiamanti alle posizioni. In Skype for Business Server, è possibile associare i seguenti elementi di rete layer 2 e layer 3 alle posizioni:
  
- Indirizzi BSSID (Basic Service Set Identification) di punti di accesso wireless (livello 2)
    
- Porta di commutazione LLDP (livello 2)
    
- ID chassis di commutazione LLDP (livello 2)
    
- Subnet IP (livello 3)
    
- Indirizzi MAC dei client (livello 2)
    
Gli elementi di rete sono elencati in ordine di precedenza. Se un client può essere individuato utilizzando più di un elemento di rete, Skype for Business Server l'ordine di precedenza per determinare quale meccanismo utilizzare. 
  
Nelle sezioni seguenti sono disponibili ulteriori dettagli sull'utilizzo di ciascun elemento di rete.
  
> [!IMPORTANT]
> Quando si utilizzano elementi di rete per mappare i chiamanti alle posizioni, è fondamentale mantenere aggiornato il database del servizio informazioni percorso. Ad esempio, se si aggiunge o modifica un elemento di rete, ad esempio se si aggiunge un punto di accesso wireless, è necessario eliminare la voce esistente e aggiungere la nuova nel database delle località. 
  
## <a name="wireless-access-point"></a>Punto di accesso wireless

Quando un client si connette alla rete in modalità wireless, la richiesta della posizione utilizza l'indirizzo BSSID del punto di accesso wireless per determinarne la posizione. Se il client è in roaming, il WAP indicato potrebbe non essere quello più vicino ed è anche possibile prelevare un WAP che si trova su un piano diverso dell'edificio. Per indicare che la posizione è approssimativa, è possibile anteporre il valore della posizione a **un descrittore [Vicino]** o **[Vicino** ].
  
Questo metodo presuppone che l'indirizzo BSSID di ogni punto di accesso wireless sia statico. Tuttavia, se il fornitore wap usa BSSID assegnati in modo dinamico, il BSSID ottenuto da un WAP potrebbe cambiare (ciò può verificarsi in seguito a una modifica della configurazione WAP) e i client wireless potrebbero essere lasciati in una situazione in cui non ricevono una posizione. Per evitare questa possibilità, è necessario popolare il database del servizio informazioni percorso con gli ERL per tutti i possibili indirizzi BSSID utilizzati da ogni WAP. 
  
## <a name="lldp-ports-and-switches"></a>Porte e switch LLDP

Switch Ethernet gestiti che supportano LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) possono comunicare informazioni su porta e identità a client compatibili con LLDP-MED, che possono quindi essere soggetti a query sul database delle località per fornire la posizione del dispositivo. È possibile associare ERL unicamente a ID chassis di commutazione oppure è possibile eseguirne il mapping a livello di porta.
  
> [!NOTE]
> Skype for Business Server supporta l'utilizzo di LLDP-MED per determinare le posizioni solo dei dispositivi Lync Telefono Edition e dei client Skype for Business in esecuzione su Windows 8. Se devi usare dati di livello 2 a livello di commutazione per determinare la posizione di altri client Skype for Business Server basati su PC cablati, devi usare il metodo dell'indirizzo MAC client. 
  
## <a name="subnet"></a>Subnet

Le subnet IP di livello 3 offrono un meccanismo supportato da tutti Skype for Business Server client che possono essere utilizzati per rilevare automaticamente la posizione del client. L'utilizzo di subnet IP rappresenta il metodo di individuazione più facile per configurare e gestire client cablati. Prima di scegliere di utilizzare le subnet, tuttavia, è consigliabile rispondere alle domande seguenti per determinare se la specificità di posizione della subnet è sufficiente per individuare accuratamente un client:
  
- Una o più subnet del client occupano più piani?
    
- Una o più subnet occupano più edifici?
    
- Quanto spazio di un piano è occupato da ogni subnet del client?
    
Se la subnet occupa un'area troppo ampia, può essere necessario utilizzare un altro meccanismo per individuare i client. Se si tratta di una scelta pratica, tuttavia, è consigliabile che gli utenti riorganizzino le proprie subnet IP in modo da soddisfare i requisiti di specificità di posizione ERL anziché affrontare i costi e la complessità di soluzioni basate su SNMP di terze parti.
  
## <a name="client-mac-address"></a>Indirizzo MAC del client

Per utilizzare l'indirizzo MAC di un computer client per individuare un chiamante, sono necessari commutatori Ethernet gestiti ed è necessario distribuire una soluzione SNMP di terze parti in grado di individuare gli indirizzi MAC dei client Skype for Business connessi o tramite tali commutatori. La soluzione SNMP esegue continuamente il polling degli switch gestiti per ottenere i mapping correnti degli indirizzi MAC degli endpoint connessi a ogni porta e ottiene gli ID porta corrispondenti. Durante la richiesta di un client di Skype for Business al servizio informazioni percorso, il servizio informazioni percorso esegue una query sull'applicazione di terze parti utilizzando l'indirizzo MAC del client e quindi restituisce gli eventuali indirizzi IP del commutatore e gli ID di porta corrispondenti. Il servizio informazioni percorso utilizza queste informazioni per eseguire una query sulla relativa wiremap di livello 2 pubblicata per un record corrispondente e restituisce la posizione al client. Se si utilizza questa opzione, assicurarsi che gli identificatori di porta degli switch siano coerenti tra l'applicazione SNMP e i record del database delle località pubblicati.
  
> [!NOTE]
> Alcune soluzioni SNMP di terze parti possono supportare commutatori di accesso non gestiti. se il commutatore che servizi il client Skype for Business non è gestito ma dispone di un uplink a un commutatore di distribuzione gestito, il commutatore gestito può segnalare all'applicazione SNMP gli indirizzi MAC dei client connessi al commutatore di accesso. Queste informazioni consentono al servizio informazioni percorso di identificare la posizione dell'utente. Tuttavia, è possibile assegnare un solo ERL a tutte le porte sullo switch non gestito, quindi la specificità della posizione è disponibile solo a livello di chassis del commutatore di accesso, non a livello di porta. 
  

