---
title: "Lync Server 2013: Supporto per l'infrastruttura di certificazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13e04e2e6746dac9c40eaa6df0c3b33d52c6a547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="52b6f-102">Supporto per l'infrastruttura di certificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52b6f-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52b6f-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="52b6f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="52b6f-104">Lync Server 2013 richiede un'infrastruttura a chiave pubblica (PKI) per supportare connessioni TLS (Transport Layer Security) e MTLS (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="52b6f-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="52b6f-105">Per impostazione predefinita, Lync Server 2013 è configurato per l'uso di TLS per le connessioni da client a server.</span><span class="sxs-lookup"><span data-stu-id="52b6f-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="52b6f-106">MTLS viene usato per le connessioni tra server.</span><span class="sxs-lookup"><span data-stu-id="52b6f-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="52b6f-107">I certificati MTLS devono essere emessi da autorità di certificazione (CAs) attendibili per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52b6f-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="52b6f-108">Lync Server supporta i certificati emessi dalle seguenti autorità di certificazione:</span><span class="sxs-lookup"><span data-stu-id="52b6f-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="52b6f-109">Certificati emessi da una CA interna:</span><span class="sxs-lookup"><span data-stu-id="52b6f-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="52b6f-110">CA del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="52b6f-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="52b6f-111">CA del sistema operativo Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="52b6f-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="52b6f-112">CA del sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="52b6f-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="52b6f-113">CA del sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="52b6f-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="52b6f-114">CA del sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="52b6f-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="52b6f-115">Certificati emessi da una CA pubblica</span><span class="sxs-lookup"><span data-stu-id="52b6f-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="52b6f-116">La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato dalle altre applicazioni e prodotti.</span><span class="sxs-lookup"><span data-stu-id="52b6f-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="52b6f-117">Per la versione di 2013, Lync Server 2013 e altri prodotti di Microsoft Server, inclusi Exchange 2013 e SharePoint Server, supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="52b6f-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="52b6f-118">Per informazioni dettagliate, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="52b6f-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="52b6f-119">Per le connessioni da client che usano il sistema operativo Windows 7, il sistema operativo Windows Server 2008 R2 e Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 include il supporto per (ma non richiede) certificati firmati con l'SHA-256 funzione hash crittografico.</span><span class="sxs-lookup"><span data-stu-id="52b6f-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="52b6f-120">Per supportare l'accesso esterno tramite SHA-256, il certificato esterno viene emesso da una CA pubblica tramite SHA-256.</span><span class="sxs-lookup"><span data-stu-id="52b6f-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="52b6f-121">Per informazioni dettagliate sui requisiti dei certificati, vedere [requisiti per l'infrastruttura dei certificati per Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="52b6f-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="52b6f-122">Per informazioni dettagliate sull'uso dei caratteri jolly con i certificati, vedere [supporto di certificati jolly in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="52b6f-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

