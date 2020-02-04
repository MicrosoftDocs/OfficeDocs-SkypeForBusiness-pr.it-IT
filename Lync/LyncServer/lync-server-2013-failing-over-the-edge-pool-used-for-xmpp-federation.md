---
title: 'Lync Server 2013: Failover del pool di server perimetrali utilizzato per la federazione di XMPP'
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
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="854d4-102">Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854d4-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="854d4-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="854d4-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="854d4-104">Nell'organizzazione esiste un pool di bordi designato come pool da usare per la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="854d4-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="854d4-105">Se il pool scende, è necessario eseguire il failover della Federazione XMPP per usare un pool di bordi diverso prima che la Federazione XMPP possa funzionare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="854d4-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="854d4-106">La prima volta che si installano pool di bordi e si Abilita la Federazione XMPP, è possibile semplificare il processo di ripristino di emergenza impostando i record SRV DNS esterni per tutti i pool di Edge per la Federazione XMPP, anziché solo uno.</span><span class="sxs-lookup"><span data-stu-id="854d4-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="854d4-107">Ognuno di questi record SRV deve avere un set di priorità diverso.</span><span class="sxs-lookup"><span data-stu-id="854d4-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="854d4-108">Tutto il traffico federativo XMPP passa attraverso il pool con il record SRV con la massima priorità.</span><span class="sxs-lookup"><span data-stu-id="854d4-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="854d4-109">Per altre informazioni sull'abilitazione e la configurazione della Federazione XMPP, vedere [configurazione della Federazione XMPP in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="854d4-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="854d4-110">Nella procedura seguente, EdgePool1 è il pool che ospitava originariamente la Federazione XMPP e EdgePool2 è il pool che ora ospiterà la Federazione XMPP.</span><span class="sxs-lookup"><span data-stu-id="854d4-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="854d4-111">Errori nel pool di bordi usato per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="854d4-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="854d4-112">Se non si dispone già di un altro pool di Edge distribuito, oltre a quello attualmente in calo, distribuire il pool.</span><span class="sxs-lookup"><span data-stu-id="854d4-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="854d4-113">Per informazioni dettagliate, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="854d4-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="854d4-114">In ogni Edge Server nel nuovo pool di Edge che ora ospiterà la Federazione XMPP (EdgePool2), eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="854d4-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="854d4-115">Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP a EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="854d4-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="854d4-116">In questo esempio, sito2 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer2.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.</span><span class="sxs-lookup"><span data-stu-id="854d4-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="854d4-117">Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="854d4-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="854d4-118">Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="854d4-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="854d4-119">Questo record SRV deve avere un valore di porta 5269.</span><span class="sxs-lookup"><span data-stu-id="854d4-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="854d4-120">Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.</span><span class="sxs-lookup"><span data-stu-id="854d4-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="854d4-121">Avviare i servizi in tutti i server perimetrali nel pool di Edge, che ora ospiterà la Federazione XMPP:</span><span class="sxs-lookup"><span data-stu-id="854d4-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

