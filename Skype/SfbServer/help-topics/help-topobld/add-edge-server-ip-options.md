---
title: Aggiungere opzioni IP del server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di server perimetrali. Ecco come fare:'
ms.openlocfilehash: d8bfed4d7318133d33d733953cfcf472aa0e88ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815206"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="a19b1-104">Aggiungere opzioni Edge Server IP</span><span class="sxs-lookup"><span data-stu-id="a19b1-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="a19b1-105">Microsoft Lync Server 2013 consente di configurare gli indirizzi IPv4 e IPv6 per ogni interfaccia per il server perimetrale e il pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a19b1-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="a19b1-106">Ecco come fare:</span><span class="sxs-lookup"><span data-stu-id="a19b1-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="a19b1-107">**Abilita IPv4 nell'interfaccia** interna: selezionare la casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="a19b1-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a19b1-108">**Abilita IPv6 nell'interfaccia** interna: selezionare la casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="a19b1-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a19b1-109">**Abilita IPv4 su** interfaccia esterna: selezionare la casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="a19b1-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="a19b1-110">**Abilita IPv6 su** interfaccia esterna: selezionare la casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="a19b1-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="a19b1-111">È inoltre possibile configurare il server perimetrale o il pool di server perimetrali per l'utilizzo di un indirizzo di conversione degli indirizzi di rete per gli indirizzi IP esterni.</span><span class="sxs-lookup"><span data-stu-id="a19b1-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a19b1-112">A tale scopo, selezionare la casella di controllo **L'indirizzo IP esterno di questo pool di server perimetrali viene convertito da NAT.**</span><span class="sxs-lookup"><span data-stu-id="a19b1-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="a19b1-p104">Supporto NAT. Dato che la conversione NAT (Network Address Translation) non è supportata quando si usa il bilanciamento del carico hardware, non selezionare l'opzione NAT quando si distribuisce un pool di server perimetrali con bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="a19b1-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

