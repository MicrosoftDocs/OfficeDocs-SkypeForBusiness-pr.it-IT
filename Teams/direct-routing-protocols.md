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
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569204"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Routing diretto - Definizioni e standard RFC

In questo articolo viene descritto Telefono Microsoft System Direct Routing implementa i protocolli standard RFC. Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra il controller SBC (Session Border Controller) locale e il servizio proxy SIP (Session Initiation Protocol).

Il cliente SBC si interfaccia con i seguenti componenti nel back-end Microsoft Teams'interno: 

- **Proxy SIP per** la segnalazione. Si tratta del componente di Routing diretto con connessione Internet che gestisce le connessioni SIP (TLS) tra le SBC e il routing diretto.

- **Processori multimediali** per supporti. Si tratta del componente di Routing diretto rivolto a Internet che gestisce il traffico multimediale. Questo componente utilizza protocolli SRTP e SRTCP.


Per ulteriori informazioni sul routing diretto, vedere [Sistema telefonico Direct Routing](direct-routing-landing-page.md).

Per ulteriori informazioni sull'implementazione del protocollo SIP da parte del routing diretto, vedere [Protocollo Direct Routing - SIP](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>Standard RFC

Il routing diretto è conforme agli standard RFC.  L'SBC collegato al routing diretto deve inoltre essere conforme alle seguenti RFC (o ai loro successori). 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità bypass non multimediale 

Gli standard seguenti sono applicabili ai dispositivi che supportano solo la modalità di bypass non multimediale:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocollo di avvio della sessione
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Estensione privata al protocollo di avvio della sessione per l'identità asserta all'interno di reti attendibili- Sezioni sulla gestione dell'intestazione P-Asserted-Identity. Il routing diretto invia p-asserted-identity con intestazioni ID privacy. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Estensione del SIP (Session Initiation Protocol) per le informazioni necessarie sulla cronologia. Per ulteriori informazioni, vedere anche: Routing SIP Protocol description.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Meccanismo di avvio della sessione Referred-By sessione
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Intestazione SIP (Session Initiation Protocol) "Replaces" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Utilizzo SIP (Session Initiation Protocol) del modello di offerta/risposta.
  Vedere la sezione "Deviazioni da RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) e [RFC 4771](https://tools.ietf.org/html/rfc4771). Proteggere il traffico RTP utilizzando SRTP. L'SBC deve essere in grado di stabilire chiavi utilizzando SDES. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Chiarimenti su offerta/risposta SDP (Session Description Protocol) per il multiplexing RTP/RTCP

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standard applicabili ai dispositivi che supportano la modalità di bypass multimediale

Oltre agli standard elencati come applicabili alla modalità non bypass, vengono utilizzati i seguenti standard per la modalità bypass multimediale:

- [RFC 5245 Interactive Connectivity Establishment (ICE) per il bypass multimediale](https://tools.ietf.org/html/rfc5245).  L'SBC deve supportare quanto segue:
  - ICE Lite : i Teams clienti sono clienti ICE completi
  - [ICE Riavvia](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Scopri di più su ICE riavvia il caso d'uso e gli esempi in ICE Restart: Chiamata di bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), vedere le sezioni 3.1, Forking e 3.2, Ringing Tone Generation 
- [Utilità di attraversamento sessione RFC 5389 per NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Norme applicabili per supportare il trasporto di informazioni sulla posizione ai fornitori dell'E911

- [RFC 6442, Trasporto posizione per il protocollo di avvio della sessione](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Deviazioni dagli RFC

Nella tabella seguente sono elencate le sezioni delle RFC in cui l'implementazione microsoft del SIP o dello stack multimediale si discosta dallo standard:

| RFC e sezioni | Descrizione | deviazione |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, sezione 5.3 Sospensione e ripresa dei supporti](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC consente di utilizzare "a=inactive", "a=sendonly", a=recvonly" per mettere una chiamata in attesa. |Il proxy SIP supporta solo "a=inactive" e non capisce se l'SBC invia "a=sendonly" o "a=recvonly".
| [RFC 6337, sezione 5.4 "Comportamento durante la ricezione di SDP con c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264 richiede](https://tools.ietf.org/html/rfc3264) che un agente sia in grado di ricevere SDP con un indirizzo di connessione 0.0.0.0, nel qual caso significa che né RTP né RTCP devono essere inviati al peer. | Il proxy SIP non supporta questa opzione. |

## <a name="operational-modes"></a>Modalità operative

Esistono due modalità operative per il routing diretto:

- **Senza bypass multimediale** in cui tutto il traffico RTP scorre tra il client Teams, i processori multimediali e l'SBC.  

- **Con bypass multimediale** in cui tutti i supporti RTP fluisce tra gli endpoint Teams e l'SBC. 

Si noti che il traffico SIP scorre sempre tramite il proxy SIP. 

## <a name="dtmf"></a>Dtmf
DTMF in banda non è supportato dallo stack multimediale.
