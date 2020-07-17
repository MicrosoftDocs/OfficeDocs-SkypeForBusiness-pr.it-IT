---
title: Restrizioni delle chiamate in uscita-audioconferenza & chiamate PSTN
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
description: Gli amministratori possono controllare il tipo di audioconferenza e chiamate PSTN degli utenti finali che possono essere effettuate dagli utenti.
ms.openlocfilehash: fd7c30a7561c06dd237bb72b405c8fc5b7b68dcd
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077671"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="d05b8-103">Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente</span><span class="sxs-lookup"><span data-stu-id="d05b8-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="d05b8-104">Gli amministratori possono usare i controlli per le chiamate in uscita per limitare il tipo di audioconferenze e di chiamate PSTN che possono essere eseguite dagli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d05b8-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="d05b8-105">I controlli delle chiamate in uscita possono essere applicati per ogni singolo utente e offrono i due controlli seguenti per limitare in modo indipendente ogni tipo di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="d05b8-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="d05b8-106">Per impostazione predefinita, entrambi i controlli sono impostati per consentire chiamate in uscita internazionali e nazionali.</span><span class="sxs-lookup"><span data-stu-id="d05b8-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="d05b8-107">Controllo</span><span class="sxs-lookup"><span data-stu-id="d05b8-107">Control</span></span>|<span data-ttu-id="d05b8-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d05b8-108">Description</span></span>|<span data-ttu-id="d05b8-109">Opzioni di controllo</span><span class="sxs-lookup"><span data-stu-id="d05b8-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d05b8-110">Chiamate PSTN per servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d05b8-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="d05b8-111">Limita il tipo di in uscita</span><span class="sxs-lookup"><span data-stu-id="d05b8-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="d05b8-112">chiamate consentite dall'interno</span><span class="sxs-lookup"><span data-stu-id="d05b8-112">calls that are allowed from within</span></span> </br><span data-ttu-id="d05b8-113">riunioni organizzate da un utente.</span><span class="sxs-lookup"><span data-stu-id="d05b8-113">meetings organized by a user.</span></span>|<span data-ttu-id="d05b8-114">Qualsiasi destinazione (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="d05b8-114">Any destination (default)</span></span></br><span data-ttu-id="d05b8-115">Nello stesso paese o area geografica di organizor</span><span class="sxs-lookup"><span data-stu-id="d05b8-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="d05b8-116">Area solo paesi o aree geografiche</span><span class="sxs-lookup"><span data-stu-id="d05b8-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="d05b8-117">Non consentire</span><span class="sxs-lookup"><span data-stu-id="d05b8-117">Don't allow</span></span>|
|<span data-ttu-id="d05b8-118">Chiamate PSTN degli utenti finali</span><span class="sxs-lookup"><span data-stu-id="d05b8-118">End user PSTN calls</span></span>|<span data-ttu-id="d05b8-119">Limita il tipo di chiamate</span><span class="sxs-lookup"><span data-stu-id="d05b8-119">Restricts the type of calls</span></span> </br><span data-ttu-id="d05b8-120">che possono essere eseguite da un utente.</span><span class="sxs-lookup"><span data-stu-id="d05b8-120">that can be made by a user.</span></span>|<span data-ttu-id="d05b8-121">Internazionali e nazionali (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="d05b8-121">International and Domestic (default)</span></span></br><span data-ttu-id="d05b8-122">Nazionali</span><span class="sxs-lookup"><span data-stu-id="d05b8-122">Domestic</span></span></br><span data-ttu-id="d05b8-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d05b8-123">None</span></span>|

<span data-ttu-id="d05b8-124">Per scoprire quali paesi/aree geografiche sono considerate zone A, vedere [zone a paesi/aree geografiche](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="d05b8-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d05b8-125">Una chiamata è considerata domestica se il numero composto si trova nello stesso paese in cui è stato configurato Microsoft 365 o Office 365 per l'organizzatore della riunione (nel caso di servizi di audioconferenza) o per l'utente finale (nel caso di chiamate PSTN degli utenti finali).</span><span class="sxs-lookup"><span data-stu-id="d05b8-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="d05b8-126">Limitare le chiamate in uscita per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d05b8-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="d05b8-127">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d05b8-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d05b8-128">Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="d05b8-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="d05b8-129">Nella parte superiore della pagina, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="d05b8-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="d05b8-130">Accanto a servizi di **audioconferenza**fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="d05b8-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="d05b8-131">In **autorizzazioni di accesso esterno da riunioni**selezionare l'opzione di restrizione della chiamata in uscita desiderata.</span><span class="sxs-lookup"><span data-stu-id="d05b8-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="d05b8-132">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d05b8-132">Click **Save**.</span></span> 

<span data-ttu-id="d05b8-133">![Icona che mostra il logo di Skype for Business](media/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d05b8-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="d05b8-134">Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, passa a utenti di servizi di **audioconferenza**  >  **Users**e quindi seleziona l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="d05b8-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="d05b8-135">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="d05b8-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="d05b8-136">In **restrizioni ai dial-out delle riunioni di questo utente**selezionare l'opzione di restrizione chiamata in uscita desiderata.</span><span class="sxs-lookup"><span data-stu-id="d05b8-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Le restrizioni alle opzioni per i dial-out](/Skype/SfbOnline/images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="d05b8-138">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d05b8-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="d05b8-139">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d05b8-139">**Using PowerShell**</span></span>

<span data-ttu-id="d05b8-140">Le restrizioni delle chiamate in uscita sono controllate da un singolo criterio denominato OnlineDialOutPolicy che contiene un attributo di restrizione per ogni.</span><span class="sxs-lookup"><span data-stu-id="d05b8-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="d05b8-141">I criteri non possono essere personalizzati, ma esistono istanze di criteri predefinite per ogni combinazione delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d05b8-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="d05b8-142">Puoi usare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e assegnarli agli utenti usando il cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="d05b8-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="d05b8-143">Tieni presente che il cmdlet Grant non contiene la parola "online" come fa il cmdlet Get.</span><span class="sxs-lookup"><span data-stu-id="d05b8-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="d05b8-144">La tabella seguente offre una panoramica di ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="d05b8-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d05b8-145">Identity =' Tag: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d05b8-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="d05b8-146">L'utente della conferenza può effettuare chiamate in uscita per i numeri nazionali e internazionali, e questo utente può anche eseguire una chiamata in uscita a numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="d05b8-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="d05b8-147">Identity =' Tag: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d05b8-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="d05b8-148">L'utente nella conferenza può effettuare la chiamata solo ai numeri nazionali e questo utente può eseguire chiamate in uscita a numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="d05b8-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="d05b8-149">Identity =' Tag: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d05b8-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="d05b8-150">L'utente della conferenza non può effettuare una chiamata esterna. Questo utente può effettuare chiamate in uscita a numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="d05b8-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="d05b8-151">Identity =' Tag: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d05b8-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="d05b8-152">L'utente della conferenza può effettuare una chiamata esterna a numeri nazionali e internazionali e questo utente può eseguire chiamate in uscita solo al numero PSTN nazionale.</span><span class="sxs-lookup"><span data-stu-id="d05b8-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="d05b8-153">Identity =' Tag: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d05b8-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="d05b8-154">L'utente della conferenza può effettuare una chiamata esterna a numeri nazionali e internazionali e questo utente non può eseguire chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d05b8-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="d05b8-155">Identity =' Tag: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d05b8-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="d05b8-156">L'utente nella conferenza può effettuare la chiamata solo ai numeri nazionali e questo utente può eseguire solo chiamate in uscita ai numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="d05b8-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="d05b8-157">Identity =' Tag: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d05b8-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="d05b8-158">L'utente nella conferenza può effettuare la chiamata solo ai numeri nazionali e questo utente non può eseguire chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d05b8-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="d05b8-159">Identity =' Tag: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d05b8-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="d05b8-160">L'utente della conferenza non può effettuare chiamate in uscita e questo utente può solo effettuare una chiamata in uscita ai numeri PSTN nazionali.</span><span class="sxs-lookup"><span data-stu-id="d05b8-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="d05b8-161">Identity =' Tag: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d05b8-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="d05b8-162">L'utente della conferenza non può effettuare chiamate in uscita e questo utente non può effettuare alcuna chiamata in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d05b8-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="d05b8-163">Identity =' Tag: DialoutCPCZoneAPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="d05b8-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="d05b8-164">L'utente nella conferenza può effettuare la chiamata solo per la zona di paesi e aree geografiche e questo utente può eseguire chiamate in uscita a numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="d05b8-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="d05b8-165">Identity =' Tag: DialoutCPCZoneAPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="d05b8-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="d05b8-166">L'utente nella conferenza può effettuare la chiamata solo per la zona di paesi e aree geografiche e questo utente può eseguire solo chiamate in uscita al numero PSTN nazionale.</span><span class="sxs-lookup"><span data-stu-id="d05b8-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="d05b8-167">Identity =' Tag: DialoutCPCZoneAPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="d05b8-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="d05b8-168">L'utente nella conferenza può effettuare la chiamata solo per la zona di paesi e aree geografiche e questo utente non può eseguire chiamate in uscita al numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="d05b8-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
