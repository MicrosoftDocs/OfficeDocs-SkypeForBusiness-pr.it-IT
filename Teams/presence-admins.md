---
title: Presenza dell'utente in teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Gli amministratori di informazioni devono comprendere la presenza in teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11902a5d6ef768afa6d7bb1bba2f33b64757fef1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184381"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="de81a-103">Presenza dell'utente in teams</span><span class="sxs-lookup"><span data-stu-id="de81a-103">User presence in Teams</span></span>

<span data-ttu-id="de81a-104">La presenza fa parte del profilo di un utente in Microsoft Teams (e in Office 365) e indica la disponibilità e lo stato correnti dell'utente ad altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de81a-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="de81a-105">Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano i team possono vedere, in tempi quasi reali, se gli altri sono o meno disponibili online.</span><span class="sxs-lookup"><span data-stu-id="de81a-105">By default, anyone in your organization using Teams can see – in nearly real time – whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="de81a-106">Stati presenza in teams</span><span class="sxs-lookup"><span data-stu-id="de81a-106">Presence states in Teams</span></span>

<span data-ttu-id="de81a-107">Gli Stati di presenza degli utenti disponibili in teams sono:</span><span class="sxs-lookup"><span data-stu-id="de81a-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="de81a-108">Configurato dall'utente</span><span class="sxs-lookup"><span data-stu-id="de81a-108">User configured</span></span>|<span data-ttu-id="de81a-109">App configurata</span><span class="sxs-lookup"><span data-stu-id="de81a-109">App configured</span></span>|
|:--- |:---|
| ![Contrassegno di Chek verde a tinta unita, che indica la presenza disponibile](media/Presence_Available.png) <span data-ttu-id="de81a-111">Disponibili</span><span class="sxs-lookup"><span data-stu-id="de81a-111">Available</span></span>|![Contrassegno di Chek verde a tinta unita, che indica la presenza disponibile](media/Presence_Available.png) <span data-ttu-id="de81a-113">Disponibili</span><span class="sxs-lookup"><span data-stu-id="de81a-113">Available</span></span>|
|| ![Aprire il contrassegno di Chek verde, indicando disponibile OOF](media/Presence_Available_OOF.png) <span data-ttu-id="de81a-115">Disponibile, fuori sede</span><span class="sxs-lookup"><span data-stu-id="de81a-115">Available, Out of Office</span></span> |
|  ![Cerchio rosso a tinta unita che indica occupato](media/Presence_Busy.png) <span data-ttu-id="de81a-117">Disponibilità</span><span class="sxs-lookup"><span data-stu-id="de81a-117">Busy</span></span> |  ![Cerchio rosso a tinta unita che indica occupato](media/Presence_Busy.png) <span data-ttu-id="de81a-119">Disponibilità</span><span class="sxs-lookup"><span data-stu-id="de81a-119">Busy</span></span>  |
|| ![Cerchio rosso a tinta unita, che indica occupato in una chiamata](media/Presence_Busy.png) <span data-ttu-id="de81a-121">In una chiamata</span><span class="sxs-lookup"><span data-stu-id="de81a-121">In a call</span></span>|
|| ![Cerchio rosso a tinta unita, che indica occupato in una riunione](media/Presence_Busy.png) <span data-ttu-id="de81a-123">In una riunione</span><span class="sxs-lookup"><span data-stu-id="de81a-123">In a meeting</span></span> |
|| ![Aprire il cerchio rosso, indicando OOF occupato](media/Presence_Busy_OOF.png) <span data-ttu-id="de81a-125">In una chiamata fuori sede</span><span class="sxs-lookup"><span data-stu-id="de81a-125">In a call, out of office</span></span>|
|  ![Cerchio rosso con linea bianca che indica che non disturbare](media/Presence_DND.png) <span data-ttu-id="de81a-127">Non disturbare</span><span class="sxs-lookup"><span data-stu-id="de81a-127">Do not disturb</span></span> ||
|| ![Cerchio rosso con linea bianca che indica la presentazione](media/Presence_DND.png) <span data-ttu-id="de81a-129">Presentazione</span><span class="sxs-lookup"><span data-stu-id="de81a-129">Presenting</span></span>|
| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) <span data-ttu-id="de81a-131">Via</span><span class="sxs-lookup"><span data-stu-id="de81a-131">Away</span></span>| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) <span data-ttu-id="de81a-133">Via</span><span class="sxs-lookup"><span data-stu-id="de81a-133">Away</span></span>|
|| <span data-ttu-id="de81a-134">![Icona dell'orologio giallo, che](media/Presence_Away.png) indica l'ora dell'ultima *volta* che è stata vista</span><span class="sxs-lookup"><span data-stu-id="de81a-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icona dell'orologio giallo, che indica di distanza, torno subito](media/Presence_Away.png) <span data-ttu-id="de81a-136">Torno subito</span><span class="sxs-lookup"><span data-stu-id="de81a-136">Be right back</span></span>| |
|| ![Icona dell'orologio giallo, con indicazione di distanza, fuori lavoro](media/Presence_Away.png)  <span data-ttu-id="de81a-138">Fuori ufficio</span><span class="sxs-lookup"><span data-stu-id="de81a-138">Off Work</span></span>|
|| ![Cerchio grigio con x, che indica offline](media/Presence_Offline.png) <span data-ttu-id="de81a-140">Offline</span><span class="sxs-lookup"><span data-stu-id="de81a-140">Offline</span></span> |
|| ![Aprire il cerchio grigio, indicando lo stato sconosciuto](media/Presence_Unknown.png) <span data-ttu-id="de81a-142">Stato sconosciuto</span><span class="sxs-lookup"><span data-stu-id="de81a-142">Status unknown</span></span>|
||![Aprire il cerchio rosso con la linea diagonale, indicando bloccato](media/Presence_Blocked.png) <span data-ttu-id="de81a-144">Bloccati</span><span class="sxs-lookup"><span data-stu-id="de81a-144">Blocked</span></span> |
|| ![Cerchio viola con freccia che indica fuori sede](media/Presence_OOF.png) <span data-ttu-id="de81a-146">Fuori sede</span><span class="sxs-lookup"><span data-stu-id="de81a-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="de81a-147">Gli utenti possono impostare manualmente lo stato presenza corrente su alcune opzioni e il relativo stato viene riflesso a tutti gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="de81a-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="de81a-148">Ulteriori dettagli sulla presenza degli utenti vengono aggiornati automaticamente in base alle attività degli utenti (ad esempio, disponibile o distante), agli Stati del calendario di Outlook (ad esempio in una riunione) o agli Stati dell'app Teams (in una chiamata, presentazione), agli Stati rientrati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="de81a-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="de81a-149">Esiste un timeout di 15 minuti di inattività, dopo il quale lo stato di presenza corrente degli utenti verrà reimpostato su away.</span><span class="sxs-lookup"><span data-stu-id="de81a-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="de81a-150">Gli utenti possono specificare chi può sfondare (contattarli eseguendo l'override di un'impostazione non disturbare).</span><span class="sxs-lookup"><span data-stu-id="de81a-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="de81a-151">Queste impostazioni sono disponibili in-app.</span><span class="sxs-lookup"><span data-stu-id="de81a-151">These settings are available in-app.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="de81a-152">Impostazioni di amministrazione in teams rispetto a Skype for business</span><span class="sxs-lookup"><span data-stu-id="de81a-152">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="de81a-153">Le seguenti impostazioni di amministratore Skype for business sono diverse in teams:</span><span class="sxs-lookup"><span data-stu-id="de81a-153">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="de81a-154">In teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de81a-154">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="de81a-155">Privacy (decidere chi può vedere la presenza) la configurazione non è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="de81a-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="de81a-156">La condivisione della presenza con tutti (inclusi i servizi federati) è sempre abilitata per gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="de81a-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="de81a-157">Il relativo elenco di contatti (se ne ha uno in Skype for business) è visibile in **Chat > contatti** o in **chiamate > contatti**.</span><span class="sxs-lookup"><span data-stu-id="de81a-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="de81a-158">Il client non disturbare e le caratteristiche di innovazione sono sempre abilitate per gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="de81a-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="de81a-159">Calendario (include fuori sede e altre informazioni sul calendario) l'integrazione è sempre abilitata per gli utenti in teams se integrata con Outlook.</span><span class="sxs-lookup"><span data-stu-id="de81a-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="de81a-160">L'ultima volta *che* è *stata visualizzata* o disattivata (se in un ambiente duale con Skype for business) l'indicatore è sempre abilitato per gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="de81a-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="de81a-161">La capacità di un amministratore di teams di personalizzare queste impostazioni non è attualmente supportata.</span><span class="sxs-lookup"><span data-stu-id="de81a-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="de81a-162">Coesistenza con Skype for business</span><span class="sxs-lookup"><span data-stu-id="de81a-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="de81a-163">Vedere la coesistenza [con Skype for business](coexistence-chat-calls-presence.md) per informazioni dettagliate su come funziona la presenza di teams in caso di coesistenza con Skype for business.</span><span class="sxs-lookup"><span data-stu-id="de81a-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
