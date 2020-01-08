---
title: 'Lync Server 2013: minacce comuni per la sicurezza in un computing moderno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "40981029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="add60-102">Minacce comuni per la sicurezza nell'informatica moderna</span><span class="sxs-lookup"><span data-stu-id="add60-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="add60-103">_**Argomento Ultima modifica:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="add60-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="add60-104">Poiché Lync Server 2013 è un sistema di comunicazioni di livello aziendale, è necessario essere consapevoli degli attacchi di sicurezza comuni che potrebbero interessare l'infrastruttura e le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="add60-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="add60-105">Attacco con chiave compromessa</span><span class="sxs-lookup"><span data-stu-id="add60-105">Compromised-Key Attack</span></span>

<span data-ttu-id="add60-106">Una chiave è un codice segreto o un numero che viene utilizzato per crittografare, decrittografare o convalidare informazioni segrete.</span><span class="sxs-lookup"><span data-stu-id="add60-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="add60-107">Esistono due tasti sensibili in uso nell'infrastruttura a chiave pubblica (PKI) che deve essere considerata:.</span><span class="sxs-lookup"><span data-stu-id="add60-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="add60-108">La chiave privata che ha il titolare di ogni certificato</span><span class="sxs-lookup"><span data-stu-id="add60-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="add60-109">Chiave di sessione usata dopo un corretto scambio di identificazioni e chiavi di sessione da parte dei partner di comunicazione</span><span class="sxs-lookup"><span data-stu-id="add60-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="add60-110">Un attacco con chiave compromessa si verifica quando l'utente malintenzionato determina la chiave privata o la chiave della sessione.</span><span class="sxs-lookup"><span data-stu-id="add60-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="add60-111">Quando l'utente malintenzionato riesce a determinare la chiave, può utilizzarla per decodificare i dati crittografati all'insaputa del mittente.</span><span class="sxs-lookup"><span data-stu-id="add60-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="add60-112">Lync Server 2013 usa le funzionalità PKI nel sistema operativo Windows Server per proteggere i dati chiave usati per la crittografia per le connessioni TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="add60-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="add60-113">Le chiavi usate per la crittografia media vengono scambiate tramite connessioni TLS.</span><span class="sxs-lookup"><span data-stu-id="add60-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="add60-114">Attacco Denial-of-Service di rete</span><span class="sxs-lookup"><span data-stu-id="add60-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="add60-115">L' *attacco Denial of Service* si verifica quando l'aggressore impedisce l'uso normale della rete e la funzione da parte di utenti validi.</span><span class="sxs-lookup"><span data-stu-id="add60-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="add60-116">Questa operazione viene eseguita quando l'aggressore inonda il servizio con richieste legittime che sovraccaricano l'uso del servizio da parte di utenti legittimi.</span><span class="sxs-lookup"><span data-stu-id="add60-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="add60-117">Usando un attacco di negazione del servizio, l'aggressore può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="add60-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="add60-118">Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete attaccata per interromperne la normale funzione.</span><span class="sxs-lookup"><span data-stu-id="add60-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="add60-119">Inviare una grande quantità di traffico, sovraccaricando il sistema fino a quando non smette di rispondere o risponde lentamente alle richieste legittime.</span><span class="sxs-lookup"><span data-stu-id="add60-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="add60-120">Nascondere l'evidenza degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="add60-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="add60-121">Impedire agli utenti di accedere alle risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="add60-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="add60-122">Intercettazioni (sniffing, snooping)</span><span class="sxs-lookup"><span data-stu-id="add60-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="add60-123">Le *intercettazioni* possono verificarsi quando un utente malintenzionato ottiene l'accesso al percorso dati in una rete e può monitorare e leggere il traffico.</span><span class="sxs-lookup"><span data-stu-id="add60-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="add60-124">Questa operazione è anche denominata *sniffing* o *snooping*.</span><span class="sxs-lookup"><span data-stu-id="add60-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="add60-125">Se il traffico è in testo normale, l'utente malintenzionato può leggerlo quando accede al percorso.</span><span class="sxs-lookup"><span data-stu-id="add60-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="add60-126">Un esempio è un attacco eseguito controllando un router sul percorso dei dati.</span><span class="sxs-lookup"><span data-stu-id="add60-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="add60-127">Le raccomandazioni e le impostazioni predefinite per il traffico in Microsoft Lync Server 2013 sono l'uso di Mutual TLS (MTLS) tra server attendibili e TLS da client a server.</span><span class="sxs-lookup"><span data-stu-id="add60-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="add60-128">Questa misura di protezione renderebbe un attacco molto difficile o impossibile da raggiungere entro il periodo di tempo in cui si verifica una determinata conversazione.</span><span class="sxs-lookup"><span data-stu-id="add60-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="add60-129">TLS autentica tutte le parti e crittografa tutto il traffico.</span><span class="sxs-lookup"><span data-stu-id="add60-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="add60-130">Ciò non impedisce l'intercettazione, ma l'utente malintenzionato non può leggere il traffico a meno che la crittografia non sia interrotta.</span><span class="sxs-lookup"><span data-stu-id="add60-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="add60-131">Il protocollo di traslazione Using Relay NAT (TURN) non obbliga il traffico a essere crittografato e le informazioni che sta inviando sono protette dall'integrità dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="add60-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="add60-132">Anche se è aperto alle intercettazioni, le informazioni che invia (ovvero gli indirizzi IP e la porta) possono essere estratte direttamente semplicemente esaminando gli indirizzi di origine e di destinazione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="add60-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="add60-133">Il servizio A/V Edge garantisce che i dati siano validi controllando l'integrità del messaggio usando la chiave derivata da alcuni elementi, tra cui una password di attivazione, che non viene mai inviata in testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="add60-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="add60-134">Se viene usato il protocollo SRTP (Secure Real Time Protocol), anche il traffico multimediale viene crittografato.</span><span class="sxs-lookup"><span data-stu-id="add60-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="add60-135">Spoofing d'identità (spoofing dell'indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="add60-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="add60-136">Lo *spoofing* si verifica quando l'aggressore determina e usa un indirizzo IP di una rete, un computer o un componente di rete senza essere autorizzato a farlo.</span><span class="sxs-lookup"><span data-stu-id="add60-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="add60-137">La riuscita dell'attacco consente all'utente malintenzionato di operare come se tale utente malintenzionato fosse l'entità normalmente identificata dall'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="add60-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="add60-138">Nel contesto di Microsoft Lync Server 2013, questa situazione entra in gioco solo se un amministratore ha eseguito entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="add60-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="add60-139">Configurato connessioni che supportano solo TCP (Transmission Control Protocol) (sconsigliato, in quanto le comunicazioni TCP non sono crittografate).</span><span class="sxs-lookup"><span data-stu-id="add60-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="add60-140">Contrassegnato gli indirizzi IP di tali connessioni come host attendibili.</span><span class="sxs-lookup"><span data-stu-id="add60-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="add60-141">Questo è un problema minore per le connessioni TLS (Transport Layer Security), poiché TLS autentica tutte le parti e crittografa tutto il traffico.</span><span class="sxs-lookup"><span data-stu-id="add60-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="add60-142">L'utilizzo di TLS impedisce a un utente malintenzionato di eseguire lo spoofing dell'indirizzo IP su una connessione specifica (ad esempio, connessioni TLS reciproche).</span><span class="sxs-lookup"><span data-stu-id="add60-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="add60-143">Un utente malintenzionato potrebbe comunque falsificare l'indirizzo del server DNS usato da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="add60-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="add60-144">Tuttavia, poiché l'autenticazione in Lync viene eseguita con i certificati, un utente malintenzionato non avrebbe un certificato valido necessario per falsificare una delle parti nella comunicazione.</span><span class="sxs-lookup"><span data-stu-id="add60-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="add60-145">Attacco MITM (Man-in-the-Middle)</span><span class="sxs-lookup"><span data-stu-id="add60-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="add60-146">Un attacco man-in-the-middle si verifica quando un utente malintenzionato dirige la comunicazione tra due utenti attraverso il proprio computer senza che i due utenti comunicanti lo sappiano.</span><span class="sxs-lookup"><span data-stu-id="add60-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="add60-147">L'utente malintenzionato può monitorare e leggere il traffico prima di inviarlo al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="add60-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="add60-148">Ogni utente della comunicazione, inconsapevolmente, invia e riceve traffico dall'utente malintenzionato, il tutto pensando di comunicare solo con l'utente previsto.</span><span class="sxs-lookup"><span data-stu-id="add60-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="add60-149">Ciò può accadere se un utente malintenzionato riesce a modificare i Servizi di Dominio di Active Directory per aggiungere il proprio server come server attendibile, o modificare il DNS (Domain Name System) per consentire ai client di connettersi tramite l'utente malintenzionato nel percorso verso il server.</span><span class="sxs-lookup"><span data-stu-id="add60-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="add60-150">Un attacco man-in-the-Middle può verificarsi anche con il traffico multimediale tra due client.</span><span class="sxs-lookup"><span data-stu-id="add60-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="add60-151">Tuttavia, in Microsoft Lync Server 2013, la condivisione di audio, video e applicazioni, i flussi vengono crittografati con SRTP, usando le chiavi crittografiche che vengono negoziate tra i peer che usano SIP (Session Initiation Protocol) su TLS.</span><span class="sxs-lookup"><span data-stu-id="add60-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="add60-152">I server, ad esempio chat di gruppo, usano HTTPS per migliorare la sicurezza del traffico Web.</span><span class="sxs-lookup"><span data-stu-id="add60-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="add60-153">Attacco di riproduzione RTP</span><span class="sxs-lookup"><span data-stu-id="add60-153">RTP Replay Attack</span></span>

<span data-ttu-id="add60-154">Un *attacco di riproduzione* si verifica quando una trasmissione multimediale valida tra due parti viene intercettata e ritrasmessa per scopi illeciti.</span><span class="sxs-lookup"><span data-stu-id="add60-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="add60-155">SRTP usato in connessione con un protocollo di segnalazione sicura protegge le trasmissioni da attacchi di riproduzione consentendo al destinatario di mantenere un indice dei pacchetti RTP già ricevuti e di confrontare ogni nuovo pacchetto con quelli già elencati nell'indice.</span><span class="sxs-lookup"><span data-stu-id="add60-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="add60-156">Spim</span><span class="sxs-lookup"><span data-stu-id="add60-156">Spim</span></span>

<span data-ttu-id="add60-157">*SPIM* è un messaggio istantaneo commerciale non richiesto o una richiesta di sottoscrizione di presenza.</span><span class="sxs-lookup"><span data-stu-id="add60-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="add60-158">Sebbene non sia di per sé una compromissione della rete, è quanto meno fastidioso, può ridurre la disponibilità e la produzione delle risorse e può comportare una compromissione della rete.</span><span class="sxs-lookup"><span data-stu-id="add60-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="add60-159">Un esempio di ciò è lo spimming reciproco degli utenti che si inviano richieste.</span><span class="sxs-lookup"><span data-stu-id="add60-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="add60-160">Gli utenti possono bloccarsi a vicenda per impedirlo, ma con la federazione, se si stabilisce un attacco spim coordinato, può essere difficile da superare a meno che non si disabiliti la federazione per il partner.</span><span class="sxs-lookup"><span data-stu-id="add60-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="add60-161">Virus e worm</span><span class="sxs-lookup"><span data-stu-id="add60-161">Viruses and Worms</span></span>

<span data-ttu-id="add60-162">Un *virus* è un'unità di codice il cui scopo è quello di riprodurre altre unità di codice simili.</span><span class="sxs-lookup"><span data-stu-id="add60-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="add60-163">Per funzionare, un virus ha bisogno di un host, come un file, un'e-mail o un programma.</span><span class="sxs-lookup"><span data-stu-id="add60-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="add60-164">Un *worm* è un'unità di codice il cui scopo è quello di riprodurre altre unità di codice simili, ma non ha bisogno di un host.</span><span class="sxs-lookup"><span data-stu-id="add60-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="add60-165">Virus e worm si manifestano principalmente durante i trasferimenti di file tra client, quando gli URL vengono inviati da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="add60-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="add60-166">Se un virus si trova sul computer, può, ad esempio, utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto.</span><span class="sxs-lookup"><span data-stu-id="add60-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="add60-167">Informazioni di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="add60-167">Personally Identifiable Information</span></span>

<span data-ttu-id="add60-168">Microsoft Lync Server 2013 offre la possibilità di divulgare informazioni in una rete pubblica che potrebbe essere collegata a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="add60-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="add60-169">I tipi di informazioni si possono suddividere in due categorie specifiche:</span><span class="sxs-lookup"><span data-stu-id="add60-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="add60-170">**Dati sulla presenza avanzati** I dati sulla presenza avanzata sono informazioni che un utente può scegliere di condividere o non condividere tramite un collegamento a un partner federato o con contatti all'interno di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="add60-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="add60-171">Questi dati non sono condivisi con gli utenti di una rete di messaggi istantanei pubblici.</span><span class="sxs-lookup"><span data-stu-id="add60-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="add60-172">Le politiche del client e altre configurazioni del client possono mettere un certo controllo con l'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="add60-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="add60-173">In Lync Server 2013 la modalità di privacy avanzata della presenza può essere configurata per un singolo utente per impedire agli utenti di Lync non presenti nell'elenco contatti dell'utente di visualizzare le informazioni sulla presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="add60-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="add60-174">La modalità di privacy avanzata della presenza non impedisce agli utenti di Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 di visualizzare le informazioni sulla presenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="add60-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="add60-175">Per informazioni dettagliate, vedere [novità per i client in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) nella documentazione introduttiva e [configurazione della modalità di privacy della presenza avanzata in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="add60-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="add60-176">**Dati obbligatori** I dati obbligatori sono necessari per il corretto funzionamento del server o del client e non sono sotto il controllo del client o dell'amministrazione di sistema.</span><span class="sxs-lookup"><span data-stu-id="add60-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="add60-177">Si tratta di informazioni necessarie a livello di server o di rete ai fini del routing, della manutenzione dello stato e della segnalazione.</span><span class="sxs-lookup"><span data-stu-id="add60-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="add60-178">Le tabelle seguenti elencano i dati esposti in una rete pubblica.</span><span class="sxs-lookup"><span data-stu-id="add60-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="add60-179">Dati sulla presenza avanzati</span><span class="sxs-lookup"><span data-stu-id="add60-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="add60-180">Dati divulgati</span><span class="sxs-lookup"><span data-stu-id="add60-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="add60-181">Impostazioni possibili</span><span class="sxs-lookup"><span data-stu-id="add60-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="add60-182">Dati Personali</span><span class="sxs-lookup"><span data-stu-id="add60-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="add60-183">Nome, titolo, società, indirizzo di posta elettronica, fuso orario</span><span class="sxs-lookup"><span data-stu-id="add60-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add60-184">Numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="add60-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="add60-185">Lavoro, mobile, casa</span><span class="sxs-lookup"><span data-stu-id="add60-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add60-186">Informazioni di calendario</span><span class="sxs-lookup"><span data-stu-id="add60-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="add60-187">Libero/occupato, avviso fuori città, dettagli riunione (per coloro che hanno accesso al calendario)</span><span class="sxs-lookup"><span data-stu-id="add60-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add60-188">Stato presenza</span><span class="sxs-lookup"><span data-stu-id="add60-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="add60-189">Assente, Disponibile, Occupato, Non disturbare, Offline</span><span class="sxs-lookup"><span data-stu-id="add60-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="add60-190">Dati obbligatori</span><span class="sxs-lookup"><span data-stu-id="add60-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="add60-191">Dati divulgati</span><span class="sxs-lookup"><span data-stu-id="add60-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="add60-192">Informazioni di esempio</span><span class="sxs-lookup"><span data-stu-id="add60-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="add60-193">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="add60-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="add60-194">Indirizzo effettivo del computer o indirizzo NAT</span><span class="sxs-lookup"><span data-stu-id="add60-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add60-195">URI SIP</span><span class="sxs-lookup"><span data-stu-id="add60-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="add60-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="add60-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

