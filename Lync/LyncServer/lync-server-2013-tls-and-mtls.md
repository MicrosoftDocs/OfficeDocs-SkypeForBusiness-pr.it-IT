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
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="5d210-102">TLS e MTLS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d210-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d210-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="5d210-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="5d210-104">I protocolli Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) garantiscono comunicazioni crittografate e autenticazione endpoint su Internet.</span><span class="sxs-lookup"><span data-stu-id="5d210-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="5d210-105">Microsoft Lync Server 2013 usa questi due protocolli per creare la rete di server attendibili e per assicurarsi che tutte le comunicazioni tramite la rete siano crittografate.</span><span class="sxs-lookup"><span data-stu-id="5d210-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="5d210-106">Tutte le comunicazioni SIP tra server si verificano su MTLS.</span><span class="sxs-lookup"><span data-stu-id="5d210-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="5d210-107">Le comunicazioni SIP da client a server si verificano su TLS.</span><span class="sxs-lookup"><span data-stu-id="5d210-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="5d210-108">TLS consente agli utenti, tramite il loro software client, di autenticare i server di Lync Server 2013 a cui si connettono.</span><span class="sxs-lookup"><span data-stu-id="5d210-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="5d210-109">Su una connessione TLS, il client richiede un certificato valido dal server.</span><span class="sxs-lookup"><span data-stu-id="5d210-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="5d210-110">Per essere valido, il certificato deve essere stato emesso da una CA che sia anche considerata affidabile dal client e il nome DNS del server deve corrispondere al nome DNS sul certificato.</span><span class="sxs-lookup"><span data-stu-id="5d210-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="5d210-111">Se il certificato è valido, il client utilizza la chiave pubblica nel certificato per crittografare le chiavi di crittografia simmetriche da utilizzare per la comunicazione, quindi solo il proprietario originale del certificato può utilizzare la propria chiave privata per decrittografare il contenuto della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="5d210-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="5d210-112">La connessione risultante è affidabile e da quel momento non viene contestata da altri server o client affidabili.</span><span class="sxs-lookup"><span data-stu-id="5d210-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="5d210-113">In questo contesto, il Secure Sockets Layer (SSL) utilizzato con i servizi web può essere associato come basato su TLS.</span><span class="sxs-lookup"><span data-stu-id="5d210-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="5d210-114">Le connessioni da server a server si basano su MTLS per l'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="5d210-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="5d210-115">Su una connessione MTLS, il server che genera un messaggio e il server che lo riceve si scambiano i certificati da una CA reciprocamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="5d210-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="5d210-116">I certificati dimostrano l'identità di ciascun server all'altro.</span><span class="sxs-lookup"><span data-stu-id="5d210-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="5d210-117">Nelle distribuzioni di Lync Server 2013 i certificati emessi dalla CA dell'organizzazione che si trovano durante il periodo di validità e non revocati dalla CA emittente vengono considerati automaticamente validi da tutti i client e i server interni, poiché tutti i membri di un dominio Active Directory considerare attendibile la CA aziendale in tale dominio.</span><span class="sxs-lookup"><span data-stu-id="5d210-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="5d210-118">Negli scenari federati la CA emittente deve essere considerata attendibile da entrambi i partner federati.</span><span class="sxs-lookup"><span data-stu-id="5d210-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="5d210-119">Ogni partner può usare una CA diversa, se lo si desidera, purché tale CA sia attendibile anche per l'altro partner.</span><span class="sxs-lookup"><span data-stu-id="5d210-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="5d210-120">Questo tipo di attendibilità è più semplice per gli Edge Server che hanno il certificato della CA radice del partner nelle rispettive autorità di certificazione radice attendibili oppure per l'uso di una CA di terze parti considerata attendibile da entrambe le entità.</span><span class="sxs-lookup"><span data-stu-id="5d210-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="5d210-121">TLS e MTLS contribuiscono a prevenire attacchi di intercettazione e attacchi man-in-the-middle.</span><span class="sxs-lookup"><span data-stu-id="5d210-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="5d210-122">In un attacco man-in-the-middle, l'utente malintenzionato dirige le comunicazioni tra due entità di rete attraverso il computer dell'utente malintenzionato all'insaputa delle due parti.</span><span class="sxs-lookup"><span data-stu-id="5d210-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="5d210-123">La specifica TLS e Lync Server 2013 dei server attendibili (solo quelli specificati in Generatore di topologia) mitiga il rischio di un attacco di tipo man-in-Middle parzialmente sul livello dell'applicazione usando la crittografia end-to-end coordinata tramite la crittografia a chiave pubblica tra i due endpoint e un utente malintenzionato dovrebbe avere un certificato valido e attendibile con la chiave privata corrispondente e rilasciato al nome del servizio a cui il client comunica per decrittografare la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="5d210-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="5d210-124">In definitiva, tuttavia, devi seguire le procedure di sicurezza ottimali con l'infrastruttura di rete (in questo caso il DNS aziendale).</span><span class="sxs-lookup"><span data-stu-id="5d210-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="5d210-125">Lync Server 2013 presuppone che il server DNS sia attendibile nello stesso modo in cui i controller di dominio e i cataloghi globali sono considerati attendibili, ma il DNS garantisce un livello di protezione dagli attacchi di hijack del DNS impedendo al server di un aggressore di rispondere correttamente a un richiedere il nome contraffatto.</span><span class="sxs-lookup"><span data-stu-id="5d210-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="5d210-126">La figura seguente mostra a livello elevato il modo in cui Lync Server 2013 USA MTLS per creare una rete di server attendibili.</span><span class="sxs-lookup"><span data-stu-id="5d210-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="5d210-127">**Connessioni attendibili in una rete Lync Server**</span><span class="sxs-lookup"><span data-stu-id="5d210-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="5d210-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="5d210-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

