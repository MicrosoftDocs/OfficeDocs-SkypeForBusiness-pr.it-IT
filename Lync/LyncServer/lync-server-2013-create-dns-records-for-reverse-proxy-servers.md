---
title: 'Lync Server 2013: creare record DNS per i server proxy inversi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af1c3179d8101a7e2f9942e15553b5831bce95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532213"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="1ee06-102">Creare record DNS per i server proxy inversi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ee06-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee06-103">_**Ultimo argomento modificato:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="1ee06-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="1ee06-104">Creare record DNS esterni che puntano all'interfaccia esterna pubblica di Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server o Internet Information Server Application Request Routing, come descritto in [configure DNS for Edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span><span class="sxs-lookup"><span data-stu-id="1ee06-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="1ee06-105">Sono necessari record DNS per gli FQDN dei servizi Web esterni per ogni pool, il Director (o il pool di server Director) e ogni URL semplice.</span><span class="sxs-lookup"><span data-stu-id="1ee06-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="1ee06-106">Per la risoluzione dei client nel proxy inverso, è almeno necessario creare i record DNS seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ee06-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="1ee06-107">Record host (A) che definiscono i servizi Web esterni pubblicati per gli amministratori e i pool di server Director (ad esempio, **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1ee06-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="1ee06-108">Record host (A) che definiscono i servizi Web esterni pubblicati per i servizi Web esterni ospitati in tutti i pool Front end e i ruoli del server Standard Edition (ad esempio, **webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1ee06-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="1ee06-109">Record host (A) per gli URL semplici (ad esempio, **dialin.contoso.com** e **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1ee06-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="1ee06-110">Record host (A) per il record esterno di individuazione di Lync e fornisce anche il puntatore all'individuazione automatica per tutte le applicazioni Web, tra cui Lync Web App, utilità di pianificazione e mobilità (ad esempio, **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1ee06-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="1ee06-111">Record host (A) per l'URL del server Office Web Apps (ad esempio **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="1ee06-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="1ee06-112">Per informazioni dettagliate, vedere [DNS Summary-reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="1ee06-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

