---
title: "Server proxy per Skype for Business online"
ms.author: tonysmit
author: tonysmit
ms.date: 11/6/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
description: "Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business."
---

# Server proxy per Skype for Business online

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](7acaf2c2-35fa-490f-84cd-822e446e0fc7.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/7acaf2c2-35fa-490f-84cd-822e446e0fc7). 
  
Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business.
  
## Consigliamo di non usare un server proxy

Per quanto riguarda il traffico di Skype for Business via proxy, Microsoft consiglia di bypassare il proxy. I proxy non rendono Skype for Business più sicuro perché il suo traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi porteranno a un'esperienza negativa in scenari di Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.
  
## Se devi usare un server proxy

Alcune organizzazioni è presente nessuna opzione per ignorare un proxy di Skype per il traffico di Business. In tal caso, è necessario prendere in considerazione i problemi indicati in precedenza.
  
Microsoft inoltre consiglia:
  
- Utilizzare la risoluzione DNS esterna
    
- Utilizzare l'instradamento diretto basato su UDP
    
- Consentire il traffico UDP 
    
- Seguire le altre raccomandazioni nelle nostre linee guida di rete:
    
  - [Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Ottimizzare la rete per Skype for Business online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## Fornitori di proxy con supporto Skype for Business integrato o opzioni di configurazione

Questa sezione contiene informazioni sui fornitori di proxy che forniscono prodotti o servizi che si sono dimostrati compatibili con il traffico di Skype for Business.
  
- Per le organizzazioni che utilizzano **le soluzioni Bluecoat Proxy**, è stato pubblicato un nuovo firmware che risolve diversi problemi con:
    
  - intercettazione SSL
    
  - controlli OCSP/SRL
    
  - SIP via TLS
    
  - supporto per TURN
    
    Il supporto nativo di Bluecoat per Skype for Business può essere attivato con facilità, e permette l'identificazione del traffico interessato e la sua corretta gestione. Questo garantisce autenticazione, segnalazione e flusso di traffico multimediale ottimali per offrire un'ottima esperienza utente senza problemi di sicurezza.
    
    Fare riferimento al collegamento seguente se Proxy Bluecoat fa parte della topologia di rete
    
- https://support.Symantec.com/en_US/article.DOC9757.HTML
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

