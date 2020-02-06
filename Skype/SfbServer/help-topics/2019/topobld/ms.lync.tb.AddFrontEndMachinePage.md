---
title: Aggiungere un computer front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Specificare il nome di dominio completo (FQDN) di ogni computer che si vuole aggiungere come server front-end in questo pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima della pubblicazione della topologia. Dopo aver pubblicato la topologia, la modifica dell'FQDN richiede l'eliminazione del server in Generatore di topologia e l'aggiunta di un nuovo server al pool con il nuovo nome di dominio completo. Per informazioni dettagliate sull'aggiunta di un pool Front-end alla topologia, vedere definire e configurare un pool Front end nella documentazione relativa alla distribuzione.
ms.openlocfilehash: a4ff4ce7a7fc775e33657dc2f8602d62163ed1d4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798543"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="e247e-106">Aggiungere un computer front-end</span><span class="sxs-lookup"><span data-stu-id="e247e-106">Add Front End Machine</span></span>

<span data-ttu-id="e247e-107">Specificare il nome di dominio completo (FQDN) di ogni computer che si vuole aggiungere come server front-end in questo pool.</span><span class="sxs-lookup"><span data-stu-id="e247e-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="e247e-108">Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima della pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="e247e-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="e247e-109">Dopo aver pubblicato la topologia, la modifica dell'FQDN richiede l'eliminazione del server in Generatore di topologia e l'aggiunta di un nuovo server al pool con il nuovo nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="e247e-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="e247e-110">Per informazioni dettagliate sull'aggiunta di un pool Front-end alla topologia, vedere [definire e configurare un pool Front End](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e247e-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e247e-111">Tieni presente che generatore di topologie indica che puoi avere fino a 20 server front-end in un pool.</span><span class="sxs-lookup"><span data-stu-id="e247e-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="e247e-112">Il numero massimo supportato di server è 12.</span><span class="sxs-lookup"><span data-stu-id="e247e-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="e247e-113">È possibile avere fino a 20 server statefull definiti nel tessuto, di cui 12 possono essere attivi e online in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="e247e-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


