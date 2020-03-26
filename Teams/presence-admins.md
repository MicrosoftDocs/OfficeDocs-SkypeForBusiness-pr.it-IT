---
title: Presenza utente in Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informazioni per gli amministratori sulla presenza in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863197"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="b8674-103">Presenza utente in Teams</span><span class="sxs-lookup"><span data-stu-id="b8674-103">User presence in Teams</span></span>

<span data-ttu-id="b8674-104">La presenza è inclusa nel profilo degli utenti di Microsoft Teams (e ovunque in Office 365) e indica la disponibilità e lo stato correnti dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b8674-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="b8674-105">Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="b8674-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8674-106">Se si disinstalla il client di Skype for Business dopo aver spostato un utente in modalità **Solo Teams**, l’icona di presenza smetterà di funzionare in Outlook e in altre app di Office.</span><span class="sxs-lookup"><span data-stu-id="b8674-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="b8674-107">L’icona di presenza funziona bene in Teams.</span><span class="sxs-lookup"><span data-stu-id="b8674-107">Presence works fine in Teams.</span></span> <span data-ttu-id="b8674-108">Soluzione alternativa: per visualizzare la presenza in Outlook (e in altre app di Office) è necessario installare Skype for Business, anche se Teams viene eseguito in modalità **Solo Teams**.</span><span class="sxs-lookup"><span data-stu-id="b8674-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="b8674-109">Microsoft è a conoscenza del problema e sta lavorando per risolverlo.</span><span class="sxs-lookup"><span data-stu-id="b8674-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="b8674-110">La presenza di Teams in Outlook è supportata nell'applicazione desktop di Outlook 2013 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b8674-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="b8674-111">Stati di presenza in Teams</span><span class="sxs-lookup"><span data-stu-id="b8674-111">Presence states in Teams</span></span>

<span data-ttu-id="b8674-112">Gli stati di presenza degli utenti disponibili in Teams sono:</span><span class="sxs-lookup"><span data-stu-id="b8674-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="b8674-113">Utente configurato</span><span class="sxs-lookup"><span data-stu-id="b8674-113">User configured</span></span>|<span data-ttu-id="b8674-114">App configurata</span><span class="sxs-lookup"><span data-stu-id="b8674-114">App configured</span></span>|
|:--- |:---|
| ![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="b8674-116">Disponibile</span><span class="sxs-lookup"><span data-stu-id="b8674-116">Available</span></span>|![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="b8674-118">Disponibile</span><span class="sxs-lookup"><span data-stu-id="b8674-118">Available</span></span>|
|| ![Segno di spunta verde trasparente, indica la disponibilità fuori sede](media/Presence_Available_OOF.png) <span data-ttu-id="b8674-120">Disponibile, fuori sede</span><span class="sxs-lookup"><span data-stu-id="b8674-120">Available, Out of Office</span></span> |
|  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="b8674-122">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="b8674-122">Busy</span></span> |  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="b8674-124">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="b8674-124">Busy</span></span>  |
|| ![Cerchio rosso pieno, indica Non disponibile, al telefono](media/Presence_Busy.png) <span data-ttu-id="b8674-126">Chiamata in corso</span><span class="sxs-lookup"><span data-stu-id="b8674-126">On a call</span></span>|
|| ![Cerchio rosso pieno, indica Non disponibile, in riunione](media/Presence_Busy.png) <span data-ttu-id="b8674-128">In riunione</span><span class="sxs-lookup"><span data-stu-id="b8674-128">In a meeting</span></span> |
|| ![Cerchio rosso trasparente, indica Non disponibile](media/Presence_Busy_OOF.png) <span data-ttu-id="b8674-130">Chiamata in corso, fuori sede</span><span class="sxs-lookup"><span data-stu-id="b8674-130">On a call, out of office</span></span>|
|  ![Cerchio rosso con linea bianca, indica Non disturbare](media/Presence_DND.png) <span data-ttu-id="b8674-132">Non disturbare</span><span class="sxs-lookup"><span data-stu-id="b8674-132">Do not disturb</span></span> ||
|| ![Cerchio rosso con linea bianca, indica Presentazione in corso](media/Presence_DND.png) <span data-ttu-id="b8674-134">Presentazione in corso</span><span class="sxs-lookup"><span data-stu-id="b8674-134">Presenting</span></span>|
|| ![Cerchio rosso con linea bianca, indica Occupato](media/Presence_DND.png) <span data-ttu-id="b8674-136">Occupato</span><span class="sxs-lookup"><span data-stu-id="b8674-136">Focusing</span></span>|
| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="b8674-138">Assente</span><span class="sxs-lookup"><span data-stu-id="b8674-138">Away</span></span>| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="b8674-140">Assente</span><span class="sxs-lookup"><span data-stu-id="b8674-140">Away</span></span>|
|| <span data-ttu-id="b8674-141">![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente, ultimo accesso *orario*</span><span class="sxs-lookup"><span data-stu-id="b8674-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icona orologio giallo, indica Assente, torno subito](media/Presence_Away.png) <span data-ttu-id="b8674-143">Torno subito</span><span class="sxs-lookup"><span data-stu-id="b8674-143">Be right back</span></span>| |
|| ![Icona orologio giallo, indica Assente, non al lavoro](media/Presence_Away.png)  <span data-ttu-id="b8674-145">Non al lavoro</span><span class="sxs-lookup"><span data-stu-id="b8674-145">Off Work</span></span>|
|| ![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) <span data-ttu-id="b8674-147">Offline</span><span class="sxs-lookup"><span data-stu-id="b8674-147">Offline</span></span> |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) <span data-ttu-id="b8674-149">Stato sconosciuto</span><span class="sxs-lookup"><span data-stu-id="b8674-149">Status unknown</span></span>|
||![Cerchio rosso trasparente con linea diagonale, indica Bloccato](media/Presence_Blocked.png) <span data-ttu-id="b8674-151">Bloccato</span><span class="sxs-lookup"><span data-stu-id="b8674-151">Blocked</span></span> |
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) <span data-ttu-id="b8674-153">Fuori sede</span><span class="sxs-lookup"><span data-stu-id="b8674-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="b8674-154">Gli utenti possono impostare manualmente lo stato corrente di presenza su alcune opzioni e quest'ultimo verrà mostrato a tutti gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="b8674-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="b8674-155">I dettagli aggiuntivi sulla presenza dell'utente vengono aggiornati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b8674-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="b8674-156">I cambiamenti di stato si basano sulle attività utente (Disponibile, Assente), gli stati del calendario di Outlook (In riunione) o gli stati dell'app Teams (Chiamata in corso, Presentazione in corso), insieme agli stati inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b8674-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="b8674-157">È presente un timeout di inattività di 15 minuti, in seguito al quale lo stato di presenza corrente viene impostato su Assente.</span><span class="sxs-lookup"><span data-stu-id="b8674-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="b8674-158">Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="b8674-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="b8674-159">Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online.</span><span class="sxs-lookup"><span data-stu-id="b8674-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="b8674-160">Se un utente è sullo stato Non disturbare, riceverà comunque i messaggi delle chat ma non verrà mostrata la notifica del banner.</span><span class="sxs-lookup"><span data-stu-id="b8674-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="b8674-161">Gli utenti ricevono le chiamate con qualsiasi stato di presenza, tranne gli stati Non disturbare, per i quali le chiamate in arrivo vengono reindirizzate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="b8674-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="b8674-162">Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.</span><span class="sxs-lookup"><span data-stu-id="b8674-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="b8674-163">Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams.</span><span class="sxs-lookup"><span data-stu-id="b8674-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="b8674-164">Le persone con accesso prioritario possono contattare l'utente anche con lo stato Non disturbare.</span><span class="sxs-lookup"><span data-stu-id="b8674-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="b8674-165">Confronto tra le impostazioni di amministrazione di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b8674-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="b8674-166">Le seguenti impostazioni di amministrazione di Skype for Business sono diverse da quelle di Teams:</span><span class="sxs-lookup"><span data-stu-id="b8674-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="b8674-167">In Teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b8674-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="b8674-168">La configurazione della privacy, grazie alla quale è possibile stabilire chi può visualizzare la presenza, non è disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="b8674-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="b8674-169">La condivisione della presenza con tutti, inclusi i servizi federati, è sempre abilitata per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="b8674-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="b8674-170">L'elenco contatti, se presente in Skype for Business, è visibile in **Chat > Contatti** o in **Chiamate > Contatti**.</span><span class="sxs-lookup"><span data-stu-id="b8674-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="b8674-171">Le funzionalità client Non disturbare e Contatti sempre ammessi sono sempre abilitate per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="b8674-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="b8674-172">L'integrazione del calendario, incluse le informazioni fuori sede e degli altri calendario, è sempre abilitata per gli utenti se Teams è integrato con Outlook.</span><span class="sxs-lookup"><span data-stu-id="b8674-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="b8674-173">L'indicatore *Ultimo accesso* o *Assente dalle* è sempre abilitato per gli utenti di Teams se l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b8674-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="b8674-174">La personalizzazione di queste impostazioni da parte di un amministratore di Teams non è supportata al momento.</span><span class="sxs-lookup"><span data-stu-id="b8674-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="b8674-175">Coesistenza con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b8674-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="b8674-176">Vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) per i dettagli sul funzionamento della presenza di Teams quando l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b8674-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
