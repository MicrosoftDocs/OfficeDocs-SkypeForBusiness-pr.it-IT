---
title: 'Lync Server 2013: supporto del protocollo di rete e IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d413c53f8f6600170cf7ec7bfdcca8b052101eca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="7c252-102">Supporto del protocollo di rete e IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c252-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c252-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7c252-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7c252-104">Lync Server 2013 supporta i protocolli IP e di rete seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c252-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="7c252-105">**Protocolli IP.**    Lync Server 2013 supporta IP versione 4 (IPv4) o IP versione 6 (IPv6) per la rete del server.</span><span class="sxs-lookup"><span data-stu-id="7c252-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c252-106">Lync Server 2013 può funzionare in una rete con doppio stack IP abilitato.</span><span class="sxs-lookup"><span data-stu-id="7c252-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="7c252-107">**Protocolli di trasporto SIP.**    A livello generico, SIP può utilizzare almeno tre tipi di trasporto: UDP (User Datagram Protocol), TCP (Transmission Control Protocol) e TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="7c252-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="7c252-108">Nella configurazione di trasporto SIP predefinita, TLS viene eseguito su TCP.</span><span class="sxs-lookup"><span data-stu-id="7c252-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="7c252-109">TLS viene utilizzato all'interno della rete Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c252-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="7c252-110">Nel perimetro della rete, Lync Server 2013 può interoperare su TCP.</span><span class="sxs-lookup"><span data-stu-id="7c252-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="7c252-111">Lync Server 2013 non supporta UDP per il trasporto SIP perché non soddisfa gli standard minimi per la sicurezza delle comunicazioni aziendali, l'affidabilità e la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="7c252-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="7c252-112">Per informazioni dettagliate, vedere l'articolo del Blog di NextHop, "per UDP o non UDP, ovvero la domanda" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span><span class="sxs-lookup"><span data-stu-id="7c252-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c252-113">Il contenuto di ogni blog e il relativo URL sono soggetti a modifica senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="7c252-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

