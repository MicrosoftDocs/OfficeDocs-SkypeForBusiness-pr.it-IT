---
title: 'Teams routing diretto del sistema telefonico: definizioni e standard RFC'
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
description: Come Telefono Microsoft system direct routing implementa i protocolli standard RFC.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26178fa52105f43ce9f7f18c0058a2ead3ef1c02
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235341"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Routing diretto : definizioni e standard RFC

Questo articolo descrive in che modo Telefono Microsoft system direct routing implementa i protocolli standard RFC. Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il session border controller (SBC) locale e il servizio proxy SIP (Session Initiation Protocol).

Il client SBC si interfaccia con i componenti seguenti nel back-end Microsoft Teams back-end: 

- **Proxy SIP per** la segnalazione. Questo è il componente di Routing diretto rivolto a Internet che gestisce le connessioni SIP (TLS) tra gli SBC e il routing diretto.

- **Processori multimediali per** supporti multimediali. Questo è il componente di Routing diretto rivolto a Internet che gestisce il traffico multimediale. Questo componente usa i protocolli SRTP e SRTCP.


Per altre informazioni sul routing diretto, vedere Sistema telefonico [routing diretto](direct-routing-landing-page.md).

Per altre informazioni sull'implementazione del protocollo SIP da parte di Routing diretto, vedere [Routing diretto - Protocollo SIP.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>Standard RFC

Il routing diretto è conforme agli standard RFC.  Anche il servizio SBC connesso al routing diretto deve essere conforme alle RFC seguenti (o ai relativi successori). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità di bypass non multimediale 

Gli standard seguenti sono applicabili ai dispositivi che supportano solo la modalità di bypass non multimediale:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Estensione privata del protocollo di avvio sessione per l'identità asserta all'interno di reti attendibili: sezioni sulla gestione dell'intestazione P-Asserted-Identity. Il routing diretto invia P-Asserted-Identity con intestazioni ID privacy. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione del protocollo SIP (Session Initiation Protocol) per le informazioni sulla cronologia necessarie. Per altre informazioni, vedere anche: Descrizione del protocollo SIP di routing.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di Referred-By Session Initiation Protocol
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione sip (Session Initiation Protocol) "Sostituisce" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Utilizzo sip (Session Initiation Protocol) del modello di offerta/risposta.
  Vedere la sezione "Deviazioni da RFC".
- [RFC 3711 e](https://tools.ietf.org/html/rfc3711) [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteggere il traffico RTP usando SRTP. SBC deve essere in grado di stabilire le chiavi usando SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Chiarimenti dell'offerta/risposta SDP (Session Description Protocol) per rtp/RTCP Multiplexing

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità bypass multimediale

Oltre agli standard elencati come applicabili alla modalità non bypass, per la modalità di bypass multimediale vengono usati gli standard seguenti:

- [RFC 5245 Interactive Connectivity Establishment (ICE) per bypass multimediale](https://tools.ietf.org/html/rfc5245).  SBC deve supportare quanto segue:
  - ICE Lite - i Teams clienti sono clienti ICE completi
  - [ICE Riavvia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Per altre informazioni sul caso di utilizzo dei riavvii ICE, vedere Riavvio ICE: chiamata bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), vedere le sezioni 3.1, Forking e 3.2, Ringing Tone Generation 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Standard applicabili per supportare la trasmissione di informazioni sulla posizione ai provider E911

- [RFC 6442, Comunicazione della posizione per il protocollo di avvio della sessione](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Deviazioni dalla RFC

La tabella seguente elenca le sezioni delle RFC in cui l'implementazione microsoft dello stack SIP o multimediale si discosta dallo standard:

| RFC e sezioni | Descrizione | Deviazione |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sezione 5.3 Blocco e riprendi elementi multimediali](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC consente di usare "a=inattivo", "a=sendonly", a=recvonly" per mettere una chiamata in attesa. |Il proxy SIP supporta solo "a=inattivo" e non comprende se SBC invia "a=sendonly" o "a=recvonly".
| [RFC 6337, sezione 5.4 "Comportamento della ricezione di SDP con c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) richiede che un agente sia in grado di ricevere SDP con un indirizzo di connessione 0.0.0.0, nel qual caso significa che né RTP né RTCP devono essere inviati al peer. | Il proxy SIP non supporta questa opzione. |

## <a name="operational-modes"></a>Modalità operative

Esistono due modalità operative per il routing diretto:

- **Senza bypass multimediale** in cui tutto il traffico RTP fluisce tra il client Teams, i processori multimediali e sBC.  

- **Con bypass multimediale** in cui tutti i supporti RTP fluire tra gli endpoint Teams e SBC.With media bypass in which all RTP media flows between the Teams endpoints and the SBC. 

Si noti che il traffico SIP fluisce sempre tramite il proxy SIP. 

## <a name="dtmf"></a>DTMF
Il DTMF in banda non è supportato dallo stack multimediale.
