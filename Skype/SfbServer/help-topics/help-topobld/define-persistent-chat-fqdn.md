---
title: Definire l'FQDN di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Si crea un nuovo server di chat persistente o un pool di server di chat persistente usando la procedura guidata Definisci nuovo pool di Persistent Chat. Selezionare l'opzione desiderata tra Pool di più computer o Pool computer singolo. Se si seleziona un pool con un singolo computer e successivamente si vuole definire un pool di più computer, sarà necessario rimuovere il primo pool e poi definire un pool di più computer.
ms.openlocfilehash: 247645e5cc87d23db25784d31c2727d56fab2681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195708"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="1ace4-105">Definire l'FQDN di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="1ace4-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="1ace4-106">Si crea un nuovo server di chat persistente o un pool di server di chat persistente usando la procedura guidata **Definisci nuovo pool di Persistent Chat** .</span><span class="sxs-lookup"><span data-stu-id="1ace4-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="1ace4-107">Selezionare l'opzione desiderata tra **Pool di più computer** o **Pool computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="1ace4-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="1ace4-108">Se si seleziona un pool con un singolo computer e successivamente si vuole definire un pool di più computer, sarà necessario rimuovere il primo pool e poi definire un pool di più computer.</span><span class="sxs-lookup"><span data-stu-id="1ace4-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="1ace4-109">Devi anche definire il **nome di dominio completo del pool** per il server di chat persistente o il pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1ace4-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="1ace4-110">Il nome di dominio completo (FQDN) del pool per un pool con un singolo computer deve essere lo stesso dell'FQDN del computer che costituisce il pool.</span><span class="sxs-lookup"><span data-stu-id="1ace4-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="1ace4-111">Per un pool di più computer, l'FQDN deve essere il nome scelto per rappresentare questo pool ed è definito in DNS da un record host A (e AAAA se si usa IPv6).</span><span class="sxs-lookup"><span data-stu-id="1ace4-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ace4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ace4-112">See also</span></span>

[<span data-ttu-id="1ace4-113">Pianificare il server Chat persistente in Skype per Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1ace4-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1ace4-114">Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1ace4-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
