---
title: 'Lync Server 2013: requisiti DNS (Domain Name System)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="d0f10-102">Requisiti DNS (Domain Name System) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0f10-103">_**Argomento Ultima modifica:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="d0f10-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="d0f10-104">Per distribuire Lync Server, è necessario creare record DNS (Domain Name System) che consentano l'individuazione di client e server e, facoltativamente, il supporto per l'accesso automatico al client se l'organizzazione vuole supportarlo.</span><span class="sxs-lookup"><span data-stu-id="d0f10-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="d0f10-105">Lync Server usa il DNS nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0f10-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="d0f10-106">Per individuare i server o i pool interni per le comunicazioni da server a server.</span><span class="sxs-lookup"><span data-stu-id="d0f10-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="d0f10-107">Per consentire ai client di individuare il pool Front-end o il server Standard Edition usato per varie transazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="d0f10-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="d0f10-108">Per consentire ai dispositivi Unified Communications (UC) che non hanno eseguito l'accesso di individuare il pool Front-end o il server Standard Edition che esegue il servizio Web Update Device, ottenere gli aggiornamenti e inviare i log.</span><span class="sxs-lookup"><span data-stu-id="d0f10-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="d0f10-109">Per consentire ai server e ai client esterni di connettersi ai server Edge o al proxy inverso HTTP per la messaggistica istantanea o i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="d0f10-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="d0f10-110">Per consentire ai dispositivi UC esterni di connettersi al servizio Web Update per dispositivi tramite Edge Server o il proxy inverso HTTP e ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="d0f10-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="d0f10-111">Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d0f10-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d0f10-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d0f10-112">In This Section</span></span>

  - [<span data-ttu-id="d0f10-113">Determinare i requisiti di DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="d0f10-114">Requisiti DNS per i pool Front-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="d0f10-115">Requisiti DNS per i server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="d0f10-116">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="d0f10-117">Requisiti DNS per l'accesso automatico client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="d0f10-118">Requisiti DNS per la mobilità con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="d0f10-119">Bilanciamento del carico DNS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f10-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

