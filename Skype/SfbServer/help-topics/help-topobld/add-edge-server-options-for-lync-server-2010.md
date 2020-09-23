---
title: Aggiungere opzioni per i server perimetrali per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'È possibile definire un nuovo server perimetrale o un pool di Edge e presentare la possibilità di definire le funzionalità per il nuovo server o pool. Sono disponibili le opzioni seguenti:'
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216597"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="a7454-104">Aggiungere opzioni per i server perimetrali per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a7454-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="a7454-105">È possibile definire un nuovo server perimetrale o un pool di Edge e presentare la possibilità di definire le funzionalità per il nuovo server o pool.</span><span class="sxs-lookup"><span data-stu-id="a7454-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="a7454-106">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7454-106">The options that you can choose are:</span></span>

- <span data-ttu-id="a7454-107">**Usa singola combinazione di FQDN e indirizzo IP**: selezionare la casella di controllo per utilizzare un singolo indirizzo IPv4 o IPv6 (se si sceglie di utilizzare sia IPv4 che IPv6, sarà necessario definire un indirizzo per ogni tipo di indirizzo IP) e un nome di dominio completo (FQDN) per le interfacce perimetrali esterne.</span><span class="sxs-lookup"><span data-stu-id="a7454-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a7454-108">Se si sceglie questa opzione, si utilizzerà solo un indirizzo IP, oppure un indirizzo IPv4 e un indirizzo IPv6, ma sarà necessario assegnare numeri di porta diversi a ogni interfaccia perimetrale.</span><span class="sxs-lookup"><span data-stu-id="a7454-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="a7454-109">**Abilita federazione per pool di server perimetrali (porta 5061)**: selezionare questa casella di controllo se si attuerà la federazione con altre federazioni SIP, con altri provider oppure con offerte ospitate che utilizzano il protocollo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="a7454-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="a7454-110">**L'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**: selezionare questa casella di controllo se si utilizzano indirizzi IP privati per le interfacce esterne perimetrali e viene fornito un dispositivo NAT (Network Address Translation) per posizionare il server perimetrale o il pool di Edge logicamente dietro.</span><span class="sxs-lookup"><span data-stu-id="a7454-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7454-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7454-111">See also</span></span>

[<span data-ttu-id="a7454-112">Pianificazione dell'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="a7454-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="a7454-113">Distribuzione dell'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="a7454-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
