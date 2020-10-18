---
title: 'Lync Server 2013: requisiti per la pubblicazione di una topologia'
description: 'Lync Server 2013: requisiti per la pubblicazione di una topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577862"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="805c4-103">Requisiti per la pubblicazione di una topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805c4-103">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="805c4-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="805c4-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="805c4-105">In questo argomento vengono descritti i requisiti dell'infrastruttura e del software specifici per la pubblicazione di una topologia, se si utilizza il generatore di topologie o l'interfaccia della riga di comando di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="805c4-105">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="805c4-106">Questi requisiti si aggiungono ai requisiti del sistema operativo, del software e delle autorizzazioni generali applicabili a tutti gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="805c4-106">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="805c4-107">Assicurarsi di soddisfare tutti i requisiti degli strumenti di amministrazione prima di pubblicare una topologia.</span><span class="sxs-lookup"><span data-stu-id="805c4-107">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="805c4-108">È necessario eseguire Generatore di topologie in un computer aggiunto allo stesso dominio o foresta della distribuzione di Lync Server 2013 che si sta creando, in modo che i passaggi di preparazione di servizi di dominio Active Directory siano già stati completati, consentendo di utilizzare gli strumenti di amministrazione di quel computer per pubblicare correttamente la topologia.</span><span class="sxs-lookup"><span data-stu-id="805c4-108">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="805c4-p102">I computer definiti nella topologia devono appartenere al dominio, ad eccezione dei server perimetrali, nonché essere in Servizi di dominio Active Directory. Non è tuttavia necessario che i computer siano online quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="805c4-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="805c4-111">La condivisione file per il pool deve essere creata ed essere disponibile per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="805c4-111">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="805c4-112">Per pubblicare un pool Enterprise Edition front end, il server back-end basato su SQL Server deve essere aggiunto al dominio in cui si distribuiscono i server, online e configurati con le regole del firewall appropriate per renderlo disponibile per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="805c4-112">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="805c4-113">Per informazioni dettagliate su come specificare le eccezioni del firewall, vedere [Understanding firewall requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="805c4-113">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="805c4-114">Per ulteriori informazioni sulla configurazione di SQL Server, vedere [Configure SQL Server for Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="805c4-114">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="805c4-115">Il server Standard Edition dispone di un database collocato che accetterà la configurazione pubblicata.</span><span class="sxs-lookup"><span data-stu-id="805c4-115">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="805c4-116">È innanzitutto necessario eseguire l'attività <STRONG>preparazione del primo server Standard Edition</STRONG> nella distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="805c4-116">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="805c4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="805c4-117">See Also</span></span>


[<span data-ttu-id="805c4-118">Pubblicare la topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805c4-118">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="805c4-119">Delegare le autorizzazioni di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805c4-119">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="805c4-120">Requisiti software per gli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805c4-120">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="805c4-121">Supporto del sistema operativo per server e strumenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805c4-121">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="805c4-122">Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805c4-122">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

