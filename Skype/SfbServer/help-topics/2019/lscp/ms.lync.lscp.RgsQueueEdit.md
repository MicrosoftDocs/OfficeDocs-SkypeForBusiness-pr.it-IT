---
title: Coda Response Group Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Le code di Response Group contengono le chiamate a un Response Group fino a quando un agente non risponde alla chiamata.
ms.openlocfilehash: ee99ac8cb4f3ea9c2f0e1804914eaf30c909a2b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118805"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="2e5b6-103">Coda dei Response Group: crearne una nuova o modificarne una esistente</span><span class="sxs-lookup"><span data-stu-id="2e5b6-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="2e5b6-104">Le code di Response Group contengono le chiamate a un Response Group fino a quando un agente non risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2e5b6-105">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="2e5b6-105">UI Reference</span></span>

<span data-ttu-id="2e5b6-106">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2e5b6-107">**Nome** Ogni coda deve avere un nome.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="2e5b6-108">Digitare un nome descrittivo per la coda.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="2e5b6-109">**Descrizione** Questo campo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-109">**Description** This field is optional.</span></span> <span data-ttu-id="2e5b6-110">Usarlo per specificare ulteriori informazioni sulla coda.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="2e5b6-111">**Gruppi** Selezionare i gruppi di agenti che si desidera assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="2e5b6-112">Fare clic su **Seleziona** per aggiungere gruppi di agenti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="2e5b6-113">Fare clic su **Rimuovi** per eliminare il gruppo di agenti selezionato dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="2e5b6-114">Le frecce rivolte verso l'alto e verso il basso spostano un gruppo di agenti selezionato verso l'alto e verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="2e5b6-115">L'ordine dei gruppi di agenti influisce sull'ordine in cui Skype for Business Server cerca un agente disponibile.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="2e5b6-116">In altre parole, viene prima cercato un agente disponibile nel primo gruppo nell'elenco, quindi nel secondo gruppo e così via.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="2e5b6-117">**Abilitare il timeout della coda** Selezionare questa casella di controllo per specificare un periodo di tempo massimo per cui un chiamante deve attendere il blocco prima che un agente risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="2e5b6-118">Se si seleziona questa opzione, è anche necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2e5b6-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="2e5b6-119">**Periodo di timeout (secondi)** Selezionare o digitare il numero massimo di secondi che un chiamante può attendere prima che un agente possa rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="2e5b6-120">**Azione chiamata** Selezionare l'azione che si verifica quando si verifica il timeout di una chiamata. Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="2e5b6-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="2e5b6-121">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="2e5b6-121">**Disconnect**</span></span>

  - <span data-ttu-id="2e5b6-122">**Inoltra alla segreteria telefonica** Se si seleziona questa opzione, in **Indirizzo SIP** digitare un indirizzo del sistema di caselle vocali nel formato sip: <username> @ <domainname> (ad esempio, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2e5b6-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="2e5b6-123">**Inoltra al numero di telefono** Se si seleziona questa opzione, in **Indirizzo SIP** digitare il numero di telefono nel formato sip: <number> @ <domainname> (ad esempio, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2e5b6-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="2e5b6-124">**Inoltra a indirizzo SIP** Selezionare questa opzione per inoltrare la chiamata a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="2e5b6-125">In **Indirizzo SIP** digitare l'URI dell'utente nel formato sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="2e5b6-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="2e5b6-126">**Inoltra a un'altra coda** Se si seleziona questa opzione, passare alla coda che deve ricevere le chiamate al timeout delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="2e5b6-127">**Abilitare l'overflow della coda** Selezionare questa casella di controllo per specificare il numero massimo di chiamate che la coda può contenere.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="2e5b6-128">Se si seleziona questa opzione, è anche necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2e5b6-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="2e5b6-129">**Numero massimo di chiamate** Selezionare o digitare il numero massimo di chiamate che la coda può contenere.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="2e5b6-130">**Inoltrare la chiamata** Selezionare la chiamata da eseguire quando viene raggiunta la soglia di overflow della coda.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="2e5b6-131">**Azione chiamata** Selezionare l'azione che viene eseguita quando viene raggiunta la soglia di overflow della coda.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="2e5b6-132">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="2e5b6-132">Your choices are:</span></span>

  - <span data-ttu-id="2e5b6-133">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="2e5b6-133">**Disconnect**</span></span>

  - <span data-ttu-id="2e5b6-134">**Inoltra alla segreteria telefonica** Se si seleziona questa opzione, in **Indirizzo SIP** digitare un indirizzo del sistema di caselle vocali nel formato sip: <username> @ <domainname> (ad esempio, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2e5b6-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="2e5b6-135">**Inoltra al numero di telefono** Se si seleziona questa opzione, in **Indirizzo SIP** digitare il numero di telefono nel formato sip: <number> @ <domainname> (ad esempio, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2e5b6-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="2e5b6-136">**Inoltra a indirizzo SIP** Selezionare questa opzione per inoltrare la chiamata a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="2e5b6-137">In **Indirizzo SIP** digitare l'URI dell'utente nel formato sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="2e5b6-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="2e5b6-138">**Inoltra a un'altra coda** Se si seleziona questa opzione, passare alla coda che deve ricevere le chiamate quando viene raggiunta la soglia di overflow della coda.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="2e5b6-139">Per informazioni dettagliate sulle funzionalità e sulle funzionalità di Response Group, vedere [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="2e5b6-140">Per informazioni dettagliate sull'uso delle code, vedere [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="2e5b6-140">For details about working with queues, see [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) in the Operations documentation.</span></span>