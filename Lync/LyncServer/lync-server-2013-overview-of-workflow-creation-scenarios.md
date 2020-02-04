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
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="1ea4d-102">Panoramica degli scenari di creazione del flusso di lavoro in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ea4d-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea4d-103">_**Argomento Ultima modifica:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="1ea4d-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="1ea4d-104">Quando si creano flussi di lavoro, esistono due scenari possibili:</span><span class="sxs-lookup"><span data-stu-id="1ea4d-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="1ea4d-105">**L'amministratore crea e configura il flusso di lavoro** , ovvero il membro del ruolo CsResponseGroupAdministrator (o equivalente) crea e attiva il flusso di lavoro e tutti gli elementi del flusso di lavoro, ad esempio i gruppi di agenti, le code, le festività e le ore lavorative, la musica in attesa e così via.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="1ea4d-106">**L'amministratore crea il flusso di lavoro e il responsabile configura le opzioni** , ovvero il membro del ruolo CsResponseGroupAdministrator (o equivalente) definisce l'URI SIP principale, il nome visualizzato, assegna un membro o i membri del ruolo CsResponseGroupManager e seleziona una coda e attiva il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-106">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow.</span></span> <span data-ttu-id="1ea4d-107">CsResponseGroupManager può quindi eseguire l'accesso e modificare la configurazione del flusso di lavoro creando gruppi di agenti e assegnando anche il gruppo alla coda, configurando il numero di telefono, le festività e le ore lavorative, la musica in attesa e così via.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-107">The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ea4d-108">Quando si vuole creare un flusso di lavoro gestito, è necessario creare il flusso di lavoro come attivo.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-108">When you want to create a managed workflow, you need to create the workflow as active.</span></span> <span data-ttu-id="1ea4d-109">Dopo aver salvato un flusso di lavoro attivo e gestito, è possibile modificare e disattivare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-109">After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

