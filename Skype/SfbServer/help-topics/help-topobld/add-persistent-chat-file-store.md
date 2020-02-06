---
title: Aggiungere l'archivio file per Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: f11443f8c10db35d5ffb8bfdbfc03d9826700b7c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820678"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="67c81-104">Aggiungere l'archivio file per Chat persistente</span><span class="sxs-lookup"><span data-stu-id="67c81-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="67c81-p102">È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.</span><span class="sxs-lookup"><span data-stu-id="67c81-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="67c81-107">La condivisione file per Skype for Business Server non può essere posizionata nel server front-end Enterprise Edition, ma può essere posizionata in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="67c81-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="67c81-108">È possibile definire la condivisione file in Generatore di topologie prima di crearla, ma è necessario crearla nel percorso definito prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="67c81-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="67c81-109">Quando si aggiunge un server di chat persistente o un pool di server di chat persistente alla topologia, generatore di topologie deve essere in grado di configurare l'archivio di file e configurarne gli elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio di file.</span><span class="sxs-lookup"><span data-stu-id="67c81-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="67c81-110">Per questo, quando si esegue Generatore di topologie per pubblicare la nuova topologia, è necessario essere connessi con un account dotato di autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="67c81-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="67c81-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67c81-111">See also</span></span>

[<span data-ttu-id="67c81-112">Pianificare il server Chat persistente in Skype per Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="67c81-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="67c81-113">Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="67c81-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="67c81-114">Requisiti hardware e software per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="67c81-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="67c81-115">Requisiti server di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="67c81-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="67c81-116">Elementi di base della topologia per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="67c81-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
