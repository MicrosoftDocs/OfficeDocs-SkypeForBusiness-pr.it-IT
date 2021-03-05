---
title: Gestire i criteri di chiamata e voce in Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni sui criteri di chiamata e voce di Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460586"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="ac5a4-103">Gestire i criteri di chiamata e voce in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac5a4-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="ac5a4-104">I criteri di chiamata e voce vengono utilizzati per controllare le chiamate e le chiamate in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="ac5a4-105">Criteri per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ac5a4-105">Emergency calling policies</span></span>

<span data-ttu-id="ac5a4-106">I criteri per [le chiamate di emergenza vengono](manage-emergency-calling-policies.md) utilizzati per configurare cosa accade quando un utente dell'organizzazione effettua una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="ac5a4-107">Questi criteri vengono gestiti nell'interfaccia di amministrazione di Teams o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Screenshot dei criteri per le chiamate di emergenza.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="ac5a4-109">Criteri per l'instradamento delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ac5a4-109">Emergency call routing policies</span></span>

<span data-ttu-id="ac5a4-110">Se l'organizzazione ha implementato l'instradamento diretto del sistema **telefonico,** è possibile utilizzare i criteri di instradamento delle chiamate di emergenza per determinare dove vengono instradati le chiamate di emergenza, se sono abilitati o meno i servizi di emergenza e quali numeri sono utilizzati per i servizi di emergenza. [](manage-emergency-call-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ac5a4-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="ac5a4-111">Questi criteri vengono gestiti tramite PowerShell o nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Screenshot dei criteri di instradamento delle chiamate di emergenza.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="ac5a4-113">Criteri ID chiamante</span><span class="sxs-lookup"><span data-stu-id="ac5a4-113">Caller ID policies</span></span>

<span data-ttu-id="ac5a4-114">[I criteri ID chiamante](caller-id-policies.md) vengono usati per modificare o bloccare l'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Screenshot del criterio ID chiamante.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="ac5a4-116">Criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="ac5a4-116">Voice routing policies</span></span>

<span data-ttu-id="ac5a4-117">Un [criterio di routing](manage-voice-routing-policies.md) vocale è un contenitore per i record di utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="ac5a4-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="ac5a4-118">È possibile usare questi criteri se l'organizzazione ha distribuito **l'instradamento diretto del sistema telefonico.**</span><span class="sxs-lookup"><span data-stu-id="ac5a4-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="ac5a4-119">I criteri di routing vocale possono essere gestiti con PowerShell o nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Screenshot dei criteri di instradamento vocale.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="ac5a4-121">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="ac5a4-121">Calling policies</span></span>

<span data-ttu-id="ac5a4-122">[I criteri di](teams-calling-policy.md) chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti, tra cui se un utente può effettuare chiamate private, inviare chiamate ai gruppi di chiamata e instradare le chiamate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Screenshot del criterio di chiamata.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="ac5a4-124">Chiamare il parco e recuperare i criteri</span><span class="sxs-lookup"><span data-stu-id="ac5a4-124">Call park and retrieve policies</span></span>

<span data-ttu-id="ac5a4-125">[Il call park e il recupero](call-park-and-retrieve.md) consentono agli utenti di mettere in attesa altri utenti e consentire allo stesso utente o a qualcun altro di continuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Screenshot del parco chiamate e recupera i criteri.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="ac5a4-127">Creare e impostare dial plan</span><span class="sxs-lookup"><span data-stu-id="ac5a4-127">Create and manage dial plans</span></span>

<span data-ttu-id="ac5a4-128">[I piani di chiamata](create-and-manage-dial-plans.md) traducono i numeri di telefono composto per l'autorizzazione e l'instradamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="ac5a4-129">È possibile creare e gestire piani di chiamata tramite PowerShell o nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ac5a4-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Schermata del piano di chiamata.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="ac5a4-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ac5a4-131">Related topics</span></span>

* [<span data-ttu-id="ac5a4-132">Gestire i criteri per le chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac5a4-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="ac5a4-133">Gestire i criteri del routing delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ac5a4-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="ac5a4-134">Gestire i criteri dell'ID chiamante in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac5a4-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="ac5a4-135">Gestire i criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="ac5a4-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="ac5a4-136">Criteri per le chiamate in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac5a4-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="ac5a4-137">Chiamare il parco e recuperare in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac5a4-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="ac5a4-138">Creare e impostare dial plan</span><span class="sxs-lookup"><span data-stu-id="ac5a4-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="ac5a4-139">Gestire Teams con i criteri</span><span class="sxs-lookup"><span data-stu-id="ac5a4-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
