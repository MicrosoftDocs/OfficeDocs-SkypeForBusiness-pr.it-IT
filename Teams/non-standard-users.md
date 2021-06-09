---
title: Teams comportamento delle app per gli utenti non standard
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sul comportamento delle app Microsoft Teams per gli utenti non standard.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7b79371cdc8ff5109bf67b1c78639106a83a95e
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796649"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="d1f63-103">Microsoft Teams delle app per gli utenti non standard</span><span class="sxs-lookup"><span data-stu-id="d1f63-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="d1f63-104">Questo articolo descrive il comportamento delle app in Teams quando gli utenti guest, esterni (federati) e anonimi sono presenti in un Teams locale.</span><span class="sxs-lookup"><span data-stu-id="d1f63-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="d1f63-105">Un **utente guest** è una persona che non è un dipendente, uno studente o un membro dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1f63-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="d1f63-106">e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1f63-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="d1f63-107">Un **utente esterno (federato)** appartiene a un altro dominio e non ha accesso ai team o alle risorse del team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1f63-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="d1f63-108">Per un confronto più dettagliato tra utenti guest e utenti esterni, vedere Comunicare [con utenti di altre organizzazioni.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="d1f63-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="d1f63-109">Un **utente anonimo** è un concetto in Teams riunioni in cui l'utente ha partecipato alla riunione tramite un collegamento.</span><span class="sxs-lookup"><span data-stu-id="d1f63-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="d1f63-110">L'utente non ha eseguito l'accesso con l'account Microsoft o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1f63-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="d1f63-111">Utenti guest</span><span class="sxs-lookup"><span data-stu-id="d1f63-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="d1f63-112">Installare, aggiornare ed eliminare per gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="d1f63-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="d1f63-113">Gli utenti guest non possono installare, aggiornare o eliminare app in un contesto condiviso, ad esempio una chat, un canale o una riunione, ma possono accedere all'ambito personale usando le estensioni dei messaggi e i collegamenti diretti.</span><span class="sxs-lookup"><span data-stu-id="d1f63-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="d1f63-114">Gli utenti guest non hanno accesso all'app store Teams dall'applicazione desktop Teams, ma possono accedervi con un collegamento diretto.</span><span class="sxs-lookup"><span data-stu-id="d1f63-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="d1f63-115">Comportamento di utilizzo e criteri per gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="d1f63-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="d1f63-116">Gli utenti guest possono usare un'app se l'app è stata installata da un utente nativo.</span><span class="sxs-lookup"><span data-stu-id="d1f63-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="d1f63-117">Bot installati in un canale</span><span class="sxs-lookup"><span data-stu-id="d1f63-117">Bots installed to a channel</span></span>

<span data-ttu-id="d1f63-118">I bot possono inviare messaggi proattivi agli utenti guest, ma gli utenti guest non possono interagire con il bot.</span><span class="sxs-lookup"><span data-stu-id="d1f63-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="d1f63-119">Gli utenti guest non possono inviare messaggi uno a uno al bot, menzionare il bot o interagire con schede adattive che comunicano con il bot.</span><span class="sxs-lookup"><span data-stu-id="d1f63-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="d1f63-120">Bot personali installati con i criteri</span><span class="sxs-lookup"><span data-stu-id="d1f63-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="d1f63-121">Gli utenti guest aderiscono ai criteri di autorizzazione globali e a livello di organizzazione impostati per il tenant host per qualsiasi app.</span><span class="sxs-lookup"><span data-stu-id="d1f63-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="d1f63-122">Se un'app è bloccata per l'intera organizzazione host, gli utenti guest non possono usare l'app.</span><span class="sxs-lookup"><span data-stu-id="d1f63-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="d1f63-123">Tutti i bot inclusi nei criteri di configurazione delle app predefinite globali verranno installati anche per gli guest.</span><span class="sxs-lookup"><span data-stu-id="d1f63-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="d1f63-124">Dopo l'installazione di un bot, i bot possono comunicare in modo proattivo con gli utenti guest e gli utenti guest possono comunicare di nuovo con i bot.</span><span class="sxs-lookup"><span data-stu-id="d1f63-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="d1f63-125">Non è possibile rimuovere un guest dai criteri di configurazione dell'app predefiniti globali.</span><span class="sxs-lookup"><span data-stu-id="d1f63-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="d1f63-126">Per evitare che i guest possano accedere ai bot, è possibile creare altri criteri di configurazione delle app, assegnarli agli utenti interni e installare i bot con i criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d1f63-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="d1f63-127">Utenti esterni (federati)</span><span class="sxs-lookup"><span data-stu-id="d1f63-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="d1f63-128">Installare, aggiornare ed eliminare utenti esterni</span><span class="sxs-lookup"><span data-stu-id="d1f63-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="d1f63-129">Gli utenti esterni non possono installare, aggiornare o eliminare app in qualsiasi contesto, ad esempio una riunione, una chat, un canale o una chat personale.</span><span class="sxs-lookup"><span data-stu-id="d1f63-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="d1f63-130">Non hanno accesso all'app store Teams dell'organizzazione di hosting.</span><span class="sxs-lookup"><span data-stu-id="d1f63-130">They don't have access to the Teams app store of the hosting organization.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="d1f63-131">Comportamento di utilizzo e criteri per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="d1f63-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="d1f63-132">Gli utenti di altre organizzazioni aderiscono ai criteri globali dell'organizzazione ospitata (impostazione predefinita a livello di organizzazione)</span><span class="sxs-lookup"><span data-stu-id="d1f63-132">People from other organizations adhere to the hosting organization's global (org-wide default) policy</span></span>
- <span data-ttu-id="d1f63-133">Gli utenti dell'organizzazione di hosting possono aggiungere app nelle chat delle riunioni con persone di altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d1f63-133">Users in the hosting organization can add apps in meeting chats with people from other organizations.</span></span> <span data-ttu-id="d1f63-134">Le persone di altre organizzazioni non possono aggiungere app nelle chat delle riunioni, ma possono interagire con bot, schede ed estensioni dei messaggi una volta aggiunte alla chat.</span><span class="sxs-lookup"><span data-stu-id="d1f63-134">People from other organizations cannot add apps in meeting chats but can interact with bots, tabs and message extensions once added to the chat.</span></span>
- <span data-ttu-id="d1f63-135">Dopo aver installato un bot in una chat di riunione, può comunicare in modo proattivo con persone di altre organizzazioni nella chat e queste persone possono comunicare con il bot.</span><span class="sxs-lookup"><span data-stu-id="d1f63-135">After a bot is installed in a meeting chat, it can proactively communicate with people from other organizations in that chat and those people can communicate with bot.</span></span>
- <span data-ttu-id="d1f63-136">Vengono applicati i criteri dati dell'organizzazione di hosting, nonché le procedure di condivisione dei dati di qualsiasi app di terze parti condivise dall'organizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d1f63-136">The data policies of the hosting organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="d1f63-137">Utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="d1f63-137">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="d1f63-138">Installare, aggiornare ed eliminare utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="d1f63-138">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="d1f63-139">Gli utenti anonimi non possono installare, aggiornare o eliminare app nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d1f63-139">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="d1f63-140">Comportamento di utilizzo e criteri per gli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="d1f63-140">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="d1f63-141">Gli utenti anonimi non possono usare direttamente le app nelle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d1f63-141">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="d1f63-142">Gli utenti nativi possono continuare a usare le app riunioni se sono presenti utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="d1f63-142">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="d1f63-143">Se un'app invia una scheda adattiva nella chat, gli utenti anonimi possono interagire con la scheda.</span><span class="sxs-lookup"><span data-stu-id="d1f63-143">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="d1f63-144">Per altre informazioni, vedere [Consentire agli utenti anonimi di partecipare alle riunioni.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="d1f63-144">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="d1f63-145">Gli utenti anonimi erediteranno i criteri di autorizzazione predefiniti globali a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="d1f63-145">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="d1f63-146">Possono interagire con le app nelle riunioni Teams se i criteri di autorizzazione a livello di utente hanno abilitato l'app.</span><span class="sxs-lookup"><span data-stu-id="d1f63-146">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="d1f63-147">Gli utenti anonimi possono interagire solo con app già disponibili in una riunione e che non possono acquisire e/o gestire queste app.</span><span class="sxs-lookup"><span data-stu-id="d1f63-147">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
