---
title: Definire l'FQDN di Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: È possibile creare un nuovo server Chat persistente o un nuovo pool di server Chat persistente utilizzando la procedura guidata Definisci nuovo pool di Chat persistente. Selezionare l'opzione desiderata tra Pool di più computer o Pool computer singolo. Se si seleziona un pool di computer singolo e in un secondo momento è necessario un pool di più computer, sarà necessario rimuovere il pool a computer singolo e quindi definire un pool di più computer.
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818446"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="8a756-105">Definire il nome di dominio completo (FQDN) di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="8a756-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="8a756-106">È possibile creare un nuovo server Chat persistente o un nuovo pool di server Chat persistente utilizzando la procedura guidata Definisci nuovo **pool di Chat** persistente.</span><span class="sxs-lookup"><span data-stu-id="8a756-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="8a756-107">Selezionare l'opzione desiderata tra **Pool di più computer** o **Pool computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="8a756-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="8a756-108">Se si seleziona un pool di computer singolo e in un secondo momento è necessario un pool di più computer, sarà necessario rimuovere il pool a computer singolo e quindi definire un pool di più computer.</span><span class="sxs-lookup"><span data-stu-id="8a756-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="8a756-109">È inoltre necessario definire un **FQDN del pool** per il server Chat persistente o il pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8a756-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="8a756-110">Il nome di dominio completo (FQDN) del pool per un pool con un singolo computer deve essere lo stesso dell'FQDN del computer che costituisce il pool.</span><span class="sxs-lookup"><span data-stu-id="8a756-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="8a756-111">Per un pool di più computer, l'FQDN deve essere il nome scelto per rappresentare questo pool ed è definito in DNS da un record host A (e AAAA se si usa IPv6).</span><span class="sxs-lookup"><span data-stu-id="8a756-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a756-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a756-112">See also</span></span>

[<span data-ttu-id="8a756-113">Pianificare il server Chat persistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8a756-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="8a756-114">Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a756-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
