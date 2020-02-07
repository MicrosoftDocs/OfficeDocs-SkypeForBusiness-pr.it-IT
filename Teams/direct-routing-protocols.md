---
title: Instradamento diretto di Sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocolli di routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835026"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Routing diretto-definizioni e standard RFC

Questo articolo descrive il modo in cui routing diretto di Microsoft Phone System implementa protocolli standard RFC. Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra il controller del bordo sessione locale (SBC) e il servizio proxy SIP (Session Initiation Protocol).

Le interfacce Customer SBC con i componenti seguenti nel backend di Microsoft teams: 

- **Proxy SIP per la** segnalazione. Questo è il componente a Internet del routing diretto che gestisce le connessioni SIP (TLS) tra SBCs e routing diretto.

- **Processori multimediali** per elementi multimediali. Questo è il componente a Internet di routing diretto che gestisce il traffico multimediale. Questo componente usa i protocolli SRTP e SRTCP.


Per altre informazioni sul routing diretto, vedere [routing diretto del sistema telefonico](direct-routing-landing-page.md).

Per altre informazioni sul modo in cui il routing diretto implementa il protocollo SIP, vedere [routing diretto-protocollo SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Standard RFC

Il routing diretto è conforme agli standard RFC.  Il servizio SBC collegato al routing diretto deve essere conforme alle RFC seguenti (o ai relativi successori). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità di bypass non multimediale 

Gli standard seguenti si applicano ai dispositivi che supportano solo la modalità non media bypass:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): protocollo di avvio della sessione
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Estensione privata al protocollo di avvio della sessione per l'identità asserita all'interno di reti attendibili: sezioni sulla gestione dell'intestazione P-Asserted-Identity. Il routing diretto Invia l'identità P-asserzione con le intestazioni di ID privacy. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione del protocollo SIP (Session Initiation Protocol) per informazioni sulla cronologia richieste. Per altre informazioni, vedere anche: routing SIP Protocol Description.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di riferimento per il protocollo di avvio della sessione
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione SIP (Session Initiation Protocol) "sostituisce" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Uso SIP (Session Initiation Protocol) del modello di offerta/risposta.
  Vedere la sezione "deviazioni da RFC".
- [Rfc 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteggere il traffico RTP con SRTP. Il SBC deve essere in grado di stabilire le chiavi usando SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Proposta di soluzione di Session Description Protocol (SDP) per il multiplexing RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità di bypass multimediale

Oltre agli standard elencati come applicabili alla modalità non di bypass, vengono usati i seguenti standard per la modalità di bypass multimediale:

- [RFC 5245 Interactive Connectivity Establishment (Ice) per il bypass multimediale](https://tools.ietf.org/html/rfc5245).  Il servizio SBC deve supportare le operazioni seguenti:
  - ICE Lite: i client di teams sono client ICE completi
  - [Riavvia il ghiaccio](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Vedere altre informazioni su ICE riavvii use case ed esempi in ICE Restart: la chiamata di bypass multimediale viene trasferita a un endpoint che non supporta il bypass multimediale   
- [Controllo delle chiamate SIP (Session Initiation Protocol) rfc 5589-Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early media e la generazione di suonerie nel protocollo SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3960), vedi sezioni 3,1, fork e 3,2, generazione di suonerie 
- [Utilità per l'attraversamento delle sessioni RFC 5389 per NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal using relays about NAT (TURN): estensioni di inoltro alle utilità per l'attraversamento delle sessioni per NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Standard applicabili per supportare il trasporto delle informazioni sulla posizione ai provider di E911

- [RFC 6442, trasferimento di posizione per il protocollo di avvio della sessione](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Deviazioni dalla RFC

La tabella seguente elenca le sezioni delle RFC in cui l'implementazione di Microsoft del SIP o dello stack multimediale differisce dallo standard:

| RFC e sezioni | Descrizione | Deviazione |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sezione 5,3 blocco e ripresa di elementi multimediali](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC consente di usare "a = inattivo", "a = sendonly", a = recvonly "per effettuare una chiamata in attesa. |Il proxy SIP supporta solo "a = inattivo" e non capisce se il SBC Invia "a = sendonly" o "a = recvonly".
| [RFC 6337, sezione 5,4 "comportamento sulla ricezione di SDP con c = 0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) richiede che un agente sia in grado di ricevere SDP con un indirizzo di connessione di 0.0.0.0, in questo caso significa che né RTP né RTCP devono essere inviati al peer. | Il proxy SIP non supporta questa opzione. |

## <a name="operational-modes"></a>Modalità operative

Esistono due modalità operative per il routing diretto:

- **Senza bypass multimediale** in cui tutti i flussi di traffico RTP tra il client teams, i processori multimediali e il SBC.  

- **Con il bypass multimediale** in cui tutti i flussi di supporto RTP si alternano tra endpoint teams e SBC. 

Tieni presente che il traffico SIP scorre sempre tramite il proxy SIP.   
