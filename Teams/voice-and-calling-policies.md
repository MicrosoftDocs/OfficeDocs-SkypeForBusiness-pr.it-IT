---
title: Gestire i criteri di chiamata e voce in Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2021
ms.locfileid: "50348035"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="35a32-102">Gestire i criteri di chiamata e voce in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35a32-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="35a32-103">I criteri di chiamata e voce vengono utilizzati per controllare le chiamate e le chiamate in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35a32-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="35a32-104">Criteri per le chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="35a32-104">Emergency calling policies</span></span>

<span data-ttu-id="35a32-105">I criteri per [le chiamate di emergenza vengono](manage-emergency-calling-policies.md) utilizzati per configurare cosa accade quando un utente dell'organizzazione effettua una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="35a32-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="35a32-106">Questi criteri vengono gestiti nell'interfaccia di amministrazione di Teams o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35a32-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Schermata dei criteri per le chiamate di emergenza.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="35a32-108">Criteri per l'instradamento delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="35a32-108">Emergency call routing policies</span></span>

<span data-ttu-id="35a32-109">Se l'organizzazione ha implementato l'instradamento diretto del sistema **telefonico,** è possibile utilizzare i criteri di instradamento delle chiamate di emergenza per determinare dove vengono instradati le chiamate di emergenza, se sono abilitati o meno i servizi di emergenza e quali numeri sono utilizzati per i servizi di emergenza. [](manage-emergency-call-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="35a32-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="35a32-110">Questi criteri vengono gestiti tramite PowerShell o nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35a32-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Screenshot dei criteri di instradamento delle chiamate di emergenza.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="35a32-112">Criteri ID chiamante</span><span class="sxs-lookup"><span data-stu-id="35a32-112">Caller ID policies</span></span>

<span data-ttu-id="35a32-113">[I criteri ID chiamante](caller-id-policies.md) vengono usati per modificare o bloccare l'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="35a32-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Screenshot del criterio ID chiamante.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="35a32-115">Criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="35a32-115">Voice routing policies</span></span>

<span data-ttu-id="35a32-116">Un [criterio di routing](manage-voice-routing-policies.md) vocale è un contenitore per i record di utilizzo PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="35a32-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="35a32-117">È possibile usare questi criteri se l'organizzazione ha distribuito **l'instradamento diretto del sistema telefonico.**</span><span class="sxs-lookup"><span data-stu-id="35a32-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="35a32-118">I criteri di routing vocale possono essere gestiti con PowerShell o nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="35a32-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Screenshot dei criteri di instradamento vocale.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="35a32-120">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="35a32-120">Calling policies</span></span>

<span data-ttu-id="35a32-121">[I criteri di](teams-calling-policy.md) chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti, tra cui se un utente può effettuare chiamate private, inviare chiamate ai gruppi di chiamata e instradare le chiamate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="35a32-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Screenshot del criterio di chiamata.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="35a32-123">Chiamare il parco e recuperare i criteri</span><span class="sxs-lookup"><span data-stu-id="35a32-123">Call park and retrieve policies</span></span>

<span data-ttu-id="35a32-124">[Il call park e il recupero](call-park-and-retrieve.md) consentono agli utenti di mettere in attesa altri utenti e consentire allo stesso utente o a qualcun altro di continuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="35a32-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Screenshot del parco chiamate e recupera i criteri.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="35a32-126">Creare e impostare piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="35a32-126">Create and manage dial plans</span></span>

<span data-ttu-id="35a32-127">[I piani di chiamata](create-and-manage-dial-plans.md) traducono i numeri di telefono composto per l'autorizzazione e l'instradamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="35a32-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="35a32-128">È possibile creare e gestire piani di chiamata tramite PowerShell o nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35a32-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Schermata del piano di chiamata.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="35a32-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="35a32-130">Related topics</span></span>

* [<span data-ttu-id="35a32-131">Gestire i criteri per le chiamate di emergenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35a32-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="35a32-132">Gestire i criteri del routing delle chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="35a32-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="35a32-133">Gestire i criteri ID chiamante in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35a32-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="35a32-134">Gestire i criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="35a32-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="35a32-135">Criteri per le chiamate in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35a32-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="35a32-136">Chiamare il parco e recuperare in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35a32-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="35a32-137">Creare e impostare piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="35a32-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="35a32-138">Gestire Teams con i criteri</span><span class="sxs-lookup"><span data-stu-id="35a32-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
