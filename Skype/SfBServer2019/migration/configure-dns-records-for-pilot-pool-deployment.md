---
title: Configurare i record DNS per la distribuzione del pool pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Prima di distribuire il pool pilota, è necessario aggiornare le voci dell'host DNS A per il pool pilota. Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754056"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="10ef7-104">Configurare i record DNS per la distribuzione del pool pilota</span><span class="sxs-lookup"><span data-stu-id="10ef7-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="10ef7-105">Prima di distribuire il pool pilota, è necessario aggiornare l'host DNS A voci per il pool pilota.</span><span class="sxs-lookup"><span data-stu-id="10ef7-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="10ef7-106">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="10ef7-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="10ef7-107">Per configurare i record A dell'host DNS</span><span class="sxs-lookup"><span data-stu-id="10ef7-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="10ef7-108">Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="10ef7-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="10ef7-109">Nell'albero della console per il dominio, espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="10ef7-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="10ef7-110">Scegliere **Nuovo host (A o AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="10ef7-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="10ef7-111">Fare clic su **nome**, digitare il nome host per il pool di Skype for Business Server 2019 (il nome di dominio viene assunto dall'area in cui il record è definito e non è necessario immetterlo come parte del record a).</span><span class="sxs-lookup"><span data-stu-id="10ef7-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="10ef7-112">Fare clic su **indirizzo IP**e quindi digitare l'indirizzo IP per il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="10ef7-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="10ef7-113">Fare clic su **Aggiungi host** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="10ef7-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="10ef7-114">Al termine, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="10ef7-114">When you are finished, click **Done**.</span></span>
    

