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
ms.openlocfilehash: 13fcb074ea5ce90bbe7097bf5c2f1f975de809c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="255c0-102">Requisiti DNS (Domain Name System) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="255c0-103">_**Ultimo argomento modificato:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="255c0-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="255c0-104">Per distribuire Lync Server, è necessario creare record DNS (Domain Name System) che consentono l'individuazione di client e server e, facoltativamente, il supporto per l'accesso automatico dei client, se l'organizzazione vuole supportarla.</span><span class="sxs-lookup"><span data-stu-id="255c0-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="255c0-105">Lync Server utilizza DNS nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="255c0-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="255c0-106">Per individuare i pool o i server interni per le comunicazioni tra server.</span><span class="sxs-lookup"><span data-stu-id="255c0-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="255c0-107">Per consentire ai client di individuare il pool Front end o il server Standard Edition utilizzato per varie transazioni SIP.</span><span class="sxs-lookup"><span data-stu-id="255c0-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="255c0-108">Per consentire ai dispositivi per comunicazioni unificate non connessi di individuare il pool Front end o il server Standard Edition che esegue il servizio Web aggiornamento dispositivi, ottenere gli aggiornamenti e inviare i registri.</span><span class="sxs-lookup"><span data-stu-id="255c0-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="255c0-109">Per consentire ai server e ai client esterni di connettersi ai server perimetrali o al proxy inverso HTTP per i servizi di messaggistica istantanea o di conferenza.</span><span class="sxs-lookup"><span data-stu-id="255c0-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="255c0-110">Consentire ai dispositivi UC esterni di connettersi al servizio Web aggiornamento dispositivi tramite i server perimetrali o il proxy inverso HTTP e ottenere gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="255c0-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="255c0-111">Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="255c0-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="255c0-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="255c0-112">In This Section</span></span>

  - [<span data-ttu-id="255c0-113">Determinare i requisiti DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="255c0-114">Requisiti DNS per i pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="255c0-115">Requisiti DNS per i server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="255c0-116">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="255c0-117">Requisiti DNS per l'accesso automatico dei client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="255c0-118">Requisiti DNS per i dispositivi mobili con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="255c0-119">Bilanciamento del carico DNS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255c0-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

