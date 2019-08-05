---
title: Configurare i record DNS per la distribuzione del pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Prima di distribuire il pool pilota, è necessario aggiornare le voci dell'host DNS per il pool di piloti. Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191561"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="70ad7-104">Configurare i record DNS per la distribuzione del pool pilota</span><span class="sxs-lookup"><span data-stu-id="70ad7-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="70ad7-105">Prima di distribuire il pool di Pilot, è necessario aggiornare le voci dell'host DNS per il pool di piloti.</span><span class="sxs-lookup"><span data-stu-id="70ad7-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="70ad7-106">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="70ad7-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="70ad7-107">Per configurare i record dell'host DNS</span><span class="sxs-lookup"><span data-stu-id="70ad7-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="70ad7-108">Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="70ad7-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="70ad7-109">Nell'albero della console per il dominio espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="70ad7-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="70ad7-110">Fare clic su **nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="70ad7-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="70ad7-111">Fare clic su **nome**, digitare il nome host per il pool di Skype for Business Server 2019 (il nome di dominio viene considerato dalla zona in cui è definito il record e non deve essere immesso come parte del record a).</span><span class="sxs-lookup"><span data-stu-id="70ad7-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="70ad7-112">Fare clic su **indirizzo IP**e quindi digitare l'indirizzo IP per il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="70ad7-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="70ad7-113">Fare clic su **Aggiungi host**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70ad7-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="70ad7-114">Al termine, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="70ad7-114">When you are finished, click **Done**.</span></span>
    

