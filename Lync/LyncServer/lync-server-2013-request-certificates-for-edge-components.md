---
title: 'Lync Server 2013: richiedere i certificati per i componenti perimetrali'
description: 'Lync Server 2013: richiedere i certificati per i componenti perimetrali.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579012"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="ad538-103">Richiedere i certificati per i componenti perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad538-103">Request certificates for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad538-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ad538-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ad538-105">I certificati necessari per supportare l'accesso utente esterno includono i certificati emessi da un'Autorità di certificazione (CA) pubblica e i certificati emessi da un'autorità di certificazione globale (enterprise) interna:</span><span class="sxs-lookup"><span data-stu-id="ad538-105">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="ad538-106">I certificati necessari per l'interfaccia esterna del server perimetrale e il proxy inverso devono essere emessi da un'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="ad538-106">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="ad538-107">I certificati necessari per l'interfaccia interna possono essere emessi da una CA pubblica o da una CA enterprise interna.</span><span class="sxs-lookup"><span data-stu-id="ad538-107">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="ad538-108">È consigliabile utilizzare un'autorità di certificazione interna di Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA o Windows Server 2012 R2 per la creazione di questi certificati per il salvataggio a scapito dell'utilizzo di certificati pubblici.</span><span class="sxs-lookup"><span data-stu-id="ad538-108">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad538-109">È possibile richiedere del tempo per elaborare le richieste di certificati, in particolare le richieste alle autorità di certificazione pubbliche, pertanto è necessario richiedere certificati per i server perimetrali in anticipo per garantire che siano disponibili quando si avvia la distribuzione dei componenti del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="ad538-109">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="ad538-110">Per un riepilogo dei requisiti relativi ai certificati per i server perimetrali, vedere <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate Requirements for External User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ad538-110">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ad538-111">Anche se per il certificato del perimetro interno è possibile utilizzare un'autorità di certificazione (CA) pubblica, per ridurre al minimo i costi è consigliabile utilizzare una CA globale (enterprise).</span><span class="sxs-lookup"><span data-stu-id="ad538-111">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="ad538-112">Per un riepilogo dei requisiti relativi ai certificati per i server perimetrali, vedere [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ad538-112">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad538-113">Quando si installa un server perimetrale, il programma di installazione include una procedura guidata di certificazione che facilita le attività relative alla richiesta, all'assegnazione e all'installazione dei certificati, come descritto nella sezione <A href="lync-server-2013-set-up-edge-certificates.md">set up Edge Certificates for Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="ad538-113">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="ad538-114">Se si desidera richiedere certificati prima di installare un server perimetrale, ad esempio per risparmiare tempo durante la distribuzione effettiva dei componenti del server perimetrale, è possibile utilizzare i server interni purché si accerti che i certificati siano esportabili e che contengano tutti i nomi alternativi del soggetto richiesti.</span><span class="sxs-lookup"><span data-stu-id="ad538-114">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="ad538-115">La presente documentazione non include le procedure per la richiesta dei certificati mediante i server interni.</span><span class="sxs-lookup"><span data-stu-id="ad538-115">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="ad538-116">Richiedere certificati di una CA pubblica</span><span class="sxs-lookup"><span data-stu-id="ad538-116">Request certificates from a public CA</span></span>

<span data-ttu-id="ad538-117">La distribuzione del server perimetrale richiede un singolo certificato pubblico per le interfacce esterne dei server perimetrali, che viene utilizzato per il servizio Access Edge, il servizio Web Conferencing Edge e per il servizio di autenticazione A/V.</span><span class="sxs-lookup"><span data-stu-id="ad538-117">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="ad538-118">Questo certificato deve disporre di una chiave privata esportabile per garantire che il servizio di autenticazione A/V utilizzi le stesse chiavi su tutti i server perimetrali in un pool.</span><span class="sxs-lookup"><span data-stu-id="ad538-118">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="ad538-119">Il proxy inverso, utilizzato con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, richiede anche un certificato pubblico.</span><span class="sxs-lookup"><span data-stu-id="ad538-119">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="ad538-120">Richiedere certificati a una CA globale (enterprise) interna</span><span class="sxs-lookup"><span data-stu-id="ad538-120">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="ad538-p106">I certificati necessari per l'interfaccia perimetrale interna possono essere rilasciati da un'Autorità di certificazione (CA) pubblica oppure interna. È possibile utilizzare una CA globale (enterprise) interna per ridurre al minimo il costo dei certificati. Se nell'organizzazione vi è una CA interna distribuita, i certificati per il perimetro interno devono essere rilasciati dalla CA interna. L'utilizzo di una CA globale (enterprise) interna per i certificati interni consente di ridurre il costo dei certificati.</span><span class="sxs-lookup"><span data-stu-id="ad538-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="ad538-125">Per un riepilogo dei requisiti relativi ai certificati per i componenti perimetrali, vedere [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ad538-125">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="ad538-126">Per informazioni dettagliate sull'utilizzo di un'autorità di certificazione pubblica per ottenere i certificati, vedere [richiesta di certificati per i componenti perimetrali in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="ad538-126">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="ad538-127">Per informazioni dettagliate sulla richiesta, l'installazione e l'assegnazione dei certificati, vedere [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="ad538-127">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

