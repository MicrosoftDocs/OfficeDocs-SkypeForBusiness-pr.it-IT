---
title: Presenza dell'utente in teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informazioni per gli amministratori sulla presenza in teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573218"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="470ae-103">Presenza dell'utente in teams</span><span class="sxs-lookup"><span data-stu-id="470ae-103">User presence in Teams</span></span>

<span data-ttu-id="470ae-104">La presenza fa parte del profilo di un utente in Microsoft Teams (e in tutto Office 365) che indica la disponibilità e lo stato correnti dell'utente ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="470ae-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="470ae-105">Per impostazione predefinita, tutti gli utenti dell'organizzazione che usano team possono vedere (in tempi quasi reali) se sono disponibili online.</span><span class="sxs-lookup"><span data-stu-id="470ae-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="470ae-106">Se si disinstalla il client Skype for business dopo aver spostato un utente in modalità **solo teams** , la presenza smette di funzionare in Outlook e in altre app di Office.</span><span class="sxs-lookup"><span data-stu-id="470ae-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="470ae-107">La presenza funziona correttamente in teams.</span><span class="sxs-lookup"><span data-stu-id="470ae-107">Presence works fine in Teams.</span></span> <span data-ttu-id="470ae-108">Soluzione alternativa: per vedere la presenza in Outlook e in altre app di Office, è necessario installare Skype for business, anche se si sta usando teams in modalità **solo teams** .</span><span class="sxs-lookup"><span data-stu-id="470ae-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="470ae-109">Microsoft è a conoscenza del problema e sta lavorando a una correzione.</span><span class="sxs-lookup"><span data-stu-id="470ae-109">Microsoft is aware of this problem and is working on a fix.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="470ae-110">Stati presenza in teams</span><span class="sxs-lookup"><span data-stu-id="470ae-110">Presence states in Teams</span></span>

<span data-ttu-id="470ae-111">Gli Stati di presenza degli utenti disponibili in teams sono:</span><span class="sxs-lookup"><span data-stu-id="470ae-111">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="470ae-112">Configurato dall'utente</span><span class="sxs-lookup"><span data-stu-id="470ae-112">User configured</span></span>|<span data-ttu-id="470ae-113">App configurata</span><span class="sxs-lookup"><span data-stu-id="470ae-113">App configured</span></span>|
|:--- |:---|
| ![Segno di spunta verde fisso, che indica la presenza disponibile](media/Presence_Available.png) <span data-ttu-id="470ae-115">Disponibili</span><span class="sxs-lookup"><span data-stu-id="470ae-115">Available</span></span>|![Segno di spunta verde fisso, che indica la presenza disponibile](media/Presence_Available.png) <span data-ttu-id="470ae-117">Disponibili</span><span class="sxs-lookup"><span data-stu-id="470ae-117">Available</span></span>|
|| ![Aprire il segno di spunta verde, indica disponibile OOF](media/Presence_Available_OOF.png) <span data-ttu-id="470ae-119">Disponibile, fuori sede</span><span class="sxs-lookup"><span data-stu-id="470ae-119">Available, Out of Office</span></span> |
|  ![Cerchio rosso a tinta unita, indica occupato](media/Presence_Busy.png) <span data-ttu-id="470ae-121">Disponibilità</span><span class="sxs-lookup"><span data-stu-id="470ae-121">Busy</span></span> |  ![Cerchio rosso a tinta unita, indica occupato](media/Presence_Busy.png) <span data-ttu-id="470ae-123">Disponibilità</span><span class="sxs-lookup"><span data-stu-id="470ae-123">Busy</span></span>  |
|| ![Cerchio rosso a tinta unita, indica occupato in una chiamata](media/Presence_Busy.png) <span data-ttu-id="470ae-125">In una chiamata</span><span class="sxs-lookup"><span data-stu-id="470ae-125">In a call</span></span>|
|| ![Cerchio rosso a tinta unita, indica occupato in una riunione](media/Presence_Busy.png) <span data-ttu-id="470ae-127">In una riunione</span><span class="sxs-lookup"><span data-stu-id="470ae-127">In a meeting</span></span> |
|| ![Aprire il cerchio rosso, indica occupato](media/Presence_Busy_OOF.png) <span data-ttu-id="470ae-129">In una chiamata fuori sede</span><span class="sxs-lookup"><span data-stu-id="470ae-129">In a call, out of office</span></span>|
|  ![Cerchio rosso con linea bianca, indica non disturbare](media/Presence_DND.png) <span data-ttu-id="470ae-131">Non disturbare</span><span class="sxs-lookup"><span data-stu-id="470ae-131">Do not disturb</span></span> ||
|| ![Cerchio rosso con linea bianca, indica la presentazione](media/Presence_DND.png) <span data-ttu-id="470ae-133">Presentazione</span><span class="sxs-lookup"><span data-stu-id="470ae-133">Presenting</span></span>|
|| ![Cerchio rosso con linea bianca, indica lo stato di messa a fuoco](media/Presence_DND.png) <span data-ttu-id="470ae-135">Incentrato</span><span class="sxs-lookup"><span data-stu-id="470ae-135">Focusing</span></span>|
| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) <span data-ttu-id="470ae-137">Via</span><span class="sxs-lookup"><span data-stu-id="470ae-137">Away</span></span>| ![Icona dell'orologio giallo che indica la distanza](media/Presence_Away.png) <span data-ttu-id="470ae-139">Via</span><span class="sxs-lookup"><span data-stu-id="470ae-139">Away</span></span>|
|| <span data-ttu-id="470ae-140">![Icona dell'orologio giallo, che](media/Presence_Away.png) indica la data dell'ultima *ora* di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="470ae-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Icona dell'orologio giallo, indica via, torno subito](media/Presence_Away.png) <span data-ttu-id="470ae-142">Torno subito</span><span class="sxs-lookup"><span data-stu-id="470ae-142">Be right back</span></span>| |
|| ![Icona dell'orologio giallo, indica via, fuori lavoro](media/Presence_Away.png)  <span data-ttu-id="470ae-144">Fuori ufficio</span><span class="sxs-lookup"><span data-stu-id="470ae-144">Off Work</span></span>|
|| ![Cerchio grigio con x, indica offline](media/Presence_Offline.png) <span data-ttu-id="470ae-146">Offline</span><span class="sxs-lookup"><span data-stu-id="470ae-146">Offline</span></span> |
|| ![Apri cerchio grigio, indica lo stato sconosciuto](media/Presence_Unknown.png) <span data-ttu-id="470ae-148">Stato sconosciuto</span><span class="sxs-lookup"><span data-stu-id="470ae-148">Status unknown</span></span>|
||![Aprire il cerchio rosso con la linea diagonale, indica il blocco](media/Presence_Blocked.png) <span data-ttu-id="470ae-150">Bloccati</span><span class="sxs-lookup"><span data-stu-id="470ae-150">Blocked</span></span> |
|| ![Cerchio viola con freccia, indica fuori sede](media/Presence_OOF.png) <span data-ttu-id="470ae-152">Fuori sede</span><span class="sxs-lookup"><span data-stu-id="470ae-152">Out of Office</span></span>|
|||
 
<span data-ttu-id="470ae-153">Gli utenti possono impostare manualmente lo stato presenza corrente su alcune opzioni e il relativo stato viene riflesso a tutti gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="470ae-153">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="470ae-154">Vengono aggiornati automaticamente anche altri dettagli sulla presenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="470ae-154">More user presence details are also automatically updated.</span></span> <span data-ttu-id="470ae-155">Le modifiche sono basate su attività utente (disponibile, assente), Stati del calendario di Outlook (in una riunione) o Stati dell'app Teams (in una chiamata, presentazione), agli Stati rientrati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="470ae-155">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="470ae-156">Si verifica un timeout di 15 minuti di inattività, dopo il quale viene reimpostato uno stato presenza corrente su assente.</span><span class="sxs-lookup"><span data-stu-id="470ae-156">There is a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="470ae-157">Gli utenti possono specificare chi può sfondare (il che significa mettersi in contatto nonostante uno stato non disturbare).</span><span class="sxs-lookup"><span data-stu-id="470ae-157">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="470ae-158">Queste impostazioni sono disponibili nel client teams.</span><span class="sxs-lookup"><span data-stu-id="470ae-158">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="470ae-159">Impostazioni di amministrazione in teams rispetto a Skype for business</span><span class="sxs-lookup"><span data-stu-id="470ae-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="470ae-160">Le seguenti impostazioni di amministratore Skype for business sono diverse in teams:</span><span class="sxs-lookup"><span data-stu-id="470ae-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="470ae-161">In teams, la condivisione della presenza è sempre abilitata per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="470ae-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="470ae-162">La privacy (dove è possibile definire chi può vedere la presenza) la configurazione non è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="470ae-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="470ae-163">La condivisione della presenza con tutti (inclusi i servizi federati) è sempre abilitata per gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="470ae-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="470ae-164">Il relativo elenco di contatti (se ne ha uno in Skype for business) è visibile in **Chat > contatti** o in **chiamate > contatti**.</span><span class="sxs-lookup"><span data-stu-id="470ae-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="470ae-165">Il client non disturbare e le caratteristiche di innovazione sono sempre abilitate per gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="470ae-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="470ae-166">Calendario (include fuori sede e altre informazioni sul calendario) l'integrazione è sempre abilitata per gli utenti quando i team sono integrati con Outlook.</span><span class="sxs-lookup"><span data-stu-id="470ae-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="470ae-167">L'indicatore l'ultima volta *che* viene *visualizzato* o disattivo è sempre abilitato per gli utenti in teams se l'organizzazione usa anche Skype for business.</span><span class="sxs-lookup"><span data-stu-id="470ae-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="470ae-168">La capacità di un amministratore di teams di personalizzare queste impostazioni non è attualmente supportata.</span><span class="sxs-lookup"><span data-stu-id="470ae-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="470ae-169">Coesistenza con Skype for business</span><span class="sxs-lookup"><span data-stu-id="470ae-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="470ae-170">Vedere la [coesistenza con Skype for business](coexistence-chat-calls-presence.md) per informazioni dettagliate su come funziona la presenza di teams quando l'organizzazione usa anche Skype for business.</span><span class="sxs-lookup"><span data-stu-id="470ae-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
