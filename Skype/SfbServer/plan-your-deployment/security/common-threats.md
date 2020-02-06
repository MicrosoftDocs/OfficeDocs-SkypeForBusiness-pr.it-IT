---
title: Minacce comuni per la sicurezza nell'informatica moderna
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Dato che Skype for Business Server è un sistema di comunicazioni di livello aziendale, dovresti essere consapevole degli attacchi di sicurezza comuni che potrebbero interessare l'infrastruttura e le comunicazioni.
ms.openlocfilehash: 58141a735858d840acbd57e8039aa1c132dbeb8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815674"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Minacce comuni per la sicurezza nell'informatica moderna
 
Dato che Skype for Business Server è un sistema di comunicazioni di livello aziendale, dovresti essere consapevole degli attacchi di sicurezza comuni che potrebbero interessare l'infrastruttura e le comunicazioni.
  
## <a name="compromised-key-attack"></a>Attacco con chiave compromessa

Una chiave è un codice segreto o un numero che viene utilizzato per crittografare, decrittografare o convalidare informazioni segrete. Esistono due tasti sensibili in uso nell'infrastruttura a chiave pubblica (PKI) che deve essere considerata: 
  
- La chiave privata che ha il titolare di ogni certificato
    
- Chiave di sessione usata dopo un corretto scambio di identificazioni e chiavi di sessione da parte dei partner di comunicazione
    
Un attacco con chiave compromessa si verifica quando l'utente malintenzionato determina la chiave privata o la chiave della sessione. Quando l'utente malintenzionato riesce a determinare la chiave, può utilizzarla per decodificare i dati crittografati all'insaputa del mittente.
  
Skype for Business Server usa le funzionalità PKI nel sistema operativo Windows Server per proteggere i dati chiave usati per la crittografia per le connessioni TLS (Transport Layer Security). Le chiavi usate per la crittografia media vengono scambiate tramite connessioni TLS.
  
## <a name="network-denial-of-service-attack"></a>Attacco Denial-of-Service di rete

L'attacco Denial-of-Service si verifica quando l'utente malintenzionato impedisce il normale utilizzo e funzionamento della rete da parte di utenti validi. Questa operazione viene eseguita quando l'aggressore inonda il servizio con richieste legittime che sovraccaricano l'uso del servizio da parte di utenti legittimi. Usando un attacco di negazione del servizio, l'aggressore può eseguire le operazioni seguenti:
  
- Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete attaccata per interromperne la normale funzione.
    
- Inviare una grande quantità di traffico, sovraccaricando il sistema fino a quando non smette di rispondere o risponde lentamente alle richieste legittime.
    
- Nascondere l'evidenza degli attacchi.
    
- Impedire agli utenti di accedere alle risorse di rete.
    
## <a name="eavesdropping-sniffing-snooping"></a>Intercettazioni (sniffing, snooping)

L'intercettazione può verificarsi quando un utente malintenzionato accede al percorso dei dati in una rete e ha la capacità di monitorare e leggere il traffico. Si chiama anche sniffing o snooping. Se il traffico è in testo normale, l'utente malintenzionato può leggerlo quando accede al percorso. Un esempio è un attacco eseguito controllando un router sul percorso dei dati. 
  
Le raccomandazioni e le impostazioni predefinite per il traffico in Skype for Business Server usano Mutual TLS (MTLS) tra server attendibili e TLS da client a server. Questa misura di protezione renderebbe un attacco molto difficile o impossibile da raggiungere entro il periodo di tempo in cui si verifica una determinata conversazione. TLS autentica tutte le parti e crittografa tutto il traffico. Ciò non impedisce l'intercettazione, ma l'utente malintenzionato non può leggere il traffico a meno che la crittografia non sia interrotta.
  
Il protocollo di traslazione Using Relay NAT (TURN) non obbliga il traffico a essere crittografato e le informazioni che sta inviando sono protette dall'integrità dei messaggi. Anche se è aperto alle intercettazioni, le informazioni che invia (ovvero gli indirizzi IP e la porta) possono essere estratte direttamente semplicemente esaminando gli indirizzi di origine e di destinazione dei pacchetti. Il servizio A/V Edge garantisce che i dati siano validi controllando l'integrità del messaggio usando la chiave derivata da alcuni elementi, tra cui una password di attivazione, che non viene mai inviata in testo non crittografato. Se viene usato il protocollo SRTP (Secure Real Time Protocol), anche il traffico multimediale viene crittografato.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Spoofing delle identità (indirizzo IP e spoofing dell'ID chiamante)

Lo spoofing delle identità si verifica quando l'aggressore determina e usa un numero di telefono di un utente valido (ID chiamante) o un indirizzo IP di una rete, un computer o un componente di rete senza essere autorizzato a farlo. Un attacco riuscito consente all'aggressore di operare come se l'aggressore fosse l'entità normalmente identificata dal numero di telefono (ID chiamante) o dall'indirizzo IP.

Nel contesto di Skype for Business Server, l'indirizzo IP spoofing entra in gioco solo se un amministratore ha eseguito entrambe le operazioni seguenti:
  
- Configurato connessioni che supportano solo TCP (Transmission Control Protocol) (sconsigliato, in quanto le comunicazioni TCP non sono crittografate).
    
- Contrassegnato gli indirizzi IP di tali connessioni come host attendibili.
    
Questo è un problema minore per le connessioni TLS (Transport Layer Security), poiché TLS autentica tutte le parti e crittografa tutto il traffico. L'utilizzo di TLS impedisce a un utente malintenzionato di eseguire lo spoofing dell'indirizzo IP su una connessione specifica (ad esempio, connessioni TLS reciproche). Un utente malintenzionato potrebbe comunque falsificare l'indirizzo del server DNS usato da Skype for Business Server. Tuttavia, poiché l'autenticazione in Skype for business viene eseguita con i certificati, un utente malintenzionato non avrebbe un certificato valido necessario per falsificare una delle parti nella comunicazione.

D'altra parte, l'ID chiamante spoofing entra in gioco quando è stato stabilito un trunk SIP tra un provider, un gateway PSTN o un altro sistema PBX e Skype for Business Server. In questi casi, Skype for Business Server non offre alcuna protezione per evitare l'identificazione dello spoofing di ID chiamante. Questo significa che un utente di Skype for business può ricevere una chiamata dal trunk SIP con un ID chiamante contraffatto che Visualizza il numero di telefono o il nome visualizzato (se si applica la ricerca di numeri inversa) di un altro utente di Skype for business. La protezione di questo aspetto deve essere applicata nel gateway lato provider, PSTN o PBX.
  
## <a name="man-in-the-middle-attack"></a>Attacco MITM (Man-in-the-Middle)

Un attacco man-in-the-Middle si verifica quando un utente malintenzionato reindirizza le comunicazioni tra due utenti tramite il computer dell'aggressore senza la conoscenza dei due utenti che la comunicano. L'utente malintenzionato può monitorare e leggere il traffico prima di inviarlo al destinatario previsto. Ogni utente della comunicazione, inconsapevolmente, invia e riceve traffico dall'utente malintenzionato, il tutto pensando di comunicare solo con l'utente previsto. Ciò può accadere se un utente malintenzionato riesce a modificare i Servizi di Dominio di Active Directory per aggiungere il proprio server come server attendibile, o modificare il DNS (Domain Name System) per consentire ai client di connettersi tramite l'utente malintenzionato nel percorso verso il server. Un attacco man-in-the-Middle può verificarsi anche con il traffico multimediale tra due client. In Skype for Business Server, tuttavia, l'audio, il video e la condivisione delle applicazioni, i flussi vengono crittografati con SRTP, usando le chiavi crittografiche che vengono negoziate tra i peer che usano SIP (Session Initiation Protocol) su TLS. I server, ad esempio chat di gruppo, usano HTTPS per migliorare la sicurezza del traffico Web.
  
## <a name="rtp-replay-attack"></a>Attacco di riproduzione RTP

Un attacco di riproduzione si verifica quando una trasmissione di file multimediali valida tra due parti viene intercettata e ritrasmessa per scopi illeciti. SRTP usato in connessione con un protocollo di segnalazione sicura protegge le trasmissioni da attacchi di riproduzione consentendo al destinatario di mantenere un indice dei pacchetti RTP già ricevuti e di confrontare ogni nuovo pacchetto con quelli già elencati nell'indice.
  
## <a name="spim"></a>Spim

Spim significa messaggi istantanei commerciali non richiesti o richieste di abbonamento di presenza. Sebbene non sia di per sé una compromissione della rete, è quanto meno fastidioso, può ridurre la disponibilità e la produzione delle risorse e può comportare una compromissione della rete. Un esempio di ciò è lo spimming reciproco degli utenti che si inviano richieste. Gli utenti possono bloccarsi a vicenda per impedirlo, ma con la federazione, se si stabilisce un attacco spim coordinato, può essere difficile da superare a meno che non si disabiliti la federazione per il partner.
  
## <a name="viruses-and-worms"></a>Virus e worm

Un virus è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive e simili. Per funzionare, un virus ha bisogno di un host, come un file, un'e-mail o un programma. Aworm è un'unità di codice il cui scopo è quello di riprodurre altre unità di codice simili, ma non ha bisogno di un host. Virus e worm si manifestano principalmente durante i trasferimenti di file tra client, quando gli URL vengono inviati da altri utenti. Se un virus si trova sul computer, può, ad esempio, utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto.
  
## <a name="personally-identifiable-information"></a>Informazioni di identificazione personale

Skype for Business Server offre la possibilità di divulgare informazioni su una rete pubblica che potrebbe essere collegata a un singolo utente. I tipi di informazioni si possono suddividere in due categorie specifiche:
  
- **Dati sulla presenza avanzati** I dati sulla presenza avanzata sono informazioni che un utente può scegliere di condividere o non condividere tramite un collegamento a un partner federato o con contatti all'interno di un'organizzazione. Questi dati non sono condivisi con gli utenti di una rete di messaggi istantanei pubblici. Le politiche del client e altre configurazioni del client possono mettere un certo controllo con l'amministratore di sistema. In Skype for Business Server la modalità di privacy avanzata della presenza può essere configurata per un singolo utente per evitare che gli utenti di Skype for business non presenti nell'elenco contatti dell'utente visualizzino le informazioni sulla presenza dell'utente. La modalità di privacy avanzata della presenza non impedisce agli utenti di Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 di visualizzare le informazioni sulla presenza di un utente. Per informazioni dettagliate sulla distribuzione del client e della presenza, vedere [distribuire client per Skype for Business Server](../../deploy/deploy-clients/deploy-clients.md) e [pianificare la messaggistica istantanea e la presenza in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Dati obbligatori** I dati obbligatori sono necessari per il corretto funzionamento del server o del client e non sono sotto il controllo del client o dell'amministrazione di sistema. Si tratta di informazioni necessarie a livello di server o di rete ai fini del routing, della manutenzione dello stato e della segnalazione.
    
Le tabelle seguenti elencano i dati esposti in una rete pubblica.
  
**Dati sulla presenza avanzati**

|**Dati divulgati**|**Impostazioni possibili**|
|:-----|:-----|
|Dati Personali  <br/> |Nome, titolo, società, indirizzo di posta elettronica, fuso orario  <br/> |
|Numeri di telefono  <br/> |Lavoro, mobile, casa  <br/> |
|Informazioni di calendario  <br/> |Libero/occupato, avviso fuori città, dettagli riunione (per coloro che hanno accesso al calendario)  <br/> |
|Stato presenza  <br/> |Assente, Disponibile, Occupato, Non disturbare, Offline  <br/> |
   
**Dati obbligatori**


| **Dati divulgati** | **Informazioni di esempio**                            |
|:-------------------|:---------------------------------------------------|
| Indirizzo IP  <br/>  | Indirizzo effettivo del computer o indirizzo NAT  <br/> |
| URI SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

