---
title: Criteri versione client Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.
ms.openlocfilehash: 614719a4d0152df4e451793e4845e7a6f72a59cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095610"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="659a6-106">Criteri versione client: crearne di nuovi o modificare quelli esistenti</span><span class="sxs-lookup"><span data-stu-id="659a6-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="659a6-107">È possibile specificare la versione dei client supportati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="659a6-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="659a6-108">Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client.</span><span class="sxs-lookup"><span data-stu-id="659a6-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="659a6-109">Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="659a6-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="659a6-110">Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="659a6-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="659a6-p103">I filtri sono elencati in ordine di precedenza. Se, ad esempio, è presente un filtro che consente ai client che eseguono la versione 1.5 di connettersi, seguito da un filtro che blocca i client che eseguono una versione precedente alla 2.0, il primo filtro ha la precedenza e i client che eseguono la versione 1.5 possono connettersi.</span><span class="sxs-lookup"><span data-stu-id="659a6-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="659a6-113">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="659a6-113">Tasks you can perform</span></span>

<span data-ttu-id="659a6-114">Nella pagina **Crea nuovi criteri versione client** o **Modifica Criteri versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="659a6-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="659a6-115">Aggiungere o modificare il nome o la descrizione dei criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="659a6-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="659a6-116">Aggiungere o modificare le regole per i criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="659a6-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="659a6-117">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="659a6-117">UI Reference</span></span>

<span data-ttu-id="659a6-118">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="659a6-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="659a6-119">**Ambito** Identifica l'ambito (Sito, Pool o Utente) del criterio versione client.</span><span class="sxs-lookup"><span data-stu-id="659a6-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="659a6-120">**Nome** È possibile aggiungere o modificare il nome del criterio versione client.</span><span class="sxs-lookup"><span data-stu-id="659a6-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="659a6-121">**Descrizione** È possibile aggiungere una descrizione per identificare il criterio nell'elenco nella pagina Criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="659a6-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="659a6-122">**Nuovo** È possibile aggiungere una nuova regola della versione client al criterio.</span><span class="sxs-lookup"><span data-stu-id="659a6-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="659a6-123">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una regola della versione client.</span><span class="sxs-lookup"><span data-stu-id="659a6-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="659a6-124">**Rimuovi** Questa opzione consente di rimuovere la regola della versione client selezionata dal criterio.</span><span class="sxs-lookup"><span data-stu-id="659a6-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="659a6-125">**Frecce su e giù** Questa opzione sposta la regola della versione client selezionata verso l'alto o verso il basso in base alla priorità.</span><span class="sxs-lookup"><span data-stu-id="659a6-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="659a6-126">Le regole vengono elaborate nell'ordine in cui sono elencate.</span><span class="sxs-lookup"><span data-stu-id="659a6-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="659a6-127">Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="659a6-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="659a6-128">Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="659a6-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>