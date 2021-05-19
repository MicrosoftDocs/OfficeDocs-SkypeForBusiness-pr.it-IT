---
title: Restrizioni per le chiamate in uscita - Servizi di audioconferenza & chiamate PSTN
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Gli amministratori possono controllare il tipo di audioconferenza e le chiamate PSTN degli utenti finali che possono essere effettuate dagli utenti.
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526729"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="e7bdc-103">Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente</span><span class="sxs-lookup"><span data-stu-id="e7bdc-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="e7bdc-104">Gli amministratori possono usare i controlli delle chiamate in uscita per limitare il tipo di audioconferenza e le chiamate PSTN (Public Switched Telephone Network) degli utenti finali che possono essere effettuate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="e7bdc-105">I controlli delle chiamate in uscita possono essere applicati in base all'utente o al tenant e forniscono i due controlli seguenti per limitare in modo indipendente ogni tipo di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="e7bdc-106">Per impostazione predefinita, entrambi i controlli sono impostati per consentire chiamate in uscita nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="e7bdc-107">Controllo</span><span class="sxs-lookup"><span data-stu-id="e7bdc-107">Control</span></span>|<span data-ttu-id="e7bdc-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7bdc-108">Description</span></span>|<span data-ttu-id="e7bdc-109">Opzioni di controllo</span><span class="sxs-lookup"><span data-stu-id="e7bdc-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7bdc-110">Chiamate PSTN per servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="e7bdc-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="e7bdc-111">Limita il tipo di messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="e7bdc-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="e7bdc-112">chiamate consentite dall'interno</span><span class="sxs-lookup"><span data-stu-id="e7bdc-112">calls that are allowed from within</span></span> </br><span data-ttu-id="e7bdc-113">riunioni organizzate da un utente.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-113">meetings organized by a user.</span></span>|<span data-ttu-id="e7bdc-114">Qualsiasi destinazione (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e7bdc-114">Any destination (default)</span></span></br><span data-ttu-id="e7bdc-115">Nello stesso paese o area geografica dell'organizzatore</span><span class="sxs-lookup"><span data-stu-id="e7bdc-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="e7bdc-116">[Solo paesi o aree geografiche dell'area A](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="e7bdc-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="e7bdc-117">Non consentire</span><span class="sxs-lookup"><span data-stu-id="e7bdc-117">Don't allow</span></span>|
|<span data-ttu-id="e7bdc-118">Chiamate PSTN per l'utente finale</span><span class="sxs-lookup"><span data-stu-id="e7bdc-118">End-user PSTN calls</span></span>|<span data-ttu-id="e7bdc-119">Limita il tipo di chiamata</span><span class="sxs-lookup"><span data-stu-id="e7bdc-119">Restricts the type of calls</span></span> </br><span data-ttu-id="e7bdc-120">che può essere effettuata da un utente.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-120">that can be made by a user.</span></span>|<span data-ttu-id="e7bdc-121">Internazionale e Nazionale (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e7bdc-121">International and Domestic (default)</span></span></br><span data-ttu-id="e7bdc-122">Nazionale</span><span class="sxs-lookup"><span data-stu-id="e7bdc-122">Domestic</span></span></br><span data-ttu-id="e7bdc-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="e7bdc-123">None</span></span>|

<span data-ttu-id="e7bdc-124">Per scoprire quali paesi e aree geografiche sono considerati zona A, vedere Aree geografiche per [audioconferenze.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="e7bdc-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7bdc-125">Una chiamata è considerata nazionale se il numero composto si trova nello stesso paese in cui è stato configurato Microsoft 365 o Office 365 per l'organizzatore della riunione (nel caso delle audioconferenze) o per l'utente finale (nel caso di chiamate PSTN dell'utente finale).</span><span class="sxs-lookup"><span data-stu-id="e7bdc-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="e7bdc-126">Limitare le chiamate in uscita per le audioconferenze</span><span class="sxs-lookup"><span data-stu-id="e7bdc-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="e7bdc-127">![logo Microsoft Teams logo ](media/teams-logo-30x30.png) **Con l'interfaccia Microsoft Teams di amministrazione**</span><span class="sxs-lookup"><span data-stu-id="e7bdc-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e7bdc-128">Nel riquadro di spostamento sinistro selezionare **Utenti** e quindi selezionare il nome visualizzato dell'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="e7bdc-129">Accanto a **Audioconferenza** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e7bdc-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="e7bdc-130">In **Uscita da riunioni** selezionare l'opzione di restrizione della chiamata in uscita desiderata.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="e7bdc-131">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-131">Select **Save**.</span></span>

<span data-ttu-id="e7bdc-132">![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="e7bdc-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="e7bdc-133">**Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Utenti di **audioconferenza** e quindi selezionare l'utente nell'elenco degli  >  utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e7bdc-134">Nel riquadro Azioni selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="e7bdc-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="e7bdc-135">In **Restrizioni alle chiamate in uscita** dalle riunioni di questo utente selezionare l'opzione di restrizione della chiamata in uscita desiderata.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Opzioni Restrizioni per le chiamate in uscita](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="e7bdc-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="e7bdc-138">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e7bdc-138">**Using PowerShell**</span></span>

<span data-ttu-id="e7bdc-139">Le restrizioni per le chiamate in uscita sono controllate da un singolo criterio denominato OnlineDialOutPolicy, che ha un attributo di restrizione per ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="e7bdc-140">Il criterio non può essere personalizzato, ma esistono istanze dei criteri predefinite per ogni combinazione di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="e7bdc-141">È possibile usare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e usare il comando seguente per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="e7bdc-142">**Impostare i criteri a livello di utente con il cmdlet seguente.**</span><span class="sxs-lookup"><span data-stu-id="e7bdc-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="e7bdc-143">Il cmdlet Grant non contiene la parola "Online" come fa il cmdlet Get.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="e7bdc-144">**Impostare i criteri a livello di tenant con il cmdlet seguente.**</span><span class="sxs-lookup"><span data-stu-id="e7bdc-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="e7bdc-145">Tutti gli utenti del tenant a cui non è assegnato alcun criterio di accesso remoto riceveranno questo criterio.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="e7bdc-146">Gli altri utenti rimangono con i criteri correnti.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="e7bdc-147">La tabella seguente fornisce una panoramica di ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="e7bdc-148">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7bdc-148">PowerShell cmdlet</span></span>|<span data-ttu-id="e7bdc-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7bdc-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="e7bdc-150">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="e7bdc-151">L'utente della conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e può anche effettuare chiamate in uscita verso numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="e7bdc-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="e7bdc-153">L'utente della conferenza può effettuare chiamate in uscita solo con numeri nazionali e può effettuare chiamate in uscita verso numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="e7bdc-155">L'utente della conferenza non può effettuare chiamate in uscita. Questo utente può effettuare chiamate in uscita verso numeri internazionali e nazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="e7bdc-157">L'utente della conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e può effettuare solo chiamate in uscita verso numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e7bdc-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="e7bdc-159">L'utente della conferenza può effettuare chiamate in uscita verso numeri internazionali e nazionali e non può effettuare chiamate in uscita verso numeri PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-160">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="e7bdc-161">L'utente della conferenza può effettuare chiamate in uscita solo con numeri nazionali e può effettuare solo chiamate in uscita verso numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="e7bdc-163">L'utente della conferenza può effettuare chiamate in uscita solo con numeri nazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="e7bdc-165">L'utente alla conferenza non può effettuare chiamate in uscita e può effettuare solo chiamate in uscita verso numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-166">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="e7bdc-167">L'utente alla conferenza non può effettuare chiamate in uscita e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="e7bdc-169">L'utente della conferenza può effettuare chiamate in uscita solo nei paesi e nelle aree geografiche dell'area [A](audio-conferencing-zones.md)e può effettuare chiamate in uscita verso numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e7bdc-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="e7bdc-171">L'utente della conferenza può effettuare chiamate in uscita solo nei paesi e nelle aree geografiche dell'area [A](audio-conferencing-zones.md)e può effettuare solo chiamate in uscita verso il numero PSTN nazionale.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e7bdc-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e7bdc-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="e7bdc-173">L'utente della conferenza può effettuare chiamate in uscita solo nei paesi e nelle aree geografiche dell'area [A](audio-conferencing-zones.md)e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e7bdc-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
