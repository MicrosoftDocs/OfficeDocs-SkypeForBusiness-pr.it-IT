---
title: 'Lync Server 2013: Configurare i record host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="8e9bb-102">Configurare i record host DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e9bb-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e9bb-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8e9bb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8e9bb-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio al minimo come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="8e9bb-105">Per configurare i record dell'host DNS</span><span class="sxs-lookup"><span data-stu-id="8e9bb-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="8e9bb-106">Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="8e9bb-107">Nell'albero della console per il dominio espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="8e9bb-108">Fare clic su **nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="8e9bb-109">Fare clic su **nome**, digitare il nome host per il pool (il nome di dominio viene considerato dalla zona in cui è definito il record e non deve essere immesso come parte del record a).</span><span class="sxs-lookup"><span data-stu-id="8e9bb-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="8e9bb-110">Fare clic su **indirizzo IP**, digitare l'IP virtuale (VIP) del bilanciamento del carico per il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e9bb-111">Nelle distribuzioni che usano un pool di Director i record host (A) per gli URL semplici devono puntare al VIP del responsabile del bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e9bb-112">Se si distribuisce solo un server Enterprise o un Director connesso alla topologia senza un bilanciamento del carico oppure se si distribuisce un server standard, digitare l'indirizzo IP del server Enterprise Edition, il server standard o il Director.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-112">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director.</span></span> <span data-ttu-id="8e9bb-113">Se si distribuiscono più server o Director Enterprise Edition in un pool, è necessario un bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-113">A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool.</span></span> <span data-ttu-id="8e9bb-114">I bilanciamento del carico non vengono usati con i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-114">Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="8e9bb-115">Fare clic su **Aggiungi host**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="8e9bb-116">Per creare un record aggiuntivo, ripetere i passaggi 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="8e9bb-117">Al termine della creazione di tutti i record necessari, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="8e9bb-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

