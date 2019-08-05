---
title: Criteri di versione client creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per sfruttare al meglio le funzionalità incluse in Skype for Business Server 2015 e per migliorare l'esperienza complessiva degli utenti, è possibile usare il filtro versione client per limitare le versioni client usate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.
ms.openlocfilehash: f89089f34086a36c3e652bf8527ba4db7d108a11
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195118"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="45e9f-106">Criteri versione client: crearne di nuovi o modificare quelli esistenti</span><span class="sxs-lookup"><span data-stu-id="45e9f-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="45e9f-107">È possibile specificare la versione dei client supportati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="45e9f-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="45e9f-108">Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="45e9f-109">Per sfruttare al meglio le funzionalità incluse in Skype for Business Server 2015 e per migliorare l'esperienza complessiva degli utenti, è possibile usare il filtro versione client per limitare le versioni client usate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="45e9f-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="45e9f-110">Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45e9f-p103">I filtri sono elencati in ordine di priorità. Se ad esempio si dispone di un filtro che consente ai client che eseguono la versione 1.5 di connettersi, seguito da un filtro che blocca i client che eseguono una versione precedente alla 2.0, il primo filtro ha la precedenza e i client che eseguono la versione 1.5 possono connettersi.</span><span class="sxs-lookup"><span data-stu-id="45e9f-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="45e9f-113">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="45e9f-113">Tasks you can perform</span></span>

<span data-ttu-id="45e9f-114">Nella pagina **Crea nuovi criteri versione client** o **Modifica Criteri versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="45e9f-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="45e9f-115">Aggiungere o modificare il nome o la descrizione dei criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="45e9f-116">Aggiungere o modificare le regole per i criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="45e9f-117">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="45e9f-117">UI Reference</span></span>

<span data-ttu-id="45e9f-118">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="45e9f-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="45e9f-119">**Ambito** Identifica l'ambito (sito, pool o utente) dei criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="45e9f-120">**Nome** È possibile aggiungere o modificare il nome dei criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="45e9f-121">**Descrizione** È possibile aggiungere una descrizione per identificare i criteri nell'elenco nella pagina Criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="45e9f-122">**Nuovo** È possibile aggiungere una nuova regola della versione client al criterio.</span><span class="sxs-lookup"><span data-stu-id="45e9f-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="45e9f-123">**Mostra dettagli** Questa opzione apre una finestra di dialogo in cui è possibile modificare le opzioni per una regola di versione client.</span><span class="sxs-lookup"><span data-stu-id="45e9f-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="45e9f-124">**Rimuovi** Questa opzione consente di rimuovere la regola della versione del client selezionata dal criterio.</span><span class="sxs-lookup"><span data-stu-id="45e9f-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="45e9f-125">**Frecce su e giù** Questa opzione Sposta la regola della versione del client selezionata in alto o in basso in priorità.</span><span class="sxs-lookup"><span data-stu-id="45e9f-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="45e9f-126">Le regole vengono elaborate nell'ordine in cui sono elencate.</span><span class="sxs-lookup"><span data-stu-id="45e9f-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="45e9f-p105">Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="45e9f-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

