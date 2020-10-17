---
title: 'Lync Server 2013: configurare i record host DNS'
description: 'Lync Server 2013: configurare i record host DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd403402d0d2f089d7fc92a62296a56df0cf2e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553432"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="0cdc1-103">Configurare i record host DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cdc1-103">Configure DNS Host records for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cdc1-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0cdc1-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0cdc1-105">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="0cdc1-106">Per configurare i record A host DNS</span><span class="sxs-lookup"><span data-stu-id="0cdc1-106">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="0cdc1-107">Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0cdc1-108">Nell'albero della console per il dominio espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="0cdc1-109">Scegliere **Nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="0cdc1-110">Fare clic su **Nome** e digitare il nome host per il pool. Il nome di dominio viene presupposto dalla zona in cui è definito il record e non deve essere immesso come parte del record A.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="0cdc1-111">Fare clic su **indirizzo IP**, digitare l'IP virtuale (VIP) del bilanciamento del carico per il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-111">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0cdc1-112">Nelle distribuzioni in cui viene utilizzato un pool di server Director, i record host (A) per gli URL semplici devono puntare al VIP del servizio di bilanciamento del carico dei server Director.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-112">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0cdc1-p101">Se si distribuisce solo un Server Enterprise o un server Director connesso alla topologia senza un servizio di bilanciamento del carico o si distribuisce un server Standard Edition, digitare l'indirizzo IP del Server Enterprise, del server Standard Edition o del server Director. Un servizio di bilanciamento del carico è necessario se si distribuiscono più Server Enterprise o server Director in un pool. I servizi di bilanciamento del carico non vengono utilizzati con server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="0cdc1-116">Fare clic su **Aggiungi host** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-116">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="0cdc1-117">Per creare un record A aggiuntivo, ripetere i passaggi 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-117">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="0cdc1-118">Al termine della creazione di tutti i record A necessari, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0cdc1-118">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

