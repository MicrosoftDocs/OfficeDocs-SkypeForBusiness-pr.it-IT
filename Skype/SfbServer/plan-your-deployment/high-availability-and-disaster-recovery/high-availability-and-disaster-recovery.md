---
title: Pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.
ms.openlocfilehash: 521ddaa9878ba660e509f248d2f2ffb944608d87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815924"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="5f039-103">Pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5f039-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="5f039-104">Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="5f039-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="5f039-105">L'elevata disponibilità fa riferimento a garantire che i servizi di Skype for Business Server siano disponibili anche se uno o più server vengono abbattuti.</span><span class="sxs-lookup"><span data-stu-id="5f039-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="5f039-106">Il ripristino di emergenza si riferisce a mantenere i servizi in corso in caso di un disastro naturale o causato dall'uomo e a preservare il maggior quantità possibile di dati prima del disastro.</span><span class="sxs-lookup"><span data-stu-id="5f039-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="5f039-107">Come nelle versioni precedenti di Lync Server, la caratteristica di elevata disponibilità principale per la maggior parte dei ruoli del server in Skype for Business Server è la ridondanza del server tramite pooling.</span><span class="sxs-lookup"><span data-stu-id="5f039-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="5f039-108">Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.</span><span class="sxs-lookup"><span data-stu-id="5f039-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="5f039-109">Questo vale per i server front-end, Edge Server, Mediation Server e direttori.</span><span class="sxs-lookup"><span data-stu-id="5f039-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="5f039-110">Skype for Business Server offre anche le opzioni di ripristino di emergenza per i pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="5f039-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="5f039-111">È possibile configurare due pool in aree geografiche diverse per fungere da backup.</span><span class="sxs-lookup"><span data-stu-id="5f039-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="5f039-112">Quindi, se si ha un intero pool o un sito, il pool di backup può continuare a prestare servizio agli utenti in entrambi i siti.</span><span class="sxs-lookup"><span data-stu-id="5f039-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="5f039-113">Skype for Business Server supporta anche quattro modalità di disponibilità elevata per i server back-end: mirroring SQL, gruppi di disponibilità AlwaysOn, istanze del cluster di failover AlwaysOn (FCI) e clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="5f039-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f039-114">Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5f039-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5f039-115">I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5f039-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="5f039-116">I gruppi di disponibilità AlwaysOn non sono supportati con i server di chat permanenti.</span><span class="sxs-lookup"><span data-stu-id="5f039-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="5f039-117">In questa sezione vengono illustrate queste funzionalità e vengono descritte anche le procedure che è possibile eseguire per l'elevata disponibilità e il ripristino di emergenza per alcuni altri ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="5f039-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5f039-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f039-118">See also</span></span>

[<span data-ttu-id="5f039-119">Disponibilità elevata e gestione del pool Front-End</span><span class="sxs-lookup"><span data-stu-id="5f039-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="5f039-120">Ripristino di emergenza del pool di front-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5f039-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="5f039-121">Esperienza utente durante l'errore del pool in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5f039-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="5f039-122">Disponibilità elevata del server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5f039-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="5f039-123">Condivisione di file con disponibilità elevata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5f039-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
