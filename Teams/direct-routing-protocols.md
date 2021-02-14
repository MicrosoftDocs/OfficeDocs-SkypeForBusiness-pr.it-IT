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
# <a name="direct-routing---definitions-and-rfc-standards"></a>Routing diretto - Definizioni e standard RFC

Questo articolo descrive in che modo Microsoft Phone System Direct Routing implementa i protocolli standard RFC. Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il controller dei confini della sessione (SBC) locale e il servizio proxy SIP (Session Initiation Protocol).

Il client SBC si interfaccia con i seguenti componenti nel back-end di Microsoft Teams: 

- **Proxy SIP per** il traffico di segnalazione. Componente per Internet del routing diretto che gestisce le connessioni SIP (TLS) tra SBC e routing diretto.

- **Processori multimediali per** gli elementi multimediali. Componente per Internet del routing diretto che gestisce il traffico multimediale. Questo componente utilizza protocolli SRTP e SRTCP.


Per altre informazioni sull'instradamento diretto, vedere [l'instradamento diretto del sistema telefonico.](direct-routing-landing-page.md)

Per altre informazioni sull'implementazione del protocollo SIP da parte di Direct Routing, vedere [Direct Routing - SIP protocol.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>Standard RFC

Il routing diretto è conforme agli standard RFC.  L'SBC connesso al routing diretto deve inoltre attenersi alle seguenti RDC (o ai relativi successori). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità bypass non multimediale 

I seguenti standard sono applicabili ai dispositivi che supportano solo la modalità bypass non multimediale:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Estensione privata del protocollo di avvio della sessione per l'identità assertti all'interno di reti attendibili: sezioni sulla gestione dell'intestazione P-Asserted-Identity. Il routing diretto invia le intestazioni P-Asserted-Identity con ID privacy. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione di SIP (Session Initiation Protocol) per le informazioni sulla cronologia richieste. Per altre informazioni, vedere anche: Routing SIP Protocol description.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di Referred-By Session Initiation Protocol
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione "Sostituisce" SIP (Session Initiation Protocol) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Utilizzo SIP (Session Initiation Protocol) del modello di offerta/risposta.
  Vedere la sezione "Deviazioni da RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771.](https://tools.ietf.org/html/rfc4771) Proteggere il traffico RTP con SRTP. SBC deve essere in grado di stabilire chiavi con SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Chiarimenti sull'offerta/risposta SDP (Session Description Protocol) per rtp/RTCP Multiplexing

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità bypass multimediale

Oltre agli standard elencati come applicabili alla modalità senza bypass, per la modalità bypass multimediale vengono utilizzati i seguenti standard:

- [RFC 5245 Interactive Connectivity Connectivity Connectivity Più (ICE) per il bypass multimediale.](https://tools.ietf.org/html/rfc5245)  Il servizio SBC deve supportare quanto segue:
  - ICE Lite - I clienti Teams sono clienti ICE completi
  - [ICE Restarts.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) Altre informazioni sul riavvio dell'ice per il riavvio del sistema ICE ed esempi in ICE Restart: chiamata di bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer.](https://tools.ietf.org/html/rfc5589) 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)vedere le sezioni 3.1, Forking e 3.2, Generazione di toni suonerii 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Standard applicabili per supportare la trasmissione di informazioni sulla posizione ai provider E911

- [RFC 6442, comunicazione della posizione per il protocollo di avvio della sessione](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Deviazioni da RFC

La tabella seguente elenca le sezioni di RFC in cui l'implementazione da parte di Microsoft dello stack di supporti SIP devia dallo standard:

| RFC e sezioni | Descrizione | Deviazione |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sezione 5.3 Blocco e curriculum multimediale](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC consente di usare "a=inactive", "a=sendonly", a=recvonly" per mettere una chiamata in attesa. |Il proxy SIP supporta solo "a=inactive" e non comprende se SBC invia "a=sendonly" o "a=recvonly".
| [RFC 6337, sezione 5.4 "Comportamento della ricezione di SDP con c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) richiede che un agente sia in grado di ricevere SDP con un indirizzo di connessione 0.0.0.0, nel qual caso non deve essere inviato né RTP né RTCP al peer. | Il proxy SIP non supporta questa opzione. |

## <a name="operational-modes"></a>Modalità operative

Esistono due modalità operative per il routing diretto:

- **Senza bypass multimediale** in cui tutto il traffico RTP passa tra il client Teams, i processori multimediali e SBC.  

- **Con bypass multimediale** in cui tutti gli elementi multimediali RTP passano tra gli endpoint di Teams e SBC. 

Tieni presente che il traffico SIP fluisce sempre attraverso il proxy SIP.   
