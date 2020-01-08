---
title: "Lync Server 2013: pianificazione per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d8ef1-102">Pianificazione per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8ef1-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8ef1-103">_**Argomento Ultima modifica:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="d8ef1-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="d8ef1-104">L'individuazione automatica è stata introdotta per Lync Server nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="d8ef1-105">Lo scopo principale di questa implementazione iniziale di individuazione automatica consiste nel creare un mezzo per Lync mobile per individuare il servizio di mobilità (MCX).</span><span class="sxs-lookup"><span data-stu-id="d8ef1-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="d8ef1-106">Il servizio di individuazione automatica in Lync Server 2013 è ora un servizio usato da tutti i client per individuare i servizi server e utente.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="d8ef1-107">Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito su direttori e server front-end.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d8ef1-108">Per una maggiore comprensione tecnica dell'individuazione automatica e delle comunicazioni ai client, vedere informazioni sull' <A href="lync-server-2013-understanding-autodiscover.md">individuazione automatica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="d8ef1-109">La mobilità è ancora uno scenario distinto e i servizi di mobilità richiedono comunque una pianificazione speciale.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="d8ef1-110">Per ulteriori informazioni, vedere <A href="lync-server-2013-planning-for-mobility.md">pianificazione della mobilità in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d8ef1-111">Quando l'individuazione automatica è stata introdotta in Lync Server 2010, sono stati compromessi da eseguire per implementare un servizio che richiedeva potenziali modifiche al certificato alle distribuzioni del server esistenti.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="d8ef1-112">L'individuazione automatica può essere usata tramite la porta TCP 443 per HTTPS o tramite la porta TCP 80 per HTTP.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="d8ef1-113">Se è stata presa la decisione di usare HTTPS, i certificati su proxy inverso, direttori e server front-end devono essere ristampati per contenere i record necessari `lyncdiscover.<domain>` e `lyncdiscoverinternal.<domain>` DNS.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="d8ef1-114">Se si decide di usare HTTP, la ristampa dei certificati può essere evitata usando i record CNAME DNS (o alias) per usare i nomi esistenti nei certificati.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="d8ef1-115">L'uso di HTTP significava che le comunicazioni iniziali non erano crittografate.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="d8ef1-116">Poiché Lync Server 2013 usa l'individuazione automatica per tutti i client, lo scenario principale è l'uso esclusivo di HTTPS e la creazione di certificati con lyncdiscover. \<dominio\> come parte della configurazione di proxy inverso, direttori e server front-end.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="d8ef1-117">Se si implementa l'individuazione automatica in una distribuzione aggiornata da Lync Server 2010, è consigliabile usare HTTP per evitare di riemettere certificati.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="d8ef1-118">Le linee guida per entrambi gli scenari sono disponibili nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8ef1-119">L'elenco di nomi alternativi oggetto nei certificati usati dalla regola di pubblicazione dei servizi Web esterni deve contenere un <EM>lyncdiscover.&lt; SipDomain&gt; </EM> voce per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="d8ef1-120">Per informazioni dettagliate sulle voci di nome alternative oggetto necessarie per direttori, server front-end e reverse proxy, vedere <A href="lync-server-2013-certificate-summary-autodiscover.md">Riepilogo dei certificati-individuazione automatica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef1-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8ef1-121">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d8ef1-121">In This Section</span></span>

  - [<span data-ttu-id="d8ef1-122">Riepilogo del certificato-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8ef1-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="d8ef1-123">Riepilogo della porta-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8ef1-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="d8ef1-124">Riepilogo DNS-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8ef1-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="d8ef1-125">Hybrid e Split-Domain-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8ef1-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

