---
title: Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare il tipo di utente finale e servizi di conferenza PSTN le chiamate audio che possono essere effettuate dagli utenti.
ms.openlocfilehash: acd75df192211465071940148e35bc7e269c7976
ms.sourcegitcommit: d1b14268efe334aa93a6889f25fcfe46e07d5daa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "33584224"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="2203d-103">Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente</span><span class="sxs-lookup"><span data-stu-id="2203d-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="2203d-104">In qualità di amministratore, è possibile utilizzare i controlli delle chiamate in uscita per limitare il tipo di utente finale e servizi di conferenza PSTN le chiamate audio che possono essere effettuate dagli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2203d-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="2203d-105">Controlli delle chiamate in uscita possono essere applicati a ogni utente e forniscono i seguenti due controlli per limitare in modo indipendente ogni tipo di chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="2203d-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="2203d-106">Per impostazione predefinita, entrambi i controlli sono impostati per consentire le chiamate in uscita nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="2203d-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="2203d-107">Controllo</span><span class="sxs-lookup"><span data-stu-id="2203d-107">Control</span></span>|<span data-ttu-id="2203d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2203d-108">Description</span></span>|<span data-ttu-id="2203d-109">Opzioni di controllo</span><span class="sxs-lookup"><span data-stu-id="2203d-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2203d-110">Chiamate PSTN per conferenze audio</span><span class="sxs-lookup"><span data-stu-id="2203d-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="2203d-111">Consente di limitare il tipo di in uscita</span><span class="sxs-lookup"><span data-stu-id="2203d-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="2203d-112">chiamate a cui sono consentite dall'interno</span><span class="sxs-lookup"><span data-stu-id="2203d-112">calls that are allowed from within</span></span> </br><span data-ttu-id="2203d-113">riunioni organizzate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2203d-113">meetings organized by a user.</span></span>|<span data-ttu-id="2203d-114">International e interno (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="2203d-114">International and Domestic (default)</span></span></br><span data-ttu-id="2203d-115">Nazionale</span><span class="sxs-lookup"><span data-stu-id="2203d-115">Domestic</span></span></br><span data-ttu-id="2203d-116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2203d-116">None</span></span>|
|<span data-ttu-id="2203d-117">Chiamate PSTN degli utenti finali</span><span class="sxs-lookup"><span data-stu-id="2203d-117">End user PSTN calls</span></span>|<span data-ttu-id="2203d-118">Consente di limitare il tipo di chiamate</span><span class="sxs-lookup"><span data-stu-id="2203d-118">Restricts the type of calls</span></span> </br><span data-ttu-id="2203d-119">che può essere effettuata da un utente.</span><span class="sxs-lookup"><span data-stu-id="2203d-119">that can be made by a user.</span></span>|<span data-ttu-id="2203d-120">International e interno (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="2203d-120">International and Domestic (default)</span></span></br><span data-ttu-id="2203d-121">Nazionale</span><span class="sxs-lookup"><span data-stu-id="2203d-121">Domestic</span></span></br><span data-ttu-id="2203d-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2203d-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="2203d-123">Una chiamata è considerata interna se il numero composto nello stesso paese in Office 365 stati impostati per l'organizzatore della riunione (nel caso di conferenze audio) o l'utente finale (nel caso di chiamate PSTN degli utenti finali).</span><span class="sxs-lookup"><span data-stu-id="2203d-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="2203d-124">Limitare le chiamate in uscita audioconferenze con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="2203d-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="2203d-125">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando l'interfaccia di amministrazione di team di Microsoft**</span><span class="sxs-lookup"><span data-stu-id="2203d-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2203d-126">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="2203d-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="2203d-127">Nella parte superiore della pagina, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2203d-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="2203d-128">Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2203d-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="2203d-129">In **autorizzazioni di chiamata in uscita dalle riunioni**, selezionare l'opzione di chiamata esterna per una restrizione desiderato.</span><span class="sxs-lookup"><span data-stu-id="2203d-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="2203d-130">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2203d-130">Click **Save**.</span></span> 

<span data-ttu-id="2203d-131">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="2203d-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="2203d-132">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="2203d-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="2203d-133">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="2203d-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="2203d-134">In **restrizioni alla connessione-outs dalle riunioni dell'utente**, selezionare l'opzione di chiamata in uscita restrizione desiderato.</span><span class="sxs-lookup"><span data-stu-id="2203d-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Le restrizioni alle opzioni di chiamate](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="2203d-136">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2203d-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="2203d-137">**Utilizzo di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2203d-137">**Using PowerShell**</span></span>

<span data-ttu-id="2203d-138">Limitazioni delle chiamate in uscita sono controllati da un singolo criterio denominato OnlineDialOutPolicy che ha un attributo di restrizione per ogni.</span><span class="sxs-lookup"><span data-stu-id="2203d-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="2203d-139">Non è possibile personalizzare il criterio, bensì sono disponibili le istanze dei criteri predefiniti per ogni combinazione delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2203d-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="2203d-140">È possibile utilizzare il cmdlet Get-CSOnlineDialOutPolicy per visualizzare i criteri di chiamata in uscita e assegnrli a utenti utilizzando il cmdlet Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="2203d-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="2203d-141">(Si noti che il cmdlet Grant non contiene la parola "Online" in modo analogo al cmdlet Get.)</span><span class="sxs-lookup"><span data-stu-id="2203d-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="2203d-142">Nella tabella seguente viene fornita una panoramica di ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="2203d-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2203d-143">Identità = 'tag: DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="2203d-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="2203d-144">Utente nella conferenza effettuare chiamate ai numeri nazionali e internazionali e l'utente può inoltre effettuare chiamate in uscita per i numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="2203d-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="2203d-145">Identità = 'tag: DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="2203d-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="2203d-146">Solo utente alla conferenza effettuare chiamate ai numeri nazionali e l'utente può effettuare chiamate in uscita per i numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="2203d-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="2203d-147">Identità = 'tag: DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="2203d-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="2203d-148">Utente alla conferenza non può effettuare qualsiasi dial out. L'utente può effettuare chiamate in uscita per i numeri nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="2203d-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="2203d-149">Identità = 'tag: DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="2203d-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="2203d-150">Utente nella conferenza effettuare chiamate ai numeri nazionali e internazionali e l'utente può effettuare solo chiamate in uscita a numero PSTN interna.</span><span class="sxs-lookup"><span data-stu-id="2203d-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="2203d-151">Identità = 'tag: DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="2203d-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="2203d-152">Utente nella conferenza effettuare chiamate ai numeri nazionali e internazionali e l'utente non può effettuare chiamate in uscita numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2203d-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="2203d-153">Identità = 'tag: DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="2203d-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="2203d-154">Solo utente alla conferenza effettuare chiamate ai numeri nazionali e l'utente può effettuare solo chiamate in uscita a numeri PSTN interne.</span><span class="sxs-lookup"><span data-stu-id="2203d-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="2203d-155">Identità = 'tag: DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="2203d-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="2203d-156">Solo utente alla conferenza effettuare chiamate ai numeri di interno e all'utente non può effettuare chiamate in uscita numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2203d-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="2203d-157">Identità = 'tag: DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="2203d-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="2203d-158">Utente alla conferenza non può effettuare le chiamate in uscita e l'utente può effettuare solo chiamate in uscita a numeri PSTN interne.</span><span class="sxs-lookup"><span data-stu-id="2203d-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="2203d-159">Identità = 'tag: DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="2203d-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="2203d-160">Utente alla conferenza non può effettuare le chiamate in uscita e l'utente non può effettuare chiamate in uscita numero PSTN oltre ai numeri di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2203d-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
