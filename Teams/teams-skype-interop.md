---
title: Teams e Skype interoperabilità
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Informazioni sulle funzionalità di interoperabilità tra Teams utenti dell'organizzazione e Skype utenti (consumer).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093956"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="f2c7d-103">Teams e Skype interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f2c7d-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="f2c7d-104">Questo articolo offre una panoramica delle funzionalità di interoperabilità tra Microsoft Teams e Skype (consumer).</span><span class="sxs-lookup"><span data-stu-id="f2c7d-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="f2c7d-105">Scopri come Teams utenti e Skype utenti possono comunicare tramite chat e chiamate e i controlli di amministrazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="f2c7d-106">Teams utenti dell'organizzazione possono chattare e chiamare Skype utenti usando l'indirizzo di posta elettronica e viceversa.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="f2c7d-107">Teams utenti possono cercare e avviare una conversazione di testo uno-a-uno o una chiamata audio/video con un Skype utente.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="f2c7d-108">Skype utenti possono cercare e avviare una conversazione di testo uno-a-uno o una chiamata audio/video con un Teams utente.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="f2c7d-109">Queste funzionalità sono disponibili nei client desktop, Web e per dispositivi mobili (Android e iOS) per Teams e Skype.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="f2c7d-110">Per un'esperienza ottimale, è consigliabile Skype versione 8.58 e successive.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="f2c7d-111">Le Teams e Skype di interoperabilità descritte in questo articolo non sono disponibili nelle distribuzioni GCC, GCC High o DOD o in ambienti cloud privati.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="f2c7d-112">Esperienza di chat e chiamate</span><span class="sxs-lookup"><span data-stu-id="f2c7d-112">Chat and calling experience</span></span>

<span data-ttu-id="f2c7d-113">Ecco una panoramica dell'esperienza di chat e chiamate.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="f2c7d-114">Teams utente avvia una chat o una chiamata con un Skype utente</span><span class="sxs-lookup"><span data-stu-id="f2c7d-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="f2c7d-115">Teams utenti possono cercare un Skype digitando il proprio indirizzo di posta elettronica in una nuova chat o nella barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="f2c7d-116">L Teams utente può quindi selezionare il Skype nei risultati della ricerca per avviare una chat o una chiamata con loro.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="f2c7d-117">Un Skype può scegliere di non comparire nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="f2c7d-118">In questo caso, non verranno visualizzati nei risultati della ricerca in Teams e Teams gli utenti non saranno in grado di trovarli.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="f2c7d-119">Skype utente avvia una chat o una chiamata con un Teams utente</span><span class="sxs-lookup"><span data-stu-id="f2c7d-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="f2c7d-120">Skype gli utenti possono cercare e avviare una chat con un Teams utente usando il proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="f2c7d-121">L Teams utente viene avvisato di avere un nuovo messaggio da un utente di Skype e deve prima accettare il messaggio prima di poter rispondere.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="f2c7d-122">Se l Teams'utente seleziona **Accetta**, la conversazione viene accettata ed entrambi gli utenti possono chattare e chiamarsi.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="f2c7d-123">Se l Teams'utente seleziona Blocca **,** la conversazione viene bloccata e i messaggi e le chiamate successivi da quell'Skype utente vengono bloccati.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="f2c7d-124">Se l Teams utente seleziona Visualizza messaggi **,** il messaggio viene visualizzato in Teams, che consente all'utente di decidere se accettare o bloccare la conversazione.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="f2c7d-125">Se è stato eseguito l'aggiornamento da Skype for Business a Teams e gli utenti sono in modalità Solo Teams, le chat e le chiamate degli utenti di Skype Teams vengono recapitate a Teams.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="f2c7d-126">Se gli utenti sono in modalità Isole, le chat e le chiamate da Skype utenti a Teams utenti vengono recapitate a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="f2c7d-127">Teams utente blocca o sblocca un Skype utente</span><span class="sxs-lookup"><span data-stu-id="f2c7d-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="f2c7d-128">Dopo che Teams un utente accetta o blocca la richiesta di conversazione iniziale da un utente di Skype, può scegliere di bloccare o sbloccare la persona in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="f2c7d-129">Possono farlo nella conversazione o nelle impostazioni di privacy in Teams.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="f2c7d-130">Skype gli utenti non sapranno che sono stati bloccati.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="f2c7d-131">Gli utenti Skype bloccati, insieme ad altre persone e ai numeri di telefono PSTN (Public Switched Telephone Network) bloccati da un utente di Teams, sono elencati nell'elenco dei contatti bloccati dell'utente in Teams.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="f2c7d-132">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="f2c7d-132">Limitations</span></span>

- <span data-ttu-id="f2c7d-133">Le conversazioni sono solo testo.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-133">Conversations are text-only.</span></span> <span data-ttu-id="f2c7d-134">Questo significa che non è disponibile una formattazione completa, @mentions, emoji o altre funzionalità di chat disponibili in un'esperienza Teams [chat nativa.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="f2c7d-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="f2c7d-135">Le conversazioni sono solo uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="f2c7d-136">Le chat di gruppo non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="f2c7d-137">Teams utenti e Skype non possono vedere la presenza degli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="f2c7d-138">La ricerca Skype utenti usando l'ID Skype o il numero di telefono non è supportato.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="f2c7d-139">Skype utenti non possono chiamare Teams utenti che configurano l'inoltro di chiamata al numero di un altro utente, a un numero di delegato o a un numero PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="f2c7d-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="f2c7d-140">È supportata solo la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="f2c7d-141">L'escalation di interoperabilità, le chiamate di gruppo e le riunioni non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="f2c7d-142">La possibilità per un delegato di chiamare un Skype utente per conto di un Teams non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="f2c7d-143">La condivisione dello schermo con la chat non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="f2c7d-144">Impostare se gli Teams utenti possono comunicare con Skype utenti</span><span class="sxs-lookup"><span data-stu-id="f2c7d-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="f2c7d-145">Gli amministratori usano l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare le impostazioni di accesso esterno per controllare se gli utenti Teams dell'organizzazione possono comunicare con Skype utenti.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="f2c7d-146">Per impostazione predefinita, questa funzionalità è attivata per i nuovi tenant.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="f2c7d-147">Tuttavia, esiste un prerequisito che il record SRV DNS seguente deve essere configurato dall'amministratore IT se non è già disponibile per il dominio, ad esempio _sipfederationtls.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="f2c7d-148">**Servizio**: sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f2c7d-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="f2c7d-149">**Protocollo**: TCP</span><span class="sxs-lookup"><span data-stu-id="f2c7d-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="f2c7d-150">**Priorità**: 100</span><span class="sxs-lookup"><span data-stu-id="f2c7d-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="f2c7d-151">**Peso**: 1</span><span class="sxs-lookup"><span data-stu-id="f2c7d-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="f2c7d-152">**Porta**: 5061</span><span class="sxs-lookup"><span data-stu-id="f2c7d-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="f2c7d-153">**Destinazione**: sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f2c7d-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="f2c7d-154">Se è stato eseguito l'aggiornamento da Skype for Business a Teams, le impostazioni delle comunicazioni esterne configurate nell'interfaccia di amministrazione di Skype for Business vengono migrate in Teams.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f2c7d-155">Nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2c7d-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="f2c7d-156">Nell'Microsoft Teams di amministrazione passare a Impostazioni a livello di organizzazione Accesso esterno e quindi attivare Gli utenti possono comunicare con Skype  >   **utenti.**</span><span class="sxs-lookup"><span data-stu-id="f2c7d-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="f2c7d-157">Per istruzioni dettagliate su come configurare questa e altre impostazioni di accesso esterno, vedere Gestire l'accesso esterno [in Teams](./manage-external-access.md#allow-or-block-domains).</span><span class="sxs-lookup"><span data-stu-id="f2c7d-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f2c7d-158">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2c7d-158">Using PowerShell</span></span>

<span data-ttu-id="f2c7d-159">Eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2c7d-159">Do the following:</span></span> 
1. <span data-ttu-id="f2c7d-160">Usare il cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) insieme al parametro per controllare se Teams gli utenti possono comunicare con Skype ```EnablePublicCloudAccess``` utenti.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="f2c7d-161">L'impostazione del parametro ```true``` su consente Teams utenti di comunicare con Skype utenti.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="f2c7d-162">È possibile usare il ```EnablePublicCloudAudioVideoAccess``` parametro per abilitare/disabilitare le chiamate audio/video.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="f2c7d-163">Usare il cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) insieme al parametro impostato su in modo che Teams gli utenti possano comunicare con Skype ```Provider``` ```"WindowsLive"``` utenti.</span><span class="sxs-lookup"><span data-stu-id="f2c7d-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2c7d-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f2c7d-164">Related topics</span></span>

- [<span data-ttu-id="f2c7d-165">Gestire l'accesso esterno in Teams</span><span class="sxs-lookup"><span data-stu-id="f2c7d-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="f2c7d-166">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="f2c7d-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)