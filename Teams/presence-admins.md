---
title: Presenza utente in Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 2629ef2fd378744647aa7ed158e7128dfbaeba8a
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581207"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="d8bdc-103">Presenza utente in Teams</span><span class="sxs-lookup"><span data-stu-id="d8bdc-103">User presence in Teams</span></span>

<span data-ttu-id="d8bdc-104">La presenza fa parte del profilo di un utente in Microsoft Teams (e in Microsoft 365 o Office 365) che indica la disponibilità e lo stato correnti dell'utente ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="d8bdc-105">Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="d8bdc-106">La presenza di Teams in Outlook è supportata nell'app desktop Outlook 2013 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="d8bdc-107">Stati di presenza in Teams</span><span class="sxs-lookup"><span data-stu-id="d8bdc-107">Presence states in Teams</span></span>

|<span data-ttu-id="d8bdc-108">Utente configurato</span><span class="sxs-lookup"><span data-stu-id="d8bdc-108">User configured</span></span>|<span data-ttu-id="d8bdc-109">App configurata</span><span class="sxs-lookup"><span data-stu-id="d8bdc-109">App configured</span></span>|
|:--- |:---|
| ![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="d8bdc-111">Disponibile</span><span class="sxs-lookup"><span data-stu-id="d8bdc-111">Available</span></span>|![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="d8bdc-113">Disponibile</span><span class="sxs-lookup"><span data-stu-id="d8bdc-113">Available</span></span>|
|| ![Segno di spunta verde trasparente, indica la disponibilità fuori sede](media/Presence_Available_OOF.png) <span data-ttu-id="d8bdc-115">Disponibile, fuori sede</span><span class="sxs-lookup"><span data-stu-id="d8bdc-115">Available, Out of Office</span></span> |
|  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="d8bdc-117">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="d8bdc-117">Busy</span></span> |  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="d8bdc-119">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="d8bdc-119">Busy</span></span>  |
|| ![Cerchio rosso pieno, indica Non disponibile, al telefono](media/Presence_Busy.png) <span data-ttu-id="d8bdc-121">Chiamata in corso</span><span class="sxs-lookup"><span data-stu-id="d8bdc-121">On a call</span></span>|
|| ![Cerchio rosso pieno, indica Non disponibile, in riunione](media/Presence_Busy.png) <span data-ttu-id="d8bdc-123">In riunione</span><span class="sxs-lookup"><span data-stu-id="d8bdc-123">In a meeting</span></span> |
|| ![Cerchio rosso trasparente, indica Non disponibile](media/Presence_Busy_OOF.png) <span data-ttu-id="d8bdc-125">Chiamata in corso, fuori sede</span><span class="sxs-lookup"><span data-stu-id="d8bdc-125">On a call, out of office</span></span>|
|  ![Cerchio rosso con linea bianca, indica Non disturbare](media/Presence_DND.png) <span data-ttu-id="d8bdc-127">Non disturbare</span><span class="sxs-lookup"><span data-stu-id="d8bdc-127">Do not disturb</span></span> ||
|| ![Cerchio rosso con linea bianca, indica Presentazione in corso](media/Presence_DND.png) <span data-ttu-id="d8bdc-129">Presentazione in corso</span><span class="sxs-lookup"><span data-stu-id="d8bdc-129">Presenting</span></span>|
|| ![Cerchio rosso con linea bianca, indica Occupato](media/Presence_DND.png) <span data-ttu-id="d8bdc-131">Occupato</span><span class="sxs-lookup"><span data-stu-id="d8bdc-131">Focusing</span></span>|
| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="d8bdc-133">Assente</span><span class="sxs-lookup"><span data-stu-id="d8bdc-133">Away</span></span>| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="d8bdc-135">Assente</span><span class="sxs-lookup"><span data-stu-id="d8bdc-135">Away</span></span>|
|| <span data-ttu-id="d8bdc-136">![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente, ultimo accesso *orario*</span><span class="sxs-lookup"><span data-stu-id="d8bdc-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icona orologio giallo, indica Assente, torno subito](media/Presence_Away.png) <span data-ttu-id="d8bdc-138">Torno subito</span><span class="sxs-lookup"><span data-stu-id="d8bdc-138">Be right back</span></span>| |
|| ![Icona orologio giallo, indica Assente, non al lavoro](media/Presence_Away.png)  <span data-ttu-id="d8bdc-140">Non al lavoro</span><span class="sxs-lookup"><span data-stu-id="d8bdc-140">Off Work</span></span>|
|| ![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) <span data-ttu-id="d8bdc-142">Offline</span><span class="sxs-lookup"><span data-stu-id="d8bdc-142">Offline</span></span> |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) <span data-ttu-id="d8bdc-144">Stato sconosciuto</span><span class="sxs-lookup"><span data-stu-id="d8bdc-144">Status unknown</span></span>|
||![Cerchio rosso trasparente con linea diagonale, indica Bloccato](media/Presence_Blocked.png) <span data-ttu-id="d8bdc-146">Bloccato</span><span class="sxs-lookup"><span data-stu-id="d8bdc-146">Blocked</span></span> |
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) <span data-ttu-id="d8bdc-148">Fuori sede</span><span class="sxs-lookup"><span data-stu-id="d8bdc-148">Out of Office</span></span>|
|||

<span data-ttu-id="d8bdc-149">Gli stati di presenza configurati dall'app si basano sulle attività utente (Disponibile, Assente), gli stati del calendario di Outlook (In riunione) o gli stati dell'app Teams (Chiamata in corso, Presentazione in corso).</span><span class="sxs-lookup"><span data-stu-id="d8bdc-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="d8bdc-150">Tieni presente che quando sei in modalità Focus in base al calendario, lo stato attivo verrà visualizzato in teans, ma verrà visualizzato come non disturbare in altri prodotti.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-150">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teans but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="d8bdc-151">Lo stato di presenza corrente cambia in Assente quando si blocca il computer o quando si attiva la modalità di sospensione.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-151">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="d8bdc-152">In un dispositivo mobile, lo stato di presenza viene impostato su Assente quando l'app Teams è in background.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-152">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="d8bdc-153">Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-153">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="d8bdc-154">Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-154">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="d8bdc-155">Se un utente è in stato Non disturbare, riceverà comunque i messaggi delle chat, ma le notifiche del banner non verranno mostrate.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-155">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="d8bdc-156">Gli utenti ricevono le chiamate con qualsiasi stato di presenza tranne Non disturbare, in cui le chiamate in arrivo vengono inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-156">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="d8bdc-157">Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-157">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="d8bdc-158">Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-158">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="d8bdc-159">Le persone con accesso prioritario possono contattare l'utente anche se è in stato Non disturbare.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-159">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="d8bdc-160">Confronto tra le impostazioni di amministrazione di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d8bdc-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="d8bdc-161">Le seguenti impostazioni di amministrazione di Skype for Business sono diverse da quelle di Teams:</span><span class="sxs-lookup"><span data-stu-id="d8bdc-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="d8bdc-162">In Teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="d8bdc-163">La configurazione della privacy, grazie alla quale è possibile stabilire chi può visualizzare la presenza, non è disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="d8bdc-164">La condivisione della presenza con tutti, inclusi i servizi federati, è sempre abilitata per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="d8bdc-165">L'elenco contatti, se presente in Skype for Business, è visibile in **Chat > Contatti** o in **Chiamate > Contatti**.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="d8bdc-166">Le funzionalità client Non disturbare e Contatti sempre ammessi sono sempre abilitate per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="d8bdc-167">L'integrazione del calendario, incluse le informazioni fuori sede e degli altri calendario, è sempre abilitata per gli utenti se Teams è integrato con Outlook.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="d8bdc-168">L'indicatore *Ultimo accesso* o *Assente dalle* è sempre abilitato per gli utenti di Teams se l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="d8bdc-169">La personalizzazione di queste impostazioni da parte di un amministratore di Teams non è supportata al momento.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="d8bdc-170">Coesistenza con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d8bdc-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="d8bdc-171">Vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) per i dettagli sul funzionamento della presenza di Teams quando l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d8bdc-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
