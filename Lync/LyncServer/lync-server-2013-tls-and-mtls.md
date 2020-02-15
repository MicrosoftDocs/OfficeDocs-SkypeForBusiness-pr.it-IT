---
title: 'Lync Server 2013: TLS e MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7681b3394a640a64966e3b9c739ea085e6c0f2f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="f62f6-102">TLS e MTLS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f62f6-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f62f6-103">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f62f6-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f62f6-104">Transport Layer Security (TLS) e i protocolli MTLS (Mutual Transport Layer Security) forniscono comunicazioni crittografate e autenticazione endpoint su Internet.</span><span class="sxs-lookup"><span data-stu-id="f62f6-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="f62f6-105">Microsoft Lync Server 2013 utilizza questi due protocolli per creare la rete di server attendibili e garantire che tutte le comunicazioni sulla rete siano crittografate.</span><span class="sxs-lookup"><span data-stu-id="f62f6-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="f62f6-106">Tutte le comunicazioni SIP tra server avvengono tramite MTLS.</span><span class="sxs-lookup"><span data-stu-id="f62f6-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="f62f6-107">Le comunicazioni SIP da client a server avvengono tramite TLS.</span><span class="sxs-lookup"><span data-stu-id="f62f6-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="f62f6-108">TLS consente agli utenti, tramite il software client, di autenticare i server Lync Server 2013 a cui si connettono.</span><span class="sxs-lookup"><span data-stu-id="f62f6-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="f62f6-109">In una connessione TLS, il client richiede al server un certificato valido.</span><span class="sxs-lookup"><span data-stu-id="f62f6-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="f62f6-110">Per essere valido, il certificato deve essere stato emesso da una CA considerata attendibile anche dal client e il nome DNS del server deve corrispondere al nome DNS nel certificato.</span><span class="sxs-lookup"><span data-stu-id="f62f6-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="f62f6-111">Se il certificato è valido, il client utilizza la chiave pubblica del certificato per crittografare le chiavi di crittografia simmetrica da utilizzare nella comunicazione, in modo che solo il proprietario originale del certificato possa utilizzare la sua chiave privata per decrittografare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="f62f6-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="f62f6-112">La connessione risultante è considerata attendibile e, da questo punto di vista, non riceve richieste di autenticazione da altri client o server trusted.</span><span class="sxs-lookup"><span data-stu-id="f62f6-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="f62f6-113">In questo contesto, SSL (Secure Sockets Layer), utilizzato con i servizi Web, può essere associato come basato su TLS.</span><span class="sxs-lookup"><span data-stu-id="f62f6-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="f62f6-114">Le connessioni da server a server si basano su MTLS per l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="f62f6-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="f62f6-115">In una connessione a MTLS, il server che ha creato un messaggio e il server che lo riceve ricevono i certificati di Exchange da una CA mutuamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="f62f6-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="f62f6-116">I certificati dimostrano l'identità di ogni server all'altro.</span><span class="sxs-lookup"><span data-stu-id="f62f6-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="f62f6-117">Nelle distribuzioni di Lync Server 2013 i certificati emessi dall'autorità di certificazione dell'organizzazione che si trovano durante il periodo di validità e non revocati dall'autorità di certificazione di emissione vengono considerati automaticamente validi da tutti i client e i server interni, poiché tutti i membri di un dominio di Active Directory considerare attendibile l'autorità di certificazione aziendale del dominio.</span><span class="sxs-lookup"><span data-stu-id="f62f6-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="f62f6-118">Negli scenari federati, è necessario che la CA di emissione sia considerata attendibile da entrambi i partner federati.</span><span class="sxs-lookup"><span data-stu-id="f62f6-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="f62f6-119">Ogni partner può utilizzare una CA diversa, se lo si desidera, purché tale CA sia anche considerata attendibile dall'altro partner.</span><span class="sxs-lookup"><span data-stu-id="f62f6-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="f62f6-120">Questa relazione di trust è più semplice per i server perimetrali che dispongono del certificato CA radice del partner nelle rispettive autorità di certificazione radice attendibili o per l'utilizzo di una CA di terze parti considerata attendibile da entrambi gli interlocutori.</span><span class="sxs-lookup"><span data-stu-id="f62f6-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="f62f6-121">TLS e MTLS aiutano a impedire sia gli attacchi di intercettazione che di tipo man-in-the-Middle.</span><span class="sxs-lookup"><span data-stu-id="f62f6-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="f62f6-122">In un attacco man-in-the-Middle, l'utente malintenzionato reindirizza le comunicazioni tra due entità di rete nel computer dell'utente malintenzionato senza la conoscenza di entrambe le parti.</span><span class="sxs-lookup"><span data-stu-id="f62f6-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="f62f6-123">Le specifiche di TLS e Lync Server 2013 dei server attendibili (solo quelle specificate in Generatore di topologie) attenuano il rischio di un attacco man-in-the Middle parzialmente sul livello dell'applicazione utilizzando la crittografia end-to-end coordinata mediante la crittografia a chiave pubblica tra i due endpoint e un utente malintenzionato deve disporre di un certificato valido e attendibile con la chiave privata corrispondente e inviato al nome del servizio al quale il client comunica per decrittografare la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="f62f6-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="f62f6-124">In definitiva, tuttavia, è necessario attenersi alle migliori procedure di sicurezza con l'infrastruttura di rete (in questo caso DNS aziendale).</span><span class="sxs-lookup"><span data-stu-id="f62f6-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="f62f6-125">Lync Server 2013 presuppone che il server DNS sia considerato attendibile nello stesso modo in cui i controller di dominio e i cataloghi globali sono attendibili, ma il DNS fornisce un livello di protezione contro gli attacchi del dirottamento DNS impedendo al server di un utente malintenzionato di rispondere correttamente a un richiesta al nome falsificato.</span><span class="sxs-lookup"><span data-stu-id="f62f6-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="f62f6-126">Nella figura seguente viene illustrato un livello elevato di come Lync Server 2013 utilizza MTLS per creare una rete di server attendibili.</span><span class="sxs-lookup"><span data-stu-id="f62f6-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="f62f6-127">**Connessioni trusted in una rete di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="f62f6-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="f62f6-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="f62f6-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

