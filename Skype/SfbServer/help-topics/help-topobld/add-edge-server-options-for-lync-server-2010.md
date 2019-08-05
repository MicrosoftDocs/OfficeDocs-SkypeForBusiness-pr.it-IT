---
title: Aggiungere le opzioni di Edge Server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Si definisce un nuovo Edge Server o un pool di Edge e si presenta la possibilità di definire le caratteristiche per il nuovo server o pool. Le opzioni che è possibile scegliere sono:'
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191663"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="6f192-104">Aggiungere le opzioni di Edge Server per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6f192-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="6f192-105">Si definisce un nuovo Edge Server o un pool di Edge e si presenta la possibilità di definire le caratteristiche per il nuovo server o pool.</span><span class="sxs-lookup"><span data-stu-id="6f192-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="6f192-106">Le opzioni che è possibile scegliere sono:</span><span class="sxs-lookup"><span data-stu-id="6f192-106">The options that you can choose are:</span></span>

- <span data-ttu-id="6f192-107">**Usare un singolo FQDN e un indirizzo IP**: selezionare la casella di controllo per usare un singolo IPv4 o IPv6 (se si sceglie di usare sia IPv4 che IPv6, sarà necessario definire uno dei singoli indirizzi IP) e il nome di dominio completo (FQDN) per le interfacce di Edge esterne.</span><span class="sxs-lookup"><span data-stu-id="6f192-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6f192-108">Se si sceglie questa opzione, si utilizzerà un solo indirizzo IP o uno IPv4 e un IPv6, ma è necessario assegnare numeri di porta diversi a ogni interfaccia Edge.</span><span class="sxs-lookup"><span data-stu-id="6f192-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="6f192-109">**Enable Federation (porta 5061)**: selezionare questa casella di controllo se si vuole eseguire la Federazione con altre federazioni SIP, provider o offerte ospitate che usano il protocollo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="6f192-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="6f192-110">**L'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**: selezionare questa casella di controllo se si usano indirizzi IP privati per le interfacce esterne di Edge e viene fornito un dispositivo NAT (Network Address Translation) per posizionare logicamente l'Edge Server o il pool di Edge dietro.</span><span class="sxs-lookup"><span data-stu-id="6f192-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f192-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f192-111">See also</span></span>

[<span data-ttu-id="6f192-112">Pianificazione per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="6f192-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="6f192-113">Distribuzione dell'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="6f192-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
