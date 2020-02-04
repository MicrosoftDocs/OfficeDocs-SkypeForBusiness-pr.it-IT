---
title: Aggiungere Edge Machine Internal IP 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno per il server perimetrale.
ms.openlocfilehash: 4c1606dfc44a303b5e9eb8e84710b14b41b7da90
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685299"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="6f84c-103">Aggiungere Edge Machine Internal IP 2010</span><span class="sxs-lookup"><span data-stu-id="6f84c-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="6f84c-104">Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="6f84c-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="6f84c-105">Nell' **indirizzo IPv4 interno**Digitare l'indirizzo IP del server perimetrale che si vuole aggiungere al pool.</span><span class="sxs-lookup"><span data-stu-id="6f84c-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="6f84c-106">In **FQDN interno**Digitare il nome di dominio completo (FQDN) dell'Edge Server che si vuole aggiungere al pool.</span><span class="sxs-lookup"><span data-stu-id="6f84c-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="6f84c-107">L'FQDN specificato deve essere identico al nome del computer configurato nel server.</span><span class="sxs-lookup"><span data-stu-id="6f84c-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="6f84c-108">Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN.</span><span class="sxs-lookup"><span data-stu-id="6f84c-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="6f84c-109">Generatore di topologie usa gli FQDN e non i nomi brevi.</span><span class="sxs-lookup"><span data-stu-id="6f84c-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6f84c-110">È quindi necessario configurare un suffisso DNS (Domain Name System) sul nome del computer da distribuire come server perimetrale che non è associato a un dominio.</span><span class="sxs-lookup"><span data-stu-id="6f84c-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="6f84c-111">Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome di computer, vedere [configurare DNS per il supporto Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f84c-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


