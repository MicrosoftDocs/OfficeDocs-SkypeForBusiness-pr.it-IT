---
title: Gestire i criteri delle riunioni per la condivisione di contenuti
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
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri delle riunioni in Teams per la condivisione del contenuto.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598739"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="14438-103">Impostazioni dei criteri di riunione - Condivisione di contenuti</span><span class="sxs-lookup"><span data-stu-id="14438-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="14438-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="14438-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="14438-105">Questo articolo descrive le impostazioni dei criteri di riunione seguenti relative alla condivisione del contenuto:</span><span class="sxs-lookup"><span data-stu-id="14438-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="14438-106">Modalità condivisione schermo</span><span class="sxs-lookup"><span data-stu-id="14438-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="14438-107">Consenti a un partecipante di fornire o richiedere il controllo</span><span class="sxs-lookup"><span data-stu-id="14438-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="14438-108">Consenti a un partecipante esterno di fornire o richiedere il controllo</span><span class="sxs-lookup"><span data-stu-id="14438-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="14438-109">Consenti la condivisione di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="14438-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="14438-110">Consenti la lavagna</span><span class="sxs-lookup"><span data-stu-id="14438-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="14438-111">Consenti note condivise</span><span class="sxs-lookup"><span data-stu-id="14438-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="14438-112">Modalità condivisione schermo</span><span class="sxs-lookup"><span data-stu-id="14438-112">Screen sharing mode</span></span>

<span data-ttu-id="14438-113">Questa impostazione è una combinazione di criteri per organizzatore e per utente.</span><span class="sxs-lookup"><span data-stu-id="14438-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="14438-114">Questa impostazione controlla se la condivisione di desktop e finestre è consentita nella riunione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="14438-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="14438-115">I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi, guest, B2B e federati, ereditano i criteri dell'organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="14438-116">Valore dell'impostazione</span><span class="sxs-lookup"><span data-stu-id="14438-116">Setting value</span></span> |<span data-ttu-id="14438-117">Comportamento</span><span class="sxs-lookup"><span data-stu-id="14438-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="14438-118">**Schermo intero**</span><span class="sxs-lookup"><span data-stu-id="14438-118">**Entire screen**</span></span>    | <span data-ttu-id="14438-119">È consentita la condivisione completa del desktop e delle applicazioni nella riunione</span><span class="sxs-lookup"><span data-stu-id="14438-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="14438-120">**Applicazione singola**</span><span class="sxs-lookup"><span data-stu-id="14438-120">**Single application**</span></span>   | <span data-ttu-id="14438-121">È consentita la condivisione di applicazioni nella riunione</span><span class="sxs-lookup"><span data-stu-id="14438-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="14438-122">**Disattiva**</span><span class="sxs-lookup"><span data-stu-id="14438-122">**Disabled**</span></span>     |<span data-ttu-id="14438-123">Condivisione dello schermo e delle applicazioni disattivata nella riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="14438-124">Osserviamo l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14438-124">Let's look at the following example.</span></span>

|<span data-ttu-id="14438-125">Utente</span><span class="sxs-lookup"><span data-stu-id="14438-125">User</span></span> |<span data-ttu-id="14438-126">Criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="14438-126">Meeting policy</span></span> |<span data-ttu-id="14438-127">Modalità condivisione schermo</span><span class="sxs-lookup"><span data-stu-id="14438-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="14438-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="14438-128">Daniela</span></span>  | <span data-ttu-id="14438-129">Globale</span><span class="sxs-lookup"><span data-stu-id="14438-129">Global</span></span>   | <span data-ttu-id="14438-130">Schermo intero</span><span class="sxs-lookup"><span data-stu-id="14438-130">Entire screen</span></span> |
|<span data-ttu-id="14438-131">Amanda</span><span class="sxs-lookup"><span data-stu-id="14438-131">Amanda</span></span>   | <span data-ttu-id="14438-132">CriterioRiunionePosizione1</span><span class="sxs-lookup"><span data-stu-id="14438-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="14438-133">Disattiva</span><span class="sxs-lookup"><span data-stu-id="14438-133">Disabled</span></span> |

<span data-ttu-id="14438-134">Le riunioni ospitate da Daniela consentono ai partecipanti alla riunione di condividere l'intero schermo o una specifica applicazione.</span><span class="sxs-lookup"><span data-stu-id="14438-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="14438-135">Se Amanda partecipa a una riunione di Daniela, non può condividere il suo schermo o una specifica applicazione, perché l'impostazione del suo criterio non lo consente.</span><span class="sxs-lookup"><span data-stu-id="14438-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="14438-136">Nelle riunioni ospitate da Amanda nessuno può condividere lo schermo o una singola applicazione, indipendentemente dal criterio di condivisione dello schermo assegnati.</span><span class="sxs-lookup"><span data-stu-id="14438-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="14438-137">Di conseguenza, Daniela non può condividere lo schermo o una singola applicazione nelle riunioni di Amanda.</span><span class="sxs-lookup"><span data-stu-id="14438-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="14438-138">Al momento, gli utenti non possono riprodurre video o condividere il proprio schermo in una riunione di Teams se usano Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="14438-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="14438-139">Consenti a un partecipante di fornire o richiedere il controllo</span><span class="sxs-lookup"><span data-stu-id="14438-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="14438-140">Questa impostazione è un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="14438-140">This setting is a per-user policy.</span></span> <span data-ttu-id="14438-141">Questa impostazione controlla se l'utente può assegnare il controllo del desktop o della finestra condivisa ad altri partecipanti della riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="14438-142">Per concedere il controllo, posizionare il puntatore del mouse nella parte superiore dello schermo.</span><span class="sxs-lookup"><span data-stu-id="14438-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="14438-143">Se questa impostazione è attivata per l'utente, nella barra superiore di una sessione di condivisione compare l'opzione **Concedi controllo**.</span><span class="sxs-lookup"><span data-stu-id="14438-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![Screenshot che mostra l'opzione Concedi controllo](media/meeting-policies-give-control.png)

<span data-ttu-id="14438-145">Se l'impostazione è disattivata per l'utente, l'opzione **Concedi controllo** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="14438-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![Screenshot che mostra che l'opzione Concedi controllo non è disponibile](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="14438-147">Osserviamo l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14438-147">Let's look at the following example.</span></span>

|<span data-ttu-id="14438-148">Utente</span><span class="sxs-lookup"><span data-stu-id="14438-148">User</span></span> |<span data-ttu-id="14438-149">Criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="14438-149">Meeting policy</span></span>  |<span data-ttu-id="14438-150">Consenti a un partecipante di fornire o richiedere il controllo</span><span class="sxs-lookup"><span data-stu-id="14438-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="14438-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="14438-151">Daniela</span></span>   | <span data-ttu-id="14438-152">Globale</span><span class="sxs-lookup"><span data-stu-id="14438-152">Global</span></span>   | <span data-ttu-id="14438-153">Attivato</span><span class="sxs-lookup"><span data-stu-id="14438-153">On</span></span>       |
|<span data-ttu-id="14438-154">Pio</span><span class="sxs-lookup"><span data-stu-id="14438-154">Babek</span></span>    | <span data-ttu-id="14438-155">CriterioRiunionePosizione1</span><span class="sxs-lookup"><span data-stu-id="14438-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="14438-156">Disattivato</span><span class="sxs-lookup"><span data-stu-id="14438-156">Off</span></span>   |

<span data-ttu-id="14438-157">Daniela può dare il controllo del desktop o della finestra condivisa ad altri partecipanti a una riunione organizzata da Babek.</span><span class="sxs-lookup"><span data-stu-id="14438-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="14438-158">Tuttavia, Babek non può dare il controllo ad altri partecipanti.</span><span class="sxs-lookup"><span data-stu-id="14438-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="14438-159">Per usare PowerShell per controllare gli utenti autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="14438-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="14438-160">Per concedere e assumere il controllo del contenuto condiviso durante la condivisione, entrambe le parti devono usare il client desktop di Teams.</span><span class="sxs-lookup"><span data-stu-id="14438-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="14438-161">Il controllo non è supportato se una delle parti esegue Teams in un browser.</span><span class="sxs-lookup"><span data-stu-id="14438-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="14438-162">Ciò è dovuto a una limitazione tecnica che si prevede di risolvere.</span><span class="sxs-lookup"><span data-stu-id="14438-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="14438-163">Consenti a un partecipante esterno di fornire o richiedere il controllo</span><span class="sxs-lookup"><span data-stu-id="14438-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="14438-164">Questa impostazione è un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="14438-164">This setting is a per-user policy.</span></span> <span data-ttu-id="14438-165">Se un'organizzazione ha impostato questo criterio per un utente, non controlla cosa possono fare i partecipanti esterni, indipendentemente da ciò che l'organizzatore della riunione ha impostato.</span><span class="sxs-lookup"><span data-stu-id="14438-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="14438-166">Questo parametro controlla se i partecipanti esterni possono ricevere o richiedere il controllo dello schermo del relatore, a seconda delle impostazioni configurate dal relatore nei criteri di riunione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14438-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="14438-167">I partecipanti esterni nelle riunioni di Teams possono essere classificati come segue:</span><span class="sxs-lookup"><span data-stu-id="14438-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="14438-168">Utente anonimo</span><span class="sxs-lookup"><span data-stu-id="14438-168">Anonymous user</span></span>
- <span data-ttu-id="14438-169">Utenti guest</span><span class="sxs-lookup"><span data-stu-id="14438-169">Guest users</span></span>  
- <span data-ttu-id="14438-170">Utente B2B</span><span class="sxs-lookup"><span data-stu-id="14438-170">B2B user</span></span>
- <span data-ttu-id="14438-171">Utente federato</span><span class="sxs-lookup"><span data-stu-id="14438-171">Federated user</span></span>  

<span data-ttu-id="14438-172">La possibilità per gli utenti federati di concedere il controllo a utenti esterni durante la condivisione è controllata dall'impostazione **Consenti a un partecipante esterno di fornire o richiedere il controllo** della loro organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14438-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="14438-173">Per usare PowerShell per controllare i partecipanti esterni autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowExternalParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="14438-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="14438-174">Consenti la condivisione di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="14438-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="14438-175">Questo è un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="14438-175">This is a per-user policy.</span></span> <span data-ttu-id="14438-176">Questa impostazione controlla se l'utente può condividere le presentazioni di PowerPoint in una riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="14438-177">Gli utenti esterni, inclusi gli utenti anonimi, guest e federati, ereditano i criteri dell'organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="14438-178">Osserviamo l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14438-178">Let's look at the following example.</span></span>

|<span data-ttu-id="14438-179">Utente</span><span class="sxs-lookup"><span data-stu-id="14438-179">User</span></span> |<span data-ttu-id="14438-180">Criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="14438-180">Meeting policy</span></span>  |<span data-ttu-id="14438-181">Consenti la condivisione di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="14438-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="14438-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="14438-182">Daniela</span></span>   | <span data-ttu-id="14438-183">Globale</span><span class="sxs-lookup"><span data-stu-id="14438-183">Global</span></span>   | <span data-ttu-id="14438-184">Attivato</span><span class="sxs-lookup"><span data-stu-id="14438-184">On</span></span>       |
|<span data-ttu-id="14438-185">Amanda</span><span class="sxs-lookup"><span data-stu-id="14438-185">Amanda</span></span>   | <span data-ttu-id="14438-186">CriterioRiunionePosizione1</span><span class="sxs-lookup"><span data-stu-id="14438-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="14438-187">Disattivato</span><span class="sxs-lookup"><span data-stu-id="14438-187">Off</span></span>   |

<span data-ttu-id="14438-188">Amanda non può condividere le presentazioni di PowerPoint nelle riunioni, anche se è l'organizzatrice della riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="14438-189">Daniela può condividere le presentazioni di PowerPoint anche se la riunione è organizzata da Amanda.</span><span class="sxs-lookup"><span data-stu-id="14438-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="14438-190">Amanda può visualizzare le presentazioni di PowerPoint condivise da altri nella riunione, anche se non può condividere presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="14438-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="14438-191">Consenti la lavagna</span><span class="sxs-lookup"><span data-stu-id="14438-191">Allow whiteboard</span></span>

<span data-ttu-id="14438-192">Questa impostazione è un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="14438-192">This setting is a per-user policy.</span></span> <span data-ttu-id="14438-193">Questa impostazione controlla se un utente può condividere la lavagna in una riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="14438-194">Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="14438-195">Osserviamo l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14438-195">Let's look at the following example.</span></span>

|<span data-ttu-id="14438-196">Utente</span><span class="sxs-lookup"><span data-stu-id="14438-196">User</span></span> |<span data-ttu-id="14438-197">Criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="14438-197">Meeting policy</span></span>  |<span data-ttu-id="14438-198">Consenti la lavagna</span><span class="sxs-lookup"><span data-stu-id="14438-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="14438-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="14438-199">Daniela</span></span>   | <span data-ttu-id="14438-200">Globale</span><span class="sxs-lookup"><span data-stu-id="14438-200">Global</span></span>   | <span data-ttu-id="14438-201">Attivato</span><span class="sxs-lookup"><span data-stu-id="14438-201">On</span></span>       |
|<span data-ttu-id="14438-202">Amanda</span><span class="sxs-lookup"><span data-stu-id="14438-202">Amanda</span></span>   | <span data-ttu-id="14438-203">CriterioRiunionePosizione1</span><span class="sxs-lookup"><span data-stu-id="14438-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="14438-204">Disattivato</span><span class="sxs-lookup"><span data-stu-id="14438-204">Off</span></span>   |

<span data-ttu-id="14438-205">Amanda non può condividere la lavagna in una riunione, anche se è l'organizzatrice della riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="14438-206">Daniela può condividere la lavagna anche se una riunione è organizzata da Amanda.</span><span class="sxs-lookup"><span data-stu-id="14438-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="14438-207">Consenti note condivise</span><span class="sxs-lookup"><span data-stu-id="14438-207">Allow shared notes</span></span>

<span data-ttu-id="14438-208">Questa impostazione è un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="14438-208">This setting is a per-user policy.</span></span> <span data-ttu-id="14438-209">Questa impostazione controlla se un utente può creare e condividere note in una riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="14438-210">Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="14438-211">La scheda **Note riunione** è attualmente supportata solo nelle riunioni con meno di 20 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="14438-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="14438-212">Osserviamo l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14438-212">Let's look at the following example.</span></span>

|<span data-ttu-id="14438-213">Utente</span><span class="sxs-lookup"><span data-stu-id="14438-213">User</span></span> |<span data-ttu-id="14438-214">Criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="14438-214">Meeting policy</span></span>  |<span data-ttu-id="14438-215">Consenti note condivise</span><span class="sxs-lookup"><span data-stu-id="14438-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="14438-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="14438-216">Daniela</span></span>   | <span data-ttu-id="14438-217">Globale</span><span class="sxs-lookup"><span data-stu-id="14438-217">Global</span></span>   | <span data-ttu-id="14438-218">Attivato</span><span class="sxs-lookup"><span data-stu-id="14438-218">On</span></span>       |
|<span data-ttu-id="14438-219">Amanda</span><span class="sxs-lookup"><span data-stu-id="14438-219">Amanda</span></span>   | <span data-ttu-id="14438-220">CriterioRiunionePosizione1</span><span class="sxs-lookup"><span data-stu-id="14438-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="14438-221">Disattivato</span><span class="sxs-lookup"><span data-stu-id="14438-221">Off</span></span> |

<span data-ttu-id="14438-222">Daniela può creare note nelle riunioni di Amanda, mentre Amanda non può creare note in alcuna riunione.</span><span class="sxs-lookup"><span data-stu-id="14438-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="14438-223">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="14438-223">Related topics</span></span>

- [<span data-ttu-id="14438-224">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="14438-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="14438-225">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="14438-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="14438-226">Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams</span><span class="sxs-lookup"><span data-stu-id="14438-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
