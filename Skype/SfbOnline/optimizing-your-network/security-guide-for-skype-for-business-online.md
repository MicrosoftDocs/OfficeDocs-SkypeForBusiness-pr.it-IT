---
title: Guida alla sicurezza per Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: ''
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Security
description: Guida alla sicurezza per Skype for Business online <add description>
ms.openlocfilehash: 555a7bd3e4a57c637c0375ea406caeca3c221be7
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "30493915"
---
# <a name="security-and-skype-for-business-online"></a>Sicurezza e Skype for Business in linea

Skype for Business Online (SfBO), as part of the Office 365 service, follows all the security best practices and procedures such as service-level security through defense-in-depth, customer controls within the service, security hardening and operational best practices. Per informazioni dettagliate, vedere Microsoft Trust Center (https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Affidabile per progettazione
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/en-us/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>Affidabile per impostazione predefinita
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>In che modo SfFBO tratta le minacce alla sicurezza comuni
In questa sezione vengono identificati i più comuni minacce alla sicurezza di SfBO Service e come Microsoft attenua ogni minaccia.

### <a name="compromised-key-attack"></a>Attacco con chiave compromessa
Una chiave è un codice segreto o un numero che viene utilizzato per crittografare, decrittografare o convalidare informazioni segrete. Esistono due chiavi sensibili in uso nell'infrastruttura a chiave pubblica (PKI) da prendere in considerazione: la chiave privata che ogni titolare del certificato ha e la chiave della sessione che viene utilizzata dopo una corretta identificazione e scambio di chiavi della sessione da parte dei partner comunicanti. Un attacco con chiave compromessa si verifica quando l'utente malintenzionato determina la chiave privata o la chiave della sessione. Quando l'utente malintenzionato riesce a determinare la chiave, può utilizzarla per decodificare i dati crittografati all'insaputa del mittente.

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>Attacco Denial-of-Service di rete
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete attaccata per interromperne la normale funzione.
- Inviare una grande quantità di traffico, sovraccaricando il sistema fino a quando non smette di rispondere o risponde lentamente alle richieste legittime.
- Nascondere l'evidenza degli attacchi.
- Impedire agli utenti di accedere alle risorse di rete.

SfBO attenua contro gli attacchi mediante l'esecuzione di protezione della rete DDOS Azure e limitando le richieste dei client dall'endpoint stesso, subnet e le entità federate.

### <a name="eavesdropping"></a>Intercettazione
Eavesdropping can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called sniffing or snooping. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path. 

SfBO uses mutual TLS (MTLS) for server communications within O365 and TLS from clients to the service, rendering this attack very difficult to impossible to achieve within the time period in which a given conversation could be attacked. TLS authenticates all parties and encrypts all traffic. This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.

Il protocollo TURN viene utilizzato per scopi multimediali in tempo reale. Il protocollo TURN non impone la crittografia del traffico e le informazioni che invia sono protette dall'integrità del messaggio. Sebbene sia aperto alle intercettazioni, le informazioni che invia (cioè gli indirizzi IP e la porta) possono essere estratte direttamente, guardando semplicemente gli indirizzi di origine e destinazione dei pacchetti. Il servizio SfBO garantisce che i dati siano validi controllando l'Integrità del Messaggio tramite la chiave derivata da alcune voci, inclusa una password TURN, che non viene mai inviata in chiaro. SRTP viene utilizzato per il traffico multimediale ed è inoltre crittografato.

### <a name="identity-spoofing-ip-address-spoofing"></a>Spoofing d'identità (spoofing dell'indirizzo IP)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- Configurato connessioni che supportano solo TCP (Transmission Control Protocol) (sconsigliato, in quanto le comunicazioni TCP non sono crittografate).
- Contrassegnato gli indirizzi IP di tali connessioni come host attendibili. 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>Attacco MITM (Man-in-the-Middle)
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

Un attacco man-in-the-middle può verificarsi anche con il traffico multimediale tra due client, tranne che in SfBO point-to-point audio, video e flussi di condivisione delle applicazioni sono crittografati con SRTP, utilizzando chiavi crittografiche negoziate tra i peer tramite SIP (Session Initiation Protocol) su TLS. 

### <a name="rtp-replay-attack"></a>Attacco di riproduzione RTP
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>Spim
Spim is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.

### <a name="viruses-and-worms"></a>Virus e worm
Un virus è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive e simili. Per funzionare, un virus ha bisogno di un host, come un file, un'e-mail o un programma. Come un virus, un worm è un'unità di codice, codificata per riprodurre unità di codice aggiuntive e simili, ma che, a differenza di un virus, non ha bisogno di un host. Virus e worm si manifestano principalmente durante i trasferimenti di file tra client, quando gli URL vengono inviati da altri utenti. Se un virus si trova sul computer, può, ad esempio, utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto. Le migliori pratiche standard di protezione del client, come la scansione periodica alla ricerca di virus, possono mitigare questo problema. 

## <a name="personally-identifiable-information"></a>Informazioni di identificazione personale
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***Tabella 1 - Dati di presenza ottimizzati***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **Dati**             | **Possibili** **impostazioni**                                                                  |   |
| Dati Personali        | Nome, titolo, società, indirizzo di posta elettronica, fuso orario                                             |   |
| Numeri di telefono    | Lavoro, mobile, casa                                                                         |   |
| Informazioni di calendario | Libero/occupato, avviso fuori città, dettagli della riunione (per chi ha accesso al tuo calendario) |   |
| Stato presenza      | Assente, Disponibile, Occupato, Non disturbare, Offline                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***Tabella 2 - Dati obbligatori***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **Categoria** | **Possibili impostazioni**                                           |   |
| Indirizzo IP   | Indirizzo effettivo del computer o indirizzo NAT                     |   |
| URI SIP      | <u>david.campbell@contoso.com</u>                               |   |
| Nome         | David Campbell (come definito in Servizi di dominio Active Directory) |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Framework di sicurezza per SfBO
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) fornisce un singolo archivio back-end attendibile per gli account utente. 
- L'infrastruttura a chiave pubblica (PKI) utilizza i certificati emessi dalle autorità di certificazione (CA) attendibili per autenticare i server e garantire l'integrità dei dati.
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- Protocolli standard del settore per l'autenticazione dell'utente, ove possibile.

Gli argomenti di questa sezione descrivono come ciascuno di questi elementi fondamentali funziona per migliorare la sicurezza del servizio SfBO.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory functions as the directory service for O365. It stores all user directory information and policy assignments. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infrastruttura a chiave pubblica per SfBO
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>Punti di distribuzione CLR
SfBO richiede che tutti i certificati del server contengano uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL, Certificate Revocation List). I punti di distribuzione CRL (CDP) sono posizioni da cui è possibile scaricare i CRL per verificare che il certificato non sia stato revocato dal momento in cui è stato rilasciato e che rientri ancora nel periodo di validità. Un punto di distribuzione CRL è indicato nelle proprietà del certificato come URL ed è HTTP protetto. Il servizio SfBO controlla il CRL con ogni autenticazione del certificato.

#### <a name="enhanced-key-usage"></a>Utilizzo chiavi avanzato
All components of the SfBO service require all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication. Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers. This EKU is essential for MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS e MTLS per SfBO
TLS and MTLS protocols provide encrypted communications and endpoint authentication on the Internet. SfBO uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted. All SIP communications between servers occur over MTLS. SIP communications from client to server occur over TLS.

TLS enables users, through their client software, to authenticate the SfBO servers to which they connect. On a TLS connection, the client requests a valid certificate from the server. To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate. If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication. The resulting connection is trusted and from that point is not challenged by other trusted servers or clients. Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.

Server-to-server connections rely on mutual TLS (MTLS) for mutual authentication. On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA. The certificates prove the identity of each server to the other. In the SfBO service, this procedure is followed.

TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks. In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party. TLS and SfBO’s specification of trusted servers mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication. 

### <a name="encryption-for-sfbo"></a>Crittografia per SfBO
SfBO uses TLS and MTLS to encrypt instant messages. All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.

La seguente tabella riassume il protocollo utilizzato da SfBO.

***Tabella 3 - Protezione del traffico***

<!--start table here with header -->


|||
|:-----|:-----|
|**Tipologia di traffico**|**Protetto da**|
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
Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. SRTP uses a session key generated by using a secure random number generator and exchanged using the signaling TLS channel. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. 

SfBO generates username/passwords for secure access to media relays over TURN. Media relays exchange the username/password over a TLS-secured SIP channel.

#### <a name="fips"></a>FIPS
SfBO utilizza algoritmi FIPS (Federal Information Processing Standard) per gli scambi di chiavi di crittografia. 

### <a name="user-and-client-authentication"></a>Autenticazione utente e client 
Un utente affidabile è un utente le cui credenziali sono state autenticate da AAD in O365. 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **Autenticazione moderna** è l'implementazione Microsoft di OAUTH 2.0 per la comunicazione client-server. Abilita funzioni di sicurezza quali l'autenticazione basata su certificato O365, l'autenticazione multi-fattore O365 e l'accesso condizionale O365. Per utilizzare MA, sia il tenant online, sia i client devono essere abilitati per MA. I tenant SfBO creati dopo maggio 2017 hanno MA abilitata per impostazione predefinita. Per i tenant creati prima di allora, segui le istruzioni qui per attivarla. Tutti i seguenti client supportano MA: client Skype for Business 2015 o 2016, Skype for Business su Mac, client Lync 2013, telefoni IP 3PIP, iOS e Android. 
- **ID organizzazione** viene utilizzato quando l'autenticazione moderno non è attivata (o non disponibile).
- **Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.

L'autenticazione SfBO consiste di due fasi:
1. Viene stabilita un'associazione di protezione tra il client e il server.
2. The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

Gli utenti con credenziali valide emesse da un partner federato sono attendibili ma opzionalmente limitati da vincoli aggiuntivi per cui non possono usufruire dell'intera gamma di privilegi concessi agli utenti interni.

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

I certificati client costituiscono un'alternativa per gli utenti essere autenticati da SfBO. Invece di fornire un nome utente e password, gli utenti dispongono di un certificato e la chiave privata corrispondente al certificato che è necessario risolvere una richiesta di crittografia. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Strumenti di gestione di Windows PowerShell e SfBO
In SfBO, gli amministratori IT possono gestire il servizio tramite il portale amministratore O365 o utilizzando TRPS (Tenant Remote PowerShell). Gli amministratori dei tenant utilizzano l'autenticazione moderna per l'autenticazione in TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configurazione dell'accesso a SfBO al tuo limite Internet
Per SfBO per il corretto funzionamento (gli utenti in grado di partecipare alle riunioni e così via), i clienti è necessario configurare l'accesso internet in modo che il traffico UDP e TCP in uscita per i servizi di SfBO cloud è consentita. Per maggiori dettagli, consultare: https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 e TCP 443

Il UDP 3478 3481 e le porte TCP 443 vengono utilizzate dai client per richiedere assistenza da A / V Edge Server. Un client utilizza queste due porte per allocare UDP e le porte TCP rispettivamente per la parte remota a cui connettersi. Per accedere A / V Edge Server, il client deve innanzitutto avere stabilito una sessione SfBO Registrar per ottenere un oggetto di segnalazione SIP autenticata / V Edge Server le credenziali di autenticazione. Questi valori vengono inviati attraverso il canale di segnalazione protetto da TLS e vengono generati dal computer per ridurre gli attacchi con dizionario. Client possono quindi utilizzare queste credenziali per l'autenticazione del digest con A / V Edge Server per allocare le porte per l'utilizzo in una sessione multimediale. Una richiesta di allocazione iniziale alla quale viene inviata dal client e ha risposto con un messaggio nonce/401 richiesta da A / V Edge Server. Il client invia una seconda richiesta di allocazione contenente il nome utente e un codice HMAC (Hash Message Authentication Code) hash del nome utente e nonce. 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50.000-59.999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>Attraversamento traffico A/V utente esterno
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![Sequenza di chiamata in Partecipa alla riunione](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>L'utente avvia la procedura di partecipazione facendo clic sull'URL della riunione contenuto nell'e-mail, che avvia un processo di rilevamento del client sul computer dell'utente. Se il client viene rilevato, viene avviato questo client. Se non viene rilevato, l'utente viene reindirizzato al client web.<p/>
2. Il client SfBO invia un INVITO SIP contenente le credenziali dell'utente. Un utente federato o remoto accede a una conferenza utilizzando le credenziali aziendali. Per un utente federato, l'INVITO SIP viene prima inviato al suo home server, che autentica l'utente e inoltra l'INVITO a SfBO. Un utente anonimo deve superare passare l'autenticazione del digest.<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. Il client invia una richiesta INFO per aggiungere l'utente alla conferenza A/V.

    A / conferenze V invia una risposta Aggiungi utente contenente il token da presentare agli A / V Conferencing Edge Server tra le altre informazioni.

    [Nota]  Tutto il traffico SIP precedente è passato attraverso l'Access Edge Server.

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. Tra il client e A / V Conferencing Server, una connessione multimediale viene negoziato e il programma di installazione tramite SRTP.
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>Garanzie di federazione per SfBO
La federazione offre all'organizzazione la capacità di comunicare con altre organizzazioni per condividere messaggi istantanei e presenza. Nella federazione SfBO è attiva per impostazione predefinita. Tuttavia, gli amministratori dei tenant hanno la possibilità di controllare questa funzione tramite il portale amministratore O365. Vedi altro.

## <a name="addressing-threats-to-sfbo-conferences"></a>Affrontare le minacce alle Conferenze SfBO

SfBO provides the capability for enterprise users to create and join real-time Web conferences. Enterprise users can also invite external users who do not have an AAD/O365 account to participate in these meetings. Users who are employed by federated partners with a secure and authenticated identity can also join meetings and, if promoted to do so, can act as presenters. Anonymous users cannot create or join a meeting as a presenter, but they can be promoted to presenter after they join.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- I ruoli dei partecipanti determinano i privilegi di controllo della conferenza.
- I tipi di partecipante consentono di limitare l'accesso a riunioni specifiche.
- I tipi di riunione definiti determinano quali tipi di partecipanti possono partecipare.
- La programmazione della conferenza è riservata agli utenti che hanno un account AAD e una licenza SfBO.
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>Ruoli del partecipante
I partecipanti alla riunione si dividono in tre gruppi, ognuno con i propri privilegi e restrizioni:
- **Raccolta multimediale** &nbsp; &nbsp;Utente che ha creato una riunione, che può essere improvvisata o pianificata. Un organizzatore deve essere un utente enterprise autenticato e dispone del controllo su tutti gli aspetti dell'utente finale di una riunione.
- **Relatore** &nbsp; &nbsp;Un utente autorizzato a presentare le informazioni durante una riunione, utilizzando qualsiasi funzionalità multimediale è supportato. Un organizzatore della riunione è per definizione anche un relatore e determina chi altro possa essere un relatore. Un organizzatore può prendere questa decisione quando è in programma una riunione o mentre la riunione è in corso.
- **Partecipante** &nbsp; &nbsp;Un utente invitato a partecipare a una riunione, ma che non è autorizzato a fungere da relatore.

Un relatore può anche promuovere un partecipante al ruolo di relatore durante la riunione.

### <a name="participant-types"></a>Tipi di partecipante

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **Utenti che appartengono al tenant** &nbsp; &nbsp;Tali utenti dispongono di credenziali di Azure Active Directory per il tenant.<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **Utenti che non appartengono al tenant**&nbsp;&nbsp;  Questi utenti non dispongono di credenziali in Azure Active Directory per il tenant.<br/>r. *Gli utenti federati* , gli utenti federati dispongono di credenziali valide con partner federati e vengono pertanto trattati come utenti autenticati da SfBO. Gli utenti federati possono partecipare a conferenze ed essere promossi a relatori dopo che sono uniti alla riunione, ma non possono creare conferenze nelle organizzazioni con cui sono federati.<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>Ammissione dei partecipanti
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

Per impostazione predefinita, i partecipanti che si collegano dalla PSTN vanno direttamente alla riunione, ma questa opzione può essere modificata per forzare i partecipanti alla chiamata a passare alla lobby.  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **Solo io, l'organizzatore della riunione**&nbsp;&nbsp; Tutti, tranne l'organizzatore, devono attendere nella lobby fino all'ammissione.
- **Persone che invito della mia società**&nbsp;&nbsp; Chiunque appartenga alla società può partecipare direttamente alla riunione, anche se non invitato.
- **Anyone from my organization**&nbsp;&nbsp;All SfBO users in the O365 tenant can join the meeting without waiting in the lobby, even if those who are not on the distribution list. All others, including all external and anonymous users, must wait in the lobby until admitted.
- **Tutti gli utenti**&nbsp;&nbsp;chiunque (non esistono restrizioni) dispone dell'accesso per il collegamento della riunione ottiene direttamente alla riunione.
Quando è specificato qualsiasi metodo, tranne Solo l'organizzatore (bloccato), l'organizzatore della riunione può anche specificare che le persone che si collegano per telefono bypassino la lobby. 

### <a name="presenter-capabilities"></a>Funzionalità del relatore
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **Solo organizzatore**&nbsp;&nbsp;solo l'organizzatore della riunione può agire come relatore.
- **Persone appartenenti alla società**&nbsp;&nbsp;tutti gli utenti interni possono presentare.
- **Tutti, incluse le persone esterne alla società**&nbsp;&nbsp;chiunque (non esistono restrizioni) partecipi alla riunione può agire come relatore.
- **Persone che scelgo**&nbsp;&nbsp; L'organizzatore della riunione specifica quali utenti possono presentare aggiungendoli a un elenco di relatori.

## <a name="related-topics"></a>Argomenti correlati
[Centro protezione di Microsoft](https://microsoft.com/trustcenter)

