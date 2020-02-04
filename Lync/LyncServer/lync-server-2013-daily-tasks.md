---
title: 'Lync Server 2013: attività quotidiane'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d63aff308b23e52284988a184e5e9d72beaca26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="67296-102">Attività quotidiane in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67296-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67296-103">_**Argomento Ultima modifica:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="67296-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="67296-104">Per garantire la disponibilità e l'affidabilità della distribuzione di Lync Server 2013, è necessario, come parte del monitor di routine quotidiana e gli elementi di test molto importanti per il funzionamento del sistema, che include la piattaforma fisica, il sistema operativo e tutti i servizi importanti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67296-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="67296-105">La manutenzione preventiva e il monitoraggio proattivo consentono di identificare potenziali errori e problemi che possono influire negativamente sulla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67296-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="67296-106">Il monitoraggio della distribuzione di Lync Server 2013 prevede il controllo dei problemi relativi a connessioni, servizi, risorse del server e risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="67296-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="67296-107">I sistemi operativi Windows Server, insieme a System Center Operations Manager e Lync Server offrono molti strumenti e servizi di monitoraggio per garantire che l'organizzazione di Lync Server sia in grado di funzionare senza problemi.</span><span class="sxs-lookup"><span data-stu-id="67296-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="67296-108">Con l'implementazione concomitante di queste tecnologie, gli amministratori possono ricevere avvisi prima o durante il verificarsi dei problemi.</span><span class="sxs-lookup"><span data-stu-id="67296-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="67296-109">I principali vantaggi di un'attività di monitoraggio quotidiana sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="67296-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="67296-110">Rispetto dei requisiti relativi a disponibilità e prestazioni dei contratti di servizio prestabiliti.</span><span class="sxs-lookup"><span data-stu-id="67296-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="67296-111">Completamento di specifiche attività amministrative, ad esempio backup giornalieri, e verifica dell'integrità del server.</span><span class="sxs-lookup"><span data-stu-id="67296-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="67296-112">Rilevamento e risoluzione dei problemi, ad esempio colli di bottiglia nelle prestazioni del server, o dell'esigenza di risorse supplementari prima che questa situazione pregiudichi la produttività.</span><span class="sxs-lookup"><span data-stu-id="67296-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="67296-113">Le attività di manutenzione quotidiana consentono al team dell'amministrazione di fissare un criterio o un riferimento di base per il normale funzionamento dei sistemi all'interno dell'organizzazione e di individuare quindi eventuali attività anomale.</span><span class="sxs-lookup"><span data-stu-id="67296-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="67296-114">È importante implementare queste attività di manutenzione giornaliera in modo che il team amministrativo possa acquisire e gestire i dati sull'infrastruttura di Lync Server 2013, ad esempio i livelli di utilizzo, i possibili colli di bottiglia delle prestazioni e le modifiche amministrative.</span><span class="sxs-lookup"><span data-stu-id="67296-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="67296-115">Per organizzare con facilità le attività quotidiane, utilizzare l'[Elenco di controllo delle attività quotidiane](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="67296-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="67296-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67296-116">See Also</span></span>


[<span data-ttu-id="67296-117">Elenco di controllo delle attività quotidiane</span><span class="sxs-lookup"><span data-stu-id="67296-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

