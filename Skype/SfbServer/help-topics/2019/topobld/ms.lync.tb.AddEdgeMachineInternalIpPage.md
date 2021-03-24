---
title: Aggiungere l'indirizzo IP interno del computer perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.
ms.openlocfilehash: ff6c965c6256e26ebe905ce25e15c9e18a2cd0d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095820"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="f647d-103">Aggiungere Edge Machine External IP</span><span class="sxs-lookup"><span data-stu-id="f647d-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="f647d-104">Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f647d-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="f647d-105">L'FQDN specificato deve essere uguale al nome computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="f647d-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="f647d-106">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="f647d-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="f647d-107">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="f647d-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="f647d-108">È pertanto necessario configurare un suffisso DNS (Domain Name System) per il nome del computer da distribuire come server perimetrale non aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="f647d-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="f647d-109">Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span><span class="sxs-lookup"><span data-stu-id="f647d-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>