---
title: Criteri delle versioni client
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
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.
ms.openlocfilehash: 0af11ac26a73452412c653c04233df7b932f2b49
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118645"
---
# <a name="client-version-policy"></a><span data-ttu-id="4d3e3-106">Criteri delle versioni client</span><span class="sxs-lookup"><span data-stu-id="4d3e3-106">Client Version Policy</span></span>

<span data-ttu-id="4d3e3-107">È possibile specificare la versione dei client supportati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="4d3e3-108">Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="4d3e3-109">Per utilizzare al massimo le funzionalità incluse in Skype for Business Server 2015 e migliorare l'esperienza utente complessiva, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="4d3e3-110">Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4d3e3-111">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="4d3e3-111">Tasks you can perform</span></span>

<span data-ttu-id="4d3e3-112">Nella pagina Criteri versione **client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d3e3-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="4d3e3-113">Modificare il criterio predefinito ( **Globale**) della versione client.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="4d3e3-114">Creare criteri versione client per un sito o un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="4d3e3-115">Creare criteri versione client che possono essere assegnati a singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="4d3e3-116">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4d3e3-117">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="4d3e3-117">UI Reference</span></span>

<span data-ttu-id="4d3e3-118">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="4d3e3-119">**Nuovo** È possibile creare uno o più dei criteri di versione client seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d3e3-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="4d3e3-120">Criterio sito</span><span class="sxs-lookup"><span data-stu-id="4d3e3-120">Site policy</span></span>

  - <span data-ttu-id="4d3e3-121">Criteri pool</span><span class="sxs-lookup"><span data-stu-id="4d3e3-121">Pool policy</span></span>

  - <span data-ttu-id="4d3e3-122">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="4d3e3-122">User policy</span></span>

- <span data-ttu-id="4d3e3-123">**Modifica** È possibile modificare le opzioni di uno qualsiasi dei criteri delle versioni client.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="4d3e3-124">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d3e3-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="4d3e3-125">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per un criterio versione client.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="4d3e3-126">**Seleziona tutto** Questa opzione consente di selezionare tutti i criteri delle versioni client nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="4d3e3-127">**Elimina** Questa opzione consente di eliminare tutti i criteri di versione client selezionati.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="4d3e3-128">**Aggiorna** È possibile aggiornare l'elenco dei criteri versione client per verificare lo stato delle opzioni di tutti i criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="4d3e3-129">Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="4d3e3-130">Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="4d3e3-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>