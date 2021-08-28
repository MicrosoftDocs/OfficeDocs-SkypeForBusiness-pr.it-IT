---
title: Guida alla sicurezza per Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Security
description: Guida alla sicurezza per Skype for Business online <add description>
ms.openlocfilehash: 9eeaa4aec19a3113013ca93c76dfc686eb85b270
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619292"
---
# <a name="security-and-skype-for-business-online"></a>Sicurezza e Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online (SfBO), nell'ambito dei servizi Microsoft 365 e Office 365, segue tutte le procedure consigliate per la sicurezza, ad esempio la sicurezza a livello di servizio, tramite controlli dei clienti approfonditi all'interno del servizio, protezione avanzata della sicurezza e procedure consigliate operative. Per informazioni dettagliate, vedere il Centro protezione Microsoft ( https://microsoft.com/trustcenter) .

## <a name="trustworthy-by-design"></a>Affidabile per progettazione
Skype for Business Online è progettato e sviluppato in conformità con MIcrosoft Trustworthy Computing Security Development Lifecycle (SDL) descritto in https://www.microsoft.com/sdl/default.aspx. Il primo passo verso la creazione di un sistema di comunicazioni unificato più sicuro è stato quello di progettare modelli di minacce e testare ciascuna funzionalità così come era stata progettata. Ulteriori miglioramenti relativi alla protezione venivano apportati durante il processo e le procedure di codifica. Gli strumenti della fase di compilazione rilevano sovraccarichi del buffer e altre potenziali minacce alla sicurezza prima che il codice venga archiviato nel prodotto finale. Naturalmente, è impossibile progettare un prodotto che sia al sicuro da tutte le possibili minacce alla protezione. Nessun sistema può garantire una protezione completa. Tuttavia, poiché lo sviluppo del prodotto ha accolto principi di progettazione sicuri fin dall'inizio, Skype for Business Online incorpora tecnologie di protezione standard del settore come parte fondamentale della sua architettura. 

## <a name="trustworthy-by-default"></a>Affidabile per impostazione predefinita
Le comunicazioni di rete in Skype for Business online sono crittografate per impostazione predefinita. Richiedendo a tutti i server di utilizzare certificati e utilizzando OAUTH, TLS, SRTP (ecure Real-Time Transport Protocol) e altre tecniche di crittografia standard del settore, inclusa la crittografia AES (Advanced Encryption Standard) a 256 bit, tutti i dati di Skype for Business Online sono protetti sulla rete.

## <a name="how-sfbo-handles-common-security-threats"></a>In che modo SfFBO tratta le minacce alla sicurezza comuni
Questa sezione identifica le minacce più comuni alla sicurezza del servizio SfBO e il modo in cui Microsoft attenua ogni minaccia.

### <a name="compromised-key-attack"></a>Attacco con chiave compromessa
Una chiave è un codice segreto o un numero che viene utilizzato per crittografare, decrittografare o convalidare informazioni segrete. Esistono due chiavi sensibili in uso nell'infrastruttura a chiave pubblica (PKI) da prendere in considerazione: la chiave privata che ogni titolare del certificato ha e la chiave della sessione che viene utilizzata dopo una corretta identificazione e scambio di chiavi della sessione da parte dei partner comunicanti. Un attacco con chiave compromessa si verifica quando l'utente malintenzionato determina la chiave privata o la chiave della sessione. Quando l'utente malintenzionato riesce a determinare la chiave, può utilizzarla per decodificare i dati crittografati all'insaputa del mittente.

Skype for Business Online utilizza le funzionalità PKI nel sistema operativo del Server Windows per proteggere i dati della chiave utilizzati per la crittografia nelle connessioni TLS (Transport Layer Security). Le chiavi utilizzate per la crittografia dei file multimediali vengono scambiate tramite le connessioni TLS. 

### <a name="network-denial-of-service-attack"></a>Attacco Denial-of-Service di rete
L'attacco Denial-of-Service si verifica quando l'utente malintenzionato impedisce il normale utilizzo e funzionamento della rete da parte di utenti validi. Utilizzando un attacco Denial-of-Service, l'utente malintenzionato può:
- Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete attaccata per interromperne la normale funzione.
- Inviare una grande quantità di traffico, sovraccaricando il sistema fino a quando non smette di rispondere o risponde lentamente alle richieste legittime.
- Nascondere l'evidenza degli attacchi.
- Impedire agli utenti di accedere alle risorse di rete.

SfBO attenua questi attacchi eseguendo la protezione di rete di Azure DDOS e limitando le richieste dei client dagli stessi endpoint, subnet ed entità federate.

### <a name="eavesdropping"></a>Intercettazione
L'intercettazione può verificarsi quando un utente malintenzionato accede al percorso dei dati in una rete e ha la capacità di monitorare e leggere il traffico. Si chiama anche sniffing o snooping. Se il traffico è in testo normale, l'utente malintenzionato può leggerlo quando accede al percorso. Un esempio è un attacco eseguito controllando un router sul percorso dei dati. 

SfBO usa MUTUAL TLS (MTLS) per le comunicazioni server all'interno di Microsoft 365 o Office 365 e TLS dai client al servizio, rendendo questo attacco molto difficile da raggiungere entro il periodo di tempo in cui una determinata conversazione potrebbe essere attaccata. TLS autentica tutte le parti ed esegue la crittografia di tutto il traffico. Ciò non impedisce l'intercettazione, ma l'utente malintenzionato non può leggere il traffico a meno che la crittografia non sia interrotta.

Il protocollo TURN viene utilizzato per scopi multimediali in tempo reale. Il protocollo TURN non impone la crittografia del traffico e le informazioni che invia sono protette dall'integrità del messaggio. Sebbene sia aperto alle intercettazioni, le informazioni che invia (cioè gli indirizzi IP e la porta) possono essere estratte direttamente, guardando semplicemente gli indirizzi di origine e destinazione dei pacchetti. Il servizio SfBO garantisce che i dati siano validi controllando l'Integrità del Messaggio tramite la chiave derivata da alcune voci, inclusa una password TURN, che non viene mai inviata in chiaro. SRTP viene utilizzato per il traffico multimediale ed è inoltre crittografato.

### <a name="identity-spoofing-ip-address-spoofing"></a>Spoofing d'identità (spoofing dell'indirizzo IP)
Lo spoofing si verifica quando l'utente malintenzionato determina e utilizza un indirizzo IP di una rete, un computer o un componente di rete senza essere autorizzato a farlo. La riuscita dell'attacco consente all'utente malintenzionato di operare come se tale utente malintenzionato fosse l'entità normalmente identificata dall'indirizzo IP. Nel contesto di Microsoft Lync Server 2010, questa situazione entra in gioco solo se un amministratore ha eseguito entrambe le seguenti operazioni:
- Configurato connessioni che supportano solo TCP (Transmission Control Protocol) (sconsigliato, in quanto le comunicazioni TCP non sono crittografate).
- Contrassegnato gli indirizzi IP di tali connessioni come host attendibili. 

Questo è un problema minore per le connessioni TLS (Transport Layer Security), poiché TLS autentica tutte le parti e crittografa tutto il traffico. L'utilizzo di TLS impedisce a un utente malintenzionato di eseguire lo spoofing dell'indirizzo IP su una connessione specifica (ad esempio, connessioni TLS reciproche). Tuttavia, un utente malintenzionato potrebbe comunque falsificare l'indirizzo del server DNS utilizzato da SfBO. Comunque, poiché l'autenticazione in SfBO viene eseguita con certificati, un utente malintenzionato non avrebbe un certificato valido richiesto per falsificare una delle parti nella comunicazione.

### <a name="man-in-the-middle-attack"></a>Attacco MITM (Man-in-the-Middle)
Un attacco man-in-the-middle si verifica quando un utente malintenzionato dirige la comunicazione tra due utenti attraverso il proprio computer senza che i due utenti comunicanti lo sappiano. L'utente malintenzionato può monitorare e leggere il traffico prima di inviarlo al destinatario previsto. Ogni utente della comunicazione, inconsapevolmente, invia e riceve traffico dall'utente malintenzionato, il tutto pensando di comunicare solo con l'utente previsto. Ciò può accadere se un utente malintenzionato riesce a modificare i Servizi di Dominio di Active Directory per aggiungere il proprio server come server attendibile, o modificare il DNS (Domain Name System) per consentire ai client di connettersi tramite l'utente malintenzionato nel percorso verso il server. 

Un attacco man-in-the-middle può verificarsi anche con il traffico multimediale tra due client, tranne che in SfBO point-to-point audio, video e flussi di condivisione delle applicazioni sono crittografati con SRTP, utilizzando chiavi crittografiche negoziate tra i peer tramite SIP (Session Initiation Protocol) su TLS. 

### <a name="rtp-replay-attack"></a>Attacco di riproduzione RTP
Un attacco di riproduzione si verifica quando una trasmissione di file multimediali valida tra due parti viene intercettata e ritrasmessa per scopi illeciti. SfBO utilizza SRTP in combinazione con un protocollo di segnalazione sicuro che protegge le trasmissioni dagli attacchi di ripetizione, abilitando il destinatario a mantenere un indice dei pacchetti RTP già ricevuti e confrontare ogni nuovo pacchetto con quelli già elencati nell'indice.

### <a name="spim"></a>Spim
Spim significa messaggi istantanei commerciali non richiesti o richieste di abbonamento di presenza. Sebbene non sia di per sé una compromissione della rete, è quanto meno fastidioso, può ridurre la disponibilità e la produzione delle risorse e può comportare una compromissione della rete. Un esempio di ciò è lo spimming reciproco degli utenti che si inviano richieste. Gli utenti possono bloccarsi a vicenda per impedirlo, ma con la federazione, se si stabilisce un attacco spim coordinato, può essere difficile da superare a meno che non si disabiliti la federazione per il partner.

### <a name="viruses-and-worms"></a>Virus e worm
Un virus è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive e simili. Per funzionare, un virus ha bisogno di un host, come un file, un'e-mail o un programma. Come un virus, un worm è un'unità di codice, codificata per riprodurre unità di codice aggiuntive e simili, ma che, a differenza di un virus, non ha bisogno di un host. Virus e worm si manifestano principalmente durante i trasferimenti di file tra client, quando gli URL vengono inviati da altri utenti. Se un virus si trova sul computer, può, ad esempio, utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto. Le migliori pratiche standard di protezione del client, come la scansione periodica alla ricerca di virus, possono mitigare questo problema. 

## <a name="personally-identifiable-information"></a>Informazioni di identificazione personale
SfBO ha il potenziale di divulgare informazioni su una rete pubblica che potrebbero essere collegate a un individuo. I tipi di informazioni si possono suddividere in due categorie specifiche:
- Dati di **presenza ottimizzati**&nbsp;&nbsp;&nbsp; I dati di presenza ottimizzati sono informazioni che un utente può scegliere di condividere o non condividere tramite un collegamento a un partner federato o con contatti all'interno di un'organizzazione. Questi dati non sono condivisi con gli utenti di una rete di messaggi istantanei pubblici. Le politiche del client e altre configurazioni del client possono mettere un certo controllo con l'amministratore di sistema. Nel servizio SfBO, è possibile configurare la modalità avanzata di presenza in incognito per un singolo utente per impedire agli utenti di SfBO non presenti nell'elenco dei contatti dell'utente di visualizzare i dati sulla presenza dell'utente. 
- **Dati obbligatoriI dati obbligatori**&nbsp;&nbsp;&nbsp; sono dati necessari per il corretto funzionamento del server o del client. Si tratta di informazioni necessarie a livello di server o di rete ai fini del routing, della manutenzione dello stato e della segnalazione.
Le seguenti tabelle elencano i dati richiesti per il funzionamento di SfBO.

***Tabella 1 - Dati di presenza ottimizzati***

<!--start table here -->



| **Dati**             | **Possibili** **impostazioni**                                                                  |
|:---------------------|:-------------------------------------------------------------------------------------------|
| Dati Personali        | Nome, titolo, società, indirizzo di posta elettronica, fuso orario                                             |
| Numeri di telefono    | Lavoro, mobile, casa                                                                         |
| Informazioni di calendario | Libero/occupato, avviso fuori città, dettagli della riunione (per chi ha accesso al tuo calendario) |
| Stato presenza      | Assente, Disponibile, Occupato, Non disturbare, Offline                                             |
|                      |                                                                                            |

<!-- end of table -->

***Tabella 2 - Dati obbligatori***

<!--start table here -->


| **Dati**             | **Possibili** **impostazioni**                                                                  |
|:---------------------|:-------------------------------------------------------------------------------------------|
| Indirizzo IP   | Indirizzo effettivo del computer o indirizzo NAT                     |
| URI SIP      | <u>david.campbell@contoso.com</u>                               |
| Nome         | David Campbell (come definito in Servizi di dominio Active Directory) |
|              |                                                                 |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Framework di sicurezza per SfBO
Questa sezione fornisce una panoramica degli elementi fondamentali che formano il framework di sicurezza per Microsoft SfBO. Questi elementi sono i seguenti:
- Azure Active Directory (AAD) fornisce un singolo archivio back-end attendibile per gli account utente. 
- L'infrastruttura a chiave pubblica (PKI) utilizza i certificati emessi dalle autorità di certificazione (CA) attendibili per autenticare i server e garantire l'integrità dei dati.
- Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e TLS reciproche (MTLS) abilitano l'autenticazione dell'endpoint e la crittografia della messaggistica istantanea (IM). Point-to-point audio, video e flussi di condivisione delle applicazioni sono crittografati  e l'integrità viene verificata tramite il protocollo SRTP (Secure Real-Time Transport Protocol).
- Protocolli standard del settore per l'autenticazione dell'utente, ove possibile.

Gli argomenti di questa sezione descrivono il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza del servizio SfBO.
 
### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory funziona come servizio directory per Microsoft 365 e Office 365. Archivia tutte le informazioni della directory degli utenti e le assegnazioni dei criteri. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infrastruttura a chiave pubblica per SfBO
Il servizio SfBO si basa su certificati per l'autenticazione del server e per stabilire una catena di fiducia tra client e server e tra i diversi ruoli del server. L'infrastruttura a chiave pubblica (PKI) di Windows Server fornisce l'infrastruttura per stabilire e convalidare questa catena di fiducia.
I certificati sono ID digitali. Identificano un server per nome e ne specificano le proprietà. Per garantire che le informazioni su un certificato siano valide, il certificato deve essere emesso da un'Autorità di Certificazione (CA) che sia attendibile per i client o altri server che si connettono al server. Se il server si connette solo con altri client e server su una rete privata, la CA può essere una CA aziendale. Se il server interagisce con entità esterne alla rete privata, potrebbe essere richiesta una CA pubblica.

Anche se le informazioni sul certificato sono valide, ci deve essere un modo per verificare che il server che presenta il certificato sia effettivamente quello rappresentato dal certificato stesso. È qui che entra in gioco la PKI di Windows.
Ogni certificato è collegato a una chiave pubblica. Il server indicato sul certificato contiene una chiave privata corrispondente di sua esclusiva conoscenza. Un client o un server che si connette utilizza la chiave pubblica per crittografare una parte di informazioni casuali e la invia al server. Se il server decrittografa le informazioni e le restituisce come testo normale, l'entità che si connette può essere certa che il server detenga la chiave privata corrispondente al certificato e pertanto sia il server indicato sul certificato.

#### <a name="crl-distribution-points"></a>Punti di distribuzione CLR
SfBO richiede che tutti i certificati del server contengano uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL, Certificate Revocation List). I punti di distribuzione CRL (CDP) sono posizioni da cui è possibile scaricare i CRL per verificare che il certificato non sia stato revocato dal momento in cui è stato rilasciato e che rientri ancora nel periodo di validità. Un punto di distribuzione CRL è indicato nelle proprietà del certificato come URL ed è HTTP protetto. Il servizio SfBO controlla il CRL con ogni autenticazione del certificato.

#### <a name="enhanced-key-usage"></a>Utilizzo chiavi avanzato
Tutti i componenti del servizio SfBO richiedono che tutti i certificati del server supportino l'utilizzo chiavi avanzato (EKU, Enhanced Key Usage) ai fini dell'autenticazione del server. La configurazione del campo EKU per l'autenticazione del server indica che il certificato è valido ai fini dell'autenticazione dei server. Tale EKU è essenziale per MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS e MTLS per SfBO
I protocolli TLS e MTLS forniscono comunicazioni crittografate e autenticazione dell'endpoint su Internet. SfBO utilizza questi due protocolli per creare la rete di server affidabili e garantire che tutte le comunicazioni su quella rete siano crittografate. Tutte le comunicazioni SIP tra server si verificano su MTLS. Le comunicazioni SIP da client a server si verificano su TLS.

TLS consente agli utenti, tramite il loro software client, di autenticare i server SfBO a cui si connettono. Su una connessione TLS, il client richiede un certificato valido dal server. Per essere valido, il certificato deve essere stato emesso da una CA che sia anche considerata affidabile dal client e il nome DNS del server deve corrispondere al nome DNS sul certificato. Se il certificato è valido, il client utilizza la chiave pubblica nel certificato per crittografare le chiavi di crittografia simmetriche da utilizzare per la comunicazione, quindi solo il proprietario originale del certificato può utilizzare la propria chiave privata per decrittografare il contenuto della comunicazione. La connessione risultante è affidabile e da quel momento non viene contestata da altri server o client affidabili. In questo contesto, il Secure Sockets Layer (SSL) utilizzato con i servizi web può essere associato come basato su TLS.

Le connessioni tra server si basano su TLS reciproco (MTLS) per l'autenticazione reciproca. Su una connessione MTLS, il server che genera un messaggio e il server che lo riceve si scambiano i certificati da una CA reciprocamente attendibile. I certificati dimostrano l'identità di ciascun server all'altro. Nel servizio SfBO, questa procedura è seguita.

TLS e MTLS contribuiscono a prevenire attacchi di intercettazione e attacchi man-in-the-middle. In un attacco man-in-the-middle, l'utente malintenzionato dirige le comunicazioni tra due entità di rete attraverso il computer dell'utente malintenzionato all'insaputa delle due parti. Le specifiche di TLS e SFBO di server attendibili attenuano il rischio di un attacco man-in-the-middle parzialmente sul livello dell'applicazione, utilizzando la crittografia end-to-end coordinata, tramite la crittografia a chiave pubblica tra i due endpoint, e un utente malintenzionato dovrebbe avere un certificato valido e affidabile con la chiave privata corrispondente ed emesso a nome del servizio con cui il client sta comunicando per decrittografare la comunicazione. 

### <a name="encryption-for-sfbo"></a>Crittografia per SfBO
SfBO utilizza TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da un server all'altro richiede MTLS, indipendentemente dal fatto che il traffico sia confinato alla rete interna o attraversi il perimetro della rete interna.

La seguente tabella riassume il protocollo utilizzato da SfBO.

***Tabella 3 - Protezione del traffico***

<!--start table here with header -->




|**Tipologia di traffico**|**Protetto da**|
|:-----|:-----|
|Da server a server|MTLS|
|Da client a server|TLS|
|Messaggistica istantanea e presenza|TLS (se configurato per TLS)|
|Audio e video e condivisione desktop di file multimediali|SRTP|
|Condivisione desktop (segnalazione)|TLS|
|Conferenza Web|TLS|
|Download contenuto della riunione, download rubrica, espansione gruppo di distribuzione|HTTPS|
|||

<!-- end of table -->

#### <a name="media-encryption"></a>Crittografia file multimediali
Il traffico di file multimediali viene crittografato tramite Secure RTP (SRTP), un profilo di Real-Time Transport Protocol (RTP) che offre riservatezza, autenticazione e protezione dagli attacchi di riproduzione al traffico RTP. SRTP utilizza una chiave della sessione generata utilizzando un generatore di numeri casuali sicuro e scambiata utilizzando il canale di segnalazione TLS. Inoltre, i file multimediali che scorrono in entrambe le direzioni tra il Mediation Server e il suo hop successivo interno sono crittografati anche tramite SRTP. 

SfBO genera username/password per l'accesso sicuro ai relay dei file multimediali su TURN. I relay dei file multimediali scambiano nome utente/password su un canale SIP protetto da TLS.

#### <a name="fips"></a>FIPS
SfBO utilizza algoritmi FIPS (Federal Information Processing Standard) per gli scambi di chiavi di crittografia. 

### <a name="user-and-client-authentication"></a>Autenticazione utente e client 
Un utente attendibile è un utente le cui credenziali sono state autenticate da AAD in Microsoft 365 o Office 365. 

L'autenticazione è la fornitura di credenziali utente a un server o servizio affidabile. SfBO utilizza i seguenti protocolli di autenticazione, a seconda dello stato e della posizione dell'utente.
- **Autenticazione moderna** è l'implementazione Microsoft di OAUTH 2.0 per la comunicazione client-server. Abilita funzionalità di sicurezza come l'autenticazione basata su certificati, l'autenticazione a più fattori e l'accesso condizionale. Per utilizzare MA, sia il tenant online, sia i client devono essere abilitati per MA. I tenant SfBO creati dopo maggio 2017 hanno MA abilitata per impostazione predefinita. Per i tenant creati prima di allora, segui le istruzioni qui per attivarla. Tutti i seguenti client supportano MA: client Skype for Business 2015 o 2016, Skype for Business su Mac, client Lync 2013, telefoni IP 3PIP, iOS e Android. 
- **L'ID** organizzazione viene usato quando l'autenticazione moderna non è abilitata (o non è disponibile).
- **Protocollo digest** per i cosiddetti utenti anonimi. Gli utenti anonimi sono utenti esterni che non hanno credenziali Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e possiedono una chiave di conferenza valida. L'autenticazione digest non viene utilizzata per altre interazioni client.

L'autenticazione SfBO consiste di due fasi:
1. Viene stabilita un'associazione di protezione tra il client e il server.
2. Il client e il server utilizzano l'associazione di protezione esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti. I messaggi non autenticati da un client non vengono accettati quando l'autenticazione è abilitata sul server.

L'attendibilità dell'utente è associata a ciascun messaggio che proviene da un utente, non all'identità dell'utente stesso. Il server verifica che ogni messaggio abbia credenziali utente valide. Se le credenziali utente sono valide, il messaggio non viene contestato non solo dal primo server che lo riceve, ma da tutti gli altri server in SfBO.

Gli utenti con credenziali valide emesse da un partner federato sono attendibili ma opzionalmente limitati da vincoli aggiuntivi per cui non possono usufruire dell'intera gamma di privilegi concessi agli utenti interni.

Per l'autenticazione dei contenuti multimediali, anche i protocolli ICE e TURN usano la challenge Digest come descritto nell'RFC su TURN di IETF. Per informazioni dettagliate, vedere [Attraversamento multimediale.](#external-user-av-traffic-traversal)

I certificati client offrono un modo alternativo per l'autenticazione degli utenti da parte di SfBO. Anziché fornire un nome utente e una password, gli utenti hanno un certificato e la chiave privata corrispondente al certificato necessario per risolvere un'autenticazione crittografica. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Strumenti di gestione di Windows PowerShell e SfBO
In SfBO, gli amministratori IT possono gestire il servizio tramite il portale amministratore O365 o utilizzando TRPS (Tenant Remote PowerShell). Gli amministratori del tenant usano l'autenticazione moderna per eseguire l'autenticazione in TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configurazione dell'accesso a SfBO al tuo limite Internet
Per il corretto funzionamento di SfBO (utenti in grado di partecipare a riunioni e così via), i clienti devono configurare l'accesso a Internet in modo che il traffico UDP e TCP in uscita verso i servizi nel cloud SfBO sia consentito. Per altre informazioni, vedere qui: https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 e TCP 443

Le porte UDP 3478-3481 e TCP 443 vengono utilizzate dai client per richiedere il servizio da A/V Edge. Un client utilizza queste due porte per assegnare rispettivamente le porte UDP e TCP a cui la parte remota deve connettersi. Per accedere al servizio A/V Edge, il client deve prima aver stabilito una sessione di segnalazione SIP autenticata con il registrar SfBO per ottenere le credenziali di autenticazione del servizio A/V Edge. Questi valori sono inviati attraverso il canale di segnalazione protetto da TLS e sono generati dal computer per attenuare gli attacchi del dizionario. I client possono quindi utilizzare queste credenziali per l'autenticazione del digest con il servizio A/V Edge per assegnare le porte da utilizzare in una sessione multimediale. Una richiesta di assegnazione iniziale viene inviata dal client e risponde con un messaggio 401 nonce/challenge del servizio A/V Edge. Il client invia una seconda assegnazione contenente il nome utente e un HMAC (Hash Message Authentication Code) del nome utente e nonce. 

È inoltre presente un meccanismo del numero di sequenze per impedire attacchi di riproduzione. Il server calcola l'HMAC previsto in base alla propria conoscenza del nome utente e della password e se i valori HMAC corrispondono, viene eseguita la procedura di assegnazione. Altrimenti, il pacchetto viene eliminato. Questo stesso meccanismo HMAC viene applicato anche ai messaggi successivi all'interno di questa sessione di chiamata. La durata di questo valore di nome utente/password è pari a un massimo di otto ore durante le quali il client riacquisisce un nuovo nome utente/password per le chiamate successive.

### <a name="udptcp-5000059999"></a>UDP/TCP 50.000–59.999
TCP 50.000 in uscita viene utilizzato per SfBO, inclusi condivisione di applicazioni e desktop, trasferimento di file. Gli intervalli di porta 50.000-59.999 UDP/TCP vengono utilizzati per le sessioni multimediali con i partner di Microsoft Office Communications Server 2007 che richiedono il servizio di attraversamento NAT/firewall dal servizio A/V Edge. Poiché il servizio A/V Edge è l'unico processo che utilizza queste porte, la dimensione dell'intervallo delle porte non indica la potenziale superficie di attacco. Una buona pratica di protezione consiste nel minimizzare sempre il numero totale di porte di ascolto non eseguendo servizi di rete non necessari. Se un servizio di rete non è in esecuzione, non è utilizzabile da un utente malintenzionato remoto e la superficie di attacco del computer host viene ridotta. Tuttavia, all'interno di un singolo servizio, la riduzione del numero di porte non offre lo stesso vantaggio. Il software di servizio A/V Edge non è più esposto agli attacchi con 10.000 porte aperte di quanto lo sia con 10. L'assegnazione delle porte all'interno di questo intervallo viene eseguita in modo casuale e le porte non attualmente assegnate non ascoltano i pacchetti.

### <a name="external-user-av-traffic-traversal"></a>Attraversamento traffico A/V utente esterno
L'abilitazione di utenti esterni e utenti interni per lo scambio di file multimediali richiede un servizio Access Edge al fine di gestire la segnalazione SIP necessaria per configurare e interrompere una sessione. Richiede inoltre che il servizio A/V Edge funga da relay per il trasferimento dei file multimediali. La sequenza di chiamate è illustrata nella seguente figura.


![Sequenza di chiamata in Partecipa alla riunione](media/sfbo-call-sequence-security.png) 

1. Un utente riceve un messaggio di posta elettronica contenente un invito a partecipare a una riunione SfBO. L'e-mail contiene una chiave di conferenza e un collegamento URL basato su HTTP alla conferenza. Sia la chiave, sia l'URL sono unici per una determinata riunione.<p>L'utente avvia la procedura di partecipazione facendo clic sull'URL della riunione contenuto nell'e-mail, che avvia un processo di rilevamento del client sul computer dell'utente. Se il client viene rilevato, viene avviato questo client. Se non viene rilevato, l'utente viene reindirizzato al client web.<p/>
2. Il client SfBO invia un INVITO SIP contenente le credenziali dell'utente. Un utente federato o remoto partecipa a una conferenza usando le credenziali aziendali. Per un utente federato, l'INVITO SIP viene prima inviato al suo home server, che autentica l'utente e inoltra l'INVITO a SfBO. Un utente anonimo deve superare passare l'autenticazione del digest.<p>SfBO autentica l'utente remoto o anonimo e avvisa il client. Come indicato nel passaggio 2, gli utenti federati che partecipano a una conferenza vengono autenticati dalla propria azienda.<p/>

3. Il client invia una richiesta INFO per aggiungere l'utente alla conferenza A/V.

    Le conferenze A/V inviano una risposta Aggiungi utente che contiene il token da presentare al servizio A/V Conferencing Edge, tra le altre informazioni.

    [Nota]  Tutto il traffico SIP precedente passava attraverso il servizio Access Edge.

    Il client si connette al server di conferenza A/V, che convalida il token e trasmette la richiesta, che contiene un altro token di autorizzazione, al server di conferenza A/V interno. Il server di conferenza A/V convalida il token di autorizzazione, che ha originariamente rilasciato tramite il canale SIP, per garantire ulteriormente che un utente valido partecipi alla conferenza.

4. Tra il client e A/V Conferencing Server, viene negoziata e impostata una connessione multimediale tramite SRTP.
5. Un utente riceve un messaggio di posta elettronica contenente un invito a partecipare a una riunione SfBO. L'e-mail contiene una chiave di conferenza e un collegamento URL basato su HTTP alla conferenza. Sia la chiave, sia l'URL sono unici per una determinata riunione.

### <a name="federation-safeguards-for-sfbo"></a>Misure di protezione della federazione per SfBO
La federazione offre all'organizzazione la capacità di comunicare con altre organizzazioni per condividere messaggi istantanei e presenza. Nella federazione SfBO è attiva per impostazione predefinita. Tuttavia, gli amministratori del tenant hanno la possibilità di controllare questa funzionalità tramite Microsoft 365 o Amministrazione di Office 365 portale. Vedi altro.

## <a name="addressing-threats-to-sfbo-conferences"></a>Affrontare le minacce alle Conferenze SfBO

SfBO offre agli utenti aziendali la possibilità di creare e partecipare a conferenze web in tempo reale. Enterprise utenti possono anche invitare utenti esterni che non hanno un account AAD, Microsoft 365 o Office 365 a partecipare a queste riunioni. Anche gli utenti impiegati da partner federati con un'identità sicura e autenticata possono partecipare alle riunioni e, se autorizzati a farlo, possono agire da relatori. Gli utenti anonimi non possono creare o partecipare a una riunione come relatori, ma possono essere promossi a relatori dopo l'adesione.

Consentire agli utenti esterni di partecipare alle riunioni SfBO aumenta notevolmente il valore di questa funzionalità, ma comporta anche alcuni rischi per la sicurezza. Per affrontare questi rischi, SfBO fornisce le seguenti misure aggiuntive:
- I ruoli dei partecipanti determinano i privilegi di controllo della conferenza.
- I tipi di partecipante consentono di limitare l'accesso a riunioni specifiche.
- I tipi di riunione definiti determinano quali tipi di partecipanti possono partecipare.
- La programmazione della conferenza è riservata agli utenti che hanno un account AAD e una licenza SfBO.
- Gli utenti anonimi, ovvero non autenticati, che desiderano partecipare a una conferenza in chiamata, compongono uno dei numeri di accesso alla conferenza e quindi ricevono la richiesta di immettere l'ID della conferenza. Anche agli utenti anonimi non autenticati viene richiesto di registrare il proprio nome. Il nome registrato identifica gli utenti non autenticati nella conferenza. Gli utenti anonimi non sono ammessi alla conferenza fino a quando almeno un leader o un utente autenticato non partecipa e non è possibile assegnare loro un ruolo predefinito.

### <a name="participant-roles"></a>Ruoli del partecipante
I partecipanti alla riunione si dividono in tre gruppi, ognuno con i propri privilegi e restrizioni:
- **Organizzatore** &nbsp; &nbsp; L'utente che crea una riunione, sia esonente che per pianificazione. Un organizzatore deve essere un utente aziendale autenticato e avere il controllo su tutti gli aspetti dell'utente finale di una riunione.
-  &nbsp; Relatore &nbsp; Utente autorizzato a presentare informazioni a una riunione, usando qualsiasi supporto supportato. Un organizzatore della riunione è per definizione anche un relatore e determina chi altro possa essere un relatore. Un organizzatore può prendere questa decisione quando è in programma una riunione o mentre la riunione è in corso.
- **Partecipante** &nbsp; &nbsp; Utente invitato a partecipare a una riunione ma che non è autorizzato a fungere da relatore.

Un relatore può anche promuovere un partecipante al ruolo di relatore durante la riunione.

### <a name="participant-types"></a>Tipi di partecipante

I partecipanti alla riunione sono inoltre classificati per posizione e credenziali. È possibile utilizzare entrambe queste caratteristiche per specificare quali utenti possano accedere a riunioni specifiche. Gli utenti possono essere suddivisi nelle seguenti categorie:
1.  **Utenti che appartengono al tenant** &nbsp; &nbsp; Questi utenti hanno una credenziale in Azure Active Directory per il tenant.<br/>
    a. *Inside corpnet:* questi utenti si uniscono dall'interno della rete aziendale.<br/>b. *Utenti remoti*: questi utenti partecipano dall'esterno della rete aziendale. Possono comprendere i dipendenti che lavorano da casa o in viaggio e altri, come dipendenti di fornitori affidabili, a cui sono state concesse credenziali aziendali per le rispettive condizioni d'uso. Gli utenti remoti possono creare e partecipare a conferenze e agire da relatori.
2.  **Utenti che non appartengono al tenant**&nbsp;&nbsp;  Questi utenti non dispongono di credenziali in Azure Active Directory per il tenant.<br/>a. *Utenti federati:* gli utenti federati possiedono credenziali valide con partner federati e vengono quindi trattati come autenticati da SfBO. Gli utenti federati possono partecipare alle conferenze ed essere promossi a relatori dopo che hanno aderito alla riunione, ma non possono creare conferenze in aziende con cui sono federati.<br/>b. *Utenti anonimi*: gli utenti anonimi non hanno un'identità di Active Directory e non sono federati con il tenant. 

I dati dei clienti mostrano che molte conferenze coinvolgono utenti esterni. Queste stesse società desiderano anche rassicurazioni in merito all'identità degli utenti esterni prima di consentire a tali utenti di partecipare a una conferenza. Come descritto nella sezione seguente, SfBO limita l'accesso ai tipi di utenti che sono stati esplicitamente autorizzati e richiede che tutti i tipi di utenti presentino credenziali appropriate quando aderiscono a una riunione.

### <a name="participant-admittance"></a>Ammissione dei partecipanti
In SfBO, gli utenti anonimi vengono trasferiti in una sala d'attesa detta lobby. I relatori possono quindi ammettere questi utenti alla riunione o rifiutarli. Questi utenti vengono trasferiti nella lobby, il leader viene avvisato e gli utenti attendono fino a quando un leader non li accetta o li rifiuta o la loro connessione scade. Mentre sono nella lobby, gli utenti ascoltano musica. 

Per impostazione predefinita, i partecipanti che si collegano dalla PSTN vanno direttamente alla riunione, ma questa opzione può essere modificata per forzare i partecipanti alla chiamata a passare alla lobby.  
Gli organizzatori della riunione controllano se i partecipanti possono partecipare a una riunione senza attendere nella lobby. Ogni riunione può essere configurata in modo da consentire l'accesso utilizzando uno dei seguenti metodi:
- **Solo io, l'organizzatore della riunione**&nbsp;&nbsp; Tutti, tranne l'organizzatore, devono attendere nella lobby fino all'ammissione.
- **Persone che invito della mia società**&nbsp;&nbsp; Chiunque appartenga alla società può partecipare direttamente alla riunione, anche se non invitato.
- **Tutti gli utenti dell'organizzazione** &nbsp; &nbsp; Tutti gli utenti SfBO nel tenant Microsoft 365 o Office 365 possono partecipare alla riunione senza aspettare nella sala d'attesa, anche se non sono presenti nella lista di distribuzione. Tutti gli altri, inclusi tutti gli utenti esterni e anonimi, devono attendere nella lobby fino all'ammissione.
-  &nbsp; Chiunque &nbsp; Chiunque (senza restrizioni) che abbia accesso al collegamento alla riunione accede direttamente alla riunione.
Quando è specificato qualsiasi metodo, tranne Solo l'organizzatore (bloccato), l'organizzatore della riunione può anche specificare che le persone che si collegano per telefono bypassino la lobby. 

### <a name="presenter-capabilities"></a>Funzionalità del relatore
Gli organizzatori della riunione controllano se i partecipanti possono presentare durante una riunione. Ogni riunione può essere configurata in modo da limitare i relatori a una delle seguenti opzioni:
- **Solo organizzatore** &nbsp; &nbsp; Solo l'organizzatore della riunione può presentare.
- **Persone della mia azienda** &nbsp; &nbsp; Tutti gli utenti interni possono presentare.
- **Tutti, incluse le persone esterne all'azienda** &nbsp; &nbsp; Chiunque (senza restrizioni) che partecipa alla riunione può presentare.
- **Persone che scelgo** &nbsp; &nbsp; L'organizzatore della riunione specifica quali utenti possono presentare aggiungendoli a un elenco di relatori.

## <a name="related-topics"></a>Argomenti correlati
[Centro protezione Microsoft](https://microsoft.com/trustcenter)

