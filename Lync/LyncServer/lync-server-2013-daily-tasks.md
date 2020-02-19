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
ms.openlocfilehash: 59204fab5a1df067668f73ca4752033b64326a2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="8df25-102">Attività quotidiane in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8df25-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8df25-103">_**Ultimo argomento modificato:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="8df25-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="8df25-104">Per garantire la disponibilità e l'affidabilità della distribuzione di Lync Server 2013, è necessario nell'ambito del monitoraggio e degli elementi di test giornalieri molto importanti per il funzionamento del sistema, che include la piattaforma fisica, il sistema operativo e tutti i servizi di Lync Server 2013 importanti.</span><span class="sxs-lookup"><span data-stu-id="8df25-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="8df25-105">La manutenzione preventiva e il monitoraggio proattivo consentono di individuare eventuali errori e problemi che possono influire negativamente sulla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8df25-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="8df25-106">Il monitoraggio della distribuzione di Lync Server 2013 prevede la verifica dei problemi relativi a connessioni, servizi, risorse del server e risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="8df25-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="8df25-107">I sistemi operativi Windows Server, insieme a System Center Operations Manager e Lync Server offrono numerosi strumenti e servizi di monitoraggio per garantire che l'organizzazione di Lync Server sia in esecuzione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="8df25-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="8df25-108">Quando queste tecnologie vengono implementate insieme, gli amministratori saranno in grado di ricevere avvisi quando o prima che si verifichino problemi.</span><span class="sxs-lookup"><span data-stu-id="8df25-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="8df25-109">Di seguito sono riportati i principali vantaggi derivanti dal monitoraggio giornaliero:</span><span class="sxs-lookup"><span data-stu-id="8df25-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="8df25-110">Soddisfare i requisiti di prestazioni e disponibilità dei contratti di SLA definiti.</span><span class="sxs-lookup"><span data-stu-id="8df25-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="8df25-111">Completamento di attività amministrative specifiche, ad esempio operazioni di backup quotidiane, e controllo dell'integrità del server.</span><span class="sxs-lookup"><span data-stu-id="8df25-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="8df25-112">Rilevamento e risoluzione dei problemi, ad esempio colli di bottiglia nelle prestazioni del server, o necessità di risorse aggiuntive prima che influiscano sulla produttività.</span><span class="sxs-lookup"><span data-stu-id="8df25-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="8df25-113">Le attività quotidiane di manutenzione aiutano il team amministrativo a definire o stabilire criteri o previsioni per le normali operazioni dei sistemi all'interno dell'organizzazione e a rilevare eventuali attività anormali.</span><span class="sxs-lookup"><span data-stu-id="8df25-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="8df25-114">È importante implementare queste attività di manutenzione giornaliera in modo che il team amministrativo possa acquisire e gestire i dati sull'infrastruttura di Lync Server 2013, ad esempio i livelli di utilizzo, i possibili colli di bottiglia delle prestazioni e le modifiche amministrative.</span><span class="sxs-lookup"><span data-stu-id="8df25-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="8df25-115">Per facilitare l'organizzazione delle prestazioni delle attività quotidiane, utilizzare l' [elenco di controllo delle attività quotidiane](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="8df25-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8df25-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8df25-116">See Also</span></span>


[<span data-ttu-id="8df25-117">Elenco di controllo delle attività quotidiane</span><span class="sxs-lookup"><span data-stu-id="8df25-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

