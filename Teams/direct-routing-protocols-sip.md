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
ms.openlocfilehash: 549ee30fa7327f1b9959cb2153d0846af61ba858
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774035"
---
# <a name="direct-routing---sip-protocol"></a>Routing diretto - Protocollo SIP

Questo articolo descrive in che modo Il routing diretto implementa il protocollo SIP (Session Initiation Protocol). Per instradare correttamente il traffico tra un session border controller (SBC) e il proxy SIP, alcuni parametri SIP devono avere valori specifici. Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il servizio SBC locale e il servizio proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Elaborazione della richiesta in arrivo: ricerca del tenant e dell'utente

Prima che sia possibile elaborare una chiamata in arrivo o in uscita, i messaggi OPTIONS vengono s scambiati tra il proxy SIP e il servizio SBC. Questi messaggi OPTIONS consentono al proxy SIP di fornire le funzionalità consentite a SBC. È importante che la negoziazione OPTIONS sia riuscita (risposta 200OK), consentendo un'ulteriore comunicazione tra SBC e proxy SIP per stabilire le chiamate. Le intestazioni SIP in un messaggio OPTIONS al proxy SIP sono fornite come esempio di seguito:

| Nome parametro | Esempio del valore | 
| :---------------------  |:---------------------- |
| Request-URI | OPZIONI sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Tramite intestazione | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards intestazione | Max-Forwards:68 |
| Da intestazione | Da intestazione da: <sip:sbc1.adatum.biz:5058> |
| A intestazione | A: <sip:sip.pstnhub.microsoft.com:5061> |
| Intestazione CSeq | CSeq: 1 INVITA | 
| Intestazione contatto | Contatto: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Le intestazioni SIP non contengono userinfo nell'URI SIP in uso. Come da [RFC 3261, sezione 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), la parte userinfo di un URI è facoltativa e può essere assente quando l'host di destinazione non ha una nozione di utenti o quando l'hosst stesso è la risorsa identificata. Se il segno @ è presente in un URI SIP, il campo utente NON DEVE essere vuoto.
> Tenere presente che l'URI SIPS non deve essere usato con il routing diretto perché non è supportato.
> Controllare la configurazione di Session Border Controller e assicurarsi di non usare le intestazioni "Replaces" nelle richieste SIP. Il routing diretto rifiuta le richieste SIP con intestazioni Replaces definite.

In una chiamata in arrivo, il proxy SIP deve trovare il tenant a cui è destinata la chiamata e trovare l'utente specifico all'interno del tenant. L'amministratore del tenant potrebbe configurare numeri non DID, ad esempio +1001, in più tenant. Pertanto, è importante trovare il tenant specifico in cui eseguire la ricerca di numeri perché i numeri non DID potrebbero essere uguali in più organizzazioni Microsoft 365 o Office 365.  

Questa sezione descrive come il proxy SIP trova il tenant e l'utente ed esegue l'autenticazione del servizio SBC sulla connessione in ingresso.

Di seguito è riportato un esempio del messaggio Invito SIP in una chiamata in arrivo:

| Nome parametro | Esempio del valore | 
| :---------------------  |:---------------------- |
| Request-URI | INVITA sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Tramite intestazione | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards intestazione | Max-Forwards:68 |
| Da intestazione | Da intestazione da: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| A intestazione | A: sip:+183338006777@sbc1.adatum.biz | 
| Intestazione CSeq | CSeq: 1 INVITA | 
| Intestazione contatto | Contatto: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Alla ricezione dell'invito, il proxy SIP esegue la procedura seguente:

1. Controllare il certificato. Nella connessione iniziale, il servizio Routing diretto prende il nome FQDN presentato nell'intestazione Contatto e lo trova in corrispondenza del nome comune o del nome alternativo del soggetto del certificato presentato. Il nome SBC deve corrispondere a una delle opzioni seguenti:

   - Opzione 1. Il nome FQDN completo presentato nell'intestazione Contatto deve corrispondere al nome comune/soggetto alternativo del certificato presentato.  

   - Opzione 2. La parte relativa al dominio del nome FQDN presentata nell'intestazione Contatto (ad esempio adatum.biz del nome FQDN sbc1.adatum.biz) deve corrispondere al valore jolly in Nome comune/Nome alternativo oggetto , ad esempio *.adatum.biz.

2. Provare a trovare un tenant usando il nome FQDN completo presentato nell'intestazione Contatto.  

   Verificare se il nome FQDN dell'intestazione contatto (sbc1.adatum.biz) è registrato come nome DNS in qualsiasi Microsoft 365 o Office 365 organizzazione. Se viene trovato, la ricerca dell'utente viene eseguita nel tenant con l'FQDN SBC registrato come nome di dominio. Se non viene trovato, si applica il passaggio 3.   

3. Il passaggio 3 si applica solo se il passaggio 2 non è riuscito. 

   Rimuovere la parte host dall'FQDN, presentata nell'intestazione contatto (FQDN: sbc12.adatum.biz, dopo aver rimosso la parte host: adatum.biz) e verificare se questo nome è registrato come nome DNS in qualsiasi organizzazione Microsoft 365 o Office 365. Se viene trovato, la ricerca utente viene eseguita in questo tenant. Se non viene trovato, la chiamata non riesce.

4. Usando il numero di telefono presentato nel Request-URI, eseguire la ricerca inversa del numero all'interno del tenant individuato nel passaggio 2 o 3. Abbinare il numero di telefono presentato a un URI SIP utente all'interno del tenant trovato nel passaggio precedente.

5. Applicare le impostazioni del trunk. Trovare i parametri impostati dall'amministratore del tenant per questo SBC.

   Microsoft non supporta la presenza di un proxy SIP di terze parti o di un server agente utente tra il proxy SIP Microsoft e l'SBC associato, che potrebbe modificare l'URI della richiesta creato dall'SBC associato.

   I requisiti per le due ricerche (passaggi 2 e 3) necessari per lo scenario in cui un SBC è interconnesso con molti tenant (scenario del gestore) sono descritti più avanti in questo articolo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisiti dettagliati per l'intestazione contact e request-URI

#### <a name="contact-header"></a>Intestazione del contatto

Per tutti i messaggi SIP in arrivo (OPZIONI, INVITE) nel proxy SIP Microsoft, l'intestazione Contact deve avere l'FQDN SBC associato nel nome host URI come indicato di seguito:

Sintassi: Contatto: <sip:phone o sip address@FQDN SBC;transport=tls> 

Come da [RFC 3261, sezione 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), un campo di intestazione Contatto può essere presente in un messaggio OPZIONI. In Direct Routing l'intestazione del contatto è obbligatoria. Per i messaggi INVITE nel formato precedente, per i messaggi OPTIONS le informazioni utente possono essere rimosse dall'URI SIP e solo il nome FQDN inviato nel formato seguente:

Sintassi: Contatto: <sip:FQDN del SBC;transport=tls>

Questo nome (FQDN) deve essere presente anche nei campi Nome comune o Nome alternativo soggetto del certificato presentato. Microsoft supporta l'uso di valori jolly dei nomi nei campi Nome comune o Nome alternativo soggetto del certificato.   

Il supporto per i caratteri jolly è descritto in [RFC 2818, sezione 3.1](https://tools.ietf.org/html/rfc2818#section-3.1). In particolare:

*"I nomi possono contenere il carattere jolly \* che viene considerato corrispondente a qualsiasi singolo componente del nome di dominio o frammento di componente. Ad esempio, \*.a.com corrisponde foo.a.com ma non bar.foo.a.com. f.com\* corrisponde foo.com ma non bar.com".*

Se più valori nell'intestazione Contatto presentata in un messaggio SIP vengono inviati dal servizio SBC, viene usata solo la parte FQDN del primo valore dell'intestazione Contatto.

Come regola generale per il routing diretto, è importante usare l'FQDN per popolare l'URI SIP invece di IP. Messaggio INVITE o OPTIONS in arrivo al proxy SIP con intestazione Contact in cui hostname è rappresentato da IP e non da FQDN, la connessione verrà rifiutata con 403 Accesso negato.

#### <a name="request-uri"></a>Request-URI 

Per tutte le chiamate in arrivo, request-URI viene usato per associare il numero di telefono a un utente.   

Attualmente il numero di telefono deve contenere un segno più (+), come illustrato nell'esempio seguente. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>Da intestazione

Per tutte le chiamate in arrivo, l'intestazione Da viene usata per abbinare il numero di telefono del chiamante all'elenco dei numeri di telefono bloccati del chiamato.

Il numero di telefono deve contenere un segno + come illustrato nell'esempio seguente.

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>Considerazioni sulle intestazioni Record-Route contatti

Il proxy SIP deve calcolare l'FQDN dell'hop successivo per le nuove transazioni client nella finestra di dialogo , ad esempio Bye o Re-Invite, e per rispondere alle opzioni SIP. Vengono usati contatti o Record-Route contatti. 

In base a [RFC 3261, sezione 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), l'intestazione Contatto è obbligatoria in qualsiasi richiesta che può comportare una nuova finestra di dialogo. Il Record-Route è necessario solo se un proxy vuole mantenere il percorso delle richieste future in una finestra di dialogo. Se un SBC proxy è in uso con Ottimizzazione multimediale locale per il routing [diretto, sarà](./direct-routing-media-optimization.md) necessario configurare una route di record perché il proxy SBC deve rimanere nella route. 

Microsoft consiglia di usare solo l'intestazione Contatto se non viene usato un SBC proxy:

- Per [RFC 3261, sezione 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route viene usato se un proxy vuole mantenere il percorso delle richieste future in una finestra di dialogo, che non è essenziale se non è configurato alcun SBC proxy perché tutto il traffico passa tra il proxy SIP Microsoft e l'SBC associato. 

- Il proxy SIP Microsoft usa solo l'intestazione contatto (non Record-Route) per determinare l'hop successivo quando si inviano le opzioni di ping in uscita. La configurazione di un solo parametro (Contatto) invece di due (Contatto e Record-Route) semplifica l'amministrazione se un SBC proxy non è in uso. 

Per calcolare l'hop successivo, il proxy SIP usa:

- Priorità 1. Record-Route di primo livello. Se il nome di Record-Route di primo livello contiene il nome FQDN, il nome FQDN viene usato per stabilire la connessione in uscita nella finestra di dialogo.

- Priorità 2. Intestazione del contatto. Se Record-Route non esiste, il proxy SIP cerca il valore dell'intestazione Contatto per stabilire la connessione in uscita. Questa è la configurazione consigliata.

Se vengono usati sia Contact che Record-Route, l'amministratore SBC deve mantenere identici i valori, causando un sovraccarico amministrativo. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso del nome FQDN in Contatto o Record-Route

L'uso di un indirizzo IP non è supportato in Record-Route o Contatto. L'unica opzione supportata è un FQDN, che deve corrispondere al nome comune o al nome alternativo del soggetto del certificato SBC (sono supportati i valori jolly nel certificato).

- Se un indirizzo IP viene presentato in Record-route o Contact, la verifica del certificato non riesce e la chiamata non riesce.

- Se l'FQDN non corrisponde al valore del nome comune o del nome alternativo del soggetto nel certificato presentato, la chiamata non riesce. 

## <a name="inbound-call-sip-dialog-description"></a>Chiamata in ingresso: descrizione della finestra di dialogo SIP

La tabella seguente riepiloga le differenze e le analogie del flusso di chiamata tra le modalità non bypass e bypass:

| Nome parametro | Modalità non bypass | Modalità bypass
| :---------------------  |:---------------------- |:----------------|
| Media candidates in 183 and 200 messages coming from | Processori multimediali | Client | 
| Numero di 183 messaggi che SBC può ricevere | Uno per sessione | Multiplo | 
| La chiamata può essere con risposta provvisoria (183) | Sì | Sì |
| La chiamata può essere senza risposta provvisoria (183) | Sì | Sì |

###  <a name="non-media-bypass-flow"></a>Flusso di bypass non multimediale

Un Teams utente potrebbe avere più endpoint contemporaneamente. Ad esempio, Teams per Windows, Teams per iPhone client e Teams Telefono (Teams client Android). Ogni endpoint potrebbe segnalare una pausa HTTP nel modo seguente:

-   Stato della chiamata: convertito dal proxy SIP nel messaggio SIP 180. Quando si riceve il messaggio 180, lo SBC deve generare squilli locali.

-   Risposta multimediale: convertita dal proxy SIP nel messaggio 183 con i candidati multimediali nel protocollo SDP (Session Description Protocol). Alla ricezione del messaggio 183, SBC prevede di connettersi ai candidati multimediali ricevuti nel messaggio SDP. 

    > [!NOTE]
    > In alcuni casi la risposta media potrebbe non essere generata e il punto finale potrebbe rispondere con il messaggio "Chiamata accettata".

-   Chiamata accettata: convertita dal proxy SIP nel messaggio SIP 200 con SDP. Alla ricezione del messaggio 200, è previsto che SBC invii e riceva elementi multimediali da e verso i candidati SDP forniti.

    > [!NOTE]
    > Il routing diretto non supporta l'invito all'offerta ritardata (invito senza SDP).

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Squillo di più endpoint con risposta provvisoria

1.  Alla ricezione del primo invito da SBC, il proxy SIP invia il messaggio "SIP SIP/2.0 100 Tentativo" e notifica a tutti gli endpoint dell'utente finale la chiamata in arrivo. 

2.  Al momento della notifica, ogni endpoint inizierà a squillare e a inviare messaggi "Stato chiamata" al proxy SIP. Poiché un Teams può avere più endpoint, il proxy SIP potrebbe ricevere più messaggi di stato delle chiamate.

3.  Per ogni messaggio di stato della chiamata ricevuto dai client, il proxy SIP converte il messaggio Stato chiamata nel messaggio SIP "SIP SIP/2.0 180 Squillo". L'intervallo per l'invio di tali messaggi è definito dall'intervallo dei messaggi ricevuti dal Controllore chiamate. Nel diagramma seguente sono presenti due 180 messaggi generati dal proxy SIP. Questi messaggi provengono dai due Teams endpoint dell'utente. Ogni client ha un ID tag univoco.  Ogni messaggio proveniente da un endpoint diverso sarà una sessione separata (il parametro "tag" nel campo "A" sarà diverso). Tuttavia, un endpoint potrebbe non generare immediatamente il messaggio 180 e inviare immediatamente il messaggio 183, come illustrato nel diagramma seguente.

4.  Quando un endpoint genera un messaggio Media Answer con gli indirizzi IP dei candidati per i supporti multimediali dell'endpoint, il proxy SIP converte il messaggio ricevuto in un messaggio "Stato sessione SIP 183" con il SDP del client sostituito dal provider di servizi multimediali dal processore multimediale. Nel diagramma seguente, l'endpoint da Fork 2 ha risposto alla chiamata. Se il trunk non viene ignorato, il messaggio SIP 183 viene generato una sola volta (Ring Bot o Client End Point). Il 183 potrebbe essere una forchetta esistente o crearne una nuova.

5.  Viene inviato un messaggio di accettazione chiamata con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio accettazione chiamata viene convertito in messaggio SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con risposta provvisoria.](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Squillo di più endpoint senza risposta provvisoria

1.  Alla ricezione del primo invito da SBC, il proxy SIP invia il messaggio "SIP SIP/2.0 100 Tentativo" e notifica a tutti gli endpoint dell'utente finale la chiamata in arrivo. 

2.  Al momento della notifica, ogni endpoint inizierà a squillare e a inviare il messaggio "Stato chiamata" al proxy SIP. Poiché un Teams può avere più punti finali, il proxy SIP potrebbe ricevere più messaggi di stato delle chiamate.

3.  Per ogni messaggio di stato della chiamata ricevuto dai client, il proxy SIP converte il messaggio Stato chiamata nel messaggio SIP "SIP SIP/2.0 180 Trying".  L'intervallo per l'invio dei messaggi è definito dall'intervallo di ricezione dei messaggi dal Controllore chiamate. Nell'immagine seguente sono presenti due 180 messaggi generati dal proxy SIP, il che significa che l'utente ha eseguito l'accesso a tre client Teams e ogni client invia lo stato di avanzamento della chiamata. Ogni messaggio sarà una sessione separata (il parametro "tag" nel campo "A" è diverso)

4.  Viene inviato un messaggio di accettazione chiamata con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio accettazione chiamata viene convertito in messaggio SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano senza risposta provvisoria.](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flusso di bypass multimediale

Gli stessi messaggi (100 Prova, 180, 183) vengono usati nello scenario di bypass multimediale. 

Lo schema seguente mostra un esempio del flusso delle chiamate bypass. 

> [!NOTE]
> I candidati ai contenuti multimediali possono provengono da endpoint diversi. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con risposta provvisoria.](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opzione Sostituisci

L'SBC deve supportare l'invito con le sostituzioni.

## <a name="size-of-sdp-considerations"></a>Considerazioni sulle dimensioni di SDP

L'interfaccia di routing diretto potrebbe inviare un messaggio SIP superiore a 1.500 byte.  Le dimensioni di SDP causano principalmente questo problema. Tuttavia, se dietro il trunk SBC è presente un trunk UDP, il messaggio potrebbe essere rifiutato se viene inoltrato dal proxy SIP Microsoft al trunk non modificato. Microsoft consiglia di rimuovere alcuni valori in SDP nel database SBC quando si invia il messaggio ai trunk UDP. Ad esempio, i candidati ICE o i codec inutilizzati possono essere rimossi.

## <a name="call-transfer"></a>Trasferimento di chiamata

Routing diretto supporta due metodi per il trasferimento delle chiamate:

- Opzione 1. Processi proxy SIP Fare riferimento al client in locale e funge da arbitro come descritto nella sezione 7.1 di RFC 3892.

  Con questa opzione, il proxy SIP termina il trasferimento e aggiunge un nuovo invito. 


- Opzione 2. Il proxy SIP invia il riferimento all'SBC e funge da transferor come descritto nella sezione 6 di RFC 5589.

  Con questa opzione, il proxy SIP invia un riferimento a SBC e prevede che SBC gestirà completamente il trasferimento.

Il proxy SIP seleziona il metodo in base alle funzionalità segnalate da SBC. Se SBC indica che supporta il metodo "Refer", il proxy SIP userà l'opzione 2 per i trasferimenti di chiamata.

Di seguito è riportato un esempio di SBC che invia il messaggio che indica che il metodo Refer è supportato:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Se L'SBC non indica che Fare riferimento come metodo supportato, il routing diretto userà l'opzione 1 (il proxy SIP funge da arbitro). SBC deve anche segnalare che supporta il metodo Notify:

Esempio di SBC che indica che il metodo Refer non è supportato:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Processi proxy SIP Fare riferimento dal client in locale e funge da arbitro

Se SBC indica che il metodo Refer non è supportato, il proxy SIP funge da arbitro. 

La richiesta referenziata del client verrà terminata nel proxy SIP. La richiesta referenziare del cliente viene visualizzata come "Trasferimento di chiamata a Davide" nel diagramma seguente.  Per altre informazioni, vedere la sezione 7.1 di [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt). 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con risposta provvisoria.](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Il proxy SIP invia l'indirizzo Refer to the SBC e funge da transferor

Questo è il metodo preferito per i trasferimenti di chiamata ed è obbligatorio per i dispositivi che cercano la certificazione del bypass multimediale. Trasferimento di chiamata senza che SBC sia in grado di gestire Refer non è supportato nella modalità di bypass multimediale. 

Lo standard è illustrato nella sezione 6 di RFC 5589. Le RFC correlate sono:

- [Session Initiation Protocol (SIP) Call Control - Transfer](https://tools.ietf.org/html/rfc5589)

- [Intestazione SIP (Session Initiation Protocol) "Sostituisce"](https://tools.ietf.org/html/rfc3891)

- [Meccanismo sip (Session Initiation Protocol) "Referred-By"](https://tools.ietf.org/html/rfc3892)

Questa opzione presuppone che il proxy SIP agisca da transferor e invii un messaggio Di riferimento a SBC. L'SBC funge da cessione e gestisce il riferimento per generare una nuova offerta per il trasferimento. Esistono due casi possibili:

- La chiamata viene trasferita a un partecipante PSTN esterno. 
- La chiamata viene trasferita da un Teams utente a un altro utente Teams nello stesso tenant tramite SBC. 

Se la chiamata viene trasferita da un utente di Teams a un altro tramite SBC, il servizio SBC dovrebbe emettere un nuovo invito (avviare una nuova finestra di dialogo) per l'obiettivo di trasferimento (l'utente Teams) usando le informazioni ricevute nel messaggio Di riferimento. 

Per popolare internamente i campi A/Trasferimento per la transazione della richiesta, il proxy SIP deve comunicare queste informazioni all'interno delle intestazioni REFER-TO/REFERRED-BY. 

Il proxy SIP formerà refer-TO come URI SIP costituito da un FQDN del proxy SIP nel nome host e da una delle opzioni seguenti:

- Un numero di telefono E.164 nella parte username dell'URI nel caso in cui l'obiettivo di trasferimento sia un numero di telefono o

- I parametri x-m e x-t codificano rispettivamente la RMI di destinazione del trasferimento completo e l'ID tenant 

L'intestazione REFERRED-BY è un URI SIP con  MRI del trasferimento codificato, l'ID tenant del trasferimento e altri parametri del contesto di trasferimento, come illustrato nella tabella seguente:

| Parametro | Valore | Descrizione |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | MRI completo dell'obiettivo di trasferimento/trasferimento come popolato da CC |
| x-t | ID tenant | x-t ID tenant ID tenant facoltativo popolato da CC |
| x-ti | ID di correlazione del trasferimentore | ID di correlazione della chiamata al trasferimento |
| x-tt | TRASFERIRE l'URI della chiamata di destinazione | URI di sostituzione della chiamata codificato |

In questo caso, le dimensioni dell'intestazione di riferimento possono essere fino a 400 simboli. SBC deve supportare la gestione dei messaggi Di riferimento con dimensioni fino a 400 simboli.

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra più endpoint che squillano con risposta provvisoria.](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Timer di sessione

Il proxy SIP supporta (sempre) il timer di sessione per le chiamate non bypass, ma non lo offre per le chiamate bypass. L'uso del timer di sessione da parte di SBC non è obbligatorio.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso del parametro Request-URI user=phone

Il proxy SIP analizza request-URI e, se il parametro user=phone è presente, il servizio gestirà l'URI della richiesta come numero di telefono, abbinando il numero a un utente. Se parametro non è presente, il proxy SIP applica l'euristica per determinare il tipo di utente Request-URI (numero di telefono o indirizzo SIP).

Microsoft consiglia di applicare sempre il parametro user=phone per semplificare il processo di configurazione della chiamata.

## <a name="history-info-header"></a>History-Info intestazione

L'intestazione History-Info viene usata per il retargeting delle richieste SIP e "fornisce un meccanismo standard per l'acquisizione delle informazioni sulla cronologia delle richieste per consentire un'ampia gamma di servizi per le reti e gli utenti finali". Per altre informazioni, vedere [RFC 4244 – Sezione 1.1](http://www.ietf.org/rfc/rfc4244.txt). Per Telefono Microsoft sistema, questa intestazione viene usata negli scenari di simulring e inoltro di chiamata.  

Se si invia, la History-Info è abilitata nel modo seguente:

- Il proxy SIP inserirà un parametro contenente il numero di telefono associato nelle singole voci History-Info che costituiscono l'intestazione History-Info messaggio inviato al controller PSTN.  Usando solo le voci che hanno il parametro numero di telefono, il controller PSTN ricostruirà una nuova intestazione History-Info e la passerà al provider trunk SIP tramite proxy SIP.

- History-Info'intestazione verrà aggiunta per i casi simultanei di squillo e inoltro di chiamata.

- History-Info'intestazione non verrà aggiunta per i casi di trasferimento di chiamata.

- Una singola voce della cronologia nell'intestazione History-Info ricostruito avrà il parametro del numero di telefono fornito insieme all'FQDN (sip.pstnhub.microsoft.com Direct Routing FQDN) impostato come parte host dell'URI. nell'URI SIP verrà aggiunto un parametro "utente=telefono".  Tutti gli altri parametri associati all'intestazione History-Info, ad eccezione dei parametri di contesto del telefono, verranno passati nell'intestazione History-Info telefono.  

  > [!NOTE]
  > Le voci private (come determinato dai meccanismi definiti nella Sezione 3.3 di RFC 4244) verranno inoltrate così come il provider trunk SIP è un peer attendibile.

- I messaggi in History-Info vengono ignorati.

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

Se un data center Di routing diretto è occupato, il servizio può inviare un messaggio di Retry-After con un intervallo di un secondo all'SBC. Quando SBC riceve un messaggio 503 con un'intestazione Retry-After in risposta a un invito, il SBC deve terminare la connessione e provare il successivo data center Microsoft disponibile.

## <a name="handling-retries-603-response"></a>Gestione dei tentativi (risposta 603)
Se un utente finale osserva diverse chiamate perse per una chiamata dopo aver declinato la chiamata in arrivo, significa che il meccanismo di ripetizione dei tentativi del provider trunk SBC o PSTN non è configurato correttamente. L'SBC deve essere riconfigurato per interrompere i tentativi nella risposta 603.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Riavvio ICE: chiamata bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale

L'SBC deve supportare i riavvii ICE come descritto in [RFC 5245, sezione 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).

Il riavvio in Direct Routing viene implementato in base ai paragrafi seguenti della RFC:

*Per riavviare ICE, un agente DEVE modificare sia ice-pwd che ice-ufrag per il flusso multimediale in un'offerta.  Si noti che è consentito usare un attributo a livello di sessione in un'offerta, ma fornire lo stesso ice-pwd o ice-ufrag come attributo a livello di supporto in un'offerta successiva.  Non si tratta di una modifica della password, ma solo di una modifica della relativa rappresentazione e non causa un riavvio ICE.*

*Un agente imposta il resto dei campi nel file SDP per questo flusso multimediale come in un'offerta iniziale di questo flusso multimediale (vedere la Sezione 4.3).  Di conseguenza, l'insieme di candidati PUÒ includere alcuni, nessuno o tutti i candidati precedenti per tale flusso e PUÒ includere un set completamente nuovo di candidati raccolti come descritto nella sezione 4.1.1.*

Se la chiamata è stata inizialmente stabilita con il bypass multimediale e la chiamata viene trasferita a un client Skype for Business, Direct Routing deve inserire un processore multimediale, perché il routing diretto non può essere usato con un client Skype for Business con bypass multimediale. Direct Routing avvia il processo di riavvio ice modificando ice-pwd e ice-ufrag e offrendo nuovi media candidate in un rinvio.
