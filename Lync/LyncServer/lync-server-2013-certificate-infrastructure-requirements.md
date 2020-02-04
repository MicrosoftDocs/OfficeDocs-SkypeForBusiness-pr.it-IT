---
title: "Lync Server 2013: Requisiti dell'infrastruttura dei certificati"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61205cf4ecdac8eac78820442264286f414095ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="3a0e0-102">Requisiti dell'infrastruttura dei certificati per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a0e0-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a0e0-103">_**Argomento Ultima modifica:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="3a0e0-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="3a0e0-104">Lync Server 2013 richiede un'infrastruttura a chiave pubblica (PKI) per il supporto delle connessioni TLS e Mutual TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="3a0e0-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="3a0e0-105">Lync Server usa i certificati per i seguenti scopi:</span><span class="sxs-lookup"><span data-stu-id="3a0e0-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="3a0e0-106">Connessioni TLS tra client e server</span><span class="sxs-lookup"><span data-stu-id="3a0e0-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="3a0e0-107">Connessioni MTLS tra server</span><span class="sxs-lookup"><span data-stu-id="3a0e0-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="3a0e0-108">Federazione che usa l'individuazione automatica del DNS dei partner</span><span class="sxs-lookup"><span data-stu-id="3a0e0-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="3a0e0-109">Accesso remoto agli utenti per la messaggistica istantanea (IM)</span><span class="sxs-lookup"><span data-stu-id="3a0e0-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="3a0e0-110">Accesso degli utenti esterni a sessioni audio/video (A/V), condivisione applicazioni e conferenze</span><span class="sxs-lookup"><span data-stu-id="3a0e0-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="3a0e0-111">Richieste per dispositivi mobili che usano l'individuazione automatica dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="3a0e0-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="3a0e0-112">Per Lync Server, si applicano i requisiti comuni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a0e0-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="3a0e0-113">Tutti i certificati server devono supportare l'autorizzazione del server (server EKU).</span><span class="sxs-lookup"><span data-stu-id="3a0e0-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="3a0e0-114">Tutti i certificati server devono contenere un punto di distribuzione CRL (CDP).</span><span class="sxs-lookup"><span data-stu-id="3a0e0-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="3a0e0-115">Tutti i certificati devono essere firmati usando un algoritmo di firma supportato dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="3a0e0-116">Lync Server 2013 supporta la famiglia di dimensioni digest SHA-1 e SHA-2 (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="3a0e0-117">Per il supporto del sistema operativo [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002), vedere.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a0e0-118">L'uso dell'algoritmo di firma RSASSA-PSS non è supportato e può comportare errori per i problemi di accesso e inoltro di chiamata, tra gli altri.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="3a0e0-119">La registrazione automatica è supportata per i server interni che gestiscono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="3a0e0-120">La registrazione automatica non è supportata per Lync Server Edge Servers.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="3a0e0-121">Quando si invia una richiesta di certificato basata sul Web a una CA di Windows Server 2003, è necessario inviarla da un computer che utilizza Windows Server 2003 con SP2 o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="3a0e0-122">Tieni presente che anche se KB922706 offre il supporto per la risoluzione dei problemi di registrazione di certificati Web su una registrazione Web di Servizi certificati di Windows Server 2003, non consente di usare Windows Server 2008, Windows Vista o Windows 7 per richiedere un certificato da una CA di Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="3a0e0-123">Sono supportate le lunghezze della chiave di crittografia di 1024, 2048 e 4096.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="3a0e0-124">Sono consigliate le lunghezze delle chiavi di 2048 e superiori.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="3a0e0-125">L'algoritmo digest predefinito o la firma hash è RSA.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="3a0e0-126">Sono supportati\_anche gli algoritmi\_ECDH P256, ECDH\_p384 e ECDH P521.</span><span class="sxs-lookup"><span data-stu-id="3a0e0-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="3a0e0-127">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3a0e0-127">In This Section</span></span>

  - [<span data-ttu-id="3a0e0-128">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a0e0-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="3a0e0-129">Requisiti dei certificati per l'accesso utente esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a0e0-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="3a0e0-130">Requisiti dei certificati per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a0e0-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="3a0e0-131">Requisiti dei certificati per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a0e0-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

