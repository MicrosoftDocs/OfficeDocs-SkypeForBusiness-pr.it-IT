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
ms.openlocfilehash: 779929d270fa4ae2f8eec59a954c2273ff61b44f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="7aa2c-102">Configurazione del supporto per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa2c-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa2c-103">_**Argomento Ultima modifica:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="7aa2c-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="7aa2c-104">Il **servizio di individuazione automatica** servizi Web di Lync Server è stato pubblicato per la prima volta nell'aggiornamento cumulativo di lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="7aa2c-105">Questo aggiornamento è stato accompagnato dalla versione iniziale dei client di Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="7aa2c-106">Il servizio di individuazione automatica ha esposto i servizi di mobilità, noti come servizio MCX.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="7aa2c-107">Il servizio di individuazione automatica funge da singola posizione per tutti i client per richiedere informazioni su quali servizi e funzionalità sono disponibili e su come contattare i Sevices tramite un nome di dominio completo o un riferimento per il localizzatore di risorse Web Uniform.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="7aa2c-108">L'individuazione automatica espone un certo numero di funzionalità e ogni client effettuerà richieste in base alle caratteristiche che il client può usare.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="7aa2c-109">Ad esempio, un client Lync 2013 Desktop utilizzerà autodiscvoer per determinare i servizi Web esterni, ma non userà i servizi di mobilità (MCX).</span><span class="sxs-lookup"><span data-stu-id="7aa2c-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="7aa2c-110">Per definire e abilitare correttamente i client per l'uso delle funzionalità disponibili, gli scenari che consentono a un client di trovare e usare efficacemente le voci di individuazione automatica devono essere definiti.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="7aa2c-111">Per usare autodoscover, la distribuzione richiede che un proxy inverso pubblichi i servizi Web di Lync Server, che i record DNS siano configurati per risolvere le query DNS per il servizio di individuazione automatica di Lync Server e i servizi Web di Lync Server e che i servizi di certificazione sono configurati correttamente per lo scenario specifico.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7aa2c-112">Per informazioni tecniche sugli elementi di una richiesta/risposta di individuazione automatica, vedere informazioni sull' <A href="lync-server-2013-understanding-autodiscover.md">individuazione automatica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7aa2c-113">Le informazioni e le tabelle seguenti definiscono, per scenario, le configurazioni (se presenti) che è necessario implementare per consentire l'uso completo ed efficace del servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="7aa2c-114">Le informazioni contenute negli argomenti seguenti sono specifiche di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7aa2c-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7aa2c-115">Per informazioni su come pianificare la mobilità per Lync Server 2010, vedere [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span><span class="sxs-lookup"><span data-stu-id="7aa2c-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="7aa2c-116">Per distribuire la mobilità per Lync Server 2010, vedere[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="7aa2c-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7aa2c-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7aa2c-117">In This Section</span></span>

  - [<span data-ttu-id="7aa2c-118">Configurazione del DNS per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa2c-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="7aa2c-119">Configurazione dei certificati per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa2c-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="7aa2c-120">Configurazione di un proxy inverso per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa2c-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="7aa2c-121">Configurazione dell'individuazione automatica in Lync Server 2013 per distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="7aa2c-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

