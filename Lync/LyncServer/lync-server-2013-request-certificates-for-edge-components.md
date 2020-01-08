---
title: 'Lync Server 2013: Richiedere i certificati per i componenti perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e848e5fb8ea120bab2251dff776e2c9c27eacca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="b8fd0-102">Richiedere i certificati per i componenti perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8fd0-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8fd0-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b8fd0-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="b8fd0-104">I certificati necessari per supportare l'accesso degli utenti esterni includono certificati emessi da un'autorità di certificazione pubblica (CA) e certificati emessi da una CA aziendale interna:</span><span class="sxs-lookup"><span data-stu-id="b8fd0-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="b8fd0-105">I certificati necessari per l'interfaccia esterna di Edge Server e il proxy inverso devono essere emessi da una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="b8fd0-106">I certificati necessari per l'interfaccia interna possono essere emessi da una CA pubblica o da una CA interna dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="b8fd0-107">È consigliabile usare una CA interna di Windows Server 2008, Windows Server 2008 R2, CA, Windows Server 2012 CA o Windows Server 2012 R2 per la creazione di questi certificati per il salvataggio a spese dell'uso di certificati pubblici.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8fd0-108">Può essere necessario un po' di tempo per elaborare le richieste di certificato, in particolare le richieste alle autorità di certificazione pubbliche, in modo da richiedere i certificati per i server perimetrali abbastanza presto per verificare che siano disponibili quando si avvia la distribuzione dei componenti del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="b8fd0-109">Per un riepilogo dei requisiti di certificato per Edge Server, vedere <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b8fd0-110">Anche se è possibile scegliere di usare una CA pubblica per il certificato di bordo interno, è consigliabile usare una CA aziendale interna per gli altri certificati per ridurre al minimo il costo dei certificati.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="b8fd0-111">Per un riepilogo dei requisiti di certificato per Edge Server, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b8fd0-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8fd0-112">Quando si installa un server perimetrale, il programma di installazione include una procedura guidata per il certificato che facilita le attività di richiesta, assegnazione e installazione dei certificati, come descritto nella sezione <A href="lync-server-2013-set-up-edge-certificates.md">configurare i certificati di Edge per Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="b8fd0-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="b8fd0-113">Se si vogliono richiedere certificati prima di installare un server perimetrale, ad esempio per risparmiare tempo durante la distribuzione effettiva dei componenti di Edge Server, è possibile usare i server interni purché si accerti che i certificati siano esportabili e contengano tutte le nomi di oggetto alternativi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="b8fd0-114">Questa documentazione non offre procedure per l'uso dei server interni per richiedere certificati.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="b8fd0-115">Richiedere certificati da una CA pubblica</span><span class="sxs-lookup"><span data-stu-id="b8fd0-115">Request certificates from a public CA</span></span>

<span data-ttu-id="b8fd0-116">La distribuzione di Edge Server richiede un singolo certificato pubblico per le interfacce esterne di Edge Server, usato per il servizio Access Edge, il servizio Web Conferencing Edge e per il servizio di autenticazione A/V.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="b8fd0-117">Questo certificato deve avere una chiave privata esportabile per verificare che il servizio di autenticazione A/V usi le stesse chiavi in tutti i server perimetrali in un pool.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="b8fd0-118">Il proxy inverso, usato con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, richiede anche un certificato pubblico.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="b8fd0-119">Richiedere certificati da una CA aziendale interna</span><span class="sxs-lookup"><span data-stu-id="b8fd0-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="b8fd0-120">I certificati necessari per l'interfaccia Edge interna possono essere emessi da un'autorità di certificazione pubblica (CA) o da una CA interna.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="b8fd0-121">È possibile usare una CA aziendale interna per ridurre al minimo il costo dei certificati.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="b8fd0-122">Se l'organizzazione ha una CA interna distribuita, i certificati per il bordo interno devono essere emessi dalla CA interna.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="b8fd0-123">L'uso di una CA aziendale interna per i certificati interni può ridurre il costo dei certificati.</span><span class="sxs-lookup"><span data-stu-id="b8fd0-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="b8fd0-124">Per un riepilogo dei requisiti di certificato per i componenti di Edge, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b8fd0-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="b8fd0-125">Per informazioni dettagliate sull'uso di una CA pubblica per ottenere i certificati, vedere [richiedere certificati per i componenti di Edge in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="b8fd0-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="b8fd0-126">Per informazioni dettagliate sulla richiesta, l'installazione e l'assegnazione di certificati, vedere [configurare i certificati di Edge per Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="b8fd0-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

