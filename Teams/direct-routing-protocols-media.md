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

Questo articolo descrive il modo in cui il routing diretto supporta il bypass multimediale con un SBC (Session Border Controller) abilitato per ICE Lite, come descritto in [RFC 5245](https://tools.ietf.org/html/rfc5245). Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra l'SBC locale e il servizio proxy SIP.

Questo articolo offre una panoramica degli scenari e dei requisiti ICE Lite per l'interoperabilità. L'articolo descrive i formati dei messaggi e le transizioni necessarie della macchina a stati per garantire la chiamata e il flusso di elementi multimediali affidabili.

## <a name="terminology"></a>Terminologia

- Primo saluto: le prime parole pronunciate dal chiamante e dal chiamato. È importante che tutti gli sforzi vengano effettuati per garantire che i primi pacchetti degli endpoint vengano recapitati in modo affidabile per la maggior parte dei casi di utilizzo.

- Fork: l'offerta del chiamante può essere recapitata a più endpoint di chiamata, se il chiamato è disponibile su più dispositivi (ad esempio, un utente di teams può essere connesso a team per Windows e teams per Android o iPhone).

- Risposta provvisoria (183): gli endpoint dei chiamanti per una configurazione più rapida delle chiamate inviano una risposta con i candidati e le chiavi necessarie per stabilire il flusso multimediale. Questa operazione viene eseguita in previsione dell'utente che può potenzialmente rispondere alla chiamata (200OK) da quella specifica istanza di chiamato. Con il fork, il chiamante dovrebbe essere pronto per ricevere più risposte provvisorie.

- Re-invite-offerta con i candidati finali selezionati dall'endpoint di controllo del ghiaccio. Questo avrà l'attributo a = Remote-candidate per risolvere qualsiasi condizione di competizione dalla gestione di più fork.

- Endpoint teams: può essere un server (media processor, Transport Relay) o il client teams.

## <a name="message-format"></a>Formato messaggio

L'infrastruttura teams segue l'RFC 5245 per ICE-Lite. Ciò significa che tutti i messaggi STUN saranno conformi alla [specifica RFC 5389](https://tools.ietf.org/html/rfc5389).

SBCs come richiesto da RFC 5389 deve ignorare gli attributi STUN che non riconoscono e continuare a elaborare i messaggi con gli attributi noti. 

Se vengono ricevuti pacchetti non validi, i pacchetti devono essere eliminati senza impatto sullo stabilimento della sessione multimediale.

## <a name="ice-lite-requirements"></a>Requisiti per ICE Lite

Questa sezione acquisisce brevemente i requisiti per ICE Lite.

### <a name="candidate-gathering"></a>Riunione candidata

Il SBC deve offrire solo un candidato che sia accessibile pubblicamente. Attualmente sono supportati solo i candidati IPV4.


#### <a name="connectivity-checks"></a>Controlli di connettività

L'implementazione di ICE Lite deve rispondere a tutti i controlli di connettività ricevuti. L'endpoint ICE Lite non deve inviare richieste di controllo della connettività. Se i controlli di connettività vengono inviati in violazione, verrà restituita l'implementazione completa, che può causare la scoperta di candidati derivati da peer imprevisti e potenzialmente causare errori di chiamata.

#### <a name="nominations"></a>Nomination

L'endpoint di implementazione completa di ICE sarà sempre l'endpoint di controllo e seguirà le nomine "regolari" per selezionare i candidati finali da usare per il flusso multimediale. L'endpoint ICE Lite può usare le nomine per concludere il percorso da usare per il supporto e per completare la creazione di chiamate.

Nota: nel caso di forking con endpoint peer che inviano risposte provvisorie di 183, il SBC deve essere pronto per rispondere ai controlli da più endpoint e anche alle nomine di più endpoint se le nomine si verificano prima di 200OK. A seconda della convergenza della macchina a stati di ghiaccio sul percorso finale e la tempistica della risposta degli utenti, le nomine possono succedere prima o dopo 200OK. Il controllo SBC deve essere in grado di gestire entrambi i casi.

#### <a name="converging-for-forking"></a>Convergenza per la diramazione

Se l'offerta proveniente da SBC si biforca a più endpoint di Team, gli endpoint di teams potrebbero rispondere con una risposta provvisoria e avviare i controlli di connettività. SBC deve essere pronto per ricevere i controlli di connettività e rispondere ai controlli di connettività da più endpoint peer. Ad esempio, l'utente di teams può essere connesso sia a un desktop che a un telefono cellulare. Entrambi i dispositivi riceveranno una notifica della chiamata in ingresso e tenteranno i controlli di connettività con SBC.

Alla fine solo uno degli endpoint risponderà alla chiamata (200OK). Quando si riceve il 200OK, il SBC può configurare il contesto appropriato per l'elaborazione dei pacchetti multimediali.

## <a name="scenarios"></a>Scenari

###  <a name="inbound-call-from-sbc"></a>Chiamata in ingresso da SBC

Per questo scenario, esistono diversi endpoint peer possibili che devono essere gestiti da SBC:

- Gli endpoint del server in genere rispondono direttamente a 200OK. Si tratta di endpoint Full ICE che in genere sono coinvolti in messaggi vocali, in coda di chiamata e in scenari di operatore automatico.

- Gli endpoint client possono inviare più risposte provvisorie con diversi tag from/to (183) seguiti da un 200OK dall'endpoint che risponde alla chiamata. Si tratta di endpoint Full ICE che rappresentano in genere i client degli utenti finali.

- Altri endpoint SBC. Si tratta di endpoint ICE Lite in genere coinvolti nello scenario di squillo simultaneo di endpoint client e di un altro numero di telefono (s).

SBC deve rispondere a tutte le richieste di controllo della connettività valide ricevute dagli endpoint Full ICE. Per RFC, gli endpoint ICE completi diventeranno il controllo degli endpoint. Gli endpoint Teams (client/server) eseguiranno le nomine "regolari" per completare i controlli di connettività. Il 200Ok finale può essere proveniente da un endpoint che ha inviato elementi multimediali iniziali o da un endpoint diverso. Quando si riceve il 200Ok, il SBC deve configurare il contesto giusto per il flusso multimediale. 

###  <a name="early-media"></a>Elementi multimediali iniziali

Se è presente un flusso multimediale iniziale, il controllo SBC deve essere bloccato sul primo endpoint che avvia il flusso multimediale; il flusso multimediale può iniziare prima che i candidati vengano nominati. SBC dovrebbe avere il supporto per l'invio di DTMF durante questa fase per abilitare gli scenari IVR/Voicemail. L'SBC deve usare il percorso con priorità più alta in cui ha ricevuto i controlli se le nomine non sono state completate.

### <a name="outbound-call-to-sbc"></a>Chiamata in uscita a SBC

Gli endpoint di teams sono il chiamante per questo scenario e saranno l'endpoint di controllo. Quando si riceve una risposta provvisoria (183) o una risposta finale (200OK), l'endpoint di teams avvierà i controlli di connettività e procederà con le nomine "regolari" per completare i controlli di connettività.

Nota: se il SBC invia una risposta provvisoria (183), il SBC deve essere pronto per ricevere le richieste di controllo della connettività e completare potenzialmente le nomine prima che il 200OK venga inviato dall'SBC. Se i controlli e/o le nomine vengono completati prima della ricezione di 200OK, i controlli e/o le nomine non verranno eseguiti dopo la ricezione di 200OK. Il SBC non deve cambiare i candidati ICE, la password e ufrag (frammento di nome utente) tra 183 e 200.

Per supportare i primi elementi multimediali, il SBC può iniziare a trasmettere il contenuto multimediale al candidato ICE peer, con la massima priorità in base ai controlli di connettività ricevuti, anche prima che le nomine vengano completate dall'endpoint teams. Il SBC dovrebbe aspettarsi che il supporto di teams su qualsiasi candidato fino al completamento delle nomine. Una volta nominato un candidato, il SBC deve reimpostare il contesto giusto per inviare e ricevere pacchetti multimediali.

## <a name="srtp-support-requirements"></a>Requisiti di supporto per SRTP

Il servizio SBC deve supportare le AES_CM_128_HMAC_SHA1_80 crittografiche di crittografia SRTP per offrire e rispondere con il formato seguente:

```console
"inline:" <key||salt> ["|" lifetime]
```

Di seguito è riportato un esempio di attributo Crypto nell'offerta SDP da SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

I parametri MKI e length non sono obbligatori.

Per altre informazioni, vedere [RFC 4568, sezione 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>Requisiti di supporto per SDES

Il dispositivo deve essere in grado di offrire SDES nel formato come descritto di seguito. I processori Microsoft Media preferiscono sempre SDES.

- Con il bypass non multimediale, anche se un client supporta solo DTLS, i processori multimediali verranno convertiti in SDES.

- Con il bypass multimediale, se un client è solo DTLS (futuro stato di Google Chrome), il routing diretto inserirà un MP nel percorso, convertendo la chiamata da un bypass multimediale a un bypass non multimediale. Tra il componente SBC e il processore multimediale di routing diretto, SDES viene sempre usato.

Attualmente, non ci sono client di team che offrono solo DTLS; Tuttavia, Google ha annunciato che ad un certo punto nel tempo smetterà di supportare SDES.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Formato per l'offerta da SBC in modalità bypass 

L'offerta deve contenere SDES e può contenere DTLS facoltativa con il formato seguente:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Formato per la risposta contenente SDES a SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Formato per l'offerta da Teams a SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Formato per SDES offerta solo per SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

