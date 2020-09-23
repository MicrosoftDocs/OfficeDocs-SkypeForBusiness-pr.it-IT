---
title: Aggiungere l'archivio SQL Server di backup per Persistent Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: È possibile configurare gli archivi SQL Server di backup che forniranno i database di backup per il server Chat persistente o per il pool di server Chat persistente.
ms.openlocfilehash: 70eec229c567120d0669979f688c152e1b1e3d79
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218707"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a><span data-ttu-id="d9741-103">Aggiungere l'archivio SQL Server di backup per Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="d9741-103">Add Persistent Chat Backup SQL Server Store</span></span>
 
<span data-ttu-id="d9741-104">È possibile configurare gli archivi SQL Server di backup che forniranno i database di backup per il server Chat persistente o per il pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9741-104">You configure the Backup SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="d9741-105">**Archivio SQL Server**: selezionare un SQL Server esistente e facoltativamente un'istanza per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9741-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="d9741-106">Fare clic su **nuovo** per definire un nuovo SQL Server e facoltativamente una nuova istanza per i dati di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="d9741-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="d9741-107">Selezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="d9741-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup data.</span></span>
  
<span data-ttu-id="d9741-108">Selezionare dall'elenco **mirroring di SQL Server archivio** un SQL Server e un'istanza facoltativa da utilizzare come mirror di SQL Server per il backup di SQL server Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="d9741-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup SQL Server.</span></span>
  
<span data-ttu-id="d9741-109">Fare clic su **nuovo** per definire un nuovo SQL Server e, se lo si desidera, una nuova istanza per il mirroring di SQL server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9741-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="d9741-110">Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="d9741-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="d9741-111">Il server di controllo non specchia o ospita i dati per i server Chat persistente, ma garantisce che un solo SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="d9741-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="d9741-112">Fare clic su **nuovo** per definire un nuovo witness di SQL Server facoltativamente un'istanza per il controllo del mirroring di SQL Server per il backup di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9741-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="d9741-113">Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.</span><span class="sxs-lookup"><span data-stu-id="d9741-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="d9741-114">Fare clic su **Avanti** dopo aver immesso le opzioni per la configurazione dell'archivio SQL Server di backup di questo pool e per continuare con la definizione del pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9741-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="d9741-115">Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="d9741-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="d9741-116">Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="d9741-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9741-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9741-117">See also</span></span>

[<span data-ttu-id="d9741-118">Pianificare il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d9741-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="d9741-119">Requisiti del server per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d9741-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="d9741-120">Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d9741-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="d9741-121">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d9741-121">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
