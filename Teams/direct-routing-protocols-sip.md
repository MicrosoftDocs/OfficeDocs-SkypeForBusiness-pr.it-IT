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
ms.openlocfilehash: 4fe636029c3a058dc1a8d33cc191d7654888ec5e
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278726"
---
# <a name="direct-routing---sip-protocol"></a>Direct Routing - SIP protocol

Questo articolo descrive in che modo Routing diretto implementa il protocollo SIP (Session Initiation Protocol). Per instradare correttamente il traffico tra un controller dei confini della sessione (SBC) e il proxy SIP, alcuni parametri SIP devono avere valori specifici. Questo articolo è rivolto agli amministratori vocali responsabili della configurazione della connessione tra il servizio SBC locale e il servizio proxy SIP.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>Elaborazione della richiesta in arrivo: ricerca del tenant e dell'utente

Prima di elaborare una chiamata in arrivo o in uscita, i messaggi OPTIONS vengono s scambiati tra il proxy SIP e sBC. Questi messaggi OPZIONI consentono al proxy SIP di fornire le funzionalità consentite a SBC. È importante che la negoziazione DELLE OPZIONI sia completata (risposta 200OK), consentendo ulteriori comunicazioni tra SBC e proxy SIP per la definizione delle chiamate. Le intestazioni SIP nei messaggi OPTIONS per il proxy SIP sono fornite come esempio di seguito:

| Nome parametro | Esempio del valore | 
| :---------------------  |:---------------------- |
| REQUEST-URI | OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| Tramite intestazione | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards intestazione | Max-in avanti:68 |
| Da intestazione | Da intestazione da: <sip:sbc1.adatum.biz:5058> |
| A intestazione | A: <sip:sip.pstnhub.microsoft.com:5061> |
| Intestazione CSeq | CSeq: 1 INVITE | 
| Intestazione contatto | Contatto: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> Le intestazioni SIP non contengono userinfo nell'URI SIP in uso. Come da [RFC 3261, sezione 19.1.1,](https://tools.ietf.org/html/rfc3261#section-19.1.1)la parte userinfo di un URI è facoltativa e potrebbe non essere presente quando l'host di destinazione non ha nozioni di utenti o quando il problema stesso è la risorsa identificata. Se il simbolo @ è presente in un URI SIP, il campo utente NON DEVE essere vuoto.

Durante una chiamata in arrivo, il proxy SIP deve trovare il tenant a cui è destinata la chiamata e trovare l'utente specifico all'interno del tenant. L'amministratore del tenant può configurare numeri non DID, ad esempio +1001, in più tenant. Di conseguenza, è importante trovare il tenant specifico in cui eseguire la ricerca del numero perché i numeri non DID potrebbero essere uguali in più organizzazioni Microsoft 365 o Office 365.  

Questa sezione descrive in che modo il proxy SIP trova il tenant e l'utente ed esegue l'autenticazione del servizio SBC nella connessione in ingresso.

Di seguito è riportato un esempio del messaggio di invito SIP in una chiamata in arrivo:

| Nome parametro | Esempio del valore | 
| :---------------------  |:---------------------- |
| REQUEST-URI | INVITA sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| Tramite intestazione | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards intestazione | Max-in avanti:68 |
| Da intestazione | Da intestazione da: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| A intestazione | A: sip:+183338006777@sbc1.adatum.biz | 
| Intestazione CSeq | CSeq: 1 INVITE | 
| Intestazione contatto | Contatto: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

Alla ricezione dell'invito, il proxy SIP esegue i passaggi seguenti:

1. Controllare il certificato. Nella connessione iniziale, il servizio di routing diretto prende il nome FQDN presentato nell'intestazione contatto e lo abbina al nome comune o al nome alternativo dell'oggetto del certificato presentato. Il nome SBC deve corrispondere a una delle opzioni seguenti:

   - Opzione 1. Il nome FQDN completo presentato nell'intestazione Contatto deve corrispondere al nome comune o al nome alternativo dell'oggetto del certificato presentato.  

   - Opzione 2. La parte relativa al dominio del nome FQDN presentata nell'intestazione contatto (ad esempio adatum.biz del nome FQDN sbc1.adatum.biz) deve corrispondere al valore jolly in Nome comune/Nome alternativo oggetto (ad esempio *.adatum.biz).

2. Provare a trovare un tenant con il nome FQDN completo presentato nell'intestazione contatto.  

   Verificare se il nome FQDN dell'intestazione contatto (sbc1.adatum.biz) è registrato come nome DNS in qualsiasi organizzazione di Microsoft 365 o Office 365. Se viene trovato, la ricerca dell'utente viene eseguita nel tenant con l'FQDN SBC registrato come nome di dominio. Se non viene trovato, si applica il passaggio 3.   

3. Il passaggio 3 si applica solo se il passaggio 2 non è riuscito. 

   Rimuovere la parte host dall'FQDN, presentata nell'intestazione contatto (FQDN: sbc12.adatum.biz, dopo la rimozione della parte host: adatum.biz) e verificare se questo nome è registrato come nome DNS in qualsiasi organizzazione di Microsoft 365 o Office 365. Se viene trovato, la ricerca dell'utente viene eseguita in questo tenant. Se non viene trovato, la chiamata non riesce.

4. Usando il numero di telefono presentato nell'URI richiesta, eseguire la ricerca del numero inverso all'interno del tenant individuato nel passaggio 2 o 3. Abbinare il numero di telefono presentato a un URI SIP dell'utente all'interno del tenant, individuato nel passaggio precedente.

5. Applicare le impostazioni del trunk. Trovare i parametri impostati dall'amministratore tenant per questo SBC.

   Microsoft non supporta la presenza di un proxy SIP di terze parti o di un server agente utente tra il proxy SIP Microsoft e il servizio SBC associato, che potrebbe modificare l'URI della richiesta creato dal servizio SBC associato.

   I requisiti per le due ricerche (passaggi 2 e 3) necessari per lo scenario in cui un SBC è interconnesso con più tenant (scenario gestore) sono descritti più avanti in questo articolo.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Requisiti dettagliati per l'intestazione contatto e l'URI richiesta

#### <a name="contact-header"></a>Intestazione del contatto

Per tutti i messaggi SIP in arrivo (OPZIONI, INVITE) al proxy SIP Microsoft, l'intestazione contatto deve avere l'FQDN SBC associato nel nome host URI nel modo seguente:

Sintassi: Contatto: <sip:phone o sip address@FQDN di SBC;transport=tls> 

Come da [RFC 3261, sezione 11.1,](https://tools.ietf.org/html/rfc3261#section-11.1)un campo di intestazione Contatto PUÒ essere presente in un messaggio OPTIONS. In Percorso diretto l'intestazione del contatto è obbligatoria. Per i messaggi INVITE nel formato precedente, per i messaggi INS è possibile rimuovere userinfo dall'URI SIP e inviare solo l'FQDN nel formato seguente:

Sintassi: Contatto: <sip:FQDN di SBC;transport=tls>

Questo nome (FQDN) deve essere presente anche nel campo o nei campi nome alternativo del soggetto del certificato presentato. Microsoft supporta l'uso di valori jolly dei nomi nei campi Nome comune o Nome alternativo oggetto del certificato.   

Il supporto dei caratteri jolly è descritto in [RFC 2818, sezione 3.1.](https://tools.ietf.org/html/rfc2818#section-3.1) In particolare:

*"I nomi possono contenere il carattere jolly corrispondente a qualsiasi frammento o componente del nome di \* dominio singolo. Ad esempio, a.com corrisponde foo.a.com ma non bar.foo.a.com. f.com corrisponde foo.com \* \* ma non bar.com".*

Se più valori nell'intestazione Contatto presentati in un messaggio SIP vengono inviati dal servizio SBC, viene usata solo la parte FQDN del primo valore dell'intestazione Contatto.

Come regola generale per il routing diretto, è importante usare l'FQDN per popolare l'URI SIP invece di IP. Messaggio INVITE o OPTIONS in arrivo al proxy SIP con intestazione Contatto in cui il nome host è rappresentato da IP e non da FQDN, la connessione verrà rifiutata con 403 Accesso negato.

#### <a name="request-uri"></a>REQUEST-URI 

Per tutte le chiamate in arrivo, l'URI richiesta viene usato per associare il numero di telefono a un utente.   

Attualmente il numero di telefono deve contenere un segno più (+), come illustrato nell'esempio seguente. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>Considerazioni sulle intestazioni Record-Route contatti e contatti

Il proxy SIP deve calcolare l'FQDN hop successivo per le nuove transazioni client nella finestra di dialogo (ad esempio Bye o Re-Invite) e per rispondere alle opzioni SIP. Vengono usati i contatti Record-Route contatti. 

In base allo [standard RFC 3261, sezione 8.1.1.8,](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)l'intestazione del contatto è obbligatoria in qualsiasi richiesta che può causare una nuova finestra di dialogo. LRecord-Route è necessario solo se un proxy vuole rimanere sul percorso delle richieste future in una finestra di dialogo. Se un proxy SBC è in uso con Ottimizzazione supporto locale per il [routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)diretto, sarà necessario configurare un percorso di record perché il proxy SBC deve rimanere nella route. 

Microsoft consiglia di usare solo l'intestazione Contatto se non si usa un proxy SBC:

- Per [RFC 3261, sezione 20.30,](https://tools.ietf.org/html/rfc3261#section-20.30)Record-Route viene usato se un proxy vuole mantenere il percorso delle richieste future in una finestra di dialogo, che non è essenziale se non è configurato alcun proxy SBC perché tutto il traffico passa tra il proxy SIP Microsoft e l'SBC associato. 

- Il proxy SIP Microsoft usa solo l'intestazione contatto (non Record-Route) per determinare l'hop successivo quando si inviano le opzioni di ping in uscita. La configurazione di un solo parametro (Contatto) invece di due (Contatto e Route record) semplifica l'amministrazione se un proxy SBC non è in uso. 

Per calcolare l'hop successivo, il proxy SIP usa:

- Priorità 1. Percorso record di primo livello. Se il nome di Record-Route principale contiene il nome FQDN, il nome FQDN viene usato per effettuare la connessione in uscita nella finestra di dialogo.

- Priorità 2. Intestazione del contatto. Se Record-Route non esiste, il proxy SIP cerca il valore dell'intestazione Contatto per effettuare la connessione in uscita. Questa è la configurazione consigliata.

Se vengono usati sia Contatti che Record-Route, l'amministratore di SBC deve mantenere gli stessi valori, comportando un sovraccarico amministrativo. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>Uso del nome FQDN in Contatti o Record-Route

L'uso di un indirizzo IP non è supportato in Record-Route o contatto. L'unica opzione supportata è un FQDN, che deve corrispondere al nome comune o al nome alternativo dell'oggetto del certificato SBC. Sono supportati i valori jolly nel certificato.

- Se un indirizzo IP viene presentato in Percorso record o Contatto, il controllo del certificato non riesce e la chiamata non riesce.

- Se l'FQDN non corrisponde al valore del nome alternativo comune o del soggetto nel certificato presentato, la chiamata non riesce. 

## <a name="inbound-call-sip-dialog-description"></a>Chiamata in ingresso: descrizione della finestra di dialogo SIP

La tabella seguente riepiloga le differenze e le similarità del flusso delle chiamate tra le modalità non bypass e bypass:

| Nome parametro | Modalità non bypass | Modalità bypass
| :---------------------  |:---------------------- |:----------------|
| Candidati media in 183 e 200 messaggi provenienti da | Processori multimediali | Client | 
| Numero di 183 messaggi che SBC può ricevere | Uno per sessione | Multiplo | 
| La chiamata può essere con risposta provvisoria (183) | Sì | Sì |
| La chiamata può essere senza risposta provvisoria (183) | Sì | Sì |

###  <a name="non-media-bypass-flow"></a>Flusso di bypass non multimediale

Un utente di Teams potrebbe avere più endpoint contemporaneamente. Ad esempio, il client Teams per Windows, il client Teams per iPhone e il telefono Teams (client Android di Teams). Ogni endpoint potrebbe segnalare un rest HTTP nel modo seguente:

-   Stato della chiamata: convertito dal proxy SIP nel messaggio SIP 180. Alla ricezione del messaggio 180, il servizio SBC deve generare uno squillo locale.

-   Risposta multimediale: convertita dal proxy SIP nel messaggio 183 con candidati per i contenuti multimediali nel protocollo SDP (Session Description Protocol). Quando riceve il messaggio 183, SBC prevede di connettersi ai candidati multimediali ricevuti nel messaggio SDP. 

    > [!NOTE]
    > In alcuni casi la risposta media potrebbe non essere generata e il punto finale potrebbe rispondere con il messaggio "Chiamata accettata".

-   Chiamata accettata: convertita dal proxy SIP nel messaggio SIP 200 con SDP. Alla ricezione del messaggio 200, il servizio SBC dovrebbe inviare e ricevere elementi multimediali da e verso i candidati SDP forniti.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>Più endpoint che squillano con una risposta provvisoria

1.  Alla ricezione del primo invito dall'SBC, il proxy SIP invia il messaggio "PROVA SIP SIP/2.0 100" e invia una notifica a tutti gli endpoint dell'utente finale sulla chiamata in arrivo. 

2.  Alla notifica, ogni endpoint inizierà a squillare e a inviare messaggi di stato della chiamata al proxy SIP. Poiché un utente di Teams può avere più punti finali, il proxy SIP potrebbe ricevere più messaggi sull'avanzamento chiamata.

3.  Per ogni messaggio di stato della chiamata ricevuto dai client, il proxy SIP converte il messaggio di stato della chiamata nel messaggio SIP "SIP SIP/2.0 180 Trying". L'intervallo per l'invio di questi messaggi è definito dall'intervallo dei messaggi ricevuti dal controller di chiamata. Nel diagramma seguente sono generati due 180 messaggi dal proxy SIP. Questi messaggi provengono dai due endpoint di Teams dell'utente. Ognuno dei clienti ha un ID tag univoco.  Ogni messaggio proveniente da un endpoint diverso sarà una sessione separata (il parametro "tag" nel campo "A" sarà diverso). Tuttavia, un endpoint potrebbe non generare immediatamente il messaggio 180 e inviare il messaggio 183, come illustrato nel diagramma seguente.

4.  Quando un endpoint genera un messaggio Media Answer con gli indirizzi IP dei candidati per gli elementi multimediali dell'endpoint, il proxy SIP converte il messaggio ricevuto in un messaggio "Stato sessione SIP 183" con la pagina SDP del client sostituita dalla SDP dal processore multimediale. Nel diagramma seguente l'endpoint di Fork 2 ha risposto alla chiamata. Se il trunk non è bypassato, il messaggio SIP 183 viene generato una sola volta (Ring Bot o Client End Point). La 183 potrebbe essere in una forchetta esistente o crearne una nuova.

5.  Viene inviato un messaggio di accettazione chiamata con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio Di accettazione chiamata viene convertito in messaggio SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra lo squillo di più endpoint con una risposta provvisoria](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>Più endpoint che squillano senza risposta provvisoria

1.  Alla ricezione del primo invito dall'SBC, il proxy SIP invia il messaggio "PROVA SIP SIP/2.0 100" e invia una notifica a tutti gli endpoint dell'utente finale sulla chiamata in arrivo. 

2.  Alla notifica, ogni endpoint inizierà a squillare e a inviare il messaggio "Stato chiamata" al proxy SIP. Poiché un utente di Teams può avere più punti finali, il proxy SIP potrebbe ricevere più messaggi sull'avanzamento chiamata.

3.  Per ogni messaggio di stato della chiamata ricevuto dai client, il proxy SIP converte il messaggio di stato della chiamata nel messaggio SIP "SIP SIP/2.0 180 Trying".  L'intervallo per l'invio dei messaggi è definito dall'intervallo di ricezione dei messaggi dal controller di chiamata. Nell'immagine seguente ci sono due 180 messaggi generati dal proxy SIP, il che significa che l'utente ha effettuato l'accesso a tre client Teams e a ogni client invia l'avanzamento della chiamata. Ogni messaggio sarà una sessione separata (il parametro "tag" nel campo "A" è diverso)

4.  Viene inviato un messaggio di accettazione chiamata con i candidati finali dell'endpoint che hanno accettato la chiamata. Il messaggio Di accettazione chiamata viene convertito in messaggio SIP 200. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra lo squillo di più endpoint senza risposta provvisoria](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>Flusso del bypass multimediale

Nello scenario di bypass multimediale vengono usati gli stessi messaggi (100 Trying, 180, 183). 

Lo schema seguente mostra un esempio del flusso delle chiamate bypass. 

> [!NOTE]
> I candidati per gli elementi multimediali possono essere provenienti da diversi endpoint. 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra lo squillo di più endpoint con una risposta provvisoria](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>Opzione Sostituisci

Il servizio SBC deve supportare l'opzione Invita con sostituzioni.

## <a name="size-of-sdp-considerations"></a>Considerazioni sulle dimensioni di SDP

L'interfaccia di routing diretto potrebbe inviare un messaggio SIP che supera i 1.500 byte.  Questa operazione viene causata principalmente dalla dimensione di SDP. Tuttavia, se c'è un trunk UDP dietro sBC, potrebbe rifiutare il messaggio se viene inoltrato dal proxy SIP Microsoft al trunk non modificato. Microsoft consiglia di rimuovere alcuni valori in SDP dal database SBC quando si invia il messaggio ai trunk UDP. Ad esempio, i candidati ICE o i codec inutilizzati possono essere rimossi.

## <a name="call-transfer"></a>Trasferimento di chiamata

L'instradamento diretto supporta due metodi per il trasferimento delle chiamate:

- Opzione 1. I processi proxy SIP Fanno riferimento dal client in locale e funge da referee, come descritto nella sezione 7.1 di RFC 3892.

  Con questa opzione, il proxy SIP termina il trasferimento e aggiunge un nuovo invito. 


- Opzione 2. Il proxy SIP invia il riferimento al servizio SBC e funge da trasferimentore, come descritto nella Sezione 6 di RFC 5589.

  Con questa opzione, il proxy SIP invia un riferimento al servizio SBC e si aspetta che il servizio SBC gestirà completamente il trasferimento.

Il proxy SIP seleziona il metodo in base alle funzionalità riportate dal servizio SBC. Se SBC indica che supporta il metodo "Fare riferimento", il proxy SIP userà l'opzione 2 per i trasferimenti di chiamata.

Di seguito è riportato un esempio di un servizio SBC che invia il messaggio che indica che il metodo Refer è supportato:

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

Se SBC non indica che Il servizio Di riferimento è un metodo supportato, l'instradamento diretto userà l'opzione 1 (il proxy SIP funge da referee). SBC deve anche segnalare che supporta il metodo Notify:

Esempio di SBC che indica che il metodo Refer non è supportato:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>Processi proxy SIP Fai riferimento dal client in locale e funge da referee

Se SBC ha indicato che il metodo di riferimento non è supportato, il proxy SIP funge da referee. 

La richiesta di riferimento del client verrà terminata nel proxy SIP. La richiesta di riferimento del client viene mostrata come "Trasferimento di chiamata a Dave" nel diagramma seguente.  Per altre informazioni, vedere la sezione 7.1 di [RFC 3892.](https://www.ietf.org/rfc/rfc3892.txt) 

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra lo squillo di più endpoint con una risposta provvisoria](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>Il proxy SIP invia il referenziato al servizio SBC e funge da trasferimentore

Questo è il metodo consigliato per i trasferimenti di chiamata ed è obbligatorio per i dispositivi che cercano la certificazione del bypass multimediale. Trasferimento chiamata senza che il servizio SBC sia in grado di gestire Refer non è supportato nella modalità bypass multimediale. 

Lo standard è spiegato nella Sezione 6 di RFC 5589. Le RDC correlate sono:

- [Controllo delle chiamate SIP (Session Initiation Protocol) - Trasferimento](https://tools.ietf.org/html/rfc5589)

- [Intestazione "Sostituisci" SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3891)

- [Meccanismo "Referred-By" SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3892)

Questa opzione presuppone che il proxy SIP funge da trasferimentore e invii un messaggio di riferimento al servizio SBC. Il servizio SBC funge da cessione e gestisce il riferimento per generare una nuova offerta per il trasferimento. I casi possibili sono due:

- La chiamata viene trasferita a un partecipante PSTN esterno. 
- La chiamata viene trasferita da un utente di Teams a un altro utente di Teams nello stesso tenant tramite SBC. 

Se la chiamata viene trasferita da un utente di Teams a un altro tramite SBC, la SBC dovrebbe emettere un nuovo invito (avviare una nuova finestra di dialogo) per il destinatario del trasferimento (l'utente di Teams) usando le informazioni ricevute nel messaggio Di riferimento. 

Per popolare i campi A/Trasferimento per la transazione della richiesta internamente, il proxy SIP deve comunicare queste informazioni all'interno delle intestazioni REFER-TO/REFERRED-BY. 

Il proxy SIP formerà REFER-TO come URI SIP costituito da un FQDN proxy SIP nel nome host ed eseguire una delle operazioni seguenti:

- Un numero di telefono E.164 nella parte nome utente dell'URI nel caso in cui il destinatario del trasferimento sia un numero di telefono oppure

- Parametri x-m e x-t che codificano rispettivamente il valore MRI di destinazione del trasferimento completo e l'ID tenant 

L'intestazione REFERRED-BY è un URI SIP con codifica MRI del trasferitore, oltre all'ID tenant del trasferimento e ad altri parametri di contesto di trasferimento, come illustrato nella tabella seguente:

| Parametro | Valore | Descrizione |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | MRI completo del trasferimento/trasferimento di destinazione come popolato da CC |
| x-t | ID tenant | ID tenant x-t FACOLTATIVO ID tenant popolato da CC |
| x-ti | ID di correlazione del certa | ID di correlazione della chiamata al trasferitore |
| x-tt | URI chiamata di destinazione trasferimento | URI di sostituzione della chiamata codificato |

In questo caso, la dimensione dell'intestazione di riferimento può essere fino a 400 simboli. Il servizio SBC deve supportare la gestione dei messaggi di riferimento con un massimo di 400 simboli.

> [!div class="mx-imgBorder"]
> ![Diagramma che mostra lo squillo di più endpoint con una risposta provvisoria](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>Timer di sessione

Il proxy SIP supporta (sempre) il timer di sessione per le chiamate senza bypass, ma non lo offre per le chiamate tramite bypass. L'uso del timer di sessione da parte del servizio SBC non è obbligatorio.

##  <a name="use-of-request-uri-parameter-userphone"></a>Uso del parametro Request-URI user=phone

Il proxy SIP analizza l'URI richiesta e, se il parametro user=phone è presente, il servizio gestirà l'URI richiesta come numero di telefono, abbinando il numero a un utente. Se il parametro non è presente, il proxy SIP applica un'euristica per determinare il tipo di utente Richiesta-URI (numero di telefono o indirizzo SIP).

Microsof consiglia di applicare sempre il parametro user=phone per semplificare il processo di impostazione delle chiamate.

## <a name="history-info-header"></a>History-Info intestazione

L'intestazione History-Info viene usata per ridefinire le richieste SIP e "fornire(e) un meccanismo standard per acquisire le informazioni della cronologia delle richieste per consentire un'ampia varietà di servizi per le reti e gli utenti finali". Per altre informazioni, vedere [RFC 4244 - Sezione 1.1.](http://www.ietf.org/rfc/rfc4244.txt) Per il Sistema telefonico Microsoft, questa intestazione viene utilizzata negli scenari di simulring e inoltro di chiamata.  

Se l'invio viene History-Info, la posta elettronica viene abilitata nel modo seguente:

- Il proxy SIP inserirà un parametro contenente il numero di telefono associato nelle singole History-Info di posta elettronica che includono l'intestazione History-Info posta elettronica inviata al controller PSTN.  Usando solo le voci che hanno il parametro del numero di telefono, il controller PSTN ricostruirà una nuova intestazione History-Info e la passerà al provider di trunk SIP tramite proxy SIP.

- History-Info'intestazione verrà aggiunta per i casi di inoltro di chiamata e squillo simultaneo.

- History-Info'intestazione non verrà aggiunta per i casi di trasferimento di chiamata.

- Una singola voce della cronologia nell'intestazione di History-Info appena stata ricostruire avrà il parametro del numero di telefono fornito in combinazione con l'FQDN di routing diretto (sip.pstnhub.microsoft.com) impostato come parte host dell'URI; Un parametro 'user=phone' verrà aggiunto come parte dell'URI SIP.  Tutti gli altri parametri associati all'intestazione History-Info originale, ad eccezione dei parametri di contesto del telefono, verranno passati nell'intestazione History-Info struttura.  

  > [!NOTE]
  > Le voci private (come determinato dai meccanismi definiti nella Sezione 3.3 di RFC 4244) verranno inoltrate così come sono perché il provider di trunk SIP è un peer attendibile.

- Le connessioni History-Info in ingresso vengono ignorate.

Di seguito è riportato il formato dell'intestazione Cronologia-info inviata dal proxy SIP:

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

La History-Info è protetta da un meccanismo TLS obbligatorio. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>Connessione SBC al meccanismo di routing diretto e failover

Consulta il meccanismo di failover della sezione per il traffico di segnalazione SIP nel [Piano per il routing diretto.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)

## <a name="retry-after"></a>Retry-After

Se un data center di instradamento diretto è occupato, il servizio può inviare un Retry-After messaggio con un intervallo di un secondo al centro dati SBC. Quando SBC riceve un messaggio 503 con un'intestazione Retry-After in risposta a un invito, deve terminare la connessione e provare il successivo data center Microsoft disponibile. 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>Riavvio ICE: chiamata bypass multimediale trasferita a un endpoint che non supporta il bypass multimediale

La SBC deve supportare i riavvii ICE come descritto nello [standard RFC 5245, sezione 9.1.1.1.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)

Il riavvio del routing diretto viene implementato in base ai paragrafi seguenti di RFC:

*Per riavviare ICE, un agente DEVE modificare sia la ice-pwd che la ice-ufrag per il flusso multimediale in un'offerta.  Si noti che è consentito usare un attributo a livello di sessione in un'offerta, ma fornire lo stesso ice-pwd o ice-ufrag come attributo a livello di supporto in un'offerta successiva.  Non si tratta di una modifica della password, ma solo di una modifica della rappresentazione e non causa il riavvio dell'ice.*

*Un agente imposta gli altri campi nel file SDP per questo flusso multimediale come farebbe in un'offerta iniziale di questo flusso multimediale (vedere la Sezione 4.3).  Di conseguenza, il set di candidati PUÒ includere alcuni, nessuno o tutti i candidati precedenti per tale flusso e PUÒ includere un nuovo set completamente nuovo di candidati, come descritto nella sezione 4.1.1.*

Se la chiamata è stata inizialmente stabilita con un bypass multimediale e la chiamata viene trasferita a un client Skype for Business, l'instradamento diretto deve inserire un processore multimediale, perché l'instradamento diretto non può essere utilizzato con un client Skype for Business con bypass multimediale. L'instradamento diretto avvia il processo di riavvio dell'ice-pwd modificando il ghiaccio e offrendo nuovi media candidati per un reinvio. 


