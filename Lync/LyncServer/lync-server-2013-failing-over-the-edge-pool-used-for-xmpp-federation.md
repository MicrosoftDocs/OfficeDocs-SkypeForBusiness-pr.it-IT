---
title: 'Lync Server 2013: failover del pool di Edge utilizzato per la Federazione XMPP'
description: 'Lync Server 2013: failover del pool di Edge utilizzato per la Federazione XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccdfe119258b4d09ddedefb22d0272d72003bf04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554902"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="dfd88-103">Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="dfd88-103">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfd88-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="dfd88-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="dfd88-p101">All'interno dell'organizzazione un solo pool di server perimetrali è designato come pool da usare per la federazione XMPP. Se questo pool non è disponibile, per consentire il funzionamento della federazione XMPP è necessario eseguire il failover di questa a un altro pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="dfd88-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="dfd88-107">Quando si installano i pool di server perimetrali e si abilita la federazione XMPP per la prima volta, per semplificare il processo di ripristino di emergenza della federazione XMPP è possibile impostare record DNS SRV esterni per tutti i pool di server perimetrali, invece che per uno solo.</span><span class="sxs-lookup"><span data-stu-id="dfd88-107">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="dfd88-108">Per ciascuno di questi record SRV deve essere impostata una priorità diversa.</span><span class="sxs-lookup"><span data-stu-id="dfd88-108">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="dfd88-109">Tutto il traffico di federazione XMPP passa per il pool con il record SRV con la priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="dfd88-109">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="dfd88-110">Per ulteriori informazioni sull'abilitazione e sulla configurazione della Federazione XMPP, vedere [Setting up XMPP Federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="dfd88-110">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="dfd88-111">Nella procedura seguente EdgePool1 è il pool di server perimetrali che ospita la federazione XMPP originariamente ed EdgePool2 è il pool che la ospiterà.</span><span class="sxs-lookup"><span data-stu-id="dfd88-111">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="dfd88-112">Failover del pool di server perimetrali usato per la federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="dfd88-112">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="dfd88-113">Se oltre al pool di server perimetrali non disponibile non ne sono stati distribuiti altri, distribuirne uno.</span><span class="sxs-lookup"><span data-stu-id="dfd88-113">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="dfd88-114">Per informazioni dettagliate, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="dfd88-114">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="dfd88-115">In ogni server perimetrale del nuovo pool di server perimetrali che ora ospita la federazione XMPP (EdgePool2) eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="dfd88-115">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="dfd88-116">Eseguire il cmdlet seguente per puntare la route della federazione XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="dfd88-116">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="dfd88-117">In questo esempio, Site2 è il sito che contiene il pool di server perimetrali che ospiterà la route della federazione XMPP ed EdgeServer2.contoso.com è l'FQDN di un server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="dfd88-117">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="dfd88-118">Nel server DNS esterno modificare il record DNS A in modo che la federazione XMPP punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dfd88-118">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="dfd88-p104">Se per la federazione XMPP non è disponibile un record DNS SRV corrispondente al pool di server perimetrali che ospiterà la federazione XMPP, è necessario aggiungerlo così com'è illustrato nell'esempio seguente. Il valore della porta del record SRV deve essere 5269.</span><span class="sxs-lookup"><span data-stu-id="dfd88-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="dfd88-121">Verificare che il pool di server perimetrali che ospiterà la federazione XMPP abbia la porta 5269 aperta verso l'esterno.</span><span class="sxs-lookup"><span data-stu-id="dfd88-121">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="dfd88-122">Avviare i servizi in tutti i server perimetrali del pool che ospiterà la federazione XMPP:</span><span class="sxs-lookup"><span data-stu-id="dfd88-122">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

