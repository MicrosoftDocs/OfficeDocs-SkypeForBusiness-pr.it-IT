---
title: Gestire i criteri delle riunioni per partecipanti e guest
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri delle riunioni in Teams per partecipanti e guest.
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598724"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="e3d6c-103">Impostazioni dei criteri di riunione - Partecipanti e ospiti</span><span class="sxs-lookup"><span data-stu-id="e3d6c-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="e3d6c-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="e3d6c-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="e3d6c-105">Queste impostazioni controllano i partecipanti che devono aspettare nella sala di attesa prima di essere ammessi alla riunione e il livello di partecipazione consentito in una riunione.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="e3d6c-106">Consenti alle persone anonime di avviare una riunione</span><span class="sxs-lookup"><span data-stu-id="e3d6c-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="e3d6c-107">Ammetti automaticamente le persone</span><span class="sxs-lookup"><span data-stu-id="e3d6c-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="e3d6c-108">Consenti agli utenti che chiamano di ignorare la sala di attesa</span><span class="sxs-lookup"><span data-stu-id="e3d6c-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="e3d6c-109">Abilita i sottotitoli in tempo reale</span><span class="sxs-lookup"><span data-stu-id="e3d6c-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="e3d6c-110">Consenti l'uso della chat nelle riunioni</span><span class="sxs-lookup"><span data-stu-id="e3d6c-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="e3d6c-111">Le opzioni per partecipare a una riunione variano in base alle impostazioni di ogni gruppo di Teams e al metodo di connessione.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="e3d6c-112">Se il gruppo ha le funzionalità di audioconferenza e le usa per la connessione, vedere [Audioconferenza](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="e3d6c-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="e3d6c-113">Se il gruppo di Teams non ha le funzionalità di audioconferenza, vedere [Partecipare a una riunione in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span><span class="sxs-lookup"><span data-stu-id="e3d6c-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="e3d6c-114">Consenti alle persone anonime di avviare una riunione</span><span class="sxs-lookup"><span data-stu-id="e3d6c-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="e3d6c-115">Questa impostazione è un criterio per organizzatore che consente riunioni di conferenza telefonica con accesso esterno senza leader.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="e3d6c-116">Questa impostazione controlla se gli utenti con accesso esterno possono partecipare alla riunione in assenza di un utente autenticato dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="e3d6c-117">Per impostazione predefinita, questa impostazione è disattivata, il che significa che gli utenti con accesso remoto attenderanno nella sala d'attesa finché un utente autenticato dell'organizzazione non partecipa alla riunione.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="e3d6c-118">Se questa impostazione è disattivata e un utente con accesso esterno accede alla riunione e viene inserito nella sala di attesa, un utente dell'organizzazione deve partecipare alla riunione con un cliente di Teams per consentire l'accesso all'utente dalla sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="e3d6c-119">Non sono disponibili controlli di sala di attesa per gli utenti che hanno effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="e3d6c-120">Ammetti automaticamente le persone</span><span class="sxs-lookup"><span data-stu-id="e3d6c-120">Automatically admit people</span></span>

<span data-ttu-id="e3d6c-121">Questo è un criterio per organizzatore.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-121">This is a per-organizer policy.</span></span> <span data-ttu-id="e3d6c-122">Questa impostazione controlla se gli utenti si uniscono direttamente a una riunione o restano in sala di attesa finché non vengono ammessi da un utente autenticato.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="e3d6c-123">Questa impostazione non si applica agli utenti con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-123">This setting does not apply to dial-in users.</span></span>

![Screenshot che mostra una riunione con un utente in sala di attesa](media/meeting-policies-lobby.png)

 <span data-ttu-id="e3d6c-125">Gli organizzatori di riunioni possono fare clic **Opzioni riunione** nell'invito alla riunione per modificare questa impostazione per ogni riunione pianificata.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="e3d6c-126">Questa opzione della riunione è denominata "Chi può evitare la sala di attesa?".</span><span class="sxs-lookup"><span data-stu-id="e3d6c-126">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="e3d6c-127">Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-127">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="e3d6c-128">Valore dell'impostazione</span><span class="sxs-lookup"><span data-stu-id="e3d6c-128">Setting value</span></span>  |<span data-ttu-id="e3d6c-129">Comportamento di partecipazione</span><span class="sxs-lookup"><span data-stu-id="e3d6c-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="e3d6c-130">**Tutti**</span><span class="sxs-lookup"><span data-stu-id="e3d6c-130">**Everyone**</span></span>   |<span data-ttu-id="e3d6c-131">Tutti i partecipanti accedono direttamente alla riunione senza passare dalla sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="e3d6c-132">Sono inclusi utenti autenticati, utenti esterni di organizzazioni attendibili (federati), guest e utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="e3d6c-133">**Tutti gli utenti dell'organizzazione e delle organizzazioni federate**</span><span class="sxs-lookup"><span data-stu-id="e3d6c-133">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="e3d6c-134">Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest e gli utenti di organizzazioni attendibili, accedono direttamente alla riunione senza passare dalla sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-134">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="e3d6c-135">Gli utenti anonimi attendono nella sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="e3d6c-136">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="e3d6c-136">**Everyone in your organization**</span></span>    |<span data-ttu-id="e3d6c-137">Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest, accedono direttamente alla riunione senza passare dalla sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-137">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="e3d6c-138">Gli utenti di organizzazioni attendibili e gli utenti anonimi attendono nella sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-138">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="e3d6c-139">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-139">This is the default setting.</span></span>           |
|<span data-ttu-id="e3d6c-140">**Solo organizzatore**</span><span class="sxs-lookup"><span data-stu-id="e3d6c-140">**Organizer only**</span></span>    |<span data-ttu-id="e3d6c-141">Solo gli organizzatori possono accedere direttamente alla riunione senza passare dalla sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-141">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="e3d6c-142">Tutti gli altri utenti, inclusi quelli autenticati all'interno dell'organizzazione, gli utenti guest, gli utenti di organizzazioni attendibili e gli utenti anonimi devono attendere nella sala di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-142">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="e3d6c-143">Consenti agli utenti che chiamano di ignorare la sala di attesa</span><span class="sxs-lookup"><span data-stu-id="e3d6c-143">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="e3d6c-144">Questo è un criterio per organizzatore.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-144">This is a per-organizer policy.</span></span> <span data-ttu-id="e3d6c-145">Questa impostazione consente di controllare se le persone che effettuano l'accesso tramite telefono si uniscono direttamente alla riunione oppure aspettano in sala d'attesa, indipendentemente dall'impostazione **Ammetti automaticamente le persone**.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-145">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="e3d6c-146">Per impostazione predefinita, questa impostazione è disattivata.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-146">By default, this setting is turned off.</span></span> <span data-ttu-id="e3d6c-147">Quando questa impostazione è disattivata, gli utenti con accesso remoto attenderanno nella sala d'attesa finché un utente dell'organizzazione non partecipa alla riunione con un client teams e non li ammette.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-147">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="e3d6c-148">Quando questa impostazione è attivata, gli utenti con accesso esterno potranno accedere automaticamente alla riunione quando un utente dell'organizzazione accede alla riunione.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-148">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="e3d6c-149">Se un utente con accesso esterno partecipa a una riunione prima che un utente dell'organizzazione acceda alla riunione, verrà inserito nella sala di attesa finché un utente dell'organizzazione non accede alla riunione usando un client di Teams e gli consente di accedere.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-149">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="e3d6c-150">Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-150">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="e3d6c-151">Abilita i sottotitoli in tempo reale</span><span class="sxs-lookup"><span data-stu-id="e3d6c-151">Enable live captions</span></span>

<span data-ttu-id="e3d6c-152">Questa impostazione è un criterio per utente e si applica durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-152">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="e3d6c-153">Questa impostazione controlla se, l'opzione **Abilita i sottotitoli in tempo reale** è disponibile nelle riunioni a cui l'utente partecipa, per l'attivazione e la disattivazione dei sottotitoli in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-153">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![Screenshot che mostra l'opzione Abilita i sottotitoli in tempo reale](media/meeting-policies-live-captions.png)

|<span data-ttu-id="e3d6c-155">Valore dell'impostazione</span><span class="sxs-lookup"><span data-stu-id="e3d6c-155">Setting value</span></span> |<span data-ttu-id="e3d6c-156">Comportamento</span><span class="sxs-lookup"><span data-stu-id="e3d6c-156">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="e3d6c-157">**Disabilitato, ma l'organizzatore può eseguire l'override**</span><span class="sxs-lookup"><span data-stu-id="e3d6c-157">**Disabled but the user can override**</span></span>     | <span data-ttu-id="e3d6c-158">I sottotitoli in tempo reale non sono attivati automaticamente per l'utente durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-158">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="e3d6c-159">L'utente vede l'opzione **Abilita i sottotitoli in tempo reale** nel menu di riversamento (**...**).</span><span class="sxs-lookup"><span data-stu-id="e3d6c-159">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="e3d6c-160">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-160">This is the default setting.</span></span> |
|<span data-ttu-id="e3d6c-161">**Disattiva**</span><span class="sxs-lookup"><span data-stu-id="e3d6c-161">**Disabled**</span></span>     | <span data-ttu-id="e3d6c-162">I sottotitoli in tempo reale sono disabilitati per l'utente durante le riunioni.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-162">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="e3d6c-163">L'utente non ha a disposizione l'opzione per attivarli.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-163">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="e3d6c-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="e3d6c-164"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="e3d6c-165">Consenti l'uso della chat nelle riunioni </span><span class="sxs-lookup"><span data-stu-id="e3d6c-165">Allow chat in meetings</span></span>

<span data-ttu-id="e3d6c-166">Questa impostazione è un'impostazione per partecipante.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-166">This setting is a per-participant setting.</span></span> <span data-ttu-id="e3d6c-167">Questa impostazione determina se la chat della riunione è consentita nella riunione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e3d6c-167">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="e3d6c-168"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="e3d6c-168"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="e3d6c-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e3d6c-169">Related topics</span></span>

- [<span data-ttu-id="e3d6c-170">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="e3d6c-170">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="e3d6c-171">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="e3d6c-171">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="e3d6c-172">Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="e3d6c-172">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
