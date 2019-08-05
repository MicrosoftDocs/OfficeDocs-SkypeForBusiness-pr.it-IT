---
title: Supporto per l'uso della funzionalità SEFAUtil in PowerShell in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: "Riepilogo: informazioni su come usare PowerShell per ottenere la funzionalità SEFAUtil in Skype for Business Server 2019 dopo l'installazione dell'aggiornamento cumulativo 1."
ms.openlocfilehash: 1c5d8d32c1b7b1b988b0ab39c79e4a7f40752875
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "36196064"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="f39e6-103">Uso della funzionalità SEFAUtil tramite PowerShell in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f39e6-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="f39e6-104">SEFAUtil (attivazione delle funzionalità di estensione secondaria) consente agli amministratori di Skype for Business Server e agli agenti helpdesk di configurare le impostazioni di chiamata delegata, di inoltro delle chiamate e di gruppo per conto di un utente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f39e6-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="f39e6-105">Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="f39e6-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="f39e6-106">Dopo aver installato questo aggiornamento, le funzionalità seguenti che possono essere gestite solo tramite SEFAUtil saranno gestibili anche tramite PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f39e6-106">After you install this update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="f39e6-107">Impostazioni inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="f39e6-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="f39e6-108">Impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="f39e6-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="f39e6-109">Membri del team e impostazioni correlate</span><span class="sxs-lookup"><span data-stu-id="f39e6-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="f39e6-110">Impostazioni inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="f39e6-110">Call forwarding settings</span></span>

<span data-ttu-id="f39e6-111">Gli amministratori possono modificare le impostazioni di inoltro di chiamata usando il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f39e6-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="f39e6-112">Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="f39e6-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="f39e6-113">Questo cmdlet modifica le impostazioni di inoltro di chiamata dell'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="f39e6-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="f39e6-114">Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f39e6-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="f39e6-115">In caso di errore verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="f39e6-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="f39e6-116">Questo cmdlet disabilita le impostazioni di inoltro di chiamata dell'utente (qui vengono mostrati due diversi esempi di parametri).</span><span class="sxs-lookup"><span data-stu-id="f39e6-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="f39e6-117">Questo cmdlet modifica le impostazioni di inoltro di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f39e6-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="f39e6-118">Questo cmdlet modifica le impostazioni di SimulRing (di nuovo, con due esempi di parametri, uno per la segreteria telefonica senza risposta e il secondo senza risposta ad altri).</span><span class="sxs-lookup"><span data-stu-id="f39e6-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="f39e6-119">Impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="f39e6-119">Delegation settings</span></span>

<span data-ttu-id="f39e6-120">Gli amministratori possono modificare le impostazioni di delega usando il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f39e6-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="f39e6-121">Questo cmdlet restituisce un oggetto di elenco delegati e visualizza l'elenco dei delegati dell'utente specificato in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f39e6-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="f39e6-122">In caso di errore verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="f39e6-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="f39e6-123">Questo cmdlet modifica le impostazioni di delega dell'utente specificato, restituisce un oggetto di elenco delegati e visualizza l'elenco dei delegati, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f39e6-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="f39e6-124">In caso di errore verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="f39e6-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="f39e6-125">Questo cmdlet aggiunge o rimuove un delegato.</span><span class="sxs-lookup"><span data-stu-id="f39e6-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="f39e6-126">Questo cmdlet imposta un elenco delegato su delegati specifici.</span><span class="sxs-lookup"><span data-stu-id="f39e6-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="f39e6-127">Membri del team e impostazioni correlate</span><span class="sxs-lookup"><span data-stu-id="f39e6-127">Team members and related settings</span></span>

<span data-ttu-id="f39e6-128">Gli amministratori possono cambiare i membri del team e le impostazioni correlate usando il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f39e6-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="f39e6-129">Questo cmdlet restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f39e6-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="f39e6-130">In caso di errore verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="f39e6-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="f39e6-131">Questo cmdlet modifica l'elenco dei membri del team dell'utente specificato, restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f39e6-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="f39e6-132">In caso di errore verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="f39e6-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="f39e6-133">Questo cmdlet aggiunge o rimuove i membri del team.</span><span class="sxs-lookup"><span data-stu-id="f39e6-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="f39e6-134">Questo cmdlet imposta un elenco di Team su membri specifici.</span><span class="sxs-lookup"><span data-stu-id="f39e6-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="f39e6-135">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="f39e6-135">More information</span></span>

<span data-ttu-id="f39e6-136">Per le distribuzioni locali, i cmdlet introdotti in questa funzionalità possono essere eseguiti solo dai membri dei gruppi seguenti, per il livello di accesso specificato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f39e6-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="f39e6-137">CsAdministrator-ottenere e impostare per tutti i cmdlet</span><span class="sxs-lookup"><span data-stu-id="f39e6-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="f39e6-138">CsVoiceAdministrator-ottenere e impostare per tutti i cmdlet</span><span class="sxs-lookup"><span data-stu-id="f39e6-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="f39e6-139">CsHelpDesk-Get per tutti i cmdlet</span><span class="sxs-lookup"><span data-stu-id="f39e6-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="f39e6-140">Per altre informazioni su questi ruoli di amministratore, vedere [creare amministratori del pannello di controllo di Skype for Business Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="f39e6-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="f39e6-141">L'amministratore può accedere a questi cmdlet direttamente o in remoto accedendo a un computer server.</span><span class="sxs-lookup"><span data-stu-id="f39e6-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="f39e6-142">Per una distribuzione ibrida, gli amministratori di Skype for business dovrebbero poter chiamare Get e set per tutti i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f39e6-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="f39e6-143">Per altre informazioni sull'elenco completo dei ruoli, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="f39e6-143">For more information about the full list of roles, see [About Office 365 admin roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="f39e6-144">L'individuazione automatica del server deve essere abilitata.</span><span class="sxs-lookup"><span data-stu-id="f39e6-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="f39e6-145">Non verranno introdotti requisiti di licenza aggiuntivi per l'uso dei cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f39e6-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
