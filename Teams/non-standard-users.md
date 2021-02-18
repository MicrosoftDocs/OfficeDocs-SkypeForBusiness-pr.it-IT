---
title: Comportamento delle app Teams per gli utenti non standard
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sul comportamento delle app in Microsoft Teams per gli utenti non standard.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66754565737929ec9d34125ca421c7e3eed9fe65
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278546"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="2b88f-103">Comportamento delle app Microsoft Teams per gli utenti non standard</span><span class="sxs-lookup"><span data-stu-id="2b88f-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="2b88f-104">Questo articolo descrive il comportamento delle app in Teams quando utenti guest, esterni (federati) e anonimi sono presenti in un contesto teams.</span><span class="sxs-lookup"><span data-stu-id="2b88f-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="2b88f-105">Un **utente guest** è una persona che non è un dipendente, uno studente o un membro dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b88f-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="2b88f-106">e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b88f-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="2b88f-107">Un **utente esterno (federato)** appartiene a un altro dominio e non ha accesso ai team o alle risorse del team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b88f-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="2b88f-108">Per un confronto più dettagliato tra utenti guest ed utenti esterni, vedere Comunicare [con utenti di altre organizzazioni .](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)</span><span class="sxs-lookup"><span data-stu-id="2b88f-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations).</span></span>

- <span data-ttu-id="2b88f-109">Un **utente anonimo** è un concetto nelle riunioni di Teams in cui l'utente si è unito alla riunione tramite un collegamento.</span><span class="sxs-lookup"><span data-stu-id="2b88f-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="2b88f-110">L'utente non ha eseguito l'accesso con l'account Microsoft o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b88f-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="2b88f-111">Accesso degli utenti guest</span><span class="sxs-lookup"><span data-stu-id="2b88f-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="2b88f-112">Installare, aggiornare ed eliminare gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="2b88f-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="2b88f-113">I guest non possono installare, aggiornare o eliminare app in un contesto condiviso, ad esempio una chat, un canale o una riunione.</span><span class="sxs-lookup"><span data-stu-id="2b88f-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="2b88f-114">Possono installare, aggiornare o eliminare le app nell'ambito personale usando le estensioni dei messaggi e i collegamenti diretti.</span><span class="sxs-lookup"><span data-stu-id="2b88f-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="2b88f-115">I guest non hanno accesso all'app store di Teams.</span><span class="sxs-lookup"><span data-stu-id="2b88f-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="2b88f-116">Comportamento di utilizzo e criteri per gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="2b88f-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="2b88f-117">Gli utenti guest possono usare un'app se l'app è stata installata da un utente nativo.</span><span class="sxs-lookup"><span data-stu-id="2b88f-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="2b88f-118">I bot possono inviare messaggi proattivamente agli utenti guest, ma i guest non possono interagire con il bot.</span><span class="sxs-lookup"><span data-stu-id="2b88f-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="2b88f-119">Gli ospiti non possono inviare messaggi al bot 1:1, @ menzionare il bot o interagire con le schede adattive che comunicano con il bot.</span><span class="sxs-lookup"><span data-stu-id="2b88f-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="2b88f-120">Gli utenti guest aderiscono ai criteri di autorizzazione globali e a livello di organizzazione impostati per il tenant host per qualsiasi app.</span><span class="sxs-lookup"><span data-stu-id="2b88f-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="2b88f-121">In altre parole, se un'app è bloccata per l'intera organizzazione host, i guest non possono neanche usare l'app.</span><span class="sxs-lookup"><span data-stu-id="2b88f-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="2b88f-122">I criteri di configurazione non si applicano agli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="2b88f-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="2b88f-123">Questo significa che l'aggiunta di un'app dall'interfaccia di amministrazione ai criteri predefiniti non ha alcun effetto sugli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="2b88f-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="2b88f-124">Accesso degli utenti esterni (federati)</span><span class="sxs-lookup"><span data-stu-id="2b88f-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="2b88f-125">Installare, aggiornare ed eliminare utenti esterni</span><span class="sxs-lookup"><span data-stu-id="2b88f-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="2b88f-126">Gli utenti esterni non possono installare, aggiornare o eliminare app in qualsiasi contesto, ad esempio una chat, un canale o una riunione personale.</span><span class="sxs-lookup"><span data-stu-id="2b88f-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="2b88f-127">Non hanno accesso all'app store di Teams.</span><span class="sxs-lookup"><span data-stu-id="2b88f-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="2b88f-128">Comportamento e criteri di utilizzo per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="2b88f-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="2b88f-129">Gli utenti esterni non possono usare alcuna app di Teams e, quando un utente esterno viene aggiunto a un contesto con utenti nativi, tutti gli utenti, sia nativi che esterni, non possono più usare le app.</span><span class="sxs-lookup"><span data-stu-id="2b88f-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="2b88f-130">Gli utenti esterni non sono influenzati dai criteri delle app perché non possono usare le app di Teams.</span><span class="sxs-lookup"><span data-stu-id="2b88f-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="2b88f-131">Utente anonimo nell'accesso alle riunioni</span><span class="sxs-lookup"><span data-stu-id="2b88f-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="2b88f-132">Installare, aggiornare ed eliminare utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="2b88f-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="2b88f-133">Gli utenti anonimi non possono installare, aggiornare o eliminare app nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="2b88f-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="2b88f-134">Comportamento di utilizzo e criteri per gli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="2b88f-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="2b88f-135">Gli utenti anonimi non possono usare direttamente le app nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="2b88f-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="2b88f-136">Gli utenti nativi possono continuare a usare le app per le riunioni se sono presenti utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="2b88f-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="2b88f-137">Se un'app invia una scheda adattiva nella chat, gli utenti anonimi possono interagire con la scheda.</span><span class="sxs-lookup"><span data-stu-id="2b88f-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span>

<span data-ttu-id="2b88f-138">Gli utenti anonimi erediteranno i criteri di autorizzazione predefiniti globali a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="2b88f-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="2b88f-139">Questo controllo consente agli utenti anonimi di interagire con le app nelle riunioni di Teams se il criterio di autorizzazione a livello utente ha abilitato l'app.</span><span class="sxs-lookup"><span data-stu-id="2b88f-139">This control allows anonymous users to interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="2b88f-140">Gli utenti anonimi possono interagire solo con le app già disponibili in una riunione e che non possono acquisire e/o gestire queste app.</span><span class="sxs-lookup"><span data-stu-id="2b88f-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
