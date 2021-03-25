---
title: Flusso di lavoro Response Group
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: I Response Group sono costituiti da gruppi di agenti, code e flussi di lavoro. I flussi di lavoro di Response Group definiscono le azioni che vengono eseguite quando l'applicazione Response Group riceve una chiamata telefonica.
ms.openlocfilehash: dc34ec69af86658c6624ada6a9f25ff3aaa61499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118765"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="5e359-104">Flusso di lavoro Response Group</span><span class="sxs-lookup"><span data-stu-id="5e359-104">Response Groups Workflow</span></span>

<span data-ttu-id="5e359-105">I Response Group sono costituiti da gruppi di agenti, code e flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e359-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="5e359-106">I flussi di lavoro di Response Group definiscono le azioni che vengono eseguite quando l'applicazione Response Group riceve una chiamata telefonica.</span><span class="sxs-lookup"><span data-stu-id="5e359-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="5e359-107">Nella **pagina Flusso di lavoro** di Response Group viene visualizzato un elenco di tutti i flussi di lavoro di Response Group definiti per  -   l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e359-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5e359-108">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="5e359-108">Tasks you can perform</span></span>

<span data-ttu-id="5e359-109">È possibile eseguire le attività seguenti dalla pagina **Flusso di lavoro di Response Group:**  -  </span><span class="sxs-lookup"><span data-stu-id="5e359-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="5e359-110">Creare o modificare un flusso di lavoro di un gruppo di risposta</span><span class="sxs-lookup"><span data-stu-id="5e359-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="5e359-111">Creare o modificare un flusso di lavoro interattivo</span><span class="sxs-lookup"><span data-stu-id="5e359-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5e359-112">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="5e359-112">UI Reference</span></span>

<span data-ttu-id="5e359-113">Nell'elenco seguente sono descritti i comandi della pagina.</span><span class="sxs-lookup"><span data-stu-id="5e359-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="5e359-114">**Creare o modificare un flusso di lavoro** Apre lo strumento di configurazione di Response Group per la creazione o la modifica di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e359-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="5e359-115">**Aggiorna** Aggiorna l'elenco dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e359-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="5e359-116">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="5e359-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="5e359-117">**Nome** Nome univoco assegnato al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e359-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="5e359-118">**Servizio** Servizio **ApplicationServer** che ospita il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e359-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="5e359-119">**Indirizzo SIP** Indirizzo SIP del gruppo che risponderà alle chiamate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e359-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="5e359-120">**Telefono** Numero di telefono chiamato per raggiungere questo Response Group.</span><span class="sxs-lookup"><span data-stu-id="5e359-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="5e359-121">**Lingua** Lingua utilizzata per il riconoscimento vocale e la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="5e359-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="5e359-122">**IVR** Indica se il flusso di lavoro è un gruppo di risposta o un flusso di lavoro interattivo.</span><span class="sxs-lookup"><span data-stu-id="5e359-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="5e359-123">**Abilitato** Indica se il flusso di lavoro è attivato per ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="5e359-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="5e359-124">Per informazioni dettagliate sulle funzionalità e sulle funzionalità di Response Group, vedere [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5e359-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="5e359-125">Per informazioni dettagliate sull'utilizzo dei flussi di lavoro di Response Group, vedere [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="5e359-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) in the Operations documentation.</span></span>