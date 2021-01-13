---
title: Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con l'abbinamento del pool e diverse modalità di disponibilità elevata del server back-end, inclusi i gruppi di disponibilità AlwaysOn, il mirroring del database e il clustering di failover SQL.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802816"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="6a6bc-103">Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a6bc-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="6a6bc-104">Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con l'abbinamento del pool e diverse modalità di disponibilità elevata del server back-end, inclusi i gruppi di disponibilità AlwaysOn, il mirroring del database e il clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="6a6bc-105">La disponibilità elevata si riferisce al fare in modo che i servizi di Skype for Business Server siano disponibili anche se uno o più server sono inattivi.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="6a6bc-106">Il ripristino di emergenza si riferisce alla conservazione dei servizi in caso di emergenza naturale o causata da un ambiente umano e alla conservazione del maggior quantità possibile di dati prima del verificarsi del disastro.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="6a6bc-107">Come nelle versioni precedenti di Lync Server, la caratteristica a disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server è la ridondanza del server tramite pool.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="6a6bc-108">In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="6a6bc-109">Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="6a6bc-110">Skype for Business Server fornisce anche le opzioni di ripristino di emergenza per i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="6a6bc-111">È possibile configurare due pool in aree geografiche diverse per fungere da backup.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="6a6bc-112">Se si dispone di un intero pool o di un sito, il pool di backup può continuare a fornire servizi agli utenti di entrambi i siti.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="6a6bc-113">Skype for Business Server supporta inoltre quattro modalità di disponibilità elevata per i server back-end: il mirroring SQL, i gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e il clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a6bc-114">Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6a6bc-115">I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="6a6bc-116">I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="6a6bc-117">In questa sezione vengono illustrate queste funzionalità e vengono descritti i passaggi che è possibile eseguire per la disponibilità elevata e il ripristino di emergenza per alcuni degli altri ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="6a6bc-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6a6bc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a6bc-118">See also</span></span>

[<span data-ttu-id="6a6bc-119">Disponibilità elevata e gestione del pool Front End</span><span class="sxs-lookup"><span data-stu-id="6a6bc-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="6a6bc-120">Ripristino di emergenza del pool Front end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a6bc-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="6a6bc-121">Esperienza utente durante un errore del pool in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a6bc-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="6a6bc-122">Disponibilità elevata del server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a6bc-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="6a6bc-123">Disponibilità elevata della condivisione di file in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a6bc-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
