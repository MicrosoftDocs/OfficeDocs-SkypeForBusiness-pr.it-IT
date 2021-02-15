---
title: Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Riepilogo: leggere questo argomento per informazioni su come pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832356"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="3cf60-103">Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cf60-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3cf60-104">**Riepilogo:** Leggere questo argomento per informazioni su come pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cf60-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3cf60-105">La disponibilità elevata e il ripristino di emergenza per il server Chat persistente richiedono risorse aggiuntive oltre a quanto in genere necessario per il funzionamento completo.</span><span class="sxs-lookup"><span data-stu-id="3cf60-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3cf60-106">L'SQL gruppi di disponibilità AlwaysOn non è supportato con i database del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3cf60-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="3cf60-107">La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3cf60-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3cf60-108">Le stesse funzionalità sono disponibili in Teams.</span><span class="sxs-lookup"><span data-stu-id="3cf60-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="3cf60-109">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="3cf60-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="3cf60-110">Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3cf60-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="3cf60-111">Requisiti in termini di risorse</span><span class="sxs-lookup"><span data-stu-id="3cf60-111">Resource requirements</span></span>

<span data-ttu-id="3cf60-112">Prima di configurare il server Chat persistente per la disponibilità elevata e il ripristino di emergenza, verificare di disporre delle risorse aggiuntive seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cf60-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="3cf60-113">Un'istanza di database dedicata che si trova nello stesso data center fisico in cui si trova il front-end principale del servizio del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3cf60-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="3cf60-114">Questo database fungerà da SQL Server mirror per il database di Persistent Chat primario.</span><span class="sxs-lookup"><span data-stu-id="3cf60-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="3cf60-115">Facoltativamente, designare un SQL Server aggiuntivo da utilizzare come controllo del mirroring se si desidera un failover automatico nel database mirror.</span><span class="sxs-lookup"><span data-stu-id="3cf60-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="3cf60-116">Un'istanza di database dedicata nell'altro data center fisico.</span><span class="sxs-lookup"><span data-stu-id="3cf60-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="3cf60-117">Questo database fungerà da SQL Server database secondario di log shipping per il database nel data center principale.</span><span class="sxs-lookup"><span data-stu-id="3cf60-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="3cf60-118">Un'istanza di database dedicata da utilizzare come SQL Server mirror per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="3cf60-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="3cf60-119">Facoltativamente, designare un'SQL Server server come server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="3cf60-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="3cf60-120">Entrambi devono trovarsi nello stesso data center fisico del database secondario.</span><span class="sxs-lookup"><span data-stu-id="3cf60-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="3cf60-121">Se la conformità del server Chat persistente è abilitata, sono necessarie altre tre istanze di database dedicate.</span><span class="sxs-lookup"><span data-stu-id="3cf60-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="3cf60-122">La distribuzione è la stessa di quelle descritte in precedenza per il database di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="3cf60-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="3cf60-123">Sebbene sia possibile per il database di conformità condividere la stessa istanza di SQL Server del database di Persistent Chat, sono consigliate istanze autonome per la disponibilità elevata e il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3cf60-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="3cf60-124">È necessario creare e designare una condivisione file per i SQL Server log shipping.</span><span class="sxs-lookup"><span data-stu-id="3cf60-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="3cf60-125">Tutti SQL server in entrambi i data center che eseguono database di Persistent Chat devono disporre dell'accesso in lettura/scrittura a questa condivisione file.</span><span class="sxs-lookup"><span data-stu-id="3cf60-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="3cf60-126">Tale condivisione non è definita come parte di un ruolo FileStore.</span><span class="sxs-lookup"><span data-stu-id="3cf60-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="3cf60-127">Una condivisione file nel server di database secondario da utilizzare come cartella di destinazione per i registri delle transazioni SQL Server copiati dalla condivisione file del server principale.</span><span class="sxs-lookup"><span data-stu-id="3cf60-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="3cf60-128">Soluzioni di ripristino di emergenza e disponibilità elevata</span><span class="sxs-lookup"><span data-stu-id="3cf60-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="3cf60-129">Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring dei database.</span><span class="sxs-lookup"><span data-stu-id="3cf60-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="3cf60-130">Per ulteriori informazioni, vedere Pianificare la disponibilità elevata e il ripristino di [emergenza in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="3cf60-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="3cf60-131">La soluzione di ripristino di emergenza per il server Chat persistente descritta in questo argomento si basa su un pool di server Chat persistente estesa.</span><span class="sxs-lookup"><span data-stu-id="3cf60-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="3cf60-132">Non è necessario utilizzare una VLAN (Virtual Local Area Network) estesa.</span><span class="sxs-lookup"><span data-stu-id="3cf60-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="3cf60-133">Estendendo un pool di server Chat persistente, si configura logicamente un pool nella topologia, ma si posizionano fisicamente i server nel pool in due data center diversi.</span><span class="sxs-lookup"><span data-stu-id="3cf60-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="3cf60-134">Configurare il SQL Server del database nello stesso modo e distribuire il database e il mirror nello stesso data center.</span><span class="sxs-lookup"><span data-stu-id="3cf60-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="3cf60-135">È necessario configurare un database di backup nel data center secondario (con un mirror facoltativo per fornire disponibilità elevata durante il ripristino di emergenza).</span><span class="sxs-lookup"><span data-stu-id="3cf60-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="3cf60-136">Si tratta del database di backup utilizzato per il failover durante il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="3cf60-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="3cf60-137">Per informazioni dettagliate su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, vedere Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="3cf60-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="3cf60-138">Nelle figure seguenti viene illustrato come configurare il pool di server Chat persistente in due diverse topologie di pool estesa:</span><span class="sxs-lookup"><span data-stu-id="3cf60-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="3cf60-139">Pool di server Persistent Chat esteso quando i data center sono georilevati con un'elevata larghezza di banda e una bassa latenza.</span><span class="sxs-lookup"><span data-stu-id="3cf60-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="3cf60-140">Pool di server Persistent Chat esteso quando i data center sono georilevati con una bassa larghezza di banda e un'elevata latenza.</span><span class="sxs-lookup"><span data-stu-id="3cf60-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="3cf60-141">Nella figura 1 viene illustrata una topologia di pool di server Chat persistente estesa in cui i data center sono georilevati con larghezza di banda elevata/bassa latenza.</span><span class="sxs-lookup"><span data-stu-id="3cf60-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="3cf60-142">Si supponga che per le topologie logiche e fisiche si presupponga quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3cf60-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="3cf60-143">La topologia logica è costituita dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="3cf60-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="3cf60-144">Un pool di Persistent Chat tra i siti 1 e 2 che contiene i server da 1 a 8.</span><span class="sxs-lookup"><span data-stu-id="3cf60-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="3cf60-145">Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non mostrato nel diagramma) che risiede fisicamente nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="3cf60-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="3cf60-146">Un secondo pool Front End Server e un database di backup che risiedono fisicamente nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="3cf60-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="3cf60-147">La topologia fisica è costituita dai siti 1 e 2 nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3cf60-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="3cf60-148">Un pool di Persistent Chat, contenente i server da 1 a 4, due attivi, due inattivi nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="3cf60-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="3cf60-149">Un pool di Persistent Chat, contenente i server da 5 a 8, due attivi, due inattivi nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="3cf60-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="3cf60-150">Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="3cf60-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="3cf60-151">Un pool Front End Server e un database di backup, ovvero la destinazione SQL log shipping, nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="3cf60-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="3cf60-152">**Pool di server Chat persistente estesa quando i data center si trovano in una posizione geografica con larghezza di banda elevata/bassa latenza**</span><span class="sxs-lookup"><span data-stu-id="3cf60-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![Pool di persistent Chat estesa con larghezza di banda elevata/bassa latenza](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="3cf60-154">Nella figura 2 viene illustrata una topologia di pool di server Chat persistente estesa in cui i data center sono georilevati con larghezza di banda bassa/latenza elevata.</span><span class="sxs-lookup"><span data-stu-id="3cf60-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="3cf60-155">La topologia logica è costituita dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="3cf60-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="3cf60-156">Un pool di Persistent Chat tra i siti 1 e 2 che contiene i server da 1 a 8.</span><span class="sxs-lookup"><span data-stu-id="3cf60-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="3cf60-157">Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non mostrato nel diagramma) che risiede fisicamente nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="3cf60-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="3cf60-158">Un secondo pool Front End Server e un database di backup che risiedono fisicamente nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="3cf60-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="3cf60-159">La topologia fisica è costituita dai siti 1 e 2 nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3cf60-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="3cf60-160">Un pool di Persistent Chat, contenente i server da 1 a 4, tutti attivi, nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="3cf60-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="3cf60-161">Un pool di Persistent Chat, contenente i server da 5 a 8, tutti inattivi, nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="3cf60-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="3cf60-162">Un pool Front End Server, un database di Persistent Chat, un database con mirroring e, facoltativamente, un database di controllo (non illustrato nel diagramma) nel sito 1.</span><span class="sxs-lookup"><span data-stu-id="3cf60-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="3cf60-163">Un pool Front End Server e un database di backup, ovvero la destinazione SQL log shipping, nel sito 2.</span><span class="sxs-lookup"><span data-stu-id="3cf60-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="3cf60-164">**Pool di server Chat persistente estesa quando i data center si trovano in una posizione geografica con larghezza di banda bassa/latenza elevata**</span><span class="sxs-lookup"><span data-stu-id="3cf60-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![Pool di persistent Chat estesa con larghezza di banda bassa/latenza elevata](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

