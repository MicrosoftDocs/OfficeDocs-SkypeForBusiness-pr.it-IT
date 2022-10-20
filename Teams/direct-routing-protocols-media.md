---
title: Panoramica del routing diretto del sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: hHw Direct Routing supporta il bypass multimediale con un session border controller abilitato per ICE Lite.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6f9715ee410116a66c572522a910cd16ef27154
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614419"
---
# <a name="overview"></a>Panoramica

Questo articolo descrive in che modo Direct Routing supporta il bypass multimediale con un Session Border Controller (SBC) abilitato per ICE Lite, come descritto in [RFC 5245](https://tools.ietf.org/html/rfc5245). Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra SBC locale e il servizio proxy SIP.

Questo articolo fornisce una panoramica degli scenari e dei requisiti di ICE Lite per l'interoperabilità. L'articolo descrive i formati dei messaggi e le transizioni del computer di stato necessarie per garantire un flusso di chiamate e supporti affidabile.

## <a name="terminology"></a>Terminologia

- First Hello - Le prime parole pronunciate dal chiamante e dal chiamante. È importante fare tutto il possibile per garantire che i primi pacchetti degli endpoint vengano distribuiti in modo affidabile per la maggior parte dei casi di utilizzo.

- Input penna – L'offerta del chiamante potrebbe essere recapitata a più endpoint chiamante se il destinatario della chiamata è disponibile su più dispositivi (ad esempio, un utente di Teams potrebbe essere connesso a Teams per Windows e Teams per Android o iPhone).

- Risposta provvisoria (183): gli endpoint del destinatario della chiamata per una configurazione più rapida della chiamata inviano una risposta con i candidati e le chiavi necessari per stabilire il flusso multimediale. Questa operazione viene eseguita prima che l'utente risponda potenzialmente alla chiamata (200OK) da quella specifica istanza del destinatario della chiamata. Con la penna, il chiamante dovrebbe essere pronto a ricevere più risposte provvisorie.

- Re-Invite: offerta con candidati finali selezionati dall'endpoint di controllo ICE. Questo avrà l'attributo a=remote-candidate per risolvere eventuali condizioni di competizione dalla gestione di più forche.

- Endpoint di Teams: può essere un server (Media Processor, Transport Relay) o il client di Teams.

## <a name="message-format"></a>Formato messaggio

L'infrastruttura di Teams segue RFC 5245 per ICE-Lite. Ciò implica che tutti i messaggi STUN saranno conformi allo [RFC 5389](https://tools.ietf.org/html/rfc5389).

Gli SBC come richiesto da RFC 5389 devono ignorare gli attributi STUN che non riconoscono e continuare a elaborare i messaggi con gli attributi noti. 

Se vengono ricevuti pacchetti non validi, i pacchetti devono essere scartati senza influire sull'istituzione della sessione multimediale.

## <a name="ice-lite-requirements"></a>Requisiti di ICE Lite

Questa sezione illustra brevemente i requisiti per ICE Lite.

### <a name="candidate-gathering"></a>Raccolta dei candidati

L'SBC deve offrire un solo candidato. Attualmente sono supportati solo i candidati IPV4.


#### <a name="connectivity-checks"></a>Controlli di connettività

L'implementazione di ICE Lite deve rispondere a tutti i controlli di connettività ricevuti. L'endpoint ICE Lite non deve inviare richieste di controllo della connettività. (Se i controlli di connettività vengono inviati in violazione, l'implementazione completa risponderà, il che può comportare l'individuazione di candidati derivati da peer imprevisti e potrebbe causare errori di chiamata.

#### <a name="nominations"></a>Nomination

L'endpoint di implementazione completa ICE sarà sempre l'endpoint di controllo e seguirà le nomine "regolari" per la selezione dei candidati finali da utilizzare per il flusso multimediale. L'endpoint ICE Lite può utilizzare le nomine per concludere il percorso da utilizzare per i media e per completare l'istituzione della chiamata.

Nota: nel caso dell'input penna con endpoint peer che inviano 183 risposte provvisorie, la SBC deve essere pronta a rispondere ai controlli da più endpoint e anche alle nomine da più endpoint se le nomine avvengono prima del 200OK. A seconda della convergenza della macchina dello stato ICE sul percorso finale e sulla tempistica della risposta dell'utente, le nomination possono avvenire prima o dopo il 200OK. Il controllo SBC deve essere in grado di gestire entrambi i casi.

#### <a name="converging-for-forking"></a>Convergente forking

Se l'offerta delle forche SBC a più endpoint di Teams, gli endpoint di Teams possono rispondere con una risposta provvisoria e avviare i controlli di connettività. L'SBC deve essere pronto a ricevere i controlli di connettività e a rispondere ai controlli di connettività da più endpoint peer. Ad esempio, l'utente di Teams potrebbe essere connesso sia a un desktop che a un cellulare. Entrambi i dispositivi riceveranno una notifica della chiamata in ingresso e proveranno i controlli di connettività con SBC.

Alla fine solo uno degli endpoint risponderà alla chiamata (200OK). Dopo aver ricevuto 200OK, SBC può configurare il contesto corretto per l'elaborazione dei pacchetti multimediali.

## <a name="scenarios"></a>Scenari

###  <a name="inbound-call-from-sbc"></a>Chiamata in ingresso da SBC

Per questo scenario, esistono diversi endpoint peer che sbc deve gestire:

- Gli endpoint server in genere rispondono direttamente con 200OK. Si tratta di endpoint ICE completi che in genere sono coinvolti in scenari di segreteria telefonica, coda di chiamata e operatore automatico.

- Gli endpoint client possono inviare più risposte provvisorie con tag Da/A diversi (183) seguiti da una 200OK dall'endpoint che risponde alla chiamata. Si tratta di endpoint ICE completi che in genere rappresentano i client degli utenti finali.

- Altri endpoint SBC. Si tratta di endpoint ICE Lite generalmente coinvolti nello scenario degli endpoint client che squillano contemporaneamente e di un altro o più numeri di telefono.

SBC deve rispondere a tutte le richieste di controllo della connettività valide ricevute dagli endpoint ICE completi. In base a RFC, gli endpoint ICE completi diventeranno gli endpoint di controllo. Gli endpoint di Teams (client/server) eseguiranno nomine "regolari" per completare i controlli di connettività. L'ultimo 200Ok può provenire da un endpoint che ha inviato elementi multimediali preliminari o da un endpoint diverso. Quando si riceve 200Ok, SBC deve configurare il contesto corretto per il flusso multimediale. 

###  <a name="early-media"></a>Elementi multimediali preliminari

Se è presente un flusso multimediale iniziale, SBC deve essere collegato al primo endpoint che avvia lo streaming multimediale; flusso dei media può iniziare prima che i candidati vengano nominati. SBC dovrebbe avere il supporto per l'invio di DTMF durante questa fase per abilitare scenari di IVR/segreteria telefonica. La SBC dovrebbe utilizzare il percorso con la massima priorità su cui ha ricevuto controlli se le nomine non sono state completate.

### <a name="outbound-call-to-sbc"></a>Chiamata in uscita a SBC

Gli endpoint di Teams sono il chiamante per questo scenario e saranno l'endpoint di controllo. Dopo aver ricevuto una risposta provvisoria (183) o una risposta finale (200OK), l'endpoint di Teams avvierà i controlli di connettività e procederà con le nomine "regolari" per completare i controlli di connettività.

Nota: se la SBC invia una risposta provvisoria (183), il SBC deve essere pronto a ricevere richieste di controllo della connettività e potenzialmente completare le nomine prima che il 200OK venga inviato dalla SBC. Se i controlli e/o le nomine vengono completati prima della ricezione di 200OK, i controlli e/o le nomine non verranno eseguiti di nuovo dopo la ricezione di 200OK. L'SBC non deve modificare i candidati ICE, la password e l'ufrag (frammento di nome utente) compresi tra 183 e 200.

Per supportare i primi media, la SBC può iniziare a trasmettere i file multimediali al candidato ICE peer, con la massima priorità in base ai controlli di connettività ricevuti, anche prima che le nomination vengano completate dall'endpoint di Teams. La SBC dovrebbe aspettarsi media da Teams su qualsiasi candidato fino al completamento delle nomine. Dopo la nomina di un candidato, la scheda SBC deve essere reimpostata nel contesto corretto per inviare e ricevere pacchetti multimediali.

## <a name="srtp-support-requirements"></a>Requisiti di supporto SRTP

Il servizio di crittografia SBC deve supportare AES_CM_128_HMAC_SHA1_80 di crittografia SRTP per offrire e rispondere nel formato seguente:

```console
"inline:" <key||salt> ["|" lifetime]
```

Di seguito è riportato un esempio dell'attributo crypto nell'offerta SDP da SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

I parametri MKI e Length non sono necessari.

Per ulteriori informazioni, vedere [RFC 4568, sezione 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Requisiti di supporto di SDES

Il dispositivo deve essere in grado di offrire SDES nel formato descritto di seguito. I processori Microsoft Media preferiscono sempre SDES.

- Con il bypass non multimediale, anche se un client supporta solo DTLS, i processori multimediali verranno convertiti in SDES.

- Con il bypass multimediale, se un client è solo DTLS (futuro stato di Google Chrome), Direct Routing inserirà un MP nel percorso, convertendo la chiamata da bypass multimediale a bypass non multimediale. Tra il componente SBC e il processore multimediale di Direct Routing, SDES viene sempre utilizzato.

Attualmente, non ci sono client di Teams che offrono solo DTLS; tuttavia Google ha annunciato che a un certo punto smetteranno di supportare SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato per l'offerta di SBC in modalità bypass 

L'offerta deve contenere SDES e può contenere DTLS facoltativo nel formato seguente:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formato della risposta contenente SDES a SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato per l'offerta da Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Il formato per SDES offre solo a SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

