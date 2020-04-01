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
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096971"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="c832d-103">Presenza utente in Teams</span><span class="sxs-lookup"><span data-stu-id="c832d-103">User presence in Teams</span></span>

<span data-ttu-id="c832d-104">La presenza fa parte del profilo di un utente in Microsoft Teams (e in tutto Office 365) che indica la disponibilità e lo stato correnti dell'utente ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="c832d-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="c832d-105">Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano Teams possono vedere (praticamente in tempo reale) se gli altri utenti sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="c832d-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c832d-106">Se si disinstalla il client di Skype for Business dopo aver spostato un utente in modalità **Solo Teams**, l’icona di presenza smetterà di funzionare in Outlook e in altre app di Office.</span><span class="sxs-lookup"><span data-stu-id="c832d-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="c832d-107">L’icona di presenza funziona bene in Teams.</span><span class="sxs-lookup"><span data-stu-id="c832d-107">Presence works fine in Teams.</span></span> <span data-ttu-id="c832d-108">Soluzione alternativa: per visualizzare la presenza in Outlook (e in altre app di Office) è necessario installare Skype for Business, anche se Teams viene eseguito in modalità **Solo Teams**.</span><span class="sxs-lookup"><span data-stu-id="c832d-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="c832d-109">Microsoft è a conoscenza del problema e sta lavorando per risolverlo.</span><span class="sxs-lookup"><span data-stu-id="c832d-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="c832d-110">La presenza di Teams in Outlook è supportata nell'applicazione desktop di Outlook 2013 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c832d-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="c832d-111">Stati di presenza in Teams</span><span class="sxs-lookup"><span data-stu-id="c832d-111">Presence states in Teams</span></span>

|<span data-ttu-id="c832d-112">Utente configurato</span><span class="sxs-lookup"><span data-stu-id="c832d-112">User configured</span></span>|<span data-ttu-id="c832d-113">App configurata</span><span class="sxs-lookup"><span data-stu-id="c832d-113">App configured</span></span>|
|:--- |:---|
| ![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="c832d-115">Disponibile</span><span class="sxs-lookup"><span data-stu-id="c832d-115">Available</span></span>|![Segno di spunta verde, indica la presenza Disponibile](media/Presence_Available.png) <span data-ttu-id="c832d-117">Disponibile</span><span class="sxs-lookup"><span data-stu-id="c832d-117">Available</span></span>|
|| ![Segno di spunta verde trasparente, indica la disponibilità fuori sede](media/Presence_Available_OOF.png) <span data-ttu-id="c832d-119">Disponibile, fuori sede</span><span class="sxs-lookup"><span data-stu-id="c832d-119">Available, Out of Office</span></span> |
|  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="c832d-121">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="c832d-121">Busy</span></span> |  ![Cerchio rosso pieno, indica Non disponibile](media/Presence_Busy.png) <span data-ttu-id="c832d-123">Non disponibile</span><span class="sxs-lookup"><span data-stu-id="c832d-123">Busy</span></span>  |
|| ![Cerchio rosso pieno, indica Non disponibile, al telefono](media/Presence_Busy.png) <span data-ttu-id="c832d-125">Chiamata in corso</span><span class="sxs-lookup"><span data-stu-id="c832d-125">On a call</span></span>|
|| ![Cerchio rosso pieno, indica Non disponibile, in riunione](media/Presence_Busy.png) <span data-ttu-id="c832d-127">In riunione</span><span class="sxs-lookup"><span data-stu-id="c832d-127">In a meeting</span></span> |
|| ![Cerchio rosso trasparente, indica Non disponibile](media/Presence_Busy_OOF.png) <span data-ttu-id="c832d-129">Chiamata in corso, fuori sede</span><span class="sxs-lookup"><span data-stu-id="c832d-129">On a call, out of office</span></span>|
|  ![Cerchio rosso con linea bianca, indica Non disturbare](media/Presence_DND.png) <span data-ttu-id="c832d-131">Non disturbare</span><span class="sxs-lookup"><span data-stu-id="c832d-131">Do not disturb</span></span> ||
|| ![Cerchio rosso con linea bianca, indica Presentazione in corso](media/Presence_DND.png) <span data-ttu-id="c832d-133">Presentazione in corso</span><span class="sxs-lookup"><span data-stu-id="c832d-133">Presenting</span></span>|
|| ![Cerchio rosso con linea bianca, indica Occupato](media/Presence_DND.png) <span data-ttu-id="c832d-135">Occupato</span><span class="sxs-lookup"><span data-stu-id="c832d-135">Focusing</span></span>|
| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="c832d-137">Assente</span><span class="sxs-lookup"><span data-stu-id="c832d-137">Away</span></span>| ![Icona orologio giallo, indica Assente](media/Presence_Away.png) <span data-ttu-id="c832d-139">Assente</span><span class="sxs-lookup"><span data-stu-id="c832d-139">Away</span></span>|
|| <span data-ttu-id="c832d-140">![Icona orologio giallo, indica Assente](media/Presence_Away.png) Assente, ultimo accesso *orario*</span><span class="sxs-lookup"><span data-stu-id="c832d-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icona orologio giallo, indica Assente, torno subito](media/Presence_Away.png) <span data-ttu-id="c832d-142">Torno subito</span><span class="sxs-lookup"><span data-stu-id="c832d-142">Be right back</span></span>| |
|| ![Icona orologio giallo, indica Assente, non al lavoro](media/Presence_Away.png)  <span data-ttu-id="c832d-144">Non al lavoro</span><span class="sxs-lookup"><span data-stu-id="c832d-144">Off Work</span></span>|
|| ![Cerchio grigio con una X, indica Offline](media/Presence_Offline.png) <span data-ttu-id="c832d-146">Offline</span><span class="sxs-lookup"><span data-stu-id="c832d-146">Offline</span></span> |
|| ![Cerchio grigio trasparente, indica Stato sconosciuto](media/Presence_Unknown.png) <span data-ttu-id="c832d-148">Stato sconosciuto</span><span class="sxs-lookup"><span data-stu-id="c832d-148">Status unknown</span></span>|
||![Cerchio rosso trasparente con linea diagonale, indica Bloccato](media/Presence_Blocked.png) <span data-ttu-id="c832d-150">Bloccato</span><span class="sxs-lookup"><span data-stu-id="c832d-150">Blocked</span></span> |
|| ![Cerchio viola con freccia, indica Fuori sede](media/Presence_OOF.png) <span data-ttu-id="c832d-152">Fuori sede</span><span class="sxs-lookup"><span data-stu-id="c832d-152">Out of Office</span></span>|
|||

<span data-ttu-id="c832d-153">Gli Stati di presenza configurati dall'app si basano sulle attività degli utenti (disponibile, assente), sugli Stati del calendario di Outlook (in una riunione) o sugli Stati dell'app Teams (in una chiamata, presentazione).</span><span class="sxs-lookup"><span data-stu-id="c832d-153">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="c832d-154">Quando si blocca il computer o quando si entra in modalità inattiva o sospensione, lo stato di presenza corrente cambia in via.</span><span class="sxs-lookup"><span data-stu-id="c832d-154">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="c832d-155">Per dispositivi mobili, lo stato presenza viene modificato in via ogni volta che l'app teams è in background.</span><span class="sxs-lookup"><span data-stu-id="c832d-155">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="c832d-156">Gli utenti ricevono tutti i messaggi delle chat di Teams, indipendentemente dallo stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="c832d-156">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="c832d-157">Se un utente è offline quando riceve un messaggio, questo apparirà nella chat di Teams non appena l'utente sarà nuovamente online.</span><span class="sxs-lookup"><span data-stu-id="c832d-157">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="c832d-158">Se un utente è in non disturbare, l'utente riceverà ancora messaggi di chat, ma le notifiche banner non vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="c832d-158">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="c832d-159">Gli utenti ricevono chiamate in tutti gli Stati di presenza, ad eccezione di non disturbare, in cui le chiamate in arrivo vanno alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c832d-159">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="c832d-160">Se il destinatario ha bloccato il chiamante, l'utente non riceverà la chiamata e il chiamante visualizzerà la presenza del destinatario come Offline.</span><span class="sxs-lookup"><span data-stu-id="c832d-160">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="c832d-161">Gli utenti possono aggiungere persone al proprio elenco degli accessi prioritari andando in **Impostazioni** > **Privacy** in Teams.</span><span class="sxs-lookup"><span data-stu-id="c832d-161">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="c832d-162">Le persone con accesso prioritario possono contattare l'utente anche quando l'utente è in non disturbare.</span><span class="sxs-lookup"><span data-stu-id="c832d-162">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="c832d-163">Confronto tra le impostazioni di amministrazione di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c832d-163">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="c832d-164">Le seguenti impostazioni di amministrazione di Skype for Business sono diverse da quelle di Teams:</span><span class="sxs-lookup"><span data-stu-id="c832d-164">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="c832d-165">In Teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c832d-165">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="c832d-166">La configurazione della privacy, grazie alla quale è possibile stabilire chi può visualizzare la presenza, non è disponibile in Teams.</span><span class="sxs-lookup"><span data-stu-id="c832d-166">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="c832d-167">La condivisione della presenza con tutti, inclusi i servizi federati, è sempre abilitata per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="c832d-167">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="c832d-168">L'elenco contatti, se presente in Skype for Business, è visibile in **Chat > Contatti** o in **Chiamate > Contatti**.</span><span class="sxs-lookup"><span data-stu-id="c832d-168">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="c832d-169">Le funzionalità client Non disturbare e Contatti sempre ammessi sono sempre abilitate per gli utenti di Teams.</span><span class="sxs-lookup"><span data-stu-id="c832d-169">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="c832d-170">L'integrazione del calendario, incluse le informazioni fuori sede e degli altri calendario, è sempre abilitata per gli utenti se Teams è integrato con Outlook.</span><span class="sxs-lookup"><span data-stu-id="c832d-170">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="c832d-171">L'indicatore *Ultimo accesso* o *Assente dalle* è sempre abilitato per gli utenti di Teams se l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c832d-171">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="c832d-172">La personalizzazione di queste impostazioni da parte di un amministratore di Teams non è supportata al momento.</span><span class="sxs-lookup"><span data-stu-id="c832d-172">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="c832d-173">Coesistenza con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c832d-173">Coexistence with Skype for Business</span></span>

<span data-ttu-id="c832d-174">Vedere [Coesistenza con Skype for Business](coexistence-chat-calls-presence.md) per i dettagli sul funzionamento della presenza di Teams quando l'organizzazione utilizza anche Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c832d-174">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
