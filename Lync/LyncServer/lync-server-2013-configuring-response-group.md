---
title: 'Lync Server 2013: configurazione di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60c224e83bc3d86dca647258540aee2551656d05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="6a4fd-102">Configurazione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a4fd-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6a4fd-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6a4fd-104">Response Group è una funzionalità di VoIP aziendale che consente di instradare e accodare le chiamate in arrivo a gruppi di utenti, denominati *agenti*, ad esempio un helpdesk o un desk del servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="6a4fd-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="6a4fd-105">I componenti necessari per Response Group vengono installati e abilitati automaticamente nel server Standard Edition o Front End Server quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="6a4fd-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="6a4fd-106">Per rendere Response Group disponibile agli utenti, è necessario configurare i gruppi di agenti, quindi le code e quindi i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6a4fd-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="6a4fd-107">Inoltre, un amministratore di Response Group può delegare la configurazione di un flusso di lavoro esistente a un responsabile del gruppo di risposta, che può quindi modificare e riconfigurare il flusso di lavoro e i gruppi di agenti e le code associati.</span><span class="sxs-lookup"><span data-stu-id="6a4fd-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="6a4fd-108">In questa sezione viene illustrata la configurazione del Response Group di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a4fd-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="6a4fd-109">Si presuppone che siano già state lette le sezioni di pianificazione relative al Response Group e che sia stato distribuito un server Enterprise Edition o un server Standard Edition con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="6a4fd-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6a4fd-110">Per informazioni dettagliate sulla creazione di un Response Group mediante Lync Server Management Shell, incluso uno script di esempio, vedere la sezione relativa alla creazione del primo Response Group utilizzando Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>Server Management Shell all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="6a4fd-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a4fd-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="6a4fd-111">In This Section</span></span>

  - [<span data-ttu-id="6a4fd-112">Autorizzazioni e prerequisiti per la configurazione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="6a4fd-113">Processo di distribuzione per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="6a4fd-114">Panoramica degli scenari di creazione del flusso di lavoro in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="6a4fd-115">Creare gruppi di agenti di Response Group Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="6a4fd-116">Creare code di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="6a4fd-117">Optional Definire l'orario di ufficio di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="6a4fd-118">Optional Definire i set di festività di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="6a4fd-119">Creare flussi di lavoro di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="6a4fd-120">Optional Verificare la distribuzione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a4fd-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a4fd-121">See Also</span></span>


[<span data-ttu-id="6a4fd-122">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a4fd-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

