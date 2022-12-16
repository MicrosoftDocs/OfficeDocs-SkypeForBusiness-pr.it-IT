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
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocolli di routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5a05dbc6519c4f90cf0cc0d49e996467bf10230
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414724"
---
# <a name="direct-routing---sip-protocol"></a>Direct Routing - Protocollo SIP

Questo articolo descrive in che modo Direct Routing implementa il session initiation protocol (SIP). Per instradare correttamente il traffico tra un session border controller (SBC) e il proxy SIP, alcuni parametri SIP devono avere valori specifici. Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra SBC locale e il servizio proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Elaborazione della richiesta in arrivo: ricerca del tenant e dell'utente

Prima di elaborare una chiamata in arrivo o in uscita, i messaggi OPTIONS vengono scambiati tra proxy SIP e SBC. Questi messaggi OPTIONS consentono al proxy SIP di fornire le funzionalità consentite a SBC. È importante che la negoziazione OPTIONS sia riuscita (risposta 200OK), consentendo ulteriori comunicazioni tra SBC e proxy SIP per stabilire le chiamate. Le intestazioni SIP in un messaggio OPTIONS per proxy SIP sono fornite come esempio di seguito:

| Nome parametro | Esempio del valore | 
| :---------------------  |:---------------------- |
| URI richiesta | OPZIONI sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Tramite intestazione | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| intestazione Max-Forwards | Avanzamenti max:68 |
| Da intestazione | Da intestazione da: <sip:sbc1.adatum.biz:5058> |
| All'intestazione | A: <sip:sip.pstnhub.microsoft.com:5061> |
| Intestazione CSeq | CSeq: 1 INVITO | 
| Intestazione contatto | Contattare: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Le intestazioni SIP non contengono userinfo nell'URI SIP in uso. Come da [RFC 3261, sezione 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), la parte userinfo di un URI è facoltativa e può essere assente quando l'host di destinazione non ha una nozione di utenti o quando l'host stesso è la risorsa identificata. Se il segno @ è presente in un URI SIP, il campo utente NON DEVE essere vuoto.
> Tenere presente che l'URI SIPS non deve essere usato con il routing diretto perché non è supportato.
> Controllare la configurazione del controller dei confini della sessione e assicurarsi di non utilizzare le intestazioni "Sostituisci" nelle richieste SIP. Direct Routing rifiuterà le richieste SIP in cui sono definite le intestazioni Sostituisci.

In una chiamata in arrivo, il proxy SIP deve trovare il tenant a cui è destinata la chiamata e trovare l'utente specifico all'interno di questo tenant. L'amministratore del tenant potrebbe configurare numeri non DID, ad esempio +1001, in più tenant. Pertanto, è importante trovare il tenant specifico in cui eseguire la ricerca dei numeri perché i numeri non DID potrebbero essere gli stessi in più organizzazioni di Microsoft 365 o Office 365.  

Questa sezione descrive in che modo il proxy SIP trova il tenant e l'utente ed esegue l'autenticazione di SBC nella connessione in arrivo.

Di seguito è riportato un esempio del messaggio Invito SIP in una chiamata in arrivo:

| Nome parametro | Esempio del valore | 
| :---------------------  |:---------------------- |
| URI richiesta | INVITA sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Tramite intestazione | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| intestazione Max-Forwards | Avanzamenti max:68 |
| Da intestazione | Da intestazione da: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| All'intestazione | A: sip:+183338006777@sbc1.adatum.biz | 
| Intestazione CSeq | CSeq: 1 INVITO | 
| Intestazione contatto | Contattare: <sip:+17168712781@sbc1.adatum.biz:5058;transport=tls> | 

Alla ricezione dell'invito, il proxy SIP esegue la procedura seguente:

1. Controllare il certificato. Nella connessione iniziale, il servizio routing diretto accetta il nome FQDN presentato nell'intestazione Contatto e lo abbina al nome comune o al nome alternativo del soggetto del certificato presentato. Il nome SBC deve corrispondere a una delle opzioni seguenti:

   - Opzione 1. Il nome FQDN completo presentato nell'intestazione Contatto deve corrispondere al nome comune/alternativa oggetto del certificato presentato.  

   - Opzione 2. La parte relativa al dominio del nome FQDN presentata nell'intestazione Contatto, ad esempio adatum.biz del nome FQDN sbc1.adatum.biz, deve corrispondere al valore jolly in Nome comune/Nome alternativo oggetto, ad esempio *.adatum.biz.

2. Provare a trovare un tenant usando il nome FQDN completo presentato nell'intestazione Contatto.  

   Verificare se il nome FQDN dell'intestazione Contatto (sbc1.adatum.biz) è registrato come nome DNS in qualsiasi organizzazione di Microsoft 365 o Office 365. Se trovato, la ricerca dell'utente viene eseguita nel tenant in cui è registrato l'FQDN SBC come nome di dominio. Se non viene trovato, si applica il passaggio 3.   

3. Il passaggio 3 si applica solo se il passaggio 2 non è riuscito. 

   Rimuovere la parte host dall'FQDN, presentato nell'intestazione Contatto (FQDN: sbc12.adatum.biz, dopo la rimozione della parte host: adatum.biz) e verificare se questo nome è registrato come nome DNS in qualsiasi organizzazione di Microsoft 365 o Office 365. Se trovato, la ricerca utente viene eseguita in questo tenant. Se non viene trovata, la chiamata non riesce.

4. Usando il numero di telefono presentato nell'URI richiesta, eseguire la ricerca del numero inverso all'interno del tenant individuato nel passaggio 2 o 3. Associare il numero di telefono presentato a un URI SIP utente all'interno del tenant individuato nel passaggio precedente.

5. Applicare le impostazioni del trunk. Trovare i parametri impostati dall'amministratore del tenant per questo SBC.

   Microsoft non supporta la presenza di un proxy SIP di terze parti o di un server agente utente tra il proxy SIP Microsoft e l'SBC associato, che potrebbe modificare l'URI della richiesta creato dall'SBC associato.

   I requisiti per le due ricerche (passaggi 2 e 3) necessari per lo scenario in cui una scheda SBC è interconnessa con molti tenant (scenario del gestore) sono descritti più avanti in questo articolo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisiti dettagliati per l'intestazione del contatto e l'URI richiesta

#### <a name="contact-header"></a>Intestazione contatto

Per tutti i messaggi SIP in arrivo (OPZIONI, INVITA) al proxy SIP Microsoft, l'intestazione Contatto deve avere l'FQDN SBC associato nel nome host URI come indicato di seguito:

Sintassi: Contatto: <sip:phone o sip address@FQDN della> SBC;transport=tls 

Come da [RFC 3261, sezione 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), un campo di intestazione Contatto può essere presente in un messaggio OPTIONS. In Routing diretto l'intestazione del contatto è obbligatoria. Per i messaggi INVITA nel formato precedente, per i messaggi OPTIONS l'info utente può essere rimosso dall'URI SIP e solo il nome FQDN inviato nel formato seguente:

Sintassi: Contatto: <sip:FQDN della> SBC;transport=tls

Questo nome (FQDN) deve trovarsi anche nei campi Nome comune o Nome alternativo oggetto del certificato presentato. Microsoft supporta l'uso di valori jolly dei nomi nei campi Nome comune o Nome alternativo oggetto del certificato.   

Il supporto per i caratteri jolly è descritto in [RFC 2818, sezione 3.1](https://tools.ietf.org/html/rfc2818#section-3.1). Specificamente:

*"I nomi possono contenere il carattere \* jolly che viene considerato corrispondente a un singolo componente o frammento di componente del nome di dominio. Ad esempio, \*.a.com corrisponde foo.a.com ma non bar.foo.a.com. f.com\* corrisponde foo.com ma non bar.com".*

Se più valori nell'intestazione Contatto presentati in un messaggio SIP vengono inviati da SBC, viene usata solo la parte FQDN del primo valore dell'intestazione Contatto.

Come regola generale per il routing diretto, è importante che l'FQDN venga usato per popolare l'URI SIP invece di IP. Un messaggio INVITA o OPZIONI in arrivo al proxy SIP con intestazione contatto in cui nome host è rappresentato da IP e non da FQDN, la connessione verrà rifiutata con 403 Forbidden.

#### <a name="request-uri"></a>URI richiesta 

Per tutte le chiamate in arrivo, l'URI richiesta viene usato per associare il numero di telefono a un utente.   

Attualmente il numero di telefono deve contenere un segno più (+), come illustrato nell'esempio seguente. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>Da intestazione

Per tutte le chiamate in arrivo, l'intestazione Da viene usata per associare il numero di telefono del chiamante all'elenco di numeri di telefono bloccati del chiamante.

Il numero di telefono deve contenere un segno + come illustrato nell'esempio seguente.

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>Considerazioni relative alle intestazioni di contatti e Record-Route

Il proxy SIP deve calcolare l'FQDN dell'hop successivo per le nuove transazioni client in-dialog (ad esempio Bye o Re-Invite) e quando risponde a Opzioni SIP. Vengono usati Contatti o Record-Route. 

In base a [RFC 3261, sezione 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), l'intestazione Contatto è obbligatoria in qualsiasi richiesta che può generare una nuova finestra di dialogo. La Record-Route è necessaria solo se un proxy vuole rimanere nel percorso delle richieste future in una finestra di dialogo. Se un proxy SBC è in uso con [Ottimizzazione multimediale locale per il routing diretto](./direct-routing-media-optimization.md), è necessario configurare un percorso di record perché il servizio SBC proxy deve rimanere nel percorso. 

Microsoft consiglia di usare solo l'intestazione Contatto se non viene usato un SBC proxy:

- Per [RFC 3261, sezione 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route viene usato se un proxy vuole rimanere nel percorso delle richieste future in una finestra di dialogo, il che non è essenziale se non è configurato alcun proxy SBC come tutto il traffico passa tra il proxy SIP Microsoft e la SBC associata. 

- Il proxy SIP Microsoft utilizza solo l'intestazione contatto (non la route dei record) per determinare l'hop successivo quando si inviano le opzioni di ping in uscita. La configurazione di un solo parametro (Contact) anziché due (Contact and Record-Route) semplifica l'amministrazione se un proxy SBC non è in uso. 

Per calcolare l'hop successivo, il proxy SIP utilizza:

- Priorità 1. Percorso record di primo livello. Se la Record-Route di primo livello contiene il nome FQDN, il nome FQDN viene usato per creare la connessione in uscita nella finestra di dialogo.

- Priorità 2. Intestazione contatto. Se Record-Route non esiste, il proxy SIP cercherà il valore dell'intestazione Contatto per effettuare la connessione in uscita. Questa è la configurazione consigliata.

Se vengono usati sia Contatto che Record-Route, l'amministratore di SBC deve mantenere identici i valori, causando un sovraccarico amministrativo. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso del nome FQDN in Contatto o Record-Route

L'uso di un indirizzo IP non è supportato in Record-Route o contatto. L'unica opzione supportata è un FQDN, che deve corrispondere al nome comune o al nome alternativo dell'oggetto del certificato SBC (sono supportati i valori jolly nel certificato).

- Se un indirizzo IP viene presentato in Percorso di registrazione o Contatto, la verifica del certificato non riesce e la chiamata non riesce.

- Se l'FQDN non corrisponde al valore del nome alternativo Common o Subject nel certificato presentato, la chiamata non riesce. 

## <a name="inbound-call-sip-dialog-description"></a>Chiamata in ingresso: descrizione della finestra di dialogo SIP

La tabella seguente riepiloga le differenze e le analogie del flusso di chiamata tra le modalità non bypass e bypass:

| Nome parametro | Modalità non bypass | Modalità bypass
| :---------------------  |:---------------------- |:----------------|
| Candidati media in 183 e 200 messaggi provenienti da | Processori multimediali | Client | 
| Numero di 183 messaggi che SBC può ricevere | Uno per sessione | Più | 
| La chiamata può essere con risposta provvisoria (183) | Sì | Sì |
| La chiamata può essere senza risposta provvisoria (183) | Sì | Sì |

###  <a name="non-media-bypass-flow"></a>Flusso di bypass non multimediale

Un utente di Teams potrebbe avere più endpoint contemporaneamente. Ad esempio, il client Teams per Windows, il client Teams per iPhone e Teams Phone (client Teams Android). Ogni endpoint potrebbe segnalare un rest HTTP come indicato di seguito:

-   Stato della chiamata: convertito dal proxy SIP nel messaggio SIP 180. Quando si riceve il messaggio 180, SBC deve generare uno squillo locale.

-   Risposta multimediale: convertita dal proxy SIP nel messaggio 183 con candidati multimediali in SDP (Session Description Protocol). Quando si riceve il messaggio 183, la SBC prevede di connettersi ai candidati dei media ricevuti nel messaggio SDP. 

    > [!NOTE]
    > In alcuni casi la risposta media potrebbe non essere generata e il punto finale potrebbe rispondere con il messaggio "Chiamata accettata".

-   Chiamata accettata, convertita dal proxy SIP nel messaggio SIP 200 con SDP. Alla ricezione del messaggio 200, si prevede che SBC invii e riceva elementi multimediali da e verso i candidati SDP forniti.

    > [!NOTE]
    > Il routing diretto non supporta l'invito a un'offerta ritardata (Invita senza SDP).

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Più endpoint che squillano con risposta provvisoria

1.  Dopo aver ricevuto il primo invito da SBC, il proxy SIP invia il messaggio "SIP/2.0 100 Trying" e notifica a tutti gli endpoint dell'utente finale la chiamata in arrivo. 

2.  Dopo la notifica, ogni endpoint inizierà a squillare e a inviare messaggi di "Stato chiamata" al proxy SIP. Poiché un utente di Teams può avere più endpoint, il proxy SIP potrebbe ricevere più messaggi di stato della chiamata.

3.  Per ogni messaggio di Stato chiamata ricevuto dai client, il proxy SIP converte il messaggio di stato della chiamata nel messaggio SIP "Chiamata SIP/2.0 180". L'intervallo per l'invio di tali messaggi è definito dall'intervallo dei messaggi ricevuti dal controller di chiamata. Nel diagramma seguente sono generati due 180 messaggi dal proxy SIP. Questi messaggi provengono dai due endpoint di Teams dell'utente. Ogni cliente ha un ID tag univoco.  Ogni messaggio proveniente da un endpoint diverso sarà una sessione separata (il parametro "tag" nel campo "A" sarà diverso). Tuttavia, un endpoint potrebbe non generare il messaggio 180 e inviare immediatamente il messaggio 183, come illustrato nel diagramma seguente.

4.  Quando un endpoint genera un messaggio Di risposta multimediale con gli indirizzi IP dei candidati multimediali dell'endpoint, il proxy SIP converte il messaggio ricevuto in un messaggio "Stato sessione SIP 183" con SDP dal client sostituito da SDP dal processore multimediale. Nel diagramma seguente, l'endpoint di Fork 2 ha risposto alla chiamata. Se il trunk non viene bypassato, il messaggio SIP 183 viene generato una sola volta (Ring Bot o Client End Point). La 183 potrebbe essere disponibile su una biforfora esistente o crearne una nuova.

5.  Viene inviato un messaggio di accettazione chiamata con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio di accettazione chiamata viene convertito nel messaggio SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con una risposta provvisoria.](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Più endpoint squillano senza risposta provvisoria

1.  Dopo aver ricevuto il primo invito da SBC, il proxy SIP invia il messaggio "SIP/2.0 100 Trying" e notifica a tutti gli endpoint dell'utente finale la chiamata in arrivo. 

2.  Dopo la notifica, ogni endpoint inizierà a squillare e a inviare il messaggio "Stato chiamata" al proxy SIP. Poiché un utente di Teams può avere più endpoint, il proxy SIP potrebbe ricevere più messaggi di stato della chiamata.

3.  Per ogni messaggio di stato della chiamata ricevuto dai client, il proxy SIP converte il messaggio di stato della chiamata nel messaggio SIP "Sip/2.0 180 Trying".  L'intervallo per l'invio dei messaggi è definito dall'intervallo di ricezione dei messaggi dal controller di chiamata. Nell'immagine seguente ci sono due 180 messaggi generati dal proxy SIP, il che significa che l'utente ha eseguito l'accesso a tre client di Teams e ogni client invia lo stato di avanzamento della chiamata. Ogni messaggio sarà una sessione separata (il parametro "tag" nel campo "A" è diverso)

4.  Viene inviato un messaggio di accettazione chiamata con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio di accettazione chiamata viene convertito nel messaggio SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano senza risposta provvisoria.](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flusso di bypass multimediale

Gli stessi messaggi (100 Trying, 180, 183) vengono usati nello scenario di bypass multimediale. 

Lo schema seguente mostra un esempio del flusso delle chiamate di bypass. 

> [!NOTE]
> I candidati multimediali possono provenire da endpoint diversi. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con una risposta provvisoria.](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opzione Sostituisci

L'SBC deve supportare Invita con sostituisci.

## <a name="size-of-sdp-considerations"></a>Dimensioni delle considerazioni sulla SDP

L'interfaccia Direct Routing potrebbe inviare un messaggio SIP che supera i 1.500 byte.  La dimensione di SDP causa principalmente questo problema. Tuttavia, se è presente un trunk UDP dietro SBC, potrebbe rifiutare il messaggio se viene inoltrato dal proxy SIP Microsoft al trunk non modificato. Microsoft consiglia di rimuovere alcuni valori in SDP in SBC quando si invia il messaggio ai trunk UDP. Ad esempio, i codec ice candidati o inutilizzati possono essere rimossi.

## <a name="call-transfer"></a>Trasferimento di chiamata

Il routing diretto supporta due metodi per il trasferimento delle chiamate:

- Opzione 1. Processi proxy SIP Refer from the client locally and acts as a Arbitrar as described in section 7.1 of RFC 3892.

  Con questa opzione, il proxy SIP termina il trasferimento e aggiunge un nuovo invito. 


- Opzione 2. Il proxy SIP invia il riferimento a SBC e funge da transferor come descritto nella Sezione 6 di RFC 5589.

  Con questa opzione, il proxy SIP invia un riferimento a SBC e prevede che sbc gestirà completamente il trasferimento.With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.

Il proxy SIP seleziona il metodo in base alle funzionalità indicate da SBC. Se SBC indica che supporta il metodo "Refer", il proxy SIP userà l'opzione 2 per i trasferimenti di chiamata.

Di seguito è riportato un esempio di SBC che invia il messaggio che indica che il metodo Refer è supportato:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Se SBC non indica che Refer come metodo supportato, Direct Routing userà l'opzione 1 (il proxy SIP funge da arbitro). L'SBC deve anche segnalare che supporta il metodo Notify:

Esempio di SBC che indica che il metodo Refer non è supportato:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Processi proxy SIP Fare riferimento dal client localmente e agisce come arbitro

Se SBC ha indicato che il metodo Refer non è supportato, il proxy SIP funge da arbitro. 

La richiesta Refer proveniente dal client verrà terminata sul proxy SIP. La richiesta refer dal client viene visualizzata come "Trasferimento di chiamata a Davide" nel diagramma seguente.  Per ulteriori informazioni, vedere la sezione 7.1 di [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con una risposta provvisoria.](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Proxy SIP invia l'oggetto Refer to the SBC e funge da transferor

Questo è il metodo preferito per i trasferimenti di chiamata ed è obbligatorio per i dispositivi che richiedono la certificazione di bypass multimediale. Trasferimento di chiamata senza che SBC sia in grado di gestire Refer non è supportato in modalità bypass multimediale. 

Lo standard è spiegato nella Sezione 6 di RFC 5589. Le richieste d'offerta correlate sono:

- [Controllo chiamate SIP (Session Initiation Protocol) - Trasferimento](https://tools.ietf.org/html/rfc5589)

- [Intestazione SIP (Session Initiation Protocol) "Sostituisce"](https://tools.ietf.org/html/rfc3891)

- [Meccanismo "Referred-By" del Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3892)

Questa opzione presuppone che il proxy SIP agirà da trasferiscitore e invierà un messaggio di riferimento a SBC. SBC funge da trasferisce e gestisce il Refer per generare una nuova offerta per il trasferimento. Esistono due possibili casi:

- La chiamata viene trasferita a un partecipante PSTN esterno. 
- La chiamata viene trasferita da un utente di Teams a un altro utente di Teams nello stesso tenant tramite SBC. 

Se la chiamata viene trasferita da un utente di Teams a un altro tramite SBC, si prevede che la scheda SBC emette un nuovo invito (avvia una nuova finestra di dialogo) per la destinazione di trasferimento (utente di Teams) usando le informazioni ricevute nel messaggio Di riferimento. 

Per popolare internamente i campi A/Transferor per la transazione della richiesta, il proxy SIP deve comunicare queste informazioni all'interno delle intestazioni REFER-TO/REFERRED-BY. 

Il proxy SIP formerà l'URI REFER-TO come URI SIP costituito da un FQDN proxy SIP nel nome host ed uno dei seguenti:

- Un numero di telefono E.164 nella parte nome utente dell'URI nel caso in cui la destinazione del trasferimento sia un numero di telefono o

- Parametri x-m e x-t che codificano rispettivamente la MRI di destinazione completa e l'ID tenant 

L'intestazione REFERRED-BY è un URI SIP con mri transferor codificati al suo interno, nonché l'ID tenant del trasferimento e altri parametri del contesto di trasferimento, come illustrato nella tabella seguente:

| Parametro | Valore | Descrizione |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | MrI completo di destinazione trasferimento/trasferimento come popolato da CC |
| x-t | ID tenant | X-t ID tenant ID tenant facoltativo popolato da CC |
| x-ti | ID di correlazione del transferor | ID di correlazione della chiamata al cedente |
| x-tt | URI trasferimento chiamata di destinazione | URI di sostituzione delle chiamate codificate |

In questo caso, le dimensioni dell'intestazione di riferimento possono essere fino a 400 simboli. SBC deve supportare la gestione dei messaggi di riferimento con dimensioni fino a 400 simboli.

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con una risposta provvisoria.](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Timer sessione

Il proxy SIP supporta (offre sempre) il timer di sessione per le chiamate non ignorate, ma non lo offre nelle chiamate di bypass. L'uso del timer di sessione da parte di SBC non è obbligatorio.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso del parametro Request-URI user=phone

Il proxy SIP analizza l'URI Request e se il parametro user=phone è presente, il servizio gestirà l'URI Request come numero di telefono, corrispondente al numero a un utente. Se il parametro non è presente, il proxy SIP applica l'euristica per determinare il tipo di utente Request-URI (numero di telefono o indirizzo SIP).

Microsoft consiglia di applicare sempre il parametro user=phone per semplificare il processo di configurazione delle chiamate.

## <a name="history-info-header"></a>intestazione History-Info

L'intestazione History-Info viene utilizzata per ridestinare le richieste SIP e "fornire uno o più meccanismi standard per l'acquisizione delle informazioni della cronologia delle richieste per abilitare un'ampia varietà di servizi per le reti e gli utenti finali". Per ulteriori informazioni, vedere [RFC 4244 - Sezione 1.1](http://www.ietf.org/rfc/rfc4244.txt). Per Sistema telefonico Microsoft, questa intestazione viene utilizzata negli scenari di inoltro di chiamata e di simuling.  

Se si invia, il History-Info è abilitato come indicato di seguito:

- Il proxy SIP inserisce un parametro contenente il numero di telefono associato nelle singole voci History-Info che comprendono l'intestazione History-Info inviata al controller PSTN.  Usando solo le voci che contengono il parametro del numero di telefono, il controller PSTN ricostruirà una nuova intestazione History-Info e la passerà al provider del trunk SIP tramite proxy SIP.

- History-Info intestazione verrà aggiunta per casi di squillo simultaneo e inoltro di chiamata.

- History-Info intestazione non verrà aggiunta per i casi di trasferimento chiamate.

- Una singola voce della cronologia nell'intestazione History-Info ricostruita avrà il parametro relativo al numero di telefono fornito combinato con l'FQDN routing diretto (sip.pstnhub.microsoft.com) impostato come parte host dell'URI. verrà aggiunto un parametro di 'user=phone' come parte dell'URI SIP.  Tutti gli altri parametri associati all'intestazione History-Info originale, ad eccezione dei parametri di contesto del telefono, verranno passati nell'intestazione History-Info ri-costruita.  

  > [!NOTE]
  > Le voci private (determinate dai meccanismi definiti nella sezione 3.3 della RFC 4244) verranno inoltrate così come sono perché il provider di trunk SIP è un peer attendibile.

- I History-Info in ingresso vengono ignorati.

Di seguito è riportato il formato dell'intestazione History-info inviata dal proxy SIP:

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Se la chiamata è stata reindirizzata più volte, le informazioni su ogni reindirizzamento vengono incluse con il motivo appropriato in ordine cronologico.


Esempio di intestazione:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Il History-Info è protetto da un meccanismo TLS obbligatorio. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Connessione SBC al meccanismo di routing diretto e failover

Vedere la sezione Meccanismo di failover per la segnalazione SIP in [Pianificare il routing diretto](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Retry-After

Se un data center routing diretto è occupato, il servizio può inviare un messaggio di Retry-After con un intervallo di un secondo al servizio SBC. Quando la scheda SBC riceve un messaggio 503 con un'intestazione di Retry-After in risposta a un invito, l'SBC deve terminare la connessione e provare il successivo data center Microsoft disponibile.

## <a name="handling-retries-603-response"></a>Gestione di tentativi (risposta 603)
Se un utente finale osserva diverse chiamate perse per una chiamata dopo aver rifiutato la chiamata in arrivo, significa che il meccanismo di ripetizione dei tentativi del provider SBC o PSTN non è configurato correttamente. Il SBC deve essere riconfigurato per interrompere gli sforzi di ripetizione sulla risposta 603.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Riavvio ICE: chiamata di bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale

SBC deve supportare i riavvii ICE come descritto in [RFC 5245, sezione 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

Il riavvio in Direct Routing viene implementato in base ai seguenti paragrafi della RFC:

*Per riavviare ICE, un agente DEVE cambiare sia il ghiaccio-pwd che il ice-ufrag per il flusso multimediale in un'offerta.  Si noti che è consentito utilizzare un attributo a livello di sessione in un'offerta, ma di fornire lo stesso ice-pwd o ice-ufrag attributo di livello media in una successiva offerta.  Non si tratta di una modifica della password, ma solo di una modifica della rappresentazione e non comporta un riavvio ICE.*

*Un agente imposta il resto dei campi nella SDP per questo flusso multimediale come in un'offerta iniziale di questo flusso multimediale (vedere sezione 4.3).  Di conseguenza, l'insieme di candidati MAY include alcuni, nessuno o tutti i candidati precedenti per tale flusso e MAY include un set di candidati completamente nuovo, come descritto nella sezione 4.1.1.*

Se la chiamata è stata inizialmente stabilita con un bypass multimediale e la chiamata viene trasferita a un client Skype for Business, l'instradamento diretto deve inserire un processore multimediale, perché non è possibile usare il routing diretto con un client Skype for Business con bypass multimediale. Direct Routing avvia il processo di riavvio ICE modificando il ice-pwd e ice-ufrag e offrendo nuovi candidati media in un rinvio.
