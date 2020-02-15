---
title: 'Lync Server 2013: Panoramica degli scenari di creazione del flusso di lavoro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27383db13176150078bf4855dee4df57cb1615af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="c345a-102">Panoramica degli scenari di creazione del flusso di lavoro in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c345a-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c345a-103">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="c345a-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="c345a-104">Quando si creano flussi di lavoro, i possibili scenari sono due:</span><span class="sxs-lookup"><span data-stu-id="c345a-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="c345a-105">**L'amministratore crea e configura il flusso di lavoro** - Il membro del ruolo CsResponseGroupAdministrator (o equivalente) crea e attiva il flusso di lavoro e tutti i relativi elementi, ad esempio gruppi di agenti, code, festività, orario di ufficio, musica di attesa e così via.</span><span class="sxs-lookup"><span data-stu-id="c345a-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="c345a-p101">**L'amministratore crea il flusso di lavoro e il manager configura le opzioni** - Il membro del ruolo CsResponseGroupAdministrator (o equivalente) definisce l'URI SIP primario, assegna uno o più membri al ruolo CsResponseGroupManager, quindi seleziona una coda e attiva il flusso di lavoro. Il membro del ruolo CsResponseGroupManager può quindi effettuare l'accesso e modificare la configurazione del flusso di lavoro creando gruppi di agenti. Assegna inoltre il gruppo alla coda, configurando il numero di telefono, festività, orario di ufficio, musica di attesa e così via.</span><span class="sxs-lookup"><span data-stu-id="c345a-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c345a-p102">Se si vuole creare un flusso di lavoro gestito è necessario crearlo come attivo. Dopo aver salvato un flusso di lavoro gestito e attivo, sarà possibile modificarlo e disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="c345a-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

