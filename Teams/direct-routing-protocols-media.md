---
title: Instradamento diretto di Sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 550836275a1ea060d6004c75e0f2bf301f3094a7752ae80ad44dc2c91bbf96bd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339782"
---
# <a name="overview"></a>Panoramica

Questo articolo descrive in che modo il routing diretto supporta il bypass multimediale con un session border controller (SBC) abilitato per ICE Lite, come descritto in [RFC 5245.](https://tools.ietf.org/html/rfc5245) Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il servizio SBC locale e il servizio proxy SIP.

Questo articolo fornisce una panoramica degli scenari e dei requisiti ice Lite per l'interoperabilità. L'articolo descrive i formati dei messaggi e le transizioni richieste della macchina a stati per garantire un flusso affidabile di chiamate e supporti.

## <a name="terminology"></a>Terminologia

- First Hello: le prime parole pronunciate dal chiamante e dal chiamato. È importante fare tutto il possibile per garantire che i primi pacchetti degli endpoint siano recapitati in modo affidabile per la maggior parte dei casi d'uso.

- Forking: l'offerta del chiamante potrebbe essere recapitata a più endpoint del chiamato se il chiamato è disponibile su più dispositivi (ad esempio, un utente di Teams potrebbe aver eseguito l'accesso a Teams per Windows e Teams per Android o iPhone).

- Risposta provvisoria (183) - Gli endpoint del chiamato per una configurazione più rapida della chiamata inviano una risposta con i candidati e i tasti necessari per stabilire il flusso multimediale. Questa operazione viene eseguita in previsione che l'utente risponda potenzialmente alla chiamata(200OK) da quella specifica istanza del chiamato. Con il forking, il chiamante dovrebbe essere pronto a ricevere più risposte provvisorie.

- Re-Invite: offerta con i candidati finali selezionati dall'endpoint di controllo ICE. Questo avrà l'attributo a=remote-candidate per risolvere eventuali condizioni di gara dalla gestione di più forche.

- Teams Endpoint: può trattarsi di un server (Processore multimediale, Inoltro di trasporto) o Teams client.

## <a name="message-format"></a>Formato del messaggio

L Teams dell'infrastruttura segue l'RFC 5245 per ICE-Lite. Questo implica che tutti i messaggi STUN saranno conformi a [RFC 5389.](https://tools.ietf.org/html/rfc5389)

Gli SBC come richiesto da RFC 5389 devono ignorare gli attributi STUN che non riconoscono e continuare a elaborare i messaggi con gli attributi noti. 

Se vengono ricevuti pacchetti in formato non corretto, i pacchetti devono essere eliminati senza influire sulla creazione della sessione multimediale.

## <a name="ice-lite-requirements"></a>Requisiti ice Lite

Questa sezione acquisisce brevemente i requisiti per ICE Lite.

### <a name="candidate-gathering"></a>Raccolta di candidati

L'SBC deve offrire un solo candidato accessibile pubblicamente. Attualmente sono supportati solo i candidati IPV4.


#### <a name="connectivity-checks"></a>Controlli di connettività

L'implementazione ICE Lite deve rispondere a tutti i controlli di connettività ricevuti. L'endpoint ICE Lite non deve inviare richieste di controllo della connettività. Se i controlli di connettività vengono inviati in violazione, l'implementazione completa risponderà, il che può comportare l'individuarsi di candidati imprevisti derivati da peer e potenzialmente errori di chiamata.

#### <a name="nominations"></a>Candidature

L'endpoint di implementazione completa ICE sarà sempre l'endpoint di controllo e seguirà le nomine "regolari" per la selezione dei candidati finali da usare per il flusso multimediale. L'endpoint ICE Lite può usare le nomine per concludere il percorso da usare per i supporti multimediali e completare la creazione di chiamate.

Nota: nel caso di un forking con endpoint peer che inviano 183 risposte provvisorie, SBC deve essere pronto a rispondere ai controlli provenienti da più endpoint e anche alle nomine da più endpoint se le nomine si verificano prima del 200OK. A seconda della convergenza della macchina a stati ICE sul percorso finale e dell'intervallo di risposta dell'utente, le nomine possono avvenire prima o dopo il 200OK. SBC deve essere in grado di gestire entrambi i casi.

#### <a name="converging-for-forking"></a>Convergenza per il forking

Se l'offerta da SBC viene forcata a più endpoint Teams, gli endpoint Teams possono rispondere con una risposta provvisoria e avviare i controlli di connettività. SBC deve essere preparato per ricevere i controlli di connettività e rispondere ai controlli di connettività da più endpoint peer. Ad esempio, l Teams utente potrebbe essere connesso sia a un desktop che a un cellulare. Entrambi i dispositivi riceveranno una notifica della chiamata in ingresso e tenteranno di verificare la connettività con SBC.

Alla fine solo uno degli endpoint risponderà alla chiamata (200OK). Quando si riceve 200OK, SBC può configurare il contesto giusto per l'elaborazione dei pacchetti multimediali.

## <a name="scenarios"></a>Scenari

###  <a name="inbound-call-from-sbc"></a>Chiamata in ingresso da SBC

Per questo scenario, sono disponibili diversi endpoint peer che il servizio SBC deve gestire:

- Gli endpoint del server in genere rispondono direttamente con 200OK. Si tratta di endpoint ICE completi che in genere sono coinvolti negli scenari di segreteria telefonica, coda di chiamata e operatore automatico.

- Gli endpoint client possono inviare più risposte provvisorie con tag From/To diversi (183) seguiti da un 200OK dall'endpoint che risponde alla chiamata. Si tratta di endpoint ICE completi che rappresentano in genere i client degli utenti finali.

- Altri endpoint SBC. Si tratta di endpoint ICE Lite in genere coinvolti nello scenario di squillo simultaneo degli endpoint client e di altri numeri di telefono.

SBC deve rispondere a tutte le richieste di controllo della connettività valide ricevute dagli endpoint ICE completi. Per RFC, gli endpoint ICE completi diventeranno Controllo degli endpoint. Gli endpoint Teams (client/server) eseguiranno nomine "regolari" per completare i controlli di connettività. Il 200Ok finale può essere da un endpoint che ha inviato elementi multimediali iniziali o da un endpoint diverso. Quando si riceve 200Ok, SBC deve configurare il contesto giusto per il flusso multimediale. 

###  <a name="early-media"></a>Elementi multimediali iniziali

Se è presente un flusso multimediale iniziale, il dispositivo SBC deve eseguire il latch al primo endpoint che avvia lo streaming multimediale. il flusso multimediale può iniziare prima della nomina dei candidati. L'SBC dovrebbe avere il supporto per l'invio di DTMF durante questa fase per abilitare gli scenari IVR/segreteria telefonica. L'SBC deve usare il percorso con la priorità più alta in cui ha ricevuto i controlli se le nomine non sono state completate.

### <a name="outbound-call-to-sbc"></a>Chiamata in uscita a SBC

Gli Teams endpoint sono il Chiamante per questo scenario e saranno l'endpoint di controllo. Quando si riceve una risposta provvisoria (183) o una risposta finale(200OK), l'endpoint di Teams avvia i controlli di connettività e procede alle nomine "regolari" per completare i controlli di connettività.

Nota: se SBC invia una risposta provvisoria (183), deve essere pronto per ricevere le richieste di verifica della connettività e potenzialmente completare le nomine prima che il 200OK venga inviato dalla SBC. Se i controlli e/o le nomine vengono completate prima della ricezione del 200OK, i controlli e/o le nomine non verranno eseguiti di nuovo dopo la ricezione di 200OK. L'SBC non deve modificare i candidati ICE, la password e l'ufrag (frammento del nome utente) tra 183 e 200.

Per supportare i primi media, la SBC può iniziare a trasmettere i contenuti multimediali al candidato ICE peer, con la priorità più alta in base ai controlli di connettività ricevuti, anche prima che le candidature siano completate da un endpoint Teams finale. La SBC dovrebbe aspettarsi che i media Teams su qualsiasi candidato fino al completamento delle candidature. Dopo la nomina di un candidato, il SBC deve reimpostare il contesto giusto per inviare e ricevere pacchetti multimediali.

## <a name="srtp-support-requirements"></a>Requisiti di supporto SRTP

La crittografia SBC deve supportare i AES_CM_128_HMAC_SHA1_80 crittografia SRTP per offrire e rispondere nel formato seguente:

```console
"inline:" <key||salt> ["|" lifetime]
```

Di seguito è riportato un esempio dell'attributo crypto nell'offerta SDP da SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

I parametri MKI e Length non sono obbligatori.

Per altre informazioni, vedere [RFC 4568, sezione 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>Requisiti di supporto per SDES

Il dispositivo deve essere in grado di offrire SDES nel formato descritto di seguito. I processori Microsoft Media preferiscono sempre SDES.

- Con il bypass non multimediale, anche se un client supporta solo DTLS, i processori multimediali verranno convertiti in SDES.

- Con il bypass multimediale, se un client è solo DTLS (stato futuro di Google Chrome), Direct Routing inserirà un MP nel percorso, convertendo la chiamata da bypass multimediale a bypass non multimediale. Tra il componente SBC e il processore multimediale di Direct Routing, viene sempre usato SDES.

Attualmente non sono disponibili client Teams che offrono solo DTLS. Tuttavia, Google ha annunciato che, a un certo punto, smetterà di supportare SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato per l'offerta da SBC in modalità bypass 

Offer deve contenere SDES e può contenere DTLS facoltativo nel formato seguente:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formato per la risposta contenente da SDES a SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato per l'offerta da Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format for SDES only offer to SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

