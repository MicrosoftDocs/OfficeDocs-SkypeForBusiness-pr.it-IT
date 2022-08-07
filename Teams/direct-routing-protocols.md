---
title: 'Routing diretto del sistema telefonico di Teams: definizioni e standard RFC'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Modalità di implementazione dei protocolli standard RFC da parte di Microsoft Phone System Direct Routing.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dbd61748d14ef21a600b2e4f44a306517e46d9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271241"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Direct routing - definizioni e standard RFC

Questo articolo descrive in che modo Microsoft Phone System Direct Routing implementa i protocolli standard RFC. Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra SBC (Session Border Controller) locale e il servizio proxy SIP (Session Initiation Protocol).

Il cliente SBC interfacce con i seguenti componenti nel back-end di Microsoft Teams: 

- **Proxy SIP** per la segnalazione. Questo è il componente internet del routing diretto che gestisce le connessioni SIP (TLS) tra gli SBC e il routing diretto.

- **Processori multimediali** per il supporto. Questo è il componente internet del routing diretto che gestisce il traffico multimediale. Questo componente utilizza protocolli SRTP e SRTCP.


Per ulteriori informazioni sul routing diretto, vedi [Routing diretto sistema telefonico](direct-routing-landing-page.md).

Per ulteriori informazioni sul modo in cui Direct Routing implementa il protocollo SIP, vedere [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Standard RFC

Direct Routing è conforme agli standard RFC.  SBC connesso a Direct Routing deve inoltre essere conforme alle seguenti RFC (o ai loro successori). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità bypass non multimediale 

I seguenti standard sono applicabili ai dispositivi che supportano solo la modalità bypass non multimediale:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks-- Sections about handling P-Asserted-Identity header. Direct Routing invia P-Asserted-Identity con intestazioni ID privacy. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione sip (Session Initiation Protocol) per le informazioni necessarie sulla cronologia. Vedere anche: Descrizione del protocollo SIP per il routing per ulteriori informazioni.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di Referred-By del protocollo di avvio della sessione
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione SIP (Session Initiation Protocol) "Sostituisce" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Utilizzo SIP (Session Initiation Protocol) del modello di offerta/risposta.
  Vedere la sezione "Deviazioni da RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteggere il traffico RTP con SRTP. Il controllo SBC deve essere in grado di stabilire le chiavi con SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Chiarimenti sull'offerta/risposta del protocollo di descrizione della sessione (SDP) per il multiplexing RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità bypass multimediale

Oltre agli standard elencati come applicabili alla modalità non bypass, per la modalità bypass multimediale vengono utilizzati i seguenti standard:

- [RFC 5245 Interactive Connectivity Establishment (ICE) per bypass multimediale](https://tools.ietf.org/html/rfc5245).  SBC deve supportare quanto segue:
  - ICE Lite - I client di Teams sono clienti ice completi
  - [ICE riavvia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Vedi altre informazioni sul caso di utilizzo dei riavvii ICE ed esempi in Riavvio ICE: chiamata di bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control - Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Standard applicabili per il supporto della trasmissione delle informazioni sulla posizione ai provider E911

- [RFC 6442, Trasmissione della posizione per il protocollo di avvio della sessione](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Deviazioni da RFC

La tabella seguente elenca le sezioni delle RFC in cui l'implementazione di Microsoft del SIP o dello stack multimediale devia dallo standard:

| RFC e sezioni | Descrizione | Deviazione |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sezione 5.3 Blocco e curriculum del supporto](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC consente di usare "a=inactive", "a=sendonly", a=recvonly" per mettere una chiamata in attesa. |Il proxy SIP supporta solo "a=inactive" e non comprende se SBC invia "a=sendonly" o "a=recvonly".
| [RFC 6337, sezione 5.4 "Behavior on Receiving SDP with c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) richiede che un agente sia in grado di ricevere SDP con un indirizzo di connessione 0.0.0.0, nel qual caso significa che né RTP né RTCP devono essere inviati al peer. | Il proxy SIP non supporta questa opzione. |

## <a name="operational-modes"></a>Modalità operative

Esistono due modalità operative per il routing diretto:

- **Senza bypass multimediale** in cui tutto il traffico RTP scorre tra il client Teams, i processori multimediali e SBC.  

- **Con il bypass multimediale** in cui tutti i flussi multimediali RTP tra gli endpoint di Teams e SBC. 

Si noti che il traffico SIP scorre sempre tramite il proxy SIP. 

## <a name="dtmf"></a>DTMF
DTMF in banda non è supportato dallo stack di supporti.
