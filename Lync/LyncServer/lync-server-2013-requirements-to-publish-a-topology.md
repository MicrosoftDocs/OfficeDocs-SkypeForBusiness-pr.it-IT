---
title: 'Lync Server 2013: Requisiti per la pubblicazione di una topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e90604315732d9e9bfe4c45968ff0bcf5fbd2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="894a7-102">Requisiti per la pubblicazione di una topologia Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="894a7-102">Requirements to publish a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="894a7-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="894a7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="894a7-104">Questo argomento descrive i requisiti di infrastruttura e software specifici per la pubblicazione di una topologia, sia tramite Generatore di topologia che con l'interfaccia della riga di comando di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="894a7-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="894a7-105">Questi requisiti si aggiungono ai requisiti del sistema operativo, del software e delle autorizzazioni generali applicabili a tutti gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="894a7-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="894a7-106">Verificare di soddisfare tutti i requisiti degli strumenti amministrativi prima di pubblicare una topologia.</span><span class="sxs-lookup"><span data-stu-id="894a7-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="894a7-107">È necessario eseguire Generatore di topologia in un computer associato allo stesso dominio o alla stessa foresta della distribuzione di Lync Server 2013 che si sta creando in modo che i passaggi di preparazione di Active Directory Domain Services siano già stati completati, consentendo di usare gli strumenti di amministrazione in tale computer per pubblicare correttamente la topologia.</span><span class="sxs-lookup"><span data-stu-id="894a7-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="894a7-108">I computer definiti nella topologia devono essere Uniti al dominio, ad eccezione di Edge Server e in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="894a7-108">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS.</span></span> <span data-ttu-id="894a7-109">Tuttavia, non è necessario che i computer siano online quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="894a7-109">However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="894a7-110">La condivisione file per il pool deve essere creata e disponibile per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="894a7-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="894a7-111">Per pubblicare un pool Front-end Enterprise Edition, il server di back-end basato su SQL Server deve essere unito al dominio in cui si distribuiscono i server, online e configurati con le regole del firewall appropriate per renderlo disponibile per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="894a7-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="894a7-112">Per informazioni dettagliate su come specificare le eccezioni del firewall, vedere [informazioni sui requisiti del firewall per SQL Server con Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="894a7-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="894a7-113">Per altri dettagli sulla configurazione di SQL Server, vedere [configurare SQL Server per Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="894a7-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="894a7-114">Il server Standard Edition include un database collocato che accetterà la configurazione pubblicata.</span><span class="sxs-lookup"><span data-stu-id="894a7-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="894a7-115">Prima di tutto, è necessario eseguire l'attività <STRONG>prepara prima configurazione server Standard Edition</STRONG> nella distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="894a7-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="894a7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="894a7-116">See Also</span></span>


[<span data-ttu-id="894a7-117">Pubblicare la topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="894a7-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="894a7-118">Delegare le autorizzazioni di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="894a7-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="894a7-119">Requisiti software degli strumenti di amministrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="894a7-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="894a7-120">Supporto del sistema operativo per server e strumenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="894a7-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="894a7-121">Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="894a7-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

