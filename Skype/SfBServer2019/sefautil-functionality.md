---
title: Supporto per l'utilizzo della funzionalità SEFAUtil in PowerShell in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: "Riepilogo: informazioni su come utilizzare PowerShell per ottenere la funzionalità SEFAUtil in Skype for Business Server 2019 dopo l'installazione dell'aggiornamento cumulativo 1."
ms.openlocfilehash: 19c3ba1124bbc1f32f301096036404f8bd101fe9
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868553"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="fc103-103">Utilizzo della funzionalità SEFAUtil tramite PowerShell in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="fc103-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="fc103-104">SEFAUtil (funzione di estensione secondaria) consente agli amministratori e ai consulenti helpdesk di Skype for Business Server di configurare le impostazioni di squillo delegati, di inoltro di chiamata e di prelievo delle chiamate di gruppo per conto di un utente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc103-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="fc103-105">Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="fc103-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="fc103-106">Dopo aver installato l'aggiornamento cumulativo di Skype for Business Server 2019 luglio, la funzionalità seguente che può essere gestita solo tramite SEFAUtil sarà gestibile anche tramite PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc103-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="fc103-107">Impostazioni di inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="fc103-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="fc103-108">Impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="fc103-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="fc103-109">Membri del team e impostazioni correlate</span><span class="sxs-lookup"><span data-stu-id="fc103-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="fc103-110">Impostazioni di inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="fc103-110">Call forwarding settings</span></span>

<span data-ttu-id="fc103-111">Gli amministratori possono modificare le impostazioni di inoltro di chiamata utilizzando il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc103-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="fc103-112">Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="fc103-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="fc103-113">Questo cmdlet consente di modificare le impostazioni di inoltro di chiamata dell'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="fc103-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="fc103-114">Questo cmdlet restituisce le impostazioni di inoltro di chiamata dell'utente specificato come oggetto e visualizza lo stesso sullo schermo, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fc103-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="fc103-115">In caso di errore, verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc103-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="fc103-116">Questo cmdlet consente di disabilitare le impostazioni di inoltro di chiamata dell'utente (vengono mostrati due esempi di parametri diversi).</span><span class="sxs-lookup"><span data-stu-id="fc103-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="fc103-117">Questo cmdlet consente di modificare le impostazioni di inoltro di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fc103-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="fc103-118">Questo cmdlet consente di modificare le impostazioni di SimulRing (di nuovo, con due esempi di parametri, uno per la segreteria telefonica senza risposta e il secondo senza risposta ad altri).</span><span class="sxs-lookup"><span data-stu-id="fc103-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="fc103-119">Impostazioni di delega</span><span class="sxs-lookup"><span data-stu-id="fc103-119">Delegation settings</span></span>

<span data-ttu-id="fc103-120">Gli amministratori possono modificare le impostazioni di delega utilizzando il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc103-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="fc103-121">Questo cmdlet restituisce un oggetto di elenco delegati e visualizza l'elenco dei delegati dell'utente specificato, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fc103-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="fc103-122">In caso di errore, verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc103-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="fc103-123">Questo cmdlet consente di modificare le impostazioni di delega dell'utente specificato, di restituire un oggetto dell'elenco delegati e di visualizzare l'elenco dei delegati, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fc103-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="fc103-124">In caso di errore, verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc103-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="fc103-125">Questo cmdlet aggiunge o rimuove un delegato.</span><span class="sxs-lookup"><span data-stu-id="fc103-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="fc103-126">Questo cmdlet consente di impostare un elenco di delegati per deleghe specifici.</span><span class="sxs-lookup"><span data-stu-id="fc103-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="fc103-127">Membri del team e impostazioni correlate</span><span class="sxs-lookup"><span data-stu-id="fc103-127">Team members and related settings</span></span>

<span data-ttu-id="fc103-128">Gli amministratori possono modificare i membri del team e le impostazioni correlate utilizzando il cmdlet seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fc103-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="fc103-129">Questo cmdlet restituisce un oggetto che contiene l'elenco dei membri del team e visualizza l'oggetto sullo schermo, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fc103-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="fc103-130">In caso di errore, verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc103-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="fc103-131">Questo cmdlet consente di modificare l'elenco dei membri del team dell'utente specificato, di restituire un oggetto che contiene l'elenco dei membri del team e di visualizzare l'oggetto sullo schermo, in caso di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fc103-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="fc103-132">In caso di errore, verrà visualizzato un messaggio di errore appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc103-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="fc103-133">Questo cmdlet aggiunge o rimuove i membri del team.</span><span class="sxs-lookup"><span data-stu-id="fc103-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="fc103-134">Questo cmdlet imposta un elenco di team per membri specifici.</span><span class="sxs-lookup"><span data-stu-id="fc103-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="fc103-135">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="fc103-135">More information</span></span>

<span data-ttu-id="fc103-136">Per le distribuzioni locali, i cmdlet introdotti in questa funzionalità possono essere eseguiti solo dai membri dei gruppi seguenti, per il livello di accesso specificato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fc103-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="fc103-137">CsAdministrator-Get e set per tutti i cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc103-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="fc103-138">CsVoiceAdministrator-Get e set per tutti i cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc103-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="fc103-139">CsHelpDesk-Get per tutti i cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc103-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="fc103-140">Per ulteriori informazioni su questi ruoli di amministratore, vedere [creare gli amministratori del pannello di controllo di Skype for Business Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="fc103-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="fc103-141">L'amministratore può accedere a questi cmdlet direttamente o in remoto accedendo a un computer server.</span><span class="sxs-lookup"><span data-stu-id="fc103-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="fc103-142">Per una distribuzione ibrida, gli amministratori di Skype for business dovrebbero essere in grado di chiamare Get e set per tutti i cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fc103-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="fc103-143">Per ulteriori informazioni sull'elenco completo dei ruoli, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="fc103-143">For more information about the full list of roles, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="fc103-144">L'individuazione automatica del server deve essere abilitata.</span><span class="sxs-lookup"><span data-stu-id="fc103-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="fc103-145">Non verranno introdotti ulteriori requisiti di licenza per l'utilizzo dei cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fc103-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
