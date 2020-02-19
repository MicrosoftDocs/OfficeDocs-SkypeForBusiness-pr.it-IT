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

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="01eb6-102">Minacce alla sicurezza comuni nell'elaborazione di giorni moderni</span><span class="sxs-lookup"><span data-stu-id="01eb6-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01eb6-103">_**Ultimo argomento modificato:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="01eb6-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="01eb6-104">Poiché Lync Server 2013 è un sistema di comunicazione di livello aziendale, è necessario essere a conoscenza di attacchi di sicurezza comuni che potrebbero influire sull'infrastruttura e le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="01eb6-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="01eb6-105">Attacco tramite chiave compromessa</span><span class="sxs-lookup"><span data-stu-id="01eb6-105">Compromised-Key Attack</span></span>

<span data-ttu-id="01eb6-106">Una chiave è un codice o un numero segreto utilizzato per crittografare, decrittografare o convalidare informazioni segrete.</span><span class="sxs-lookup"><span data-stu-id="01eb6-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="01eb6-107">Sono disponibili due tasti sensibili in uso nell'infrastruttura a chiave pubblica (PKI) che devono essere considerati:.</span><span class="sxs-lookup"><span data-stu-id="01eb6-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="01eb6-108">La chiave privata che ogni titolare del certificato ha</span><span class="sxs-lookup"><span data-stu-id="01eb6-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="01eb6-109">La chiave di sessione utilizzata dopo una corretta identificazione e la chiave di sessione di Exchange da parte dei partner che comunicano</span><span class="sxs-lookup"><span data-stu-id="01eb6-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="01eb6-110">Un attacco di compromissione della chiave si verifica quando l'autore dell'attacco riesce a determinare la chiave privata o la chiave di sessione.</span><span class="sxs-lookup"><span data-stu-id="01eb6-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="01eb6-111">In questo caso, l'autore dell'attacco può utilizzare la chiave per decrittografare i dati crittografati all'insaputa del mittente.</span><span class="sxs-lookup"><span data-stu-id="01eb6-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="01eb6-112">Lync Server 2013 utilizza le funzionalità PKI nel sistema operativo Windows Server per proteggere i dati della chiave utilizzati per la crittografia per le connessioni TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="01eb6-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="01eb6-113">Le chiavi utilizzate per la crittografia multimediale vengono scambiate tramite connessioni TLS.</span><span class="sxs-lookup"><span data-stu-id="01eb6-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="01eb6-114">Attacco Denial of Service alla rete</span><span class="sxs-lookup"><span data-stu-id="01eb6-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="01eb6-115">L' *attacco Denial-of-Service* si verifica quando l'utente malintenzionato impedisce l'utilizzo e la funzione normale della rete da parte di utenti validi.</span><span class="sxs-lookup"><span data-stu-id="01eb6-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="01eb6-116">Questa operazione viene fatta quando l'utente malintenzionato inonda il servizio con richieste legittime che sovraccaricano l'utilizzo del servizio da parte di utenti legittimi.</span><span class="sxs-lookup"><span data-stu-id="01eb6-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="01eb6-117">Se si utilizza un attacco Denial of Service, l'utente malintenzionato può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01eb6-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="01eb6-118">Inviare dati non validi alle applicazioni e ai servizi in esecuzione nella rete sottoposta all'attacco per disturbarne il normale funzionamento.</span><span class="sxs-lookup"><span data-stu-id="01eb6-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="01eb6-119">Inviare una grande quantità di traffico, sovraccaricando il sistema finché non smette di rispondere o risponde lentamente a richieste legittime.</span><span class="sxs-lookup"><span data-stu-id="01eb6-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="01eb6-120">Nascondere la prova degli attacchi.</span><span class="sxs-lookup"><span data-stu-id="01eb6-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="01eb6-121">Impedire agli utenti di accedere alle risorse della rete.</span><span class="sxs-lookup"><span data-stu-id="01eb6-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="01eb6-122">Intercettazioni (sniffing, snooping)</span><span class="sxs-lookup"><span data-stu-id="01eb6-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="01eb6-123">L' *intercettazione* può verificarsi quando un utente malintenzionato accede al percorso dei dati in una rete e ha la possibilità di monitorare e leggere il traffico.</span><span class="sxs-lookup"><span data-stu-id="01eb6-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="01eb6-124">Questo è anche chiamato *sniffing* o *snooping*.</span><span class="sxs-lookup"><span data-stu-id="01eb6-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="01eb6-125">Se il traffico è in testo normale, l'autore dell'attacco può leggerlo quando ottiene l'accesso al percorso.</span><span class="sxs-lookup"><span data-stu-id="01eb6-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="01eb6-126">Un esempio è un attacco eseguito controllando un router nel percorso dei dati.</span><span class="sxs-lookup"><span data-stu-id="01eb6-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="01eb6-127">La raccomandazione predefinita e l'impostazione per il traffico all'interno di Microsoft Lync Server 2013 è l'utilizzo di Mutual TLS (MTLS) tra server attendibili e TLS da client a server.</span><span class="sxs-lookup"><span data-stu-id="01eb6-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="01eb6-128">Questa misura di protezione renderebbe un attacco molto difficile o impossibile da raggiungere entro il periodo di tempo in cui si verifica una determinata conversazione.</span><span class="sxs-lookup"><span data-stu-id="01eb6-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="01eb6-129">TLS autentica tutte le parti e crittografa tutto il traffico.</span><span class="sxs-lookup"><span data-stu-id="01eb6-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="01eb6-130">Questo processo non impedisce che si verifichi un attacco eavesdropping, ma l'autore dell'attacco non può leggere il traffico a meno che non venga violata la crittografia.</span><span class="sxs-lookup"><span data-stu-id="01eb6-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="01eb6-131">Il protocollo di traslazione tramite Relay NAT (turno) non impone la crittografia del traffico e le informazioni inviate sono protette dall'integrità dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="01eb6-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="01eb6-132">Anche se è aperto a intercettazioni, le informazioni inviate (ovvero gli indirizzi IP e la porta) possono essere estratte direttamente semplicemente osservando gli indirizzi di origine e di destinazione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="01eb6-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="01eb6-133">Il servizio A/V Edge assicura che i dati siano validi verificando l'integrità del messaggio utilizzando la chiave derivata da alcuni elementi, tra cui una password di trasformazioni, che non viene mai inviata in testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="01eb6-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="01eb6-134">Se viene utilizzato il protocollo SRTP (Secure Real Time Protocol), viene crittografato anche il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="01eb6-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="01eb6-135">Spoofing di identità (spoofing dell'indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="01eb6-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="01eb6-136">Lo *spoofing* si verifica quando l'utente malintenzionato determina e utilizza un indirizzo IP di una rete, un computer o un componente di rete senza essere autorizzato a farlo.</span><span class="sxs-lookup"><span data-stu-id="01eb6-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="01eb6-137">Se l'autore riesce a portare a termine l'attacco, può operare come se fosse l'entità normalmente identificata dall'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="01eb6-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="01eb6-138">Nel contesto di Microsoft Lync Server 2013, questa situazione entra in gioco solo se un amministratore ha eseguito entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01eb6-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="01eb6-139">Ha configurato connessioni che supportano solo TCP (Transmission Control Protocol). Questa operazione è sconsigliata perché le comunicazioni TCP non vengono crittografate.</span><span class="sxs-lookup"><span data-stu-id="01eb6-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="01eb6-140">Ha contrassegnato gli indirizzi IP di tali connessioni come host attendibile.</span><span class="sxs-lookup"><span data-stu-id="01eb6-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="01eb6-141">Il problema non si presenta con le connessioni TLS (Transport Layer Security), in quanto TLS autentica tutte le parti e crittografa tutto il traffico.</span><span class="sxs-lookup"><span data-stu-id="01eb6-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="01eb6-142">L'utilizzo di TLS impedisce all'autore di un attacco di eseguire lo spoofing degli indirizzi PI in una connessione specifica, ad esempio MTLS (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="01eb6-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="01eb6-143">Tuttavia, un utente malintenzionato può ancora falsificare l'indirizzo del server DNS utilizzato da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01eb6-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="01eb6-144">Tuttavia, poiché in Lync l'autenticazione viene eseguita con i certificati, l'autore di un attacco non disporrebbe di un certificato valido necessario per lo spoofing di una delle parti della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="01eb6-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="01eb6-145">Attacco man-in-the-middle</span><span class="sxs-lookup"><span data-stu-id="01eb6-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="01eb6-146">Un attacco man-in-the-middle si verifica quando l'autore di un attacco reinstrada la comunicazione tra due utenti attraverso il proprio computer senza che i due utenti che stanno comunicando ne siano a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="01eb6-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="01eb6-147">L'autore dell'attacco può monitorare e leggere il traffico prima di inviarlo al destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="01eb6-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="01eb6-148">Ogni utente della comunicazione invia e riceve il traffico dall'autore dell'attacco a propria insaputa, pensando di comunicare solo con l'utente previsto.</span><span class="sxs-lookup"><span data-stu-id="01eb6-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="01eb6-149">Questa situazione può verificarsi se l'autore di un attacco può modificare Servizi di dominio Active Directory per aggiungere il server come server trusted o modificare DNS (Domain Name System) per fare in modo che i client si connettano all'autore dell'attacco mentre cercano di raggiungere il server.</span><span class="sxs-lookup"><span data-stu-id="01eb6-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="01eb6-150">Un attacco man-in-the-Middle può verificarsi anche con il traffico multimediale tra due client.</span><span class="sxs-lookup"><span data-stu-id="01eb6-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="01eb6-151">Tuttavia, in Microsoft Lync Server 2013 audio, video e condivisione applicazioni, i flussi vengono crittografati con SRTP, utilizzando le chiavi di crittografia che vengono negoziate tra i peer che utilizzano SIP (Session Initiation Protocol) su TLS.</span><span class="sxs-lookup"><span data-stu-id="01eb6-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="01eb6-152">I server come Group Chat utilizzano HTTPS per aumentare la sicurezza del traffico Web.</span><span class="sxs-lookup"><span data-stu-id="01eb6-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="01eb6-153">Attacco di tipo replay RTP</span><span class="sxs-lookup"><span data-stu-id="01eb6-153">RTP Replay Attack</span></span>

<span data-ttu-id="01eb6-154">Un *attacco di riesecuzione* si verifica quando una trasmissione multimediale valida tra due parti viene intercettata e ritrasmessa per scopi dannosi.</span><span class="sxs-lookup"><span data-stu-id="01eb6-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="01eb6-155">SRTP utilizzato insieme a un protocollo di segnalazione sicuro protegge le trasmissioni da attacchi di tipo replay consentendo al destinatario di mantenere un indice dei pacchetti RTP già ricevuti e di confrontare ogni nuovo pacchetto con quelli già elencati nell'indice.</span><span class="sxs-lookup"><span data-stu-id="01eb6-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="01eb6-156">SPIM</span><span class="sxs-lookup"><span data-stu-id="01eb6-156">Spim</span></span>

<span data-ttu-id="01eb6-157">*SPIM* è messaggi istantanei commerciali non richiesti o richieste di sottoscrizione di presenza.</span><span class="sxs-lookup"><span data-stu-id="01eb6-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="01eb6-158">Sebbene non costituiscano in se stessi una violazione della rete, sono quanto meno fastidiosi, possono ridurre la produttività e la disponibilità delle risorse e provocare una violazione della rete.</span><span class="sxs-lookup"><span data-stu-id="01eb6-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="01eb6-159">Un esempio di questo tipo è l'invio di richieste indesiderate da un utente a un altro.</span><span class="sxs-lookup"><span data-stu-id="01eb6-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="01eb6-160">Ogni utente può bloccare gli altri per evitare questo problema, ma con la federazione, se viene stabilito un attacco coordinato con invio di messaggi istantanei indesiderati, può risultare difficile respingerlo a meno che non si disabiliti la federazione per il partner.</span><span class="sxs-lookup"><span data-stu-id="01eb6-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="01eb6-161">Virus e worm</span><span class="sxs-lookup"><span data-stu-id="01eb6-161">Viruses and Worms</span></span>

<span data-ttu-id="01eb6-162">Un *virus* è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive e simili.</span><span class="sxs-lookup"><span data-stu-id="01eb6-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="01eb6-163">Per funzionare, un virus necessita di un host, ad esempio un file, un messaggio di posta elettronica o un programma.</span><span class="sxs-lookup"><span data-stu-id="01eb6-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="01eb6-164">Un *worm* è un'unità di codice il cui scopo è riprodurre unità di codice aggiuntive e simili, ma non richiede un host.</span><span class="sxs-lookup"><span data-stu-id="01eb6-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="01eb6-165">Virus e worm si presentano principalmente durante il trasferimento di file tra client o quando vengono inviati URL da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="01eb6-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="01eb6-166">Se nel computer in uso è presente un virus, questo può ad esempio utilizzare l'identità dell'utente e inviare messaggi istantanei per suo conto.</span><span class="sxs-lookup"><span data-stu-id="01eb6-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="01eb6-167">Informazioni personali</span><span class="sxs-lookup"><span data-stu-id="01eb6-167">Personally Identifiable Information</span></span>

<span data-ttu-id="01eb6-168">Microsoft Lync Server 2013 è in grado di divulgare informazioni su una rete pubblica che potrebbe essere collegata a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="01eb6-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="01eb6-169">È possibile suddividere i tipi di informazioni in due categorie specifiche:</span><span class="sxs-lookup"><span data-stu-id="01eb6-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="01eb6-170">**Dati sulla presenza avanzata** I dati sulla presenza avanzata sono informazioni che un utente può scegliere di condividere o non condividere tramite un collegamento a un partner federato o ai contatti all'interno di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="01eb6-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="01eb6-171">Questi dati non vengono condivisi con gli utenti di una rete di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="01eb6-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="01eb6-172">Con i criteri client e altre configurazioni dei client, parte del controllo può venire affidato all'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="01eb6-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="01eb6-173">In Lync Server 2013, è possibile configurare la modalità di privacy della presenza avanzata per un singolo utente per impedire agli utenti di Lync nell'elenco contatti dell'utente di visualizzare le informazioni sulla presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="01eb6-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="01eb6-174">La modalità di privacy della presenza avanzata non impedisce agli utenti di Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 di visualizzare le informazioni sulla presenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="01eb6-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="01eb6-175">Per informazioni dettagliate, vedere [What ' s New for clients in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) nella documentazione introduttiva e [configurazione della modalità di privacy della presenza avanzata in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="01eb6-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="01eb6-176">**Dati obbligatori** I dati obbligatori sono necessari per il corretto funzionamento del server o del client e non sono sotto il controllo del client o dell'amministrazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="01eb6-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="01eb6-177">Si tratta di informazioni necessarie a livello di server o di rete ai fini del routing, del mantenimento dello stato e della segnalazione.</span><span class="sxs-lookup"><span data-stu-id="01eb6-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="01eb6-178">Nelle tabelle riportate di seguito sono elencati i dati esposti su una rete pubblica.</span><span class="sxs-lookup"><span data-stu-id="01eb6-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="01eb6-179">Dati sulla presenza avanzata</span><span class="sxs-lookup"><span data-stu-id="01eb6-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01eb6-180">Dati divulgati</span><span class="sxs-lookup"><span data-stu-id="01eb6-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="01eb6-181">Impostazioni possibili</span><span class="sxs-lookup"><span data-stu-id="01eb6-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01eb6-182">Dati personali</span><span class="sxs-lookup"><span data-stu-id="01eb6-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="01eb6-183">Nome, titolo, società, indirizzo di posta elettronica, fuso orario</span><span class="sxs-lookup"><span data-stu-id="01eb6-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01eb6-184">Numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="01eb6-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="01eb6-185">Ufficio, cellulare, abitazione</span><span class="sxs-lookup"><span data-stu-id="01eb6-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01eb6-186">Informazioni del calendario</span><span class="sxs-lookup"><span data-stu-id="01eb6-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="01eb6-187">Informazioni sulla disponibilità, avviso fuori città, dettagli sulle riunioni (per coloro che hanno accesso al calendario)</span><span class="sxs-lookup"><span data-stu-id="01eb6-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01eb6-188">Stato presenza</span><span class="sxs-lookup"><span data-stu-id="01eb6-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="01eb6-189">Non al computer, Disponibile, Occupato, Non disturbare, Non in linea</span><span class="sxs-lookup"><span data-stu-id="01eb6-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="01eb6-190">Dati obbligatori</span><span class="sxs-lookup"><span data-stu-id="01eb6-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01eb6-191">Dati divulgati</span><span class="sxs-lookup"><span data-stu-id="01eb6-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="01eb6-192">Informazioni di esempio</span><span class="sxs-lookup"><span data-stu-id="01eb6-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01eb6-193">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="01eb6-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="01eb6-194">Indirizzo effettivo del computer o indirizzo NAT</span><span class="sxs-lookup"><span data-stu-id="01eb6-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01eb6-195">URI SIP</span><span class="sxs-lookup"><span data-stu-id="01eb6-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="01eb6-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="01eb6-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

