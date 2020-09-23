---
title: Aggiungere il computer Front End Server
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
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere Define and Configure a Front End Pool nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218317"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="6e0b4-106">Aggiungere il computer Front End Server</span><span class="sxs-lookup"><span data-stu-id="6e0b4-106">Add Front End Machine</span></span>

<span data-ttu-id="6e0b4-107">Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="6e0b4-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="6e0b4-108">Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="6e0b4-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="6e0b4-109">Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN.</span><span class="sxs-lookup"><span data-stu-id="6e0b4-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="6e0b4-110">Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6e0b4-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e0b4-111">Si noti che generatore di topologie indica che è possibile disporre di un massimo di 20 front end server in un pool.</span><span class="sxs-lookup"><span data-stu-id="6e0b4-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="6e0b4-112">Il numero massimo supportato di server è 12.</span><span class="sxs-lookup"><span data-stu-id="6e0b4-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="6e0b4-113">È possibile disporre di un massimo di 20 server statefull definiti nel tessuto, di cui 12 possono essere attivi e online in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="6e0b4-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


