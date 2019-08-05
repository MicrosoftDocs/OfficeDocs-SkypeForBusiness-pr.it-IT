---
title: Aggiungere le opzioni IP di Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per Edge Server e Edge pool. A questo scopo, eseguire le operazioni seguenti:'
ms.openlocfilehash: de0b0e0c050721a4fb54a450db89e34f65ea7f7f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194489"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="3e468-104">Aggiungere le opzioni IP di Edge Server</span><span class="sxs-lookup"><span data-stu-id="3e468-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="3e468-105">Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per Edge Server e Edge pool.</span><span class="sxs-lookup"><span data-stu-id="3e468-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="3e468-106">A questo scopo, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e468-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="3e468-107">**Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="3e468-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="3e468-108">**Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="3e468-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="3e468-109">**Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="3e468-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="3e468-110">**Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge</span><span class="sxs-lookup"><span data-stu-id="3e468-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="3e468-111">È anche possibile configurare l'Edge Server o il pool di Edge in uso di un indirizzo di rete per gli indirizzi IP esterni.</span><span class="sxs-lookup"><span data-stu-id="3e468-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="3e468-112">A tale scopo, seleziona la casella di controllo **l'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**.</span><span class="sxs-lookup"><span data-stu-id="3e468-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="3e468-113">Supporto NAT.</span><span class="sxs-lookup"><span data-stu-id="3e468-113">NAT support.</span></span> <span data-ttu-id="3e468-114">NAT (Network Address Translation) non è supportato quando si usa il bilanciamento del carico hardware, quindi non selezionare l'opzione NAT se si distribuisce un pool di Edge Server con il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="3e468-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

