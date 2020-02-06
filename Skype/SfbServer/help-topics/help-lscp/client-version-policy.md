---
title: Criteri versione client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: È possibile specificare la versione dei client supportati nell'ambiente. Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client. Per sfruttare al meglio le funzionalità incluse in Skype for Business Server 2015 e per migliorare l'esperienza complessiva degli utenti, è possibile usare il filtro versione client per limitare le versioni client usate nell'ambiente. Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.
ms.openlocfilehash: ac43816dfe3b5afac44bf846f76f92dc80667930
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823069"
---
# <a name="client-version-policy"></a><span data-ttu-id="d87f8-106">Criteri versione client</span><span class="sxs-lookup"><span data-stu-id="d87f8-106">Client Version Policy</span></span>

<span data-ttu-id="d87f8-107">È possibile specificare la versione dei client supportati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d87f8-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="d87f8-108">Quando due client che eseguono versioni diverse interagiscono, le caratteristiche disponibili per uno dei due client possono essere limitate dalle funzionalità dell'altro client.</span><span class="sxs-lookup"><span data-stu-id="d87f8-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="d87f8-109">Per sfruttare al meglio le funzionalità incluse in Skype for Business Server 2015 e per migliorare l'esperienza complessiva degli utenti, è possibile usare il filtro versione client per limitare le versioni client usate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d87f8-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="d87f8-110">Grazie a tale filtro è anche possibile ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="d87f8-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d87f8-111">Attività che è possibile eseguire</span><span class="sxs-lookup"><span data-stu-id="d87f8-111">Tasks you can perform</span></span>

<span data-ttu-id="d87f8-112">Nella pagina **Criteri versione client** è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d87f8-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="d87f8-113">Modificare i criteri di versione client predefiniti ( **globali**).</span><span class="sxs-lookup"><span data-stu-id="d87f8-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="d87f8-114">Creare criteri versione client per un particolare sito o pool.</span><span class="sxs-lookup"><span data-stu-id="d87f8-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="d87f8-115">Creare criteri versione client assegnabili a singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="d87f8-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="d87f8-116">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="d87f8-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d87f8-117">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="d87f8-117">UI Reference</span></span>

<span data-ttu-id="d87f8-118">Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.</span><span class="sxs-lookup"><span data-stu-id="d87f8-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d87f8-119">**Nuovo** È possibile creare uno o più dei criteri di versione client seguenti:</span><span class="sxs-lookup"><span data-stu-id="d87f8-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="d87f8-120">Criteri sito</span><span class="sxs-lookup"><span data-stu-id="d87f8-120">Site policy</span></span>

  - <span data-ttu-id="d87f8-121">Criteri pool</span><span class="sxs-lookup"><span data-stu-id="d87f8-121">Pool policy</span></span>

  - <span data-ttu-id="d87f8-122">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="d87f8-122">User policy</span></span>

- <span data-ttu-id="d87f8-123">**Modifica** È possibile modificare le opzioni di qualsiasi criterio di versione client.</span><span class="sxs-lookup"><span data-stu-id="d87f8-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="d87f8-124">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d87f8-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="d87f8-125">**Mostra dettagli** Questa opzione apre una finestra di dialogo in cui è possibile modificare le opzioni per i criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="d87f8-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="d87f8-126">**Seleziona tutto** Questa opzione consente di selezionare tutti i criteri di versione client nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d87f8-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="d87f8-127">**Eliminare** Questa opzione consente di eliminare tutti i criteri di versione client selezionati.</span><span class="sxs-lookup"><span data-stu-id="d87f8-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="d87f8-128">**Aggiornare** È possibile aggiornare l'elenco dei criteri di versione client per verificare lo stato delle opzioni di tutti i criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="d87f8-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="d87f8-p104">Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri versione client, vedere [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="d87f8-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

