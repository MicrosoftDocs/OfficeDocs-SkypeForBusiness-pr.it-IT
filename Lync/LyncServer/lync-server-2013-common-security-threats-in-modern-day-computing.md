---
title: 'Lync Server 2013: minacce comuni per la sicurezza in un computing moderno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e17f9f6dbba30697c72fecf77fbff4bfbdc003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Minacce comuni per la sicurezza nell'informatica moderna

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-09-10_

Poiché Lync Server 2013 è un sistema di comunicazioni di livello aziendale, è necessario essere consapevoli degli attacchi di sicurezza comuni che potrebbero interessare l'infrastruttura e le comunicazioni.

<div>

## <a name="compromised-key-attack"></a>Attacco con chiave compromessa

Una chiave è un codice segreto o un numero che viene utilizzato per crittografare, decrittografare o convalidare informazioni segrete. Esistono due tasti sensibili in uso nell'infrastruttura a chiave pubblica (PKI) che deve essere considerata:.

  - La chiave privata che ha il titolare di ogni certificato

  - Chiave di sessione usata dopo un corretto scambio di identificazioni e chiavi di sessione da parte dei partner di comunicazione

Un attacco con chiave compromessa si verifica quando l'utente malintenzionato determina la chiave privata o la chiave della sessione. Quando l'utente malintenzionato riesce a determinare la chiave, può utilizzarla per decodificare i dati crittografati all'insaputa del mittente.

Lync Server 2013 usa le funzionalità PKI nel sistema operativo Windows Server per proteggere i dati chiave usati per la crittografia per le connessioni TLS (Transport Layer Security). Le chiavi usate per la crittografia media vengono scambiate tramite connessioni TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Attacco Denial-of-Service di rete

L' *attacco Denial of Service* si verifica quando l'aggressore impedisce l'uso normale della rete e la funzione da parte di utenti validi. Questa operazione viene eseguita quando l'aggressore inonda il servizio con richieste legittime che sovraccaricano l'uso del servizio da parte di utenti legittimi. Usando un attacco di negazione del servizio, l'aggressore può eseguire le operazioni seguenti:

  - Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete attaccata per interromperne la normale funzione.

  - Inviare una grande quantità di traffico, sovraccaricando il sistema fino a quando non smette di rispondere o risponde lentamente alle richieste legittime.

  - Nascondere l'evidenza degli attacchi.

  - Impedire agli utenti di accedere alle risorse di rete.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Intercettazioni (sniffing, snooping)

Le *intercettazioni* possono verificarsi quando un utente malintenzionato ottiene l'accesso al percorso dati in una rete e può monitorare e leggere il traffico. Questa operazione è anche denominata *sniffing* o *snooping*. Se il traffico è in testo normale, l'utente malintenzionato può leggerlo quando accede al percorso. Un esempio è un attacco eseguito controllando un router sul percorso dei dati.

Le raccomandazioni e le impostazioni predefinite per il traffico in Microsoft Lync Server 2013 sono l'uso di Mutual TLS (MTLS) tra server attendibili e TLS da client a server. Questa misura di protezione renderebbe un attacco molto difficile o impossibile da raggiungere entro il periodo di tempo in cui si verifica una determinata conversazione. TLS autentica tutte le parti e crittografa tutto il traffico. Ciò non impedisce l'intercettazione, ma l'utente malintenzionato non può leggere il traffico a meno che la crittografia non sia interrotta.

Il protocollo di traslazione Using Relay NAT (TURN) non obbliga il traffico a essere crittografato e le informazioni che sta inviando sono protette dall'integrità dei messaggi. Anche se è aperto alle intercettazioni, le informazioni che invia (ovvero gli indirizzi IP e la porta) possono essere estratte direttamente semplicemente esaminando gli indirizzi di origine e di destinazione dei pacchetti. Il servizio A/V Edge garantisce che i dati siano validi controllando l'integrità del messaggio usando la chiave derivata da alcuni elementi, tra cui una password di attivazione, che non viene mai inviata in testo non crittografato. Se viene usato il protocollo SRTP (Secure Real Time Protocol), anche il traffico multimediale viene crittografato.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Spoofing d'identità (spoofing dell'indirizzo IP)

Lo *spoofing* si verifica quando l'aggressore determina e usa un indirizzo IP di una rete, un computer o un componente di rete senza essere autorizzato a farlo. La riuscita dell'attacco consente all'utente malintenzionato di operare come se tale utente malintenzionato fosse l'entità normalmente identificata dall'indirizzo IP. Nel contesto di Microsoft Lync Server 2013, questa situazione entra in gioco solo se un amministratore ha eseguito entrambe le operazioni seguenti:

  - Configurato connessioni che supportano solo TCP (Transmission Control Protocol) (sconsigliato, in quanto le comunicazioni TCP non sono crittografate).

  - Contrassegnato gli indirizzi IP di tali connessioni come host attendibili.

Questo è un problema minore per le connessioni TLS (Transport Layer Security), poiché TLS autentica tutte le parti e crittografa tutto il traffico. L'utilizzo di TLS impedisce a un utente malintenzionato di eseguire lo spoofing dell'indirizzo IP su una connessione specifica (ad esempio, connessioni TLS reciproche). Un utente malintenzionato potrebbe comunque falsificare l'indirizzo del server DNS usato da Lync Server 2013. Tuttavia, poiché l'autenticazione in Lync viene eseguita con i certificati, un utente malintenzionato non avrebbe un certificato valido necessario per falsificare una delle parti nella comunicazione.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Attacco MITM (Man-in-the-Middle)

Un attacco man-in-the-middle si verifica quando un utente malintenzionato dirige la comunicazione tra due utenti attraverso il proprio computer senza che i due utenti comunicanti lo sappiano. L'utente malintenzionato può monitorare e leggere il traffico prima di inviarlo al destinatario previsto. Ogni utente della comunicazione, inconsapevolmente, invia e riceve traffico dall'utente malintenzionato, il tutto pensando di comunicare solo con l'utente previsto. Ciò può accadere se un utente malintenzionato riesce a modificare i Servizi di Dominio di Active Directory per aggiungere il proprio server come server attendibile, o modificare il DNS (Domain Name System) per consentire ai client di connettersi tramite l'utente malintenzionato nel percorso verso il server. Un attacco man-in-the-Middle può verificarsi anche con il traffico multimediale tra due client. Tuttavia, in Microsoft Lync Server 2013, la condivisione di audio, video e applicazioni, i flussi vengono crittografati con SRTP, usando le chiavi crittografiche che vengono negoziate tra i peer che usano SIP (Session Initiation Protocol) su TLS. I server, ad esempio chat di gruppo, usano HTTPS per migliorare la sicurezza del traffico Web.

</div>

<div>

## <a name="rtp-replay-attack"></a>Attacco di riproduzione RTP

Un *attacco di riproduzione* si verifica quando una trasmissione multimediale valida tra due parti viene intercettata e ritrasmessa per scopi illeciti. SRTP usato in connessione con un protocollo di segnalazione sicura protegge le trasmissioni da attacchi di riproduzione consentendo al destinatario di mantenere un indice dei pacchetti RTP già ricevuti e di confrontare ogni nuovo pacchetto con quelli già elencati nell'indice.

</div>

<div>

## <a name="spim"></a>Spim

*SPIM* è un messaggio istantaneo commerciale non richiesto o una richiesta di sottoscrizione di presenza. Sebbene non sia di per sé una compromissione della rete, è quanto meno fastidioso, può ridurre la disponibilità e la produzione delle risorse e può comportare una compromissione della rete. Un esempio di ciò è lo spimming reciproco degli utenti che si inviano richieste. Gli utenti possono bloccarsi a vicenda per impedirlo, ma con la federazione, se si stabilisce un attacco spim coordinato, può essere difficile da superare a meno che non si disabiliti la federazione per il partner.

</div>

<div>

## <a name="viruses-and-worms"></a>Virus e worm

Un *virus* è un'unità di codice il cui scopo è quello di riprodurre altre unità di codice simili. Per funzionare, un virus ha bisogno di un host, come un file, un'e-mail o un programma. Un *worm* è un'unità di codice il cui scopo è quello di riprodurre altre unità di codice simili, ma non ha bisogno di un host. Virus e worm si manifestano principalmente durante i trasferimenti di file tra client, quando gli URL vengono inviati da altri utenti. Se un virus si trova sul computer, può, ad esempio, utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informazioni di identificazione personale

Microsoft Lync Server 2013 offre la possibilità di divulgare informazioni in una rete pubblica che potrebbe essere collegata a un singolo utente. I tipi di informazioni si possono suddividere in due categorie specifiche:

  - **Dati sulla presenza avanzati** I dati sulla presenza avanzata sono informazioni che un utente può scegliere di condividere o non condividere tramite un collegamento a un partner federato o con contatti all'interno di un'organizzazione. Questi dati non sono condivisi con gli utenti di una rete di messaggi istantanei pubblici. Le politiche del client e altre configurazioni del client possono mettere un certo controllo con l'amministratore di sistema. In Lync Server 2013 la modalità di privacy avanzata della presenza può essere configurata per un singolo utente per impedire agli utenti di Lync non presenti nell'elenco contatti dell'utente di visualizzare le informazioni sulla presenza dell'utente. La modalità di privacy avanzata della presenza non impedisce agli utenti di Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 di visualizzare le informazioni sulla presenza di un utente. Per informazioni dettagliate, vedere [novità per i client in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) nella documentazione introduttiva e [configurazione della modalità di privacy della presenza avanzata in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) nella documentazione relativa alla distribuzione.

  - **Dati obbligatori** I dati obbligatori sono necessari per il corretto funzionamento del server o del client e non sono sotto il controllo del client o dell'amministrazione di sistema. Si tratta di informazioni necessarie a livello di server o di rete ai fini del routing, della manutenzione dello stato e della segnalazione.

Le tabelle seguenti elencano i dati esposti in una rete pubblica.

### <a name="enhanced-presence-data"></a>Dati sulla presenza avanzati

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dati divulgati</th>
<th>Impostazioni possibili</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dati Personali</p></td>
<td><p>Nome, titolo, società, indirizzo di posta elettronica, fuso orario</p></td>
</tr>
<tr class="even">
<td><p>Numeri di telefono</p></td>
<td><p>Lavoro, mobile, casa</p></td>
</tr>
<tr class="odd">
<td><p>Informazioni di calendario</p></td>
<td><p>Libero/occupato, avviso fuori città, dettagli riunione (per coloro che hanno accesso al calendario)</p></td>
</tr>
<tr class="even">
<td><p>Stato presenza</p></td>
<td><p>Assente, Disponibile, Occupato, Non disturbare, Offline</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>Dati obbligatori

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dati divulgati</th>
<th>Informazioni di esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Indirizzo IP</p></td>
<td><p>Indirizzo effettivo del computer o indirizzo NAT</p></td>
</tr>
<tr class="even">
<td><p>URI SIP</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

