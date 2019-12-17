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
description: Protocolli di routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ab2203544e1d0e4d8679a4ad8107c2048e5b3b8
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065676"
---
# <a name="direct-routing---sip-protocol"></a>Routing diretto-protocollo SIP

Questo articolo descrive il modo in cui il routing diretto implementa il SIP (Session Initiation Protocol). Per indirizzare correttamente il traffico tra un SBC (Session Border Controller) e il proxy SIP, alcuni parametri SIP devono avere valori specifici. Questo articolo è destinato agli amministratori vocali responsabili della configurazione della connessione tra l'SBC locale e il servizio proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Elaborazione della richiesta in arrivo: individuazione del tenant e dell'utente

In una chiamata in arrivo, il proxy SIP deve trovare il tenant a cui è destinata la chiamata e trovare l'utente specifico all'interno del tenant. L'amministratore del tenant può configurare i numeri non DID, ad esempio + 1001, in più tenant. Di conseguenza, è importante trovare il tenant specifico in cui eseguire la ricerca di numeri perché i numeri non DID potrebbero essere uguali in più tenant di Office 365.  

Questa sezione descrive il modo in cui il proxy SIP trova il tenant e l'utente ed esegue l'autenticazione di SBC sulla connessione in ingresso.

Di seguito è riportato un esempio del messaggio SIP INVITE in una chiamata in arrivo:

| Nome parametro | Esempio di valore | 
| :---------------------  |:---------------------- |
| Request-URI | INVITARE sip:+18338006777@sip.pstnhub.microsoft.com SIP/2,0 |
| Intestazione tramite | Via: SIP/2.0/TLS sbc1. adatum. BIZ: 5058; alias; Branch = z9hG4bKac2121518978 | 
| Intestazione Max-Forwards | Max-inoltri: 68 |
| Intestazione da | Da intestazione da: <SIP: 7168712781@sbc1. adatum. biz; Transport = UDP; Tag = 1c747237679 |
| Intestazione | A: sip:+183338006777@sbc1.adatum.biz | 
| Intestazione CSeq | CSeq: 1 invito | 
| Intestazione contatto | Contatto: <SIP: 68712781@sbc1. adatum. biz; Transport = TLS> | 

Alla ricezione dell'invito, il proxy SIP esegue i passaggi seguenti:

1. Controllare il certificato. Nella connessione iniziale il servizio di routing diretto accetta il nome FQDN presentato nell'intestazione del contatto e lo confronta con il nome comune o l'oggetto alternativo del certificato presentato. Il nome SBC deve corrispondere a una delle opzioni seguenti:

   - Opzione 1. Il nome FQDN completo presentato nell'intestazione del contatto deve corrispondere al nome comune/oggetto alternativo del certificato presentato.  

   - Opzione 2. La parte del dominio del nome FQDN presentato nell'intestazione del contatto (ad esempio adatum.biz del nome FQDN sbc1.adatum.biz) deve corrispondere al valore jolly in nome comune/oggetto alternativo (ad esempio *. adatum.biz).

2. Provare a trovare un tenant usando il nome FQDN completo presentato nell'intestazione del contatto.  

   Verificare che il nome FQDN dell'intestazione del contatto (sbc1.adatum.biz) sia registrato come nome DNS in qualsiasi tenant di Office 365. Se trovata, la ricerca dell'utente viene eseguita nel tenant che ha il nome di dominio completo SBC registrato come Domain Name. Se non viene trovato, il passaggio 3 si applica.   

3. Il passaggio 3 si applica solo se il passaggio 2 non è riuscito. 

   Rimuovere la porzione host dall'FQDN, presentata nell'intestazione del contatto (FQDN: sbc12.adatum.biz, dopo aver rimosso la porzione host: adatum.biz) e verificare se questo nome è registrato come nome DNS in un tenant di Office 365. Se trovata, la ricerca dell'utente viene eseguita in questo tenant. Se non viene trovata, la chiamata non riesce.

4. Usando il numero di telefono presentato nell'URI della richiesta, eseguire la ricerca in numero inverso all'interno del tenant disponibile nel passaggio 2 o 3. Corrispondere al numero di telefono presentato a un URI SIP dell'utente all'interno del tenant trovato nel passaggio precedente.

5. Applicare le impostazioni trunk. Individuare i parametri impostati dall'amministratore del tenant per questo SBC.

   Microsoft non supporta l'uso di un proxy SIP di terze parti o di un server agente utente tra il proxy SIP Microsoft e il SBC associato, che può modificare l'URI della richiesta creato dal SBC associato.

   I requisiti per le due ricerche (passaggi 2 e 3) necessari per lo scenario in cui un SBC è collegato a molti tenant (scenario di Carrier) sono descritti più avanti in questo articolo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisiti dettagliati per l'intestazione del contatto e la richiesta-URI

#### <a name="contact-header"></a>Intestazione contatto

Per tutte le chiamate in arrivo al proxy SIP Microsoft, l'intestazione del contatto deve avere il nome di dominio completo SBC associato nel nome host dell'URI come indicato di seguito:

Sintassi: contatto: <SIP: telefono o SIP address@FQDN del SBC; Transport = TLS> 

Questo nome deve essere anche il nome comune o i campi nome alternativo oggetto del certificato presentato. Microsoft supporta l'uso di valori jolly dei nomi nei campi nome comune o nome alternativo oggetto del certificato.   

Il supporto per i caratteri jolly è descritto in [RFC 2818, sezione 3,1](https://tools.ietf.org/html/rfc2818#section-3.1). Specificamente

*"I nomi possono contenere il carattere \* jolly che si ritiene corrisponda a qualsiasi singolo componente del nome di dominio o frammento di componente. Ad esempio, \*. a.com corrisponde a foo.a.com ma non a bar.foo.a.com. f\*. com corrisponde a foo.com ma non a bar.com. "*

Se più di un valore nell'intestazione del contatto presentato in un messaggio SIP viene inviato dall'SBC, viene usata solo la parte FQDN del primo valore dell'intestazione del contatto.

#### <a name="request-uri"></a>Request-URI 

Per tutte le chiamate in arrivo, l'URI della richiesta viene usato per corrispondere al numero di telefono a un utente.   

Attualmente il numero di telefono deve contenere un segno più (+), come illustrato nell'esempio seguente. 

```
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Considerazioni sulle intestazioni di contatti e record-route

Il proxy SIP deve calcolare il nome di dominio completo dell'hop successivo per le nuove transazioni client nella finestra di dialogo, ad esempio bye o re-invite, e quando si risponde alle opzioni SIP. Vengono usati contatti o record-route. 

In base alla RFC 3261, l'intestazione del contatto è obbligatoria in qualsiasi richiesta che può comportare una nuova finestra di dialogo. La route di record è necessaria solo se un proxy vuole rimanere sul percorso delle richieste future in una finestra di dialogo. 

Microsoft consiglia di usare solo l'intestazione del contatto per i motivi seguenti:

- Per RFC 3261, record-route viene usato se un proxy vuole rimanere sul percorso delle richieste future in una finestra di dialogo, che non è essenziale perché tutto il traffico passa tra il proxy SIP Microsoft e il SBC associato. Non c'è bisogno di un server proxy intermedio tra SBC e proxy SIP Microsoft.

- Il proxy SIP Microsoft usa solo l'intestazione del contatto (non il record-route) per determinare l'hop successivo quando si inviano le opzioni di ping in uscita. La configurazione di un solo parametro (contatto) invece di due (contatto e record-route) semplifica l'amministrazione.

Per calcolare l'hop successivo, il proxy SIP USA:

- Priorità 1. Route record di primo livello. Se la route di record di primo livello contiene il nome FQDN o l'indirizzo IP, il nome FQDN o IP viene usato per creare la connessione in uscita nella finestra di dialogo.

- Priorità 2. Intestazione contatto. Se record-route non esiste, il proxy SIP cercherà il valore dell'intestazione del contatto per effettuare la connessione in uscita. Questa è la configurazione consigliata.

Se si usano sia il contatto che la route di record, l'amministratore SBC deve mantenerne i valori identici, causando il sovraccarico amministrativo. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso del nome FQDN in contatti o record-route

L'utilizzo di un indirizzo IP non è supportato in record-route o Contact. L'unica opzione supportata è un FQDN, che deve corrispondere al nome comune o al nome alternativo dell'oggetto del certificato SBC (i valori jolly nel certificato sono supportati).

- Se un indirizzo IP viene presentato in una route di record o in un contatto, il controllo del certificato non riesce e la chiamata non riesce.

- Se l'FQDN non corrisponde al valore del nome comune o dell'oggetto alternativo nel certificato presentato, la chiamata non riesce. 

## <a name="inbound-call-sip-dialog-description"></a>Chiamata in ingresso: Descrizione della finestra di dialogo SIP

La tabella seguente riepiloga le differenze di flusso delle chiamate e le analogie tra le modalità di esclusione e non-bypass:

| Nome parametro | Modalità non di bypass | Modalità bypass
| :---------------------  |:---------------------- |:----------------|
| Candidati multimediali nei messaggi di 183 e 200 provenienti da | Processori multimediali | Client | 
| Numero di messaggi di 183 che SBC può ricevere | Uno per sessione | Più | 
| La chiamata può essere con la risposta provvisoria (183) | Sì | Sì |
| La chiamata può essere senza risposta provvisoria (183) | Sì | Sì |

###  <a name="non-media-bypass-flow"></a>Flusso di bypass non multimediale

Un utente di teams potrebbe avere più endpoint contemporaneamente. Ad esempio, teams for Windows client, teams for iPhone client e teams Phone (teams Android client). Ogni endpoint può segnalare un REST HTTP come segue:

-   Avanzamento chiamata: convertito dal proxy SIP nel messaggio SIP 180. Quando si riceve il messaggio 180, il SBC deve generare la chiamata locale.

-   Risposta multimediale: convertita dal proxy SIP nel messaggio 183 con i candidati multimediali nel protocollo SDP (Session Description Protocol). Quando si riceve il messaggio 183, il SBC si aspetta di connettersi ai candidati multimediali ricevuti nel messaggio SDP. Tieni presente che in alcuni casi la risposta multimediale potrebbe non essere generata e il punto finale potrebbe rispondere con il messaggio "chiamata accettata".

-   Chiamata accettata: convertita dal proxy SIP in SIP Message 200 con SDP. Quando si riceve il messaggio 200, il SBC dovrebbe inviare e ricevere elementi multimediali da e verso i candidati SDP forniti.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Più endpoint che squillano con la risposta provvisoria

1.  Quando si riceve il primo invito da SBC, il proxy SIP invia il messaggio "SIP SIP/2.0 100 provando" e informa tutti gli endpoint dell'utente finale sulla chiamata in arrivo. 

2.  Dopo la notifica, ogni endpoint inizierà a squillare e a inviare messaggi di "avanzamento chiamata" al proxy SIP. Dato che un utente di teams può avere più punti finali, il proxy SIP può ricevere più messaggi di stato di avanzamento delle chiamate.

3.  Per ogni messaggio di stato delle chiamate ricevuto dai client, il proxy SIP converte il messaggio di stato della chiamata nel messaggio SIP "SIP SIP/2.0 180 provando". L'intervallo per l'invio di tali messaggi è definito dall'intervallo di messaggi ricevuti dal controller di chiamata. Nel diagramma seguente sono presenti 2 180 messaggi generati dal proxy SIP. Questi messaggi provengono dai due endpoint di Teams dell'utente. I client hanno ognuno un ID di tag univoco.  Ogni messaggio proveniente da un endpoint diverso sarà una sessione separata (il parametro "tag" nel campo "a" sarà diverso). Ma un endpoint potrebbe non generare il messaggio 180 e inviare subito il messaggio 183, come illustrato nel diagramma seguente.

4.  Dopo che un endpoint genera un messaggio di risposta multimediale con gli indirizzi IP dei candidati multimediali dell'endpoint, il proxy SIP converte il messaggio ricevuto in un messaggio di "avanzamento sessione SIP 183" con lo SDP dal client sostituito da SDP dal processore multimediale. Nel diagramma seguente l'endpoint da fork 2 ha risposto alla chiamata. Se il trunk non è bypassato, il messaggio SIP di 183 viene generato una sola volta (Ring bot o client end point). Il 183 potrebbe essere presente in un fork esistente o crearne uno nuovo.

5.  Viene inviato un messaggio di accettazione delle chiamate con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio di accettazione delle chiamate viene convertito in SIP Message 200. 

![Diagramma che Mostra più endpoint che squillano con la risposta provvisoria](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Più endpoint che squillano senza risposta provvisoria

1.  Quando si riceve il primo invito da SBC, il proxy SIP invia il messaggio "SIP SIP/2.0 100 provando" e informa tutti gli endpoint dell'utente finale sulla chiamata in arrivo. 

2.  Dopo la notifica, ogni endpoint inizierà a squillare e a inviare il messaggio "avanzamento chiamata" al proxy SIP. Dato che un utente di teams può avere più punti finali, il proxy SIP può ricevere più messaggi di stato di avanzamento delle chiamate.

3.  Per ogni messaggio di stato delle chiamate ricevuto dai client, il proxy SIP converte il messaggio di stato della chiamata nel messaggio SIP "SIP SIP/2.0 180 provando".  L'intervallo per l'invio dei messaggi viene definito dall'intervallo di ricezione dei messaggi dal controller di chiamata. Nell'immagine seguente sono presenti 2 180 messaggi generati dal proxy SIP, che significa che l'utente ha eseguito l'accesso a tre client di team e ogni client invia lo stato di avanzamento delle chiamate. Ogni messaggio sarà una sessione separata (il parametro "tag" nel campo "a" è diverso)

4.  Viene inviato un messaggio di accettazione delle chiamate con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio di accettazione delle chiamate viene convertito in SIP Message 200. 

![Diagramma che Mostra più endpoint che squillano senza risposta provvisoria](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flusso di bypass multimediale

Gli stessi messaggi (100 che provano, 180, 183) vengono usati nello scenario di bypass multimediale. 

Lo schema seguente mostra un esempio del flusso di chiamata di bypass. Tieni presente che i candidati multimediali possono provenire da endpoint diversi. 

![Diagramma che Mostra più endpoint che squillano con la risposta provvisoria](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opzione sostituisce

Il servizio SBC deve supportare l'invito con Sostituisci.

## <a name="size-of-sdp-considerations"></a>Dimensioni delle considerazioni SDP

L'interfaccia di routing diretto può inviare un messaggio SIP che supera i 1.500 byte.  La dimensione di SDP causa principalmente questo. Tuttavia, se c'è un tronco UDP dietro il SBC, potrebbe rifiutare il messaggio se viene inoltrato dal proxy SIP Microsoft al trunk invariato. Microsoft consiglia di stripping alcuni valori in SDP sul SBC quando si invia il messaggio ai trunk UDP. Ad esempio, i candidati ICE o i codec inutilizzati possono essere rimossi.

## <a name="call-transfer"></a>Trasferimento delle chiamate

Il routing diretto supporta due metodi per il trasferimento delle chiamate:

- Opzione 1. I processi proxy SIP si riferiscono al client localmente e agiscono come arbitro come descritto nella sezione 7,1 della RFC 3892.

  Con questa opzione, il proxy SIP termina il trasferimento e aggiunge un nuovo invito. 


- Opzione 2. Proxy SIP invia il riferimento a SBC e funge da cedente come descritto nella sezione 6 della RFC 5589.

  Con questa opzione, il proxy SIP invia un riferimento a SBC e prevede che SBC gestisca completamente il trasferimento.

Il proxy SIP seleziona il metodo in base alle funzionalità segnalate da SBC. Se SBC indica che supporta il metodo "refer", il proxy SIP userà l'opzione 2 per i trasferimenti di chiamata.

Di seguito è riportato un esempio di un SBC che invia il messaggio che indica che il metodo refer è supportato:

```
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Se il SBC non indica che si riferisce a un metodo supportato, il routing diretto userà l'opzione 1 (il proxy SIP funge da arbitro). SBC deve inoltre segnalare che supporta il metodo Notify:

Esempio di SBC che indica che il metodo refer non è supportato:

```
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>I processi proxy SIP si riferiscono al client localmente e agiscono come arbitro

Se il SBC indica che il metodo refer non è supportato, il proxy SIP funge da arbitro. 

La richiesta di riferimento che deriva dal client verrà terminata nel proxy SIP. La richiesta di riferimento del client viene visualizzata come "trasferimento di chiamata a Dave" nel diagramma seguente.  Per altre informazioni, vedere la sezione 7,1 della [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

![Diagramma che Mostra più endpoint che squillano con la risposta provvisoria](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Proxy SIP invia il riferimento a SBC e funge da cedente

Questo è il metodo preferito per i trasferimenti delle chiamate ed è obbligatorio per i dispositivi che cercano la certificazione per il bypass multimediale. Il trasferimento delle chiamate senza che il SBC sia in grado di gestire il riferimento non è supportato in modalità bypass multimediale. 

Lo standard è spiegato nella sezione 6 della RFC 5589. Le RFC correlate sono:

- [Controllo delle chiamate SIP (Session Initiation Protocol)-trasferimento](https://tools.ietf.org/html/rfc5589)

- [Intestazione SIP (Session Initiation Protocol) "sostituisce"](https://tools.ietf.org/html/rfc3891)

- [Meccanismo SIP (Session Initiation Protocol) "a cui si fa riferimento"](https://tools.ietf.org/html/rfc3892)

Questa opzione presuppone che il proxy SIP funga da cedente e invii un messaggio di riferimento a SBC. Il SBC funge da cessionario e gestisce il riferimento per generare una nuova offerta per il trasferimento. Esistono due casi possibili:

- La chiamata viene trasferita a un partecipante esterno PSTN. 
- La chiamata viene trasferita da un utente di Teams a un altro utente di teams nello stesso tenant tramite SBC. 

Se la chiamata viene trasferita da un utente di Teams a un'altra tramite SBC, è previsto che il servizio SBC rilascerà un nuovo invito (avviare una nuova finestra di dialogo) per la destinazione di trasferimento (l'utente Teams) usando le informazioni ricevute nel messaggio di riferimento. 

Per popolare i campi to/transfert per la transazione della richiesta internamente, il proxy SIP deve trasmettere queste informazioni all'interno delle intestazioni REFER-TO/denominate. 

Il proxy SIP formerà il REFER-TO come URI SIP costituito da un nome di dominio completo del proxy SIP nel nome host e uno dei seguenti:

- Numero di telefono E. 164 nella parte nome utente dell'URI nel caso in cui la destinazione di trasferimento sia un numero di telefono oppure

- parametri x-m e x-t che codificano rispettivamente per la destinazione del trasferimento completo MRI e ID tenant 

L'intestazione di riferimento è un URI SIP con il transfert MRI codificato in esso, nonché l'ID tenant del cedente e altri parametri di contesto di trasferimento, come illustrato nella tabella seguente:

| Parametro | Valore | Descrizione |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | MRI completo della destinazione transfert/Transfer come popolato da CC |
| x-t | ID tenant | ID tenant dell'ID tenant x-t opzionale compilato da CC |
| x-ti | ID correlazione del cedente | ID di correlazione della chiamata al cedente |
| x-tt | URI di chiamata di destinazione del trasferimento | URI di sostituzione delle chiamate codificate |

In questo caso, la dimensione dell'intestazione Refer può contenere fino a 400 simboli. SBC deve supportare la gestione dei messaggi di riferimento con dimensioni fino a 400 simboli.

![Diagramma che Mostra più endpoint che squillano con la risposta provvisoria](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Timer sessione

Il proxy SIP supporta (sempre offre) il timer di sessione sulle chiamate non di bypass, ma non lo offre sulle chiamate di bypass. L'uso del timer di sessione da SBC non è obbligatorio.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso di request-parametro URI user = Phone

Il proxy SIP analizza l'URI della richiesta e se il parametro user = Phone è presente, il servizio gestirà l'URI della richiesta come numero di telefono, in modo che corrisponda al numero a un utente. Se il parametro non è presente, il proxy SIP applica le euristiche per determinare il tipo di utente dell'URI della richiesta (numero di telefono o indirizzo SIP).

Microsof consiglia di applicare sempre il parametro user = Phone per semplificare il processo di configurazione delle chiamate.

## <a name="history-info-header"></a>Intestazione cronologia-info

L'intestazione History-info viene usata per la ridestinazione delle richieste SIP e "offre un meccanismo standard per l'acquisizione delle informazioni sulla cronologia delle richieste per consentire un'ampia varietà di servizi per le reti e gli utenti finali". Per altre informazioni, vedere [RFC 4244-Section 1,1](http://www.ietf.org/rfc/rfc4244.txt). Per il sistema telefonico Microsoft, questa intestazione viene usata in Simulring e in scenari di inoltro di chiamata.  

Se si invia l'invio, le informazioni sulla cronologia sono abilitate nel modo seguente:

- Il proxy SIP inserisce un parametro contenente il numero di telefono associato nella cronologia singole-voci di info che includono l'intestazione History-info inviata al controller PSTN.  Usando solo le voci con il parametro numero di telefono, il controller PSTN ricostruirà una nuova intestazione di informazioni sulla cronologia e la passerà al provider trunk SIP tramite proxy SIP.

- L'intestazione History-info verrà aggiunta per i casi di inoltro di chiamata e squillo simultanei.

- L'intestazione History-info non verrà aggiunta per i casi di trasferimento delle chiamate.

- Una singola voce della cronologia nell'intestazione ricostruita della cronologia-info avrà il parametro numero di telefono fornito in combinazione con il nome FQDN (sip.pstnhub.microsoft.com) impostato come parte ospitante dell'URI. un parametro di ' user = phone ' verrà aggiunto come parte dell'URI SIP.  Tutti gli altri parametri associati all'intestazione cronologia-info originale, fatta eccezione per i parametri di contesto per i telefoni, verranno passati nell'intestazione cronologia-informazioni ricostruita.  Tieni presente che le voci private (come determinato dai meccanismi definiti nella sezione 3,3 della RFC 4244) verranno inoltrate come avviene perché il provider trunk SIP è un peer attendibile.

- La cronologia in ingresso-info viene ignorata.

Di seguito è riportato il formato dell'intestazione History-info inviata dal proxy SIP:

```
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

Se la chiamata è stata reindirizzata più volte, le informazioni su ogni redirect vengono incluse con il motivo appropriato in ordine cronologico.


Esempio di intestazione:

```
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

Le informazioni sulla cronologia sono protette da un meccanismo TLS obbligatorio. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Connessione SBC per il routing diretto e il meccanismo di failover

Vedere il meccanismo di failover delle sezioni per la segnalazione SIP in [piano per il routing diretto](direct-routing-plan.md#failover-mechanism-for-sip-signaling).

## <a name="retry-after"></a>Retry-After

Se un centro dati di routing diretto è occupato, il servizio può inviare un messaggio di riprova con un intervallo di un secondo all'SBC. Quando il SBC riceve un messaggio di 503 con un'intestazione Retry-After in risposta a un invito, SBC deve terminare la connessione e provare il nuovo Data Center Microsoft disponibile. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE Restart: la chiamata di bypass multimediale viene trasferita a un endpoint che non supporta il bypass multimediale

L'SBC deve supportare il riavvio del ghiaccio come descritto in [RFC 5245, sezione 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

Il riavvio in routing diretto viene implementato in base ai paragrafi seguenti della RFC:

*Per riavviare ICE, un agente deve cambiare sia l'Ice-pwd che il Ice-ufrag per il flusso multimediale in un'offerta.  Tieni presente che è lecito usare un attributo a livello di sessione in un'offerta, ma per fornire lo stesso Ice-pwd o Ice-ufrag come attributo a livello di media in un'offerta successiva.  Non si tratta di una modifica della password, bensì di una modifica nella relativa rappresentazione e non provoca un riavvio di ghiaccio.*

*Un agente imposta il resto dei campi nel SDP per questo flusso multimediale come in un'offerta iniziale di questo flusso multimediale (vedere la sezione 4,3).  Di conseguenza, il set di candidati può includere alcuni, nessuno o tutti i candidati precedenti per tale flusso e può includere un set di candidati completamente nuovo, come descritto nella sezione 4.1.1.*

Se la chiamata è stata inizialmente stabilita con il bypass multimediale e la chiamata viene trasferita a un client Skype for business, il routing diretto deve inserire un processore multimediale, perché il routing diretto non può essere usato con un client Skype for business con il bypass multimediale. Il routing diretto avvia il processo di riavvio del ghiaccio modificando i file Ice-PWD e Ice-ufrag e offrendo nuovi candidati multimediali in un nuovo invito. 


