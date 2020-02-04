---
title: "Lync Server 2013: Nuove funzionalità dell'applicazione Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddf1f670ef2a0a246100564962b2f69db741186
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="9e00d-102">Nuove funzionalità dell'applicazione Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e00d-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e00d-103">_**Argomento Ultima modifica:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9e00d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9e00d-104">Con l'applicazione Response Group è possibile instradare e accodare le chiamate in arrivo a persone designate per scopi speciali, come il servizio clienti, un help desk interno o il supporto telefonico generale per un reparto.</span><span class="sxs-lookup"><span data-stu-id="9e00d-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="9e00d-105">Le caratteristiche dell'applicazione di Response Group seguenti sono nuove in Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9e00d-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="9e00d-106">**Ruolo di Manager**</span><span class="sxs-lookup"><span data-stu-id="9e00d-106">**Manager role**</span></span>
    
    <span data-ttu-id="9e00d-107">Lync Server 2013 introduce un nuovo ruolo di Response Group Manager.</span><span class="sxs-lookup"><span data-stu-id="9e00d-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="9e00d-108">Ora ci sono due ruoli di gestione per i gruppi di risposta: Response Group Manager e Response Group Administrator.</span><span class="sxs-lookup"><span data-stu-id="9e00d-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="9e00d-109">Mentre gli amministratori di Response Group possono ancora configurare qualsiasi elemento per qualsiasi gruppo di risposte, i responsabili possono configurare solo determinati elementi, solo per i gruppi di risposta di cui sono proprietari.</span><span class="sxs-lookup"><span data-stu-id="9e00d-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="9e00d-110">Questo miglioramento del modello di amministrazione beneficia della scalabilità dei gruppi di risposta, in particolare per gli scenari di distribuzione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9e00d-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="9e00d-111">**Disponibilità elevata**</span><span class="sxs-lookup"><span data-stu-id="9e00d-111">**High availability**</span></span>
    
    <span data-ttu-id="9e00d-112">Il supporto per la disponibilità elevata per l'applicazione Response Group, sotto forma di mirroring di SQL Server, è abilitato come parte della configurazione e della distribuzione generali della disponibilità elevata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e00d-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="9e00d-113">Se si configura per l'elevata disponibilità e si perde la connettività al server back-end principale, la funzionalità Response Group non viene modificata sfruttando il server back-end con mirroring.</span><span class="sxs-lookup"><span data-stu-id="9e00d-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="9e00d-114">Il supporto per il mirroring di SQL Server per l'applicazione Response Group non può essere abilitato o configurato individualmente all'esterno della configurazione di disponibilità elevata di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e00d-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="9e00d-115">**Ripristino d'emergenza**</span><span class="sxs-lookup"><span data-stu-id="9e00d-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="9e00d-116">Il supporto per il ripristino di emergenza per l'applicazione Response Group viene abilitato come parte della configurazione e della distribuzione dei pool di front end associati, che fanno parte della configurazione complessiva di Disaster Recovery di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e00d-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="9e00d-117">Inoltre, i cmdlet di importazione ed esportazione di Response Group supportano il processo di failover per il pool di backup e il processo di failback nel pool principale o in un nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="9e00d-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="9e00d-118">Se si verifica un'interruzione nel pool principale, è possibile che i gruppi di risposta non vengano eseguiti nel pool di backup e quindi non vengano riportati nel pool principale o in un nuovo pool al termine dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="9e00d-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e00d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e00d-119">See Also</span></span>


[<span data-ttu-id="9e00d-120">Pianificazione dei Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e00d-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

