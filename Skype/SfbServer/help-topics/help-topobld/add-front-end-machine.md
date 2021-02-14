---
title: Aggiungere il computer Front End Server
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
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere Define and Configure a Front End Pool nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 4582aa09527dbc2e663dd6986772b5e88f980a0f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800151"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="dc8be-106">Aggiungere un computer front-end</span><span class="sxs-lookup"><span data-stu-id="dc8be-106">Add Front End Machine</span></span>

<span data-ttu-id="dc8be-107">Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="dc8be-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="dc8be-108">Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="dc8be-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="dc8be-109">Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN.</span><span class="sxs-lookup"><span data-stu-id="dc8be-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="dc8be-110">Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dc8be-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc8be-111">Si noti che Generatore di topologie indica che in un pool possono essere presenti fino a 20 Front End Server.</span><span class="sxs-lookup"><span data-stu-id="dc8be-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="dc8be-112">Il numero massimo supportato di server è 12.</span><span class="sxs-lookup"><span data-stu-id="dc8be-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="dc8be-113">Nell'infrastruttura possono essere definiti fino a 20 server con stato, di cui 12 possono essere attivi e online in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="dc8be-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


