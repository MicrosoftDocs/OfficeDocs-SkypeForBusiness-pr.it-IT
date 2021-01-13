---
title: Criteri delle versioni client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client.
ms.openlocfilehash: c52921df4e68b8273a4e87af0cfe54105e8a10ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812396"
---
# <a name="client-version-policy"></a><span data-ttu-id="ee5ef-104">Criteri delle versioni client</span><span class="sxs-lookup"><span data-stu-id="ee5ef-104">Client Version Policy</span></span>

<span data-ttu-id="ee5ef-105">È possibile specificare la versione dei client supportati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="ee5ef-106">Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="ee5ef-107">Per sfruttare al meglio le funzionalità incluse in Skype for Business Server e per migliorare l'esperienza complessiva degli utenti, è possibile utilizzare il filtro versione client per limitare le versioni client utilizzate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="ee5ef-108">Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ee5ef-109">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="ee5ef-109">Tasks you can perform</span></span>

<span data-ttu-id="ee5ef-110">Nella pagina **criteri versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee5ef-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="ee5ef-111">Modificare il criterio di versione client predefinito ( **globale**).</span><span class="sxs-lookup"><span data-stu-id="ee5ef-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="ee5ef-112">Creare criteri versione client per un particolare sito o pool.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="ee5ef-113">Creare criteri versione client che possono essere assegnati a singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="ee5ef-114">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ee5ef-115">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="ee5ef-115">UI Reference</span></span>

<span data-ttu-id="ee5ef-116">Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="ee5ef-117">**Nuovo** È possibile creare uno o più dei seguenti criteri di versione client:</span><span class="sxs-lookup"><span data-stu-id="ee5ef-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="ee5ef-118">Criterio sito</span><span class="sxs-lookup"><span data-stu-id="ee5ef-118">Site policy</span></span>

  - <span data-ttu-id="ee5ef-119">Criteri pool</span><span class="sxs-lookup"><span data-stu-id="ee5ef-119">Pool policy</span></span>

  - <span data-ttu-id="ee5ef-120">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="ee5ef-120">User policy</span></span>

- <span data-ttu-id="ee5ef-121">**Modifica** È possibile modificare le opzioni di tutti i criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="ee5ef-122">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee5ef-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="ee5ef-123">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per i criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="ee5ef-124">**Seleziona tutto** Questa opzione consente di selezionare tutti i criteri versione client nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="ee5ef-125">**Eliminare** Questa opzione consente di eliminare tutti i criteri versione client selezionati.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="ee5ef-126">**Aggiorna** È possibile aggiornare l'elenco dei criteri di versione client per verificare lo stato delle opzioni di tutti i criteri versione client.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="ee5ef-127">Per informazioni dettagliate sull'interoperabilità tra client e versioni client, vedere [interoperabilità dei client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-127">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ee5ef-128">Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="ee5ef-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

