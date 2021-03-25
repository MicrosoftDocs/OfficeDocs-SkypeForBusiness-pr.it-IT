---
title: Aggiungere opzioni per i server perimetrali per Lync Server 2010
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: "Si definisce un nuovo server perimetrale o un nuovo pool di server perimetrali e viene offerta l'opportunità di definire le funzionalità per il nuovo server o pool. Sono disponibili le opzioni seguenti:"
ms.openlocfilehash: dfc8238bbbe4899f9819118a11fc11ba47fe21f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119805"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="e0529-104">Aggiungere opzioni Edge Server per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e0529-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="e0529-105">Si definisce un nuovo server perimetrale o un nuovo pool di server perimetrali e viene offerta l'opportunità di definire le funzionalità per il nuovo server o pool.</span><span class="sxs-lookup"><span data-stu-id="e0529-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="e0529-106">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0529-106">The options that you can choose are:</span></span>

- <span data-ttu-id="e0529-107">**Usa singola combinazione di FQDN e indirizzo IP**: selezionare la casella di controllo per utilizzare un singolo indirizzo IPv4 o IPv6 (se si sceglie di utilizzare sia IPv4 che IPv6, sarà necessario definire un indirizzo per ogni tipo di indirizzo IP) e un nome di dominio completo (FQDN) per le interfacce perimetrali esterne.</span><span class="sxs-lookup"><span data-stu-id="e0529-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e0529-108">Se si sceglie questa opzione, si utilizzerà solo un indirizzo IP, oppure un indirizzo IPv4 e un indirizzo IPv6, ma sarà necessario assegnare numeri di porta diversi a ogni interfaccia perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e0529-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="e0529-109">**Abilita federazione per pool di server perimetrali (porta 5061)**: selezionare questa casella di controllo se si attuerà la federazione con altre federazioni SIP, con altri provider oppure con offerte ospitate che utilizzano il protocollo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="e0529-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="e0529-110">**L'indirizzo IP** esterno di questo pool di server perimetrali viene convertito da NAT: selezionare questa casella di controllo se si utilizzano indirizzi IP privati per le interfacce esterne perimetrali e si fornirà un dispositivo NAT (Network Address Translation) in cui posizionare logicamente il server perimetrale o il pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="e0529-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0529-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0529-111">See also</span></span>

[<span data-ttu-id="e0529-112">Pianificazione dell'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="e0529-112">Planning for External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[<span data-ttu-id="e0529-113">Distribuzione dell'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="e0529-113">Deploying External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)