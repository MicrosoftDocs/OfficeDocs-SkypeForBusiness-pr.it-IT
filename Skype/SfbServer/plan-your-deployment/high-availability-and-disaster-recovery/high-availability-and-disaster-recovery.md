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
description: Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con associazione di pool e diverse modalità di disponibilità elevata del server back-end, tra cui gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802816"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="876a1-103">Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="876a1-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="876a1-104">Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con associazione di pool e diverse modalità di disponibilità elevata del server back-end, tra cui gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="876a1-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="876a1-105">Per disponibilità elevata si intende verificare che i servizi di Skype for Business Server siano disponibili anche se uno o più server non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="876a1-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="876a1-106">Per ripristino di emergenza si intende mantenere i servizi in esecuzione in caso di un'emergenza naturale o causata dall'uomo e conservare la maggior quantità possibile di dati prima della situazione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="876a1-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="876a1-107">Come nelle versioni precedenti di Lync Server, la funzionalità di disponibilità elevata principale per la maggior parte dei ruoli del server in Skype for Business Server è la ridondanza dei server tramite pooling.</span><span class="sxs-lookup"><span data-stu-id="876a1-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="876a1-108">In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.</span><span class="sxs-lookup"><span data-stu-id="876a1-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="876a1-109">Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="876a1-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="876a1-110">Skype for Business Server offre anche opzioni di ripristino di emergenza per i pool Front End.</span><span class="sxs-lookup"><span data-stu-id="876a1-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="876a1-111">È possibile configurare due pool in aree geografiche diverse per fungere da backup l'uno per l'altro.</span><span class="sxs-lookup"><span data-stu-id="876a1-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="876a1-112">Se quindi si verifica un errore in un intero pool o sito, il pool di backup può continuare a fornire il servizio agli utenti di entrambi i siti.</span><span class="sxs-lookup"><span data-stu-id="876a1-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="876a1-113">Skype for Business Server supporta anche quattro modalità di disponibilità elevata per i server back-end: mirroring SQL, gruppi di disponibilità AlwaysOn, istanze del cluster di failover AlwaysOn e clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="876a1-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="876a1-114">SQL mirroring è disponibile in Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="876a1-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="876a1-115">I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="876a1-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="876a1-116">I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="876a1-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="876a1-117">In questa sezione vengono illustrate queste funzionalità e vengono inoltre illustrati i passaggi che è possibile eseguire per la disponibilità elevata e il ripristino di emergenza per alcuni degli altri ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="876a1-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="876a1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="876a1-118">See also</span></span>

[<span data-ttu-id="876a1-119">Disponibilità elevata e gestione del pool Front End</span><span class="sxs-lookup"><span data-stu-id="876a1-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="876a1-120">Ripristino di emergenza del pool Front End in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="876a1-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="876a1-121">Esperienza utente durante un errore del pool in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="876a1-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="876a1-122">Disponibilità elevata del server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="876a1-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="876a1-123">Disponibilità elevata per la condivisione di file in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="876a1-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
