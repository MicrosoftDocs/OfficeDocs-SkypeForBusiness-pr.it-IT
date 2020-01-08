---
title: 'Lync Server 2013: Creare record DNS per server proxy inversi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5608e3dd851c943e890fe3f718a38c2df02c1c08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="4eeb7-102">Creare record DNS per server proxy inversi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eeb7-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eeb7-103">_**Argomento Ultima modifica:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="4eeb7-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="4eeb7-104">Creare record DNS esterni che puntano all'interfaccia esterna pubblica di Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server o Internet Information Server Application Request Routing, come descritto in [configurare DNS per il supporto di Edge in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span><span class="sxs-lookup"><span data-stu-id="4eeb7-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="4eeb7-105">Sono necessari record DNS per gli FQDN dei servizi Web esterni per ogni pool, il Director (o il pool di Director) e ogni URL semplice.</span><span class="sxs-lookup"><span data-stu-id="4eeb7-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="4eeb7-106">I record DNS minimi per la risoluzione del client al proxy inverso, devono essere creati i seguenti record:</span><span class="sxs-lookup"><span data-stu-id="4eeb7-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="4eeb7-107">Record host (A) che definiscono i servizi Web esterni pubblicati per gli amministratori e i pool di Director, ad esempio **webdirext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="4eeb7-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="4eeb7-108">Record host (A) che definiscono i servizi Web esterni pubblicati per i servizi Web esterni ospitati in tutti i pool di front end e i ruoli del server Standard Edition (ad esempio, **webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="4eeb7-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="4eeb7-109">Record host (A) per gli URL semplici (ad esempio, **dialin.contoso.com** e **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="4eeb7-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="4eeb7-110">Host (A) record per il record esterno di Lync Discover e fornisce anche il puntatore per l'individuazione automatica per tutte le app Web, tra cui Lync Web App, Scheduler e mobilità (ad esempio, **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="4eeb7-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="4eeb7-111">Record host (A) per l'URL del server Office Web Apps (ad esempio **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="4eeb7-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="4eeb7-112">Per informazioni dettagliate, vedere [proxy inverso di riepilogo DNS in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="4eeb7-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

