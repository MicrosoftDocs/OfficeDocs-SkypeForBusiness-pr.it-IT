---
title: "Lync Server 2013: minacce comuni per la sicurezza nell'elaborazione di giorni moderni"
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
ms.openlocfilehash: 6dffff9cfbc501a8e6a9a79439183966ef0a1956
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>Minacce alla sicurezza comuni nell'elaborazione di giorni moderni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-09-10_

Poiché Lync Server 2013 è un sistema di comunicazione di livello aziendale, è necessario essere a conoscenza di attacchi di sicurezza comuni che potrebbero influire sull'infrastruttura e le comunicazioni.

<div>

## <a name="compromised-key-attack"></a>Attacco tramite chiave compromessa

Una chiave è un codice o un numero segreto utilizzato per crittografare, decrittografare o convalidare informazioni segrete. Sono disponibili due tasti sensibili in uso nell'infrastruttura a chiave pubblica (PKI) che devono essere considerati:.

  - La chiave privata che ogni titolare del certificato ha

  - La chiave di sessione utilizzata dopo una corretta identificazione e la chiave di sessione di Exchange da parte dei partner che comunicano

Un attacco di compromissione della chiave si verifica quando l'autore dell'attacco riesce a determinare la chiave privata o la chiave di sessione. In questo caso, l'autore dell'attacco può utilizzare la chiave per decrittografare i dati crittografati all'insaputa del mittente.

Lync Server 2013 utilizza le funzionalità PKI nel sistema operativo Windows Server per proteggere i dati della chiave utilizzati per la crittografia per le connessioni TLS (Transport Layer Security). Le chiavi utilizzate per la crittografia multimediale vengono scambiate tramite connessioni TLS.

</div>

<div>

## <a name="network-denial-of-service-attack"></a>Attacco Denial of Service alla rete

L' *attacco Denial-of-Service* si verifica quando l'utente malintenzionato impedisce l'utilizzo e la funzione normale della rete da parte di utenti validi. Questa operazione viene fatta quando l'utente malintenzionato inonda il servizio con richieste legittime che sovraccaricano l'utilizzo del servizio da parte di utenti legittimi. Se si utilizza un attacco Denial of Service, l'utente malintenzionato può eseguire le operazioni seguenti:

  - Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete sottoposta all'attacco per disturbarne il normale funzionamento.

  - Inviare una grande quantità di traffico, sovraccaricando il sistema finché non smette di rispondere o risponde lentamente a richieste legittime.

  - Nascondere la prova degli attacchi.

  - Impedire agli utenti di accedere alle risorse della rete.

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>Intercettazioni (sniffing, snooping)

L' *intercettazione* può verificarsi quando un utente malintenzionato accede al percorso dei dati in una rete e ha la possibilità di monitorare e leggere il traffico. Questo è anche chiamato *sniffing* o *snooping*. Se il traffico è in testo normale, l'autore dell'attacco può leggerlo quando ottiene l'accesso al percorso. Un esempio è un attacco eseguito controllando un router nel percorso dei dati.

La raccomandazione predefinita e l'impostazione per il traffico all'interno di Microsoft Lync Server 2013 è l'utilizzo di Mutual TLS (MTLS) tra server attendibili e TLS da client a server. Questa misura di protezione renderebbe un attacco molto difficile o impossibile da raggiungere entro il periodo di tempo in cui si verifica una determinata conversazione. TLS autentica tutte le parti e crittografa tutto il traffico. Questo processo non impedisce che si verifichi un attacco eavesdropping, ma l'autore dell'attacco non può leggere il traffico a meno che non venga violata la crittografia.

Il protocollo di traslazione tramite Relay NAT (turno) non impone la crittografia del traffico e le informazioni inviate sono protette dall'integrità dei messaggi. Anche se è aperto a intercettazioni, le informazioni inviate (ovvero gli indirizzi IP e la porta) possono essere estratte direttamente semplicemente osservando gli indirizzi di origine e di destinazione dei pacchetti. Il servizio A/V Edge assicura che i dati siano validi verificando l'integrità del messaggio utilizzando la chiave derivata da alcuni elementi, tra cui una password di trasformazioni, che non viene mai inviata in testo non crittografato. Se viene utilizzato il protocollo SRTP (Secure Real Time Protocol), viene crittografato anche il traffico multimediale.

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>Spoofing di identità (spoofing dell'indirizzo IP)

Lo *spoofing* si verifica quando l'utente malintenzionato determina e utilizza un indirizzo IP di una rete, un computer o un componente di rete senza essere autorizzato a farlo. Se l'autore riesce a portare a termine l'attacco, può operare come se fosse l'entità normalmente identificata dall'indirizzo IP. Nel contesto di Microsoft Lync Server 2013, questa situazione entra in gioco solo se un amministratore ha eseguito entrambe le operazioni seguenti:

  - Ha configurato connessioni che supportano solo TCP (Transmission Control Protocol). Questa operazione è sconsigliata perché le comunicazioni TCP non vengono crittografate.

  - Ha contrassegnato gli indirizzi IP di tali connessioni come host attendibile.

Il problema non si presenta con le connessioni TLS (Transport Layer Security), in quanto TLS autentica tutte le parti e crittografa tutto il traffico. L'utilizzo di TLS impedisce all'autore di un attacco di eseguire lo spoofing degli indirizzi PI in una connessione specifica, ad esempio MTLS (Mutual TLS). Tuttavia, un utente malintenzionato può ancora falsificare l'indirizzo del server DNS utilizzato da Lync Server 2013. Tuttavia, poiché in Lync l'autenticazione viene eseguita con i certificati, l'autore di un attacco non disporrebbe di un certificato valido necessario per lo spoofing di una delle parti della comunicazione.

</div>

<div>

## <a name="man-in-the-middle-attack"></a>Attacco man-in-the-middle

Un attacco man-in-the-middle si verifica quando l'autore di un attacco reinstrada la comunicazione tra due utenti attraverso il proprio computer senza che i due utenti che stanno comunicando ne siano a conoscenza. L'autore dell'attacco può monitorare e leggere il traffico prima di inviarlo al destinatario previsto. Ogni utente della comunicazione invia e riceve il traffico dall'autore dell'attacco a propria insaputa, pensando di comunicare solo con l'utente previsto. Questa situazione può verificarsi se l'autore di un attacco può modificare Servizi di dominio Active Directory per aggiungere il server come server trusted o modificare DNS (Domain Name System) per fare in modo che i client si connettano all'autore dell'attacco mentre cercano di raggiungere il server. Un attacco man-in-the-Middle può verificarsi anche con il traffico multimediale tra due client. Tuttavia, in Microsoft Lync Server 2013 audio, video e condivisione applicazioni, i flussi vengono crittografati con SRTP, utilizzando le chiavi di crittografia che vengono negoziate tra i peer che utilizzano SIP (Session Initiation Protocol) su TLS. I server come Group Chat utilizzano HTTPS per aumentare la sicurezza del traffico Web.

</div>

<div>

## <a name="rtp-replay-attack"></a>Attacco di tipo replay RTP

Un *attacco di riesecuzione* si verifica quando una trasmissione multimediale valida tra due parti viene intercettata e ritrasmessa per scopi dannosi. SRTP utilizzato insieme a un protocollo di segnalazione sicuro protegge le trasmissioni da attacchi di tipo replay consentendo al destinatario di mantenere un indice dei pacchetti RTP già ricevuti e di confrontare ogni nuovo pacchetto con quelli già elencati nell'indice.

</div>

<div>

## <a name="spim"></a>SPIM

*SPIM* è messaggi istantanei commerciali non richiesti o richieste di sottoscrizione di presenza. Sebbene non costituiscano in se stessi una violazione della rete, sono quanto meno fastidiosi, possono ridurre la produttività e la disponibilità delle risorse e provocare una violazione della rete. Un esempio di questo tipo è l'invio di richieste indesiderate da un utente a un altro. Ogni utente può bloccare gli altri per evitare questo problema, ma con la federazione, se viene stabilito un attacco coordinato con invio di messaggi istantanei indesiderati, può risultare difficile respingerlo a meno che non si disabiliti la federazione per il partner.

</div>

<div>

## <a name="viruses-and-worms"></a>Virus e worm

Un *virus* è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive e simili. Per funzionare, un virus necessita di un host, ad esempio un file, un messaggio di posta elettronica o un programma. Un *worm* è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive e simili, ma non richiede un host. Virus e worm si presentano principalmente durante il trasferimento di file tra client o quando vengono inviati URL da altri utenti. Se nel computer in uso è presente un virus, questo può ad esempio utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto.

</div>

<div>

## <a name="personally-identifiable-information"></a>Informazioni personali

Microsoft Lync Server 2013 è in grado di divulgare informazioni su una rete pubblica che potrebbe essere collegata a un singolo utente. È possibile suddividere i tipi di informazioni in due categorie specifiche:

  - **Dati sulla presenza avanzata** I dati sulla presenza avanzata sono informazioni che un utente può scegliere di condividere o non condividere tramite un collegamento a un partner federato o ai contatti all'interno di un'organizzazione. Questi dati non vengono condivisi con gli utenti di una rete di messaggistica istantanea pubblica. Con i criteri client e altre configurazioni dei client, parte del controllo può venire affidato all'amministratore di sistema. In Lync Server 2013, è possibile configurare la modalità di privacy della presenza avanzata per un singolo utente per impedire agli utenti di Lync nell'elenco contatti dell'utente di visualizzare le informazioni sulla presenza dell'utente. La modalità di privacy della presenza avanzata non impedisce agli utenti di Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 di visualizzare le informazioni sulla presenza di un utente. Per informazioni dettagliate, vedere [What ' s New for clients in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) nella documentazione introduttiva e [configurazione della modalità di privacy della presenza avanzata in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) nella documentazione relativa alla distribuzione.

  - **Dati obbligatori** I dati obbligatori sono necessari per il corretto funzionamento del server o del client e non sono sotto il controllo del client o dell'amministrazione del sistema. Si tratta di informazioni necessarie a livello di server o di rete ai fini del routing, del mantenimento dello stato e della segnalazione.

Nelle tabelle riportate di seguito sono elencati i dati esposti su una rete pubblica.

### <a name="enhanced-presence-data"></a>Dati sulla presenza avanzata

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
<td><p>Dati personali</p></td>
<td><p>Nome, titolo, società, indirizzo di posta elettronica, fuso orario</p></td>
</tr>
<tr class="even">
<td><p>Numeri di telefono</p></td>
<td><p>Ufficio, cellulare, abitazione</p></td>
</tr>
<tr class="odd">
<td><p>Informazioni del calendario</p></td>
<td><p>Informazioni sulla disponibilità, avviso fuori città, dettagli sulle riunioni (per coloro che hanno accesso al calendario)</p></td>
</tr>
<tr class="even">
<td><p>Stato presenza</p></td>
<td><p>Non al computer, Disponibile, Occupato, Non disturbare, Non in linea</p></td>
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

