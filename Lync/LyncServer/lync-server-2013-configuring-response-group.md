---
title: 'Lync Server 2013: Configurazione di Response Group'
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
ms.openlocfilehash: b94bc731ac00a4ff774930f506282b6aef16cbaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="6497a-102">Configurazione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6497a-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6497a-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6497a-104">Response Group è una funzionalità VoIP aziendale che instrada e accoda le chiamate in arrivo a gruppi di persone, detti *agenti*, ad esempio un help desk o un servizio di assistenza clienti.</span><span class="sxs-lookup"><span data-stu-id="6497a-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="6497a-105">I componenti necessari per il gruppo di risposte sono installati e abilitati automaticamente nel server front-end o Standard Edition quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="6497a-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="6497a-106">Per rendere disponibile un gruppo di risposte agli utenti, è necessario configurare i gruppi di agenti, le code e quindi i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6497a-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="6497a-107">Inoltre, un amministratore del gruppo di risposte può delegare la configurazione di un flusso di lavoro esistente a un responsabile del gruppo di risposte, che può quindi modificare e riconfigurare il flusso di lavoro e i gruppi e le code dell'agente associato.</span><span class="sxs-lookup"><span data-stu-id="6497a-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="6497a-108">Questa sezione illustra la configurazione del gruppo di risposte di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6497a-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="6497a-109">Si presuppone che siano già state lette le sezioni di pianificazione correlate al gruppo di risposte e che sia stato distribuito un server Enterprise Edition o un server Standard Edition con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="6497a-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6497a-110">Per informazioni dettagliate sulla creazione di un gruppo di risposte tramite Lync Server Management Shell, incluso uno script di esempio, vedere "creazione del primo gruppo di risposte tramite Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>Management Shell".</span><span class="sxs-lookup"><span data-stu-id="6497a-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6497a-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6497a-111">In This Section</span></span>

  - [<span data-ttu-id="6497a-112">Autorizzazioni e prerequisiti per la configurazione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="6497a-113">Processo di distribuzione per il gruppo di risposte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="6497a-114">Panoramica degli scenari di creazione del flusso di lavoro in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="6497a-115">Creare gruppi di agenti per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="6497a-116">Creare code di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="6497a-117">Opzionale Definire le ore lavorative per il gruppo di risposte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="6497a-118">Opzionale Definire set di festività di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="6497a-119">Creare flussi di lavoro per Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="6497a-120">Opzionale Verificare la distribuzione di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6497a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6497a-121">See Also</span></span>


[<span data-ttu-id="6497a-122">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6497a-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

