---
title: Server proxy per Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business."
ms.openlocfilehash: 19c12ed4265c6549f00b54b3463215702d3ced2b
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Server proxy per Skype for Business online

[] Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Consigliamo di non usare un server proxy

Per quanto riguarda il traffico di Skype for Business via proxy, Microsoft consiglia di bypassare il proxy. I proxy non rendono Skype for Business più sicuro perché il suo traffico è già crittografato.
  
Inoltre, avere un proxy può causare problemi. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi porteranno a un'esperienza negativa in scenari di Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Se devi usare un server proxy

Alcune organizzazioni non hanno la possibilità di bypassare il proxy per il traffico di Skype for Business. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.
  
Microsoft inoltre consiglia:
  
- Utilizzare la risoluzione DNS esterna
    
- Utilizzare l'instradamento diretto basato su UDP
    
- Consentire il traffico UDP
    
- Seguire le altre raccomandazioni nelle nostre linee guida di rete:
    
  - [Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Ottimizzare la rete per Skype for Business online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a>Fornitori di proxy con supporto Skype for Business integrato o opzioni di configurazione

Questa sezione contiene informazioni sui fornitori di proxy che forniscono prodotti o servizi che si sono dimostrati compatibili con il traffico di Skype for Business.
  
Per le organizzazioni che utilizzano **le soluzioni Bluecoat Proxy**, è stato pubblicato un nuovo firmware che risolve diversi problemi con:
    
  - intercettazione SSL
    
  - controlli OCSP/SRL
    
  - SIP via TLS
    
  - supporto per TURN
    
Il supporto nativo di Bluecoat per Skype for Business può essere attivato con facilità, e permette l'identificazione del traffico interessato e la sua corretta gestione. Questo garantisce autenticazione, segnalazione e flusso di traffico multimediale ottimali per offrire un'ottima esperienza utente senza problemi di sicurezza.
    
Consultare il collegamento seguente se Proxy Bluecoat è una parte della topologia di rete: https://support.symantec.com/en_US/article.DOC9757.html

## <a name="related-topics"></a>See also

[Ottimizzare la rete per Skype for Business online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)