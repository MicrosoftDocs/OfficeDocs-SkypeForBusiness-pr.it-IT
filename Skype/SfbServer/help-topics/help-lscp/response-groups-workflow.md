---
title: Flusso di lavoro Response Groups
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: I gruppi di risposte sono costituiti da gruppi di agenti, code e flussi di lavoro. I flussi di lavoro di Response Group definiscono le azioni che vengono eseguite quando l'applicazione Response Group riceve una telefonata.
ms.openlocfilehash: 5ce7d302063750a2fe316b7986c47bb6e08bb63f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186611"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="e8161-104">Flusso di lavoro Response Groups</span><span class="sxs-lookup"><span data-stu-id="e8161-104">Response Groups Workflow</span></span>

<span data-ttu-id="e8161-105">I gruppi di risposte sono costituiti da gruppi di agenti, code e flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8161-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="e8161-106">I flussi di lavoro di Response Group definiscono le azioni che vengono eseguite quando l'applicazione Response Group riceve una telefonata.</span><span class="sxs-lookup"><span data-stu-id="e8161-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="e8161-107">Nella pagina**flusso di lavoro** **Response** - Groups viene visualizzato un elenco di tutti i flussi di lavoro del gruppo di risposte definiti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8161-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e8161-108">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="e8161-108">Tasks you can perform</span></span>

<span data-ttu-id="e8161-109">È possibile eseguire le attività seguenti nella pagina del**flusso di lavoro** **Response Groups** - :</span><span class="sxs-lookup"><span data-stu-id="e8161-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="e8161-110">Creare o modificare un flusso di lavoro di gruppo di ricerca</span><span class="sxs-lookup"><span data-stu-id="e8161-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="e8161-111">Creare o modificare un flusso di lavoro interattivo</span><span class="sxs-lookup"><span data-stu-id="e8161-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e8161-112">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="e8161-112">UI Reference</span></span>

<span data-ttu-id="e8161-113">L'elenco seguente descrive i comandi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e8161-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="e8161-114">**Creare o modificare un flusso di lavoro** Apre lo strumento di configurazione di Response Group per la creazione o la modifica di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8161-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="e8161-115">**Aggiornare** Aggiorna l'elenco dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8161-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="e8161-116">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e8161-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e8161-117">**Nome** Nome univoco assegnato al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8161-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="e8161-118">**Servizio** Servizio **ApplicationServer** che ospita il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8161-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="e8161-119">**Indirizzo SIP** Indirizzo SIP del gruppo che risponderà alle chiamate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e8161-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="e8161-120">**Telefono** Il numero di telefono che viene chiamato per raggiungere questo gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="e8161-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="e8161-121">**Lingua** Lingua usata per il riconoscimento vocale e la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="e8161-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="e8161-122">**IVR** Indica se il flusso di lavoro è un gruppo di ricerca o un flusso di lavoro interattivo.</span><span class="sxs-lookup"><span data-stu-id="e8161-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="e8161-123">**Abilitato** Indica se il flusso di lavoro viene attivato per ricevere chiamate.</span><span class="sxs-lookup"><span data-stu-id="e8161-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="e8161-124">Per informazioni dettagliate sulle funzionalità e le caratteristiche dei gruppi di risposta, vedere [pianificare l'applicazione Response Group in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e8161-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="e8161-125">Per informazioni dettagliate sull'uso dei flussi di lavoro di Response Group, vedere [gestire i flussi di risposta di Response Group](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="e8161-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


