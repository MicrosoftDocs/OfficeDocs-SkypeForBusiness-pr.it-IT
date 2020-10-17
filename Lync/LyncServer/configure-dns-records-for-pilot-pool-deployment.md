---
title: Configurare i record DNS per la distribuzione del pool pilota
description: Configurare i record DNS per la distribuzione del pool pilota.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e41e163432ba910f6d083cc508e8ad8c9f2006d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548492"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="20e02-103">Configurare i record DNS per la distribuzione del pool pilota</span><span class="sxs-lookup"><span data-stu-id="20e02-103">Configure DNS records for pilot pool deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20e02-104">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="20e02-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="20e02-105">Prima di distribuire il pool pilota di Lync Server 2013, è necessario aggiornare le voci dell'host DNS A per il pool pilota.</span><span class="sxs-lookup"><span data-stu-id="20e02-105">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="20e02-106">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="20e02-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="20e02-107">**Per configurare i record A dell'host DNS**</span><span class="sxs-lookup"><span data-stu-id="20e02-107">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="20e02-108">Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="20e02-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="20e02-109">Nell'albero della console per il dominio espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20e02-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="20e02-110">Scegliere **Nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="20e02-110">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="20e02-111">Fare clic su **nome**, digitare il nome host per il pool di Lync Server 2013 (il nome di dominio viene assunto dall'area in cui è definito il record e non è necessario immetterlo come parte del record a).</span><span class="sxs-lookup"><span data-stu-id="20e02-111">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="20e02-112">Fare clic su **indirizzo IP**, digitare l'indirizzo IP per il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="20e02-112">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="20e02-113">Fare clic su **Aggiungi host** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20e02-113">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="20e02-114">Al termine, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="20e02-114">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

