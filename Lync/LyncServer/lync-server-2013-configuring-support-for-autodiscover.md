---
title: "Lync Server 2013: configurazione del supporto per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79511202ddc9e413e313d12f881e7079f088c473
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="99e82-102">Configurazione del supporto per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e82-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99e82-103">_**Ultimo argomento modificato:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="99e82-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="99e82-104">Il **servizio di individuazione automatica** dei servizi Web di Lync Server è stato introdotto per la prima volta nell'aggiornamento cumulativo di lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="99e82-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="99e82-105">Questo aggiornamento è stato accompagnato dalla versione iniziale dei client di Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="99e82-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="99e82-106">Il servizio di individuazione automatica ha esposto i servizi per dispositivi mobili, noto come servizio di MCX.</span><span class="sxs-lookup"><span data-stu-id="99e82-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="99e82-107">Il servizio di individuazione automatica funge da singola posizione per tutti i client per richiedere informazioni su quali servizi e funzionalità sono disponibili e su come contattare i sevizi, in base a un nome di dominio completo o a un riferimento a un Uniform Resource Locator del Web.</span><span class="sxs-lookup"><span data-stu-id="99e82-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="99e82-108">L'individuazione automatica espone numerose funzionalità e ogni client eseguirà le richieste in base alle caratteristiche che il client può utilizzare.</span><span class="sxs-lookup"><span data-stu-id="99e82-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="99e82-109">Ad esempio, un client Lync 2013 Desktop utilizzerà autodiscvoer per determinare i servizi Web esterni, ma non utilizzerà i servizi per dispositivi mobili (MCX).</span><span class="sxs-lookup"><span data-stu-id="99e82-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="99e82-110">Per definire correttamente e consentire ai client di utilizzare le funzionalità disponibili, è necessario definire gli scenari che consentono a un client di trovare e utilizzare in modo efficace le voci di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="99e82-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="99e82-111">Per utilizzare autodoscover, la distribuzione richiede che un proxy inverso pubblichi i servizi Web di Lync Server, che i record DNS siano configurati per la risoluzione delle query DNS per il servizio di individuazione automatica di Lync Server e per i servizi Web di Lync Server e che i servizi certificati sono configurati correttamente per lo scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="99e82-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="99e82-112">Per informazioni tecniche su cosa fare gli elementi all'interno della richiesta/risposta di individuazione automatica, vedere <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="99e82-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="99e82-113">Le seguenti informazioni e tabelle definiscono, per ogni scenario, quali configurazioni (se presenti) è necessario implementare per fornire l'utilizzo completo ed efficace del servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="99e82-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="99e82-114">Le informazioni contenute negli argomenti seguenti sono specifiche di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99e82-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="99e82-115">Se si cercano indicazioni su come pianificare la mobilità per Lync Server 2010, vedere [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span><span class="sxs-lookup"><span data-stu-id="99e82-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="99e82-116">Per distribuire la mobilità per Lync Server 2010, vedere[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="99e82-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99e82-117">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="99e82-117">In This Section</span></span>

  - [<span data-ttu-id="99e82-118">Configurazione del DNS per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e82-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="99e82-119">Configurazione dei certificati per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e82-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="99e82-120">Configurazione di un proxy inverso per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99e82-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="99e82-121">Configurazione dell'individuazione automatica in Lync Server 2013 per le distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="99e82-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

