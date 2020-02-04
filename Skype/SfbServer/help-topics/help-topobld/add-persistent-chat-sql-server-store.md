---
title: Aggiungere l'archivio SQL Server per Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Si configurano gli archivi di SQL Server che offrono database per il server di chat persistente o per il pool di server di chat persistente.
ms.openlocfilehash: 794ad4a1b5427fab7a8409fbbbd76448c33e918e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685059"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="87e3a-103">Aggiungere l'archivio SQL Server per Chat persistente</span><span class="sxs-lookup"><span data-stu-id="87e3a-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="87e3a-104">Si configurano gli archivi di SQL Server che offrono database per il server di chat persistente o per il pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87e3a-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="87e3a-105">**SQL Server Store**: selezionare un server SQL esistente e, facoltativamente, un'istanza per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87e3a-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="87e3a-106">Fare clic su **nuovo** per definire un nuovo SQL Server e facoltativamente una nuova istanza per i dati della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87e3a-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="87e3a-107">Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87e3a-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="87e3a-108">Selezionare nell'elenco **mirroring di SQL Server archiviare** un'istanza di SQL Server e facoltativa per fungere da mirror di SQL Server per la chat persistente di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87e3a-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="87e3a-109">Fare clic su **nuovo** per definire un nuovo SQL Server e, facoltativamente, una nuova istanza per il mirroring della chat persistente in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87e3a-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="87e3a-110">Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="87e3a-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="87e3a-111">Il server di controllo non rispecchia né ospita i dati per i server di chat persistenti, ma garantisce che solo un server SQL in una configurazione con mirroring sia il server SQL attivo in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="87e3a-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="87e3a-112">Fare clic su **nuovo** per definire una nuova testimonianza di SQL Server facoltativamente un'istanza per il witness di SQL Server mirroring della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87e3a-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="87e3a-113">Fare clic su **Indietro** per tornare alla precedente finestra di dialogo per la definizione del pool.</span><span class="sxs-lookup"><span data-stu-id="87e3a-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="87e3a-114">Fare clic su **Avanti** dopo aver completato l'immissione delle opzioni per la configurazione di SQL Server Store di questo pool e per procedere con la definizione del pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87e3a-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="87e3a-115">Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool di Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="87e3a-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="87e3a-116">Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="87e3a-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="87e3a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87e3a-117">See also</span></span>

[<span data-ttu-id="87e3a-118">Pianificare il server Chat persistente in Skype per Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="87e3a-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="87e3a-119">Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="87e3a-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="87e3a-120">Requisiti hardware e software per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="87e3a-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="87e3a-121">Requisiti server di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="87e3a-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="87e3a-122">Elementi di base della topologia per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="87e3a-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="87e3a-123">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="87e3a-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
