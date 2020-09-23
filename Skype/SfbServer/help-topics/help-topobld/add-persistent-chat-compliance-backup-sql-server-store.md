---
title: Aggiungere l'archivio SQL Server di backup per Conformità Persistent Chat
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: È possibile configurare gli archivi SQL Server di conformità di backup che forniranno i database di backup per il server Chat persistente o per gli archivi SQL Server di conformità di Persistent Chat Server.
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218697"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a><span data-ttu-id="16403-103">Aggiungere l'archivio SQL Server di backup per Conformità Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="16403-103">Add Persistent Chat Compliance Backup SQL Server Store</span></span>
 
<span data-ttu-id="16403-104">È possibile configurare gli archivi SQL Server di conformità di backup che forniranno i database di backup per il server Chat persistente o per gli archivi SQL Server di conformità di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="16403-104">You configure the Backup compliance SQL Server stores that will provide backup databases for the Persistent Chat Server or Persistent Chat Server compliance SQL Server stores.</span></span>
  
 <span data-ttu-id="16403-105">**Archivio SQL Server**: selezionare un SQL Server esistente e facoltativamente un'istanza per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="16403-105">**SQL Server store**: Select an existing SQL Server and optionally an instance for Persistent Chat.</span></span>
  
<span data-ttu-id="16403-106">Fare clic su **nuovo** per definire un nuovo SQL Server e, se lo si desidera, una nuova istanza per i dati di conformità di backup Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="16403-106">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="16403-107">Selezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di conformità di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="16403-107">Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.</span></span>
  
<span data-ttu-id="16403-108">Selezionare dall'elenco **mirroring di SQL Server archivio** un SQL Server e un'istanza facoltativa che funga da mirror di SQL Server per la conformità a SQL Server per il backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="16403-108">Select from the list **Mirroring SQL Server store** a SQL Server and optional instance to act as the SQL Server mirror for the Persistent Chat backup compliance SQL Server.</span></span>
  
<span data-ttu-id="16403-109">Fare clic su **nuovo** per definire un nuovo SQL Server e, se lo si desidera, una nuova istanza per il mirroring di SQL server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="16403-109">Click **New** to define a new SQL Server and optionally a new instance for the Persistent Chat SQL Server mirroring.</span></span>
  
<span data-ttu-id="16403-110">Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="16403-110">Select the list **Use SQL Server mirroring witness to enable automatic failover** a SQL Server that will act as the witness server in failover scenarios.</span></span> <span data-ttu-id="16403-111">Il server di controllo non specchia o ospita i dati per i server Chat persistente, ma garantisce che un solo SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="16403-111">The witness server does not mirror or host data for the Persistent Chat servers, but ensures that only one SQL Server in a mirrored configuration is the active SQL Server at any time.</span></span>
  
<span data-ttu-id="16403-112">Fare clic su **nuovo** per definire un nuovo controllo di SQL Server facoltativamente un'istanza per il controllo del mirroring di SQL Server di conformità di backup di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="16403-112">Click **New** to define a new SQL Server witness optionally an instance for the Persistent Chat backup compliance SQL Server mirroring witness.</span></span>
  
<span data-ttu-id="16403-113">Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.</span><span class="sxs-lookup"><span data-stu-id="16403-113">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="16403-114">Fare clic su **Avanti** dopo aver immesso le opzioni per la configurazione dell'archivio SQL Server di backup di questo pool e per continuare con la definizione del pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="16403-114">Click **Next** after you have finished entering the options for this pool's backup SQL Server store configuration and to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="16403-115">Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="16403-115">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="16403-116">Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="16403-116">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16403-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16403-117">See also</span></span>

[<span data-ttu-id="16403-118">Pianificare il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="16403-118">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="16403-119">Requisiti del server per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="16403-119">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="16403-120">Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="16403-120">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="16403-121">Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="16403-121">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-compliance.md)
  
[<span data-ttu-id="16403-122">Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="16403-122">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
