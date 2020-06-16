---
title: Configurare i record DNS per la distribuzione del pool pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 3388fb148b4d4f4825432e6168b657405e337c35
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="74620-102">Configurare i record DNS per la distribuzione del pool pilota</span><span class="sxs-lookup"><span data-stu-id="74620-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74620-103">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="74620-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="74620-104">Prima di distribuire il pool pilota di Lync Server 2013, è necessario aggiornare le voci dell'host DNS A per il pool pilota.</span><span class="sxs-lookup"><span data-stu-id="74620-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="74620-105">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="74620-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="74620-106">**Per configurare i record A host DNS**</span><span class="sxs-lookup"><span data-stu-id="74620-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="74620-107">Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="74620-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="74620-108">Nell'albero della console per il dominio espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74620-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="74620-109">Scegliere **Nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="74620-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="74620-110">Fare clic su **Nome** e digitare il nome host per il pool. Il nome di dominio viene presupposto dalla zona in cui è definito il record e non deve essere immesso come parte del record A.</span><span class="sxs-lookup"><span data-stu-id="74620-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="74620-111">Fare clic su **indirizzo IP**, digitare l'indirizzo IP per il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="74620-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="74620-112">Fare clic su **Aggiungi host** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="74620-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="74620-113">Al termine, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="74620-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

