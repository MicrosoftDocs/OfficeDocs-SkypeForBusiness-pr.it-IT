---
title: Configurare i record DNS per la distribuzione del pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 612857ba1a0ec599b0011ab5779cb7fc4b5a0615
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="9257f-102">Configurare i record DNS per la distribuzione del pool pilota</span><span class="sxs-lookup"><span data-stu-id="9257f-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9257f-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="9257f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="9257f-104">Prima di distribuire il pool di piloti di Lync Server 2013, è necessario aggiornare le voci dell'host DNS per il pool di piloti.</span><span class="sxs-lookup"><span data-stu-id="9257f-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="9257f-105">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio al minimo come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="9257f-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="9257f-106">**Per configurare i record dell'host DNS**</span><span class="sxs-lookup"><span data-stu-id="9257f-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="9257f-107">Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="9257f-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="9257f-108">Nell'albero della console per il dominio espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9257f-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="9257f-109">Fare clic su **nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="9257f-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="9257f-110">Fare clic su **nome**, digitare il nome host per il pool (il nome di dominio viene considerato dalla zona in cui è definito il record e non deve essere immesso come parte del record a).</span><span class="sxs-lookup"><span data-stu-id="9257f-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="9257f-111">Fare clic su **indirizzo IP**, digitare l'indirizzo IP per il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="9257f-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="9257f-112">Fare clic su **Aggiungi host**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9257f-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="9257f-113">Al termine, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="9257f-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

