---
title: Aggiungere l'archivio SQL Server per Persistent Chat
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configurare gli archivi SQL Server che forniranno i database per il server Chat persistente o il pool di server Chat persistente.
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818656"
---
# <a name="add-persistent-chat-sql-server-store"></a><span data-ttu-id="8653f-103">Aggiungere l'archivio SQL Server per Chat persistente</span><span class="sxs-lookup"><span data-stu-id="8653f-103">Add Persistent Chat SQL Server Store</span></span>
 
<span data-ttu-id="8653f-104">Configurare gli archivi SQL Server che forniranno i database per il server Chat persistente o il pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8653f-104">You configure the SQL Server stores that will provide databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="8653f-105">**SQL Server:** selezionare un'istanza esistente SQL Server e facoltativamente un'istanza per Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="8653f-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="8653f-106">Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per i dati di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="8653f-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat data.</span></span>
  
<span data-ttu-id="8653f-107">Selezionare la **casella di controllo SQL Server mirroring** dell'archivio per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="8653f-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat data.</span></span>
  
<span data-ttu-id="8653f-108">Selezionare nell'elenco **Mirroring SQL Server archiviare** un SQL Server e un'istanza facoltativa per fungere da SQL Server mirror per il SQL Server persistente.</span><span class="sxs-lookup"><span data-stu-id="8653f-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat SQL Server.</span></span>
  
<span data-ttu-id="8653f-109">Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per il mirroring SQL Server Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="8653f-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="8653f-110">Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="8653f-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="8653f-111">Il server di controllo non esegue il mirroring o ospita i dati per i server Chat persistente, ma garantisce che un solo SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="8653f-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="8653f-112">Fare **clic su** Nuovo per definire un nuovo SQL Server di controllo, facoltativamente un'istanza per il SQL Server di mirroring di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="8653f-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="8653f-113">Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.</span><span class="sxs-lookup"><span data-stu-id="8653f-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="8653f-114">Fare **clic** su Avanti dopo aver immesso le opzioni per la configurazione dell'archivio SQL Server pool e per continuare con la definizione del pool del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8653f-114">Click **Next** after you have finished entering the options for this pool's SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="8653f-115">Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="8653f-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="8653f-116">Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="8653f-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8653f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8653f-117">See also</span></span>

[<span data-ttu-id="8653f-118">Pianificare il server Chat persistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8653f-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="8653f-119">Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8653f-119">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="8653f-120">Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8653f-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="8653f-121">Requisiti del server per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8653f-121">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="8653f-122">Nozioni di base sulla topologia per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8653f-122">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[<span data-ttu-id="8653f-123">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8653f-123">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
