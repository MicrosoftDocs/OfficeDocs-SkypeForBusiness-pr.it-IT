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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888575"
---
# <a name="overview"></a>Panoramica

Questo articolo descrive in che modo l'instradamento diretto supporta il bypass multimediale con un controller SBC (Session Border Controller) abilitato per ICE Lite, come descritto in [RFC 5245.](https://tools.ietf.org/html/rfc5245) Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il servizio SBC locale e il servizio proxy SIP.

Questo articolo fornisce una panoramica degli scenari e dei requisiti di ICE Lite per l'interoperabilità. L'articolo descrive i formati dei messaggi e le transizioni richieste dalla macchina a stati per garantire un flusso affidabile delle chiamate e dei supporti multimediali.

## <a name="terminology"></a>Terminologia

- Primo saluto: le prime parole pronunciate dal chiamante e dal chiamato. È importante fare tutto il possibile per assicurare che i primi pacchetti dagli endpoint siano recapitati in modo affidabile nella maggior parte dei casi di utilizzo.

- Forking: l'offerta del chiamante potrebbe essere recapitata a più endpoint del chiamato se il chiamato è disponibile su più dispositivi (ad esempio, un utente di Teams potrebbe essere connesso a Teams per Windows e Teams per Android o iPhone).

- Risposta provvisoria (183) - Gli endpoint del chiamato per una configurazione della chiamata più rapida inviano una risposta con i candidati e i codici necessari per stabilire il flusso multimediale. Questa operazione viene eseguita anticipatamente dall'utente potenzialmente rispondendo alla chiamata(200OK) da quella specifica istanza del chiamato. Con la penna, il chiamante dovrebbe essere pronto a ricevere più risposte provvisorie.

- Re-Invite : offerta con candidati finali selezionati dall'endpoint di controllo ICE. Avrà l'attributo a=remote-candidate per risolvere eventuali condizioni di corsa dalla gestione di più fork.

- Endpoint di Teams: può trattarsi di un server (Processore multimediale, Inoltro di trasporto) o del client di Teams.

## <a name="message-format"></a>Formato del messaggio

L'infrastruttura Teams è conforme allo standard RFC 5245 per ICE-Lite. Questo implica che tutti i messaggi STUN saranno conformi allo [standard RFC 5389.](https://tools.ietf.org/html/rfc5389)

I file STUN richiesti da RFC 5389 devono ignorare gli attributi STUN che non riconoscono e continuare a elaborare i messaggi con gli attributi noti. 

Se vengono ricevuti pacchetti non in formato corretto, i pacchetti devono essere ignorati senza alcun impatto sulla connessione della sessione del supporto.

## <a name="ice-lite-requirements"></a>Requisiti di ICE Lite

Questa sezione contiene brevemente i requisiti per ICE Lite.

### <a name="candidate-gathering"></a>Raccolta dei candidati

Il servizio SBC deve offrire un solo candidato raggiungibile pubblicamente. Attualmente sono supportati solo i candidati IPV4.


#### <a name="connectivity-checks"></a>Controlli della connettività

L'implementazione di ICE Lite deve rispondere a qualsiasi verifica di connettività ricevuta. L'endpoint ICE Lite non deve inviare richieste di verifica della connettività. Se i controlli di connettività vengono inviati in violazione, risponderà l'implementazione completa, il che può causare la ricerca di candidati non imprevisti derivati da peer e potenziali errori di chiamata.

#### <a name="nominations"></a>Marsie

L'endpoint di implementazione completa ICE sarà sempre l'endpoint di controllo e seguirà le indicazioni "Regular" per selezionare i candidati finali da usare per il flusso multimediale. L'endpoint ICE Lite può usare i loghi per concludere il percorso da utilizzare per il supporto e completare lo stabilire della chiamata.

Nota: in caso di forking con endpoint peer che inviano 183 risposte provvisorie, il servizio SBC deve essere pronto per rispondere ai controlli da più endpoint e anche per ottenere risposte da più endpoint se i problemi si verificano prima del 200OK. A seconda della convergenza della macchina a stati ICE sul percorso finale e sui tempi di risposta dell'utente, le risposte possono verificarsi prima o dopo il 200OK. Il controller SBC deve essere in grado di gestire entrambi i casi.

#### <a name="converging-for-forking"></a>Convergenza per la distorsive

Se l'offerta dal database SBC offre fork a più endpoint di Teams, gli endpoint di Teams possono rispondere con una risposta provvisoria e avviare i controlli di connettività. Il servizio SBC deve essere preparato per ricevere i controlli di connettività e rispondere ai controlli di connettività da più endpoint peer. Ad esempio, l'utente di Teams potrebbe essere connesso sia a un desktop che a un cellulare. Entrambi i dispositivi riceveranno una notifica della chiamata in entrata e tenteranno di verificare la connettività con il dispositivo SBC.

Alla fine solo uno degli endpoint risponderà alla chiamata (200OK). Alla ricezione di 200OK, SBC può configurare il contesto giusto per l'elaborazione dei pacchetti multimediali.

## <a name="scenarios"></a>Scenari

###  <a name="inbound-call-from-sbc"></a>Chiamata in ingresso da SBC

Per questo scenario, sono presenti diversi endpoint peer possibili che il servizio SBC deve gestire:

- Gli endpoint server in genere rispondono direttamente con 200OK. Si tratta di endpoint ICE completi che in genere sono coinvolti in scenari di segreteria telefonica, coda di chiamata e operatore automatico.

- Gli endpoint client possono inviare più risposte provvisorie con tag Da/A diversi (183) seguiti da un 200OK dall'endpoint che risponde alla chiamata. Si tratta di endpoint ICE completi che rappresentano in genere i client degli utenti finali.

- Altri endpoint SBC. Si tratta di endpoint ICE Lite generalmente coinvolti nello scenario di squillo simultaneo degli endpoint client e di altri numeri di telefono.

Il servizio SBC deve rispondere a tutte le richieste di verifica della connettività valide ricevute dagli endpoint ICE completi. Per RFC, gli endpoint ICE completi diventeranno gli endpoint di controllo. Gli endpoint di Teams (client/server) eseguiranno "Normale" per completare i controlli di connettività. La versione 200Ok finale può essere da un endpoint che ha inviato elementi multimediali iniziali o da un altro endpoint. Alla ricezione di 200Ok, SBC deve configurare il contesto giusto per il flusso multimediale. 

###  <a name="early-media"></a>Early media

Se c'è un flusso di elementi multimediali iniziale, il dispositivo SBC deve essere in fase di latenza verso il primo endpoint che avvia lo streaming degli elementi multimediali; il flusso multimediale può iniziare prima della nomina dei candidati. Durante questa fase, il sistema SBC dovrebbe supportare l'invio di DTMF per abilitare gli scenari IVR/segreteria telefonica. Il valore SBC deve usare il percorso con la priorità più alta in cui ha ricevuto i controlli per verificare se non sono state completate.

### <a name="outbound-call-to-sbc"></a>Chiamata in uscita a SBC

Gli endpoint di Teams sono il chiamante per questo scenario e saranno il controllo dell'endpoint. Alla ricezione di una risposta provvisoria (183) o di una risposta finale (200OK), l'endpoint di Teams avvia i controlli di connettività e procede verso "Normale" per completare i controlli di connettività.

Nota: se SBC invia una risposta provvisoria (183), deve essere pronto per ricevere le richieste di verifica della connettività e potrebbe completare le attività prima dell'invio del 200OK da parte del SBC. Se i controlli e/o le cine vengono completati prima della ricezione del 200OK, i controlli e/o i controlli non verranno eseguiti di nuovo dopo la ricezione della funzione 200OK. L'SBC non deve cambiare i candidati ICE, la password e gli ufrag (frammento di nome utente) tra 183 e 200.

Per supportare i contenuti multimediali iniziali, il servizio SBC può avviare lo streaming dei contenuti multimediali al candidato peer ICE, con la massima priorità in base ai controlli di connettività ricevuti, anche prima del completamento delle attività da parte dell'endpoint di Teams. L'SBC dovrebbe aspettarsi che i contenuti multimediali da Teams su qualsiasi candidato siano completati. Dopo la nomina del candidato, il servizio SBC deve reimpostarsi nel contesto giusto per inviare e ricevere pacchetti multimediali.

## <a name="srtp-support-requirements"></a>Requisiti di supporto per SRTP

Il servizio SBC deve supportare la crittografia SRTP AES_CM_128_HMAC_SHA1_80 per offrire e rispondere nel formato seguente:

```console
"inline:" <key||salt> ["|" lifetime]
```

Di seguito è riportato un esempio dell'attributo crypto nell'offerta SDP da SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

I parametri MKI e Length non sono necessari.

Per altre informazioni, vedere [RFC 4568, sezione 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>Requisiti di supporto per SDES

Il dispositivo deve essere in grado di offrire SDES nel formato descritto di seguito. I processori Microsoft Media preferiscono sempre SDES.

- Con bypass non multimediali, anche se un client supporta solo DTLS, i processori multimediali verranno convertiti in SDES.

- Con il bypass multimediale, se un client è solo DTLS (stato futuro di Google Chrome), l'instradamento diretto inserirà un MP nel percorso, convertendo la chiamata dal bypass multimediale al bypass non multimediale. Tra SBC e il componente processore multimediale dell'instradamento diretto, SDES viene sempre utilizzato.

Attualmente, non esiste un client Teams che offre solo DTLS; Tuttavia, Google ha annunciato che a un certo punto smetteranno di supportare SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato dell'offerta da SBC in modalità bypass 

L'offerta deve contenere SDES e può contenere DTLS facoltativo nel formato seguente:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formato per la risposta che contiene da SDES a SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato per l'offerta da Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Formato disponibile solo per SDES a SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

