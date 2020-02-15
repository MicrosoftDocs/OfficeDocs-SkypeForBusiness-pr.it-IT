---
title: 'Lync Server 2013: pianificare i certificati del server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b70d9635b253c793170ff11373f6d063f0f46c81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="d5115-102">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5115-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5115-103">_**Ultimo argomento modificato:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="d5115-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="d5115-104">La creazione di certificati per Edge è semplificata in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5115-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="d5115-105">**Diagramma di flusso dei certificati per i server perimetrali**</span><span class="sxs-lookup"><span data-stu-id="d5115-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="d5115-106">![a5fc20db-7ced-4364-B577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-B577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="d5115-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="d5115-107">Creare un singolo certificato pubblico, verificare di disporre di una chiave privata esportabile definita per il certificato e assegnarlo alle interfacce esterne dei server perimetrali seguenti utilizzando la Configurazione guidata certificati:</span><span class="sxs-lookup"><span data-stu-id="d5115-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5115-108">I certificati con caratteri jolly non sono supportati in Lync Server, tranne se utilizzati per riepilogare gli URL semplici tramite il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d5115-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="d5115-109">È necessario definire SANs (Subject Alternate Names) distinti per ogni nome di dominio SIP, servizio Web Conferencing Edge, servizio A/V Edge e dominio XMPP offerti dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d5115-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d5115-110">Introdotti in Lync Server 2013, la gestione dei certificati di autenticazione audio/video in anticipo rispetto alla data di scadenza del certificato corrente richiede una pianificazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d5115-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="d5115-111">Invece di un certificato con più scopi per l'interfaccia perimetrale esterna, sono necessari due certificati, uno assegnato al servizio Access Edge e il servizio Web Conferencing Edge e un certificato per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="d5115-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="d5115-112">Per ulteriori informazioni, vedere <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="d5115-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5115-113">In caso di un pool di server perimetrali, esportare il certificato con la chiave privata in ogni server perimetrale e assegnare il certificato a ogni servizio server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d5115-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="d5115-114">Fare lo stesso per il certificato del server perimetrale interno, esportando il certificato con la chiave privata e assegnando a ogni interfaccia perimetrale interna.</span><span class="sxs-lookup"><span data-stu-id="d5115-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="d5115-115">Verificare di disporre di una chiave privata esportabile assegnata per il certificato</span><span class="sxs-lookup"><span data-stu-id="d5115-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="d5115-116">Servizio Access Edge (denominato **Access Edge SIP esterno** nella configurazione guidata certificati)</span><span class="sxs-lookup"><span data-stu-id="d5115-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="d5115-117">Servizio Web Conferencing Edge (denominato **Web Conferencing Edge esterno** nella configurazione guidata certificati)</span><span class="sxs-lookup"><span data-stu-id="d5115-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="d5115-118">Servizio di autenticazione A/V (denominato **A/V Edge Server esterno** nella Configurazione guidata certificati)</span><span class="sxs-lookup"><span data-stu-id="d5115-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="d5115-119">Creare un singolo certificato interno con chiave privata esportabile, copiarlo e assegnarlo a ciascuna delle interfacce interne del server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="d5115-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="d5115-120">Server perimetrale (denominato **Edge Server interno** nella Configurazione guidata certificati)</span><span class="sxs-lookup"><span data-stu-id="d5115-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5115-121">È possibile utilizzare certificati separati e distinti per ogni servizio server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d5115-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="d5115-122">Se si desidera utilizzare la nuova funzionalità di certificazione per il certificato del servizio A/V Edge, è consigliabile scegliere certificati distinti.</span><span class="sxs-lookup"><span data-stu-id="d5115-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="d5115-123">Nel caso di questa funzionalità, è consigliabile separare il certificato del servizio A/V Edge dal servizio Access Edge e il servizio Web Conferencing Edge.</span><span class="sxs-lookup"><span data-stu-id="d5115-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="d5115-124">Se si sceglie di richiedere, acquisire e assegnare certificati distinti per ogni servizio, è necessario richiedere che la chiave privata sia esportabile per il servizio A/V Edge (di nuovo, questo è il servizio di autenticazione A/V) e assegnare lo stesso certificato all'interfaccia esterna a/V Edge in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d5115-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5115-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5115-125">See Also</span></span>


[<span data-ttu-id="d5115-126">Staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="d5115-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="d5115-127">Modifiche apportate in Lync Server 2013 che influiscono sulla pianificazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="d5115-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

