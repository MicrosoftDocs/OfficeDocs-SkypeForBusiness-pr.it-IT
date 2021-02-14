---
title: Restrizioni alle chiamate in uscita - Audioconferenza & chiamate PSTN
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
description: Gli amministratori possono controllare il tipo di audioconferenza e di chiamate PSTN degli utenti finali che possono essere effettuate dagli utenti.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908655"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="0fb5c-103">Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente</span><span class="sxs-lookup"><span data-stu-id="0fb5c-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="0fb5c-104">Gli amministratori possono usare i controlli per le chiamate in uscita per limitare il tipo di audioconferenze e di chiamate PSTN che possono essere eseguite dagli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="0fb5c-105">I controlli delle chiamate in uscita possono essere applicati per utente e forniscono i due controlli seguenti per limitare in modo indipendente ogni tipo di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="0fb5c-106">Per impostazione predefinita, entrambi i controlli sono impostati per consentire chiamate in uscita nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="0fb5c-107">Controllo</span><span class="sxs-lookup"><span data-stu-id="0fb5c-107">Control</span></span>|<span data-ttu-id="0fb5c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fb5c-108">Description</span></span>|<span data-ttu-id="0fb5c-109">Opzioni di controllo</span><span class="sxs-lookup"><span data-stu-id="0fb5c-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0fb5c-110">Chiamate PSTN per audioconferenze</span><span class="sxs-lookup"><span data-stu-id="0fb5c-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="0fb5c-111">Limita il tipo di connessioni in uscita</span><span class="sxs-lookup"><span data-stu-id="0fb5c-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="0fb5c-112">chiamate consentite dall'interno</span><span class="sxs-lookup"><span data-stu-id="0fb5c-112">calls that are allowed from within</span></span> </br><span data-ttu-id="0fb5c-113">riunioni organizzate da un utente.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-113">meetings organized by a user.</span></span>|<span data-ttu-id="0fb5c-114">Qualsiasi destinazione (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="0fb5c-114">Any destination (default)</span></span></br><span data-ttu-id="0fb5c-115">Nello stesso paese o area geografica dell'organizzatore</span><span class="sxs-lookup"><span data-stu-id="0fb5c-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="0fb5c-116">[Solo paesi o aree geografiche dell'area A](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="0fb5c-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="0fb5c-117">Non consentire</span><span class="sxs-lookup"><span data-stu-id="0fb5c-117">Don't allow</span></span>|
|<span data-ttu-id="0fb5c-118">Chiamate PSTN dell'utente finale</span><span class="sxs-lookup"><span data-stu-id="0fb5c-118">End user PSTN calls</span></span>|<span data-ttu-id="0fb5c-119">Limita il tipo di chiamata</span><span class="sxs-lookup"><span data-stu-id="0fb5c-119">Restricts the type of calls</span></span> </br><span data-ttu-id="0fb5c-120">che può essere effettuata da un utente.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-120">that can be made by a user.</span></span>|<span data-ttu-id="0fb5c-121">Internazionale e nazionale (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="0fb5c-121">International and Domestic (default)</span></span></br><span data-ttu-id="0fb5c-122">Nazionale</span><span class="sxs-lookup"><span data-stu-id="0fb5c-122">Domestic</span></span></br><span data-ttu-id="0fb5c-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0fb5c-123">None</span></span>|

<span data-ttu-id="0fb5c-124">Per sapere quali paesi e aree geografiche sono considerati Area A, consulta Paese e aree [geografiche per le audioconferenze.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="0fb5c-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0fb5c-125">Una chiamata è considerata nazionale se il numero composto si trova nello stesso paese in cui Microsoft 365 o Office 365 è stato configurato per l'organizzatore della riunione (nel caso dei servizi di audioconferenza) o per l'utente finale (nel caso delle chiamate PSTN dell'utente finale).</span><span class="sxs-lookup"><span data-stu-id="0fb5c-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="0fb5c-126">Limitare le chiamate in uscita per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="0fb5c-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="0fb5c-127">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0fb5c-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0fb5c-128">Nel riquadro di spostamento sinistro fare **clic su** Utenti e quindi sul nome visualizzato dell'utente nell'elenco di utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-128">In the left navigation, click **Users**, and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="0fb5c-129">Accanto a **Audioconferenza,** fai clic **su Modifica.**</span><span class="sxs-lookup"><span data-stu-id="0fb5c-129">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="0fb5c-130">In **Chiamata in uscita dalle riunioni** selezionare l'opzione di restrizione per la chiamata in uscita desiderata.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="0fb5c-131">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-131">Click **Save**.</span></span> 

<span data-ttu-id="0fb5c-132">![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="0fb5c-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="0fb5c-133">**Nell'interfaccia di amministrazione di Skype for Business,** nella barra di spostamento sinistra, accedi a Utenti di **audioconferenza** e quindi seleziona l'utente dall'elenco  >  degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0fb5c-134">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="0fb5c-135">In **Restrizioni alle chiamate in** uscita dalle riunioni di questo utente, selezionare l'opzione di restrizione per la chiamata in uscita desiderata.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Restrizioni alle opzioni di chiamata in uscita](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="0fb5c-137">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="0fb5c-138">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0fb5c-138">**Using PowerShell**</span></span>

<span data-ttu-id="0fb5c-139">Le limitazioni delle chiamate in uscita sono controllate da un singolo criterio denominato OnlineDialOutPolicy, che ha un attributo di restrizione per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="0fb5c-140">Il criterio non può essere personalizzato, ma esistono istanze di criteri predefinite per ogni combinazione di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="0fb5c-141">È possibile usare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e assegnarli agli utenti usando Grant-CSDialOutPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="0fb5c-142">Tenere presente che il cmdlet Grant non contiene la parola "Online" come fa il cmdlet Get.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="0fb5c-143">La tabella seguente fornisce una panoramica di ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0fb5c-144">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="0fb5c-145">L'utente che è presente alla conferenza può effettuare chiamate in uscita verso numeri nazionali e internazionali e può effettuare chiamate in uscita verso numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="0fb5c-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="0fb5c-147">L'utente alla conferenza può effettuare chiamate in uscita solo a numeri nazionali e può effettuare chiamate in uscita verso numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="0fb5c-149">L'utente che è in conferenza non può effettuare chiamate in uscita. Questo utente può effettuare chiamate in uscita verso numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="0fb5c-151">L'utente che è in conferenza può effettuare chiamate in uscita verso numeri nazionali e internazionali e può effettuare chiamate in uscita solo verso numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="0fb5c-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="0fb5c-153">L'utente alla conferenza può effettuare chiamate in uscita verso numeri nazionali e internazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-154">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="0fb5c-155">L'utente che è in conferenza può effettuare chiamate in uscita solo a numeri nazionali e può effettuare chiamate in uscita solo su numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="0fb5c-157">L'utente alla conferenza può effettuare chiamate in uscita solo a numeri nazionali e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="0fb5c-159">L'utente che è in conferenza non può effettuare chiamate in uscita e può effettuare chiamate in uscita solo verso numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-160">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="0fb5c-161">L'utente alla conferenza non può effettuare chiamate in uscita e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="0fb5c-163">L'utente alla conferenza può effettuare chiamate in uscita solo verso i paesi e le aree geografiche dell'Area [A](audio-conferencing-zones.md)e può effettuare chiamate in uscita verso numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0fb5c-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="0fb5c-165">L'utente alla conferenza può effettuare chiamate in uscita solo verso i paesi e le aree geografiche dell'Area [A](audio-conferencing-zones.md)e può effettuare chiamate in uscita solo verso numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="0fb5c-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0fb5c-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="0fb5c-167">L'utente alla conferenza può effettuare chiamate in uscita solo verso i paesi e le aree geografiche dell'Area [A](audio-conferencing-zones.md)e non può effettuare chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="0fb5c-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
