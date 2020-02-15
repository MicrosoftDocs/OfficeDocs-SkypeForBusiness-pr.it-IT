---
title: "Lync Server 2013: pianificazione dell'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0b470908849b47c499287123d194b8868e3147
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="02c27-102">Pianificazione dell'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02c27-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02c27-103">_**Ultimo argomento modificato:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="02c27-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="02c27-104">L'individuazione automatica è stata introdotta per Lync Server nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="02c27-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="02c27-105">Lo scopo principale di questa implementazione iniziale dell'individuazione automatica è stato quello di fornire un mezzo per Lync mobile per individuare il servizio per dispositivi mobili (MCX).</span><span class="sxs-lookup"><span data-stu-id="02c27-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="02c27-106">Il servizio di individuazione automatica in Lync Server 2013 è ora un servizio utilizzato da tutti i client per individuare i servizi server e utente.</span><span class="sxs-lookup"><span data-stu-id="02c27-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="02c27-107">Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito su Director e front end server.</span><span class="sxs-lookup"><span data-stu-id="02c27-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="02c27-108">Per informazioni più tecniche sull'individuazione automatica e su ciò che viene comunicato ai client, vedere <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02c27-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="02c27-109">La mobilità è ancora uno scenario distinto e i servizi per dispositivi mobili richiedono comunque una pianificazione speciale.</span><span class="sxs-lookup"><span data-stu-id="02c27-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="02c27-110">Per ulteriori informazioni, vedere <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02c27-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="02c27-111">Quando la funzione di individuazione automatica è stata introdotta in Lync Server 2010, sono stati necessari compromessi per implementare un servizio che richiedeva potenziali modifiche del certificato alle distribuzioni esistenti del server.</span><span class="sxs-lookup"><span data-stu-id="02c27-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="02c27-112">L'individuazione automatica può essere utilizzata su porta TCP 443 per HTTPS o su porta TCP 80 per HTTP.</span><span class="sxs-lookup"><span data-stu-id="02c27-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="02c27-113">Se è stata presa la decisione di utilizzare HTTPS, i certificati su proxy inversi, direttori e front end server devono essere riemessi per soddisfare i record DNS e `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` necessari.</span><span class="sxs-lookup"><span data-stu-id="02c27-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="02c27-114">Se si decide di utilizzare il protocollo HTTP, la ristampa dei certificati potrebbe essere evitata utilizzando record CNAME DNS (o alias) per l'utilizzo dei nomi esistenti nei certificati.</span><span class="sxs-lookup"><span data-stu-id="02c27-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="02c27-115">L'utilizzo di HTTP significa che le comunicazioni iniziali non sono state crittografate.</span><span class="sxs-lookup"><span data-stu-id="02c27-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="02c27-116">Poiché Lync Server 2013 utilizza l'individuazione automatica per tutti i client, lo scenario principale consiste nell'utilizzare solo HTTPS e creare certificati con lyncdiscover. \<dominio\> come parte della configurazione dei proxy inversi, direttori e front end server.</span><span class="sxs-lookup"><span data-stu-id="02c27-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="02c27-117">Se si sta implementando l'individuazione automatica in una distribuzione aggiornata da Lync Server 2010, è consigliabile utilizzare HTTP per evitare di riemettere certificati.</span><span class="sxs-lookup"><span data-stu-id="02c27-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="02c27-118">Le linee guida per entrambi gli scenari sono disponibili nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="02c27-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="02c27-119">L'elenco dei nomi alternativi del soggetto nei certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni deve contenere un <EM>lyncdiscover.&lt; voce&gt; SipDomain</EM> per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="02c27-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="02c27-120">Per informazioni dettagliate sulle voci dei nomi alternativi del soggetto necessarie per i direttori, i Front End Server e i proxy inversi, vedere <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02c27-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02c27-121">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="02c27-121">In This Section</span></span>

  - [<span data-ttu-id="02c27-122">Riepilogo del certificato-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02c27-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="02c27-123">Riepilogo delle porte-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02c27-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="02c27-124">Riepilogo DNS-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02c27-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="02c27-125">Ambiente ibrido e Split-Domain-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02c27-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

