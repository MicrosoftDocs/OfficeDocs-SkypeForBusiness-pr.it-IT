---
title: Aggiungere l'indirizzo IP interno del computer perimetrale (2010)
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.
ms.openlocfilehash: 51ab7e117892efbbbd7fd16a27b3f06b599297b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120948"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="0feb3-103">Aggiungere Edge Machine Internal IP 2010</span><span class="sxs-lookup"><span data-stu-id="0feb3-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="0feb3-104">Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0feb3-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="0feb3-105">In **Indirizzo IPv4 interno** digitare l'indirizzo IP del server perimetrale che si desidera aggiungere al pool.</span><span class="sxs-lookup"><span data-stu-id="0feb3-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="0feb3-106">In **FQDN interno** digitare il nome di dominio completo (FQDN) del server perimetrale che si desidera aggiungere al pool.</span><span class="sxs-lookup"><span data-stu-id="0feb3-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="0feb3-107">L'FQDN specificato deve essere uguale al nome computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="0feb3-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="0feb3-108">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="0feb3-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="0feb3-109">Generatore di topologie utilizza gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="0feb3-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="0feb3-110">È pertanto necessario configurare un suffisso DNS (Domain Name System) per il nome del computer da distribuire come server perimetrale non aggiunto a un dominio.</span><span class="sxs-lookup"><span data-stu-id="0feb3-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="0feb3-111">Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span><span class="sxs-lookup"><span data-stu-id="0feb3-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>