---
title: Presenza utente in Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informazioni sugli stati di presenza in teams e sulle impostazioni amministrative per la funzionalità presenza.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369211"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="41c6a-103">Presenza utente in Teams</span><span class="sxs-lookup"><span data-stu-id="41c6a-103">User presence in Teams</span></span>

<span data-ttu-id="41c6a-104">La presenza fa parte del profilo di un utente in Microsoft Teams (e in Microsoft 365 o Office 365) che indica la disponibilità e lo stato correnti dell'utente ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="41c6a-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="41c6a-105">Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="41c6a-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="41c6a-106">La presenza di Teams in Outlook è supportata nell'app desktop Outlook 2013 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="41c6a-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="41c6a-107">Per informazioni dettagliate sui profili utente di Team su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="41c6a-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="41c6a-108">Stati di presenza in Teams</span><span class="sxs-lookup"><span data-stu-id="41c6a-108">Presence states in Teams</span></span>

|<span data-ttu-id="41c6a-109">Utente configurato</span><span class="sxs-lookup"><span data-stu-id="41c6a-109">User configured</span></span>|<span data-ttu-id="41c6a-110">App configurata</span><span class="sxs-lookup"><span data-stu-id="41c6a-110">App configured</span></span>|
|:--- |:---|
| ![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="41c6a-112">Disponibile</span><span class="sxs-lookup"><span data-stu-id="41c6a-112">Available</span></span>|![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="41c6a-114">Disponibile</span><span class="sxs-lookup"><span data-stu-id="41c6a-114">Available</span></span>|
|| ![Segno di spunta verde trasparente, indica la disponibilità fuori sede](media/Presence_Available_OOF.png) <span data-ttu-id="41c6a-116">Disponibile, fuori sede</span><span class="sxs-lookup"><span data-stu-id="41c6a-116">Available, Out of Office</span></span> |
|  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="41c6a-118">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="41c6a-118">Busy</span></span> |  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="41c6a-120">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="41c6a-120">Busy</span></span>  |
|| ![Cerchio rosso pieno, indica Non disponibile, al telefono](media/Presence_Busy.png) <span data-ttu-id="41c6a-122">Chiamata in corso</span><span class="sxs-lookup"><span data-stu-id="41c6a-122">On a call</span></span>|
|| ![Cerchio rosso pieno, indica Non disponibile, in riunione](media/Presence_Busy.png) <span data-ttu-id="41c6a-124">In riunione</span><span class="sxs-lookup"><span data-stu-id="41c6a-124">In a meeting</span></span> |
|| ![Cerchio rosso trasparente, indica Non disponibile](media/Presence_Busy_OOF.png) <span data-ttu-id="41c6a-126">Chiamata in corso, fuori sede</span><span class="sxs-lookup"><span data-stu-id="41c6a-126">On a call, out of office</span></span>|
|  ![Cerchio rosso con linea bianca, indica Non disturbare](media/Presence_DND.png) <span data-ttu-id="41c6a-128">Non disturbare</span><span class="sxs-lookup"><span data-stu-id="41c6a-128">Do not disturb</span></span> ||
|| ![Cerchio rosso con linea bianca, indica Presentazione in corso](media/Presence_DND.png) <span data-ttu-id="41c6a-130">Presentazione in corso</span><span class="sxs-lookup"><span data-stu-id="41c6a-130">Presenting</span></span>|
|| ![Cerchio rosso con linea bianca, indica Occupato](media/Presence_DND.png) <span data-ttu-id="41c6a-132">Occupato</span><span class="sxs-lookup"><span data-stu-id="41c6a-132">Focusing</span></span>|
| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="41c6a-134">Assente</span><span class="sxs-lookup"><span data-stu-id="41c6a-134">Away</span></span>| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="41c6a-136">Assente</span><span class="sxs-lookup"><span data-stu-id="41c6a-136">Away</span></span>|
|| <span data-ttu-id="41c6a-137">![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente, ultimo accesso *orario*</span><span class="sxs-lookup"><span data-stu-id="41c6a-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icona orologio giallo, indica Assente, torno subito](media/Presence_Away.png) <span data-ttu-id="41c6a-139">Torno subito</span><span class="sxs-lookup"><span data-stu-id="41c6a-139">Be right back</span></span>| |
|![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) <span data-ttu-id="41c6a-141">Visualizzazione offline</span><span class="sxs-lookup"><span data-stu-id="41c6a-141">Appear offline</span></span> | ![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) <span data-ttu-id="41c6a-143">Offline</span><span class="sxs-lookup"><span data-stu-id="41c6a-143">Offline</span></span>| |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) <span data-ttu-id="41c6a-145">Stato sconosciuto</span><span class="sxs-lookup"><span data-stu-id="41c6a-145">Status unknown</span></span>|
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) <span data-ttu-id="41c6a-147">Fuori sede</span><span class="sxs-lookup"><span data-stu-id="41c6a-147">Out of Office</span></span>|
|||

<span data-ttu-id="41c6a-148">Gli stati di presenza configurati dall'app si basano sulle attività utente (Disponibile, Assente), gli stati del calendario di Outlook (In riunione) o gli stati dell'app Teams (Chiamata in corso, Presentazione in corso).</span><span class="sxs-lookup"><span data-stu-id="41c6a-148">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="41c6a-149">Tieni presente che quando sei in modalità Focus in base al calendario, lo stato attivo verrà visualizzato in teams, ma verrà visualizzato come non disturbare in altri prodotti.</span><span class="sxs-lookup"><span data-stu-id="41c6a-149">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams, but it will display as Do not disturb in other products.</span></span>

<span data-ttu-id="41c6a-150">Quando si blocca il computer o quando il computer entra in modalità Idle o Sleep, lo stato di presenza corrente cambia in via.</span><span class="sxs-lookup"><span data-stu-id="41c6a-150">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="41c6a-151">In un dispositivo mobile, lo stato presenza viene modificato in via ogni volta che l'app teams è in background.</span><span class="sxs-lookup"><span data-stu-id="41c6a-151">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="41c6a-152">Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="41c6a-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="41c6a-153">Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online.</span><span class="sxs-lookup"><span data-stu-id="41c6a-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="41c6a-154">Se uno stato utente è impostato su non disturbare, l'utente riceverà comunque i messaggi di chat, ma le notifiche banner non vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="41c6a-154">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="41c6a-155">Gli utenti ricevono le chiamate con qualsiasi stato di presenza tranne Non disturbare, in cui le chiamate in arrivo vengono inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="41c6a-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="41c6a-156">Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.</span><span class="sxs-lookup"><span data-stu-id="41c6a-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="41c6a-157">Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams.</span><span class="sxs-lookup"><span data-stu-id="41c6a-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="41c6a-158">Le persone con accesso prioritario possono contattare l'utente anche quando lo stato dell'utente è impostato su non disturbare.</span><span class="sxs-lookup"><span data-stu-id="41c6a-158">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="41c6a-159">Scadenza degli stati configurati dall'utente</span><span class="sxs-lookup"><span data-stu-id="41c6a-159">User configured states expiration</span></span>
<span data-ttu-id="41c6a-160">Quando un utente seleziona uno stato di presenza specifico, prevale su qualsiasi aggiornamento delle attività dell'app.</span><span class="sxs-lookup"><span data-stu-id="41c6a-160">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="41c6a-161">Ad esempio, se un utente si imposta come non disturbare, la sua presenza rimarrà come non disturbare, anche se partecipa a una riunione o risponde a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="41c6a-161">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="41c6a-162">Gli stati configurati dall'utente hanno impostazioni di scadenza predefinite in teams per evitare che gli utenti visualizzino uno stato che potrebbe non essere pertinente dopo un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="41c6a-162">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="41c6a-163">Stato configurato dall'utente</span><span class="sxs-lookup"><span data-stu-id="41c6a-163">User configured state</span></span>|<span data-ttu-id="41c6a-164">Scadenza predefinita</span><span class="sxs-lookup"><span data-stu-id="41c6a-164">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="41c6a-165">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="41c6a-165">Busy</span></span>|<span data-ttu-id="41c6a-166">1 giorno</span><span class="sxs-lookup"><span data-stu-id="41c6a-166">1 day</span></span>|
| <span data-ttu-id="41c6a-167">Non disturbare</span><span class="sxs-lookup"><span data-stu-id="41c6a-167">Do not disturb</span></span>|<span data-ttu-id="41c6a-168">1 giorno</span><span class="sxs-lookup"><span data-stu-id="41c6a-168">1 day</span></span>|
| <span data-ttu-id="41c6a-169">Altri</span><span class="sxs-lookup"><span data-stu-id="41c6a-169">Others</span></span>|<span data-ttu-id="41c6a-170">7 giorni</span><span class="sxs-lookup"><span data-stu-id="41c6a-170">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="41c6a-171">Confronto tra le impostazioni di amministrazione di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="41c6a-171">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="41c6a-172">Le seguenti impostazioni di amministrazione di Skype for Business sono diverse da quelle di Teams:</span><span class="sxs-lookup"><span data-stu-id="41c6a-172">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="41c6a-173">In Teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41c6a-173">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="41c6a-174">La configurazione della privacy, grazie alla quale è possibile stabilire chi può visualizzare la presenza, non è disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="41c6a-174">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="41c6a-175">La condivisione della presenza con tutti, inclusi i servizi federati, è sempre abilitata per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="41c6a-175">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="41c6a-176">L'elenco contatti, se presente in Skype for Business, è visibile in **Chat > Contatti** o in **Chiamate > Contatti**.</span><span class="sxs-lookup"><span data-stu-id="41c6a-176">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="41c6a-177">Le funzionalità client Non disturbare e Contatti sempre ammessi sono sempre abilitate per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="41c6a-177">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="41c6a-178">L'integrazione del calendario, incluse le informazioni fuori sede e degli altri calendario, è sempre abilitata per gli utenti se Teams è integrato con Outlook.</span><span class="sxs-lookup"><span data-stu-id="41c6a-178">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="41c6a-179">L'indicatore *Ultimo accesso* o *Assente dalle* è sempre abilitato per gli utenti di Teams se l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="41c6a-179">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="41c6a-180">La personalizzazione di queste impostazioni da parte di un amministratore di Teams non è supportata al momento.</span><span class="sxs-lookup"><span data-stu-id="41c6a-180">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="41c6a-181">Coesistenza con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="41c6a-181">Coexistence with Skype for Business</span></span>

<span data-ttu-id="41c6a-182">Vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) per i dettagli sul funzionamento della presenza di Teams quando l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="41c6a-182">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
