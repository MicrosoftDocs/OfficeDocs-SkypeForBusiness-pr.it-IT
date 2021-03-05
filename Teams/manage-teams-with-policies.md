---
title: Gestire Teams con i criteri
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni sui criteri di Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f06e9aa87cc0c1af758bf0c8c9abad6641debbd
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460496"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="9f901-103">Gestire Teams con i criteri</span><span class="sxs-lookup"><span data-stu-id="9f901-103">Manage Teams with policies</span></span>

<span data-ttu-id="9f901-104">I criteri sono una parte importante della gestione di Teams.</span><span class="sxs-lookup"><span data-stu-id="9f901-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="9f901-105">Usare questo articolo per informazioni su come usare i criteri a vantaggio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f901-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="9f901-106">Per cosa si usano i criteri</span><span class="sxs-lookup"><span data-stu-id="9f901-106">What you use policies for</span></span>

<span data-ttu-id="9f901-107">I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9f901-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="9f901-108">Alcune delle operazioni che è possibile eseguire includono il consentire agli utenti di pianificare riunioni in un canale di Teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra dell'app di Teams.</span><span class="sxs-lookup"><span data-stu-id="9f901-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="9f901-109">Come assegnare criteri</span><span class="sxs-lookup"><span data-stu-id="9f901-109">How to assign policies</span></span>

<span data-ttu-id="9f901-110">I criteri possono essere assegnati in diversi modi a seconda del risultato che l'organizzazione sta cercando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="9f901-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="9f901-111">È possibile fare e visualizzare le attività nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="9f901-111">You can make and view assignments in the Teams admin center.</span></span>

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

<span data-ttu-id="9f901-113">Per altre informazioni sull'assegnazione dei criteri, [vedere](assign-policies.md)qui.</span><span class="sxs-lookup"><span data-stu-id="9f901-113">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="9f901-114">Come gestire i criteri</span><span class="sxs-lookup"><span data-stu-id="9f901-114">How to manage policies</span></span>

<span data-ttu-id="9f901-115">I criteri vengono gestiti con l'interfaccia di amministrazione di Microsoft Teams [o con PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="9f901-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="9f901-116">Ad esempio, un criterio di configurazione delle app può consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra dell'app di Teams.</span><span class="sxs-lookup"><span data-stu-id="9f901-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="9f901-117">Questi criteri sono configurati nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="9f901-117">These policies are configured in the Teams admin center.</span></span>

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

<span data-ttu-id="9f901-119">Inoltre, un criterio di riunione può essere usato per controllare le impostazioni audio e video nelle riunioni di Teams, ad esempio trascrizioni, registrazioni cloud e audio/video IP.</span><span class="sxs-lookup"><span data-stu-id="9f901-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Screenshot del criterio di riunione.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="9f901-121">Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="9f901-121">Teams for Education</span></span>

<span data-ttu-id="9f901-122">È anche possibile usare la procedura [guidata dei criteri di Teams for Education](easy-policy-setup-edu.md) per configurare e gestire facilmente i criteri per l'ambiente di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="9f901-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Screenshot della procedura guidata per i criteri di Teams for Education.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="9f901-124">Tipi di criteri</span><span class="sxs-lookup"><span data-stu-id="9f901-124">Types of policies</span></span>

<span data-ttu-id="9f901-125">I seguenti criteri possono essere gestiti con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f901-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="9f901-126">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="9f901-126">Policy type</span></span> | <span data-ttu-id="9f901-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f901-127">Description</span></span>
------------|------------
[<span data-ttu-id="9f901-128">Pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="9f901-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="9f901-129">Un pacchetto di criteri in Microsoft Teams è una raccolta di impostazioni e criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f901-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="9f901-130">Criteri riunione</span><span class="sxs-lookup"><span data-stu-id="9f901-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="9f901-131">I criteri di riunione vengono utilizzati per controllare le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f901-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="9f901-132">I criteri delle riunioni includono gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f901-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="9f901-133">- Criteri audio e video</span><span class="sxs-lookup"><span data-stu-id="9f901-133">- Audio and video policies</span></span><br> <span data-ttu-id="9f901-134">- Criteri di condivisione del contenuto e dello schermo</span><span class="sxs-lookup"><span data-stu-id="9f901-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="9f901-135">- Partecipanti, guest e criteri di accesso</span><span class="sxs-lookup"><span data-stu-id="9f901-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="9f901-136">- Criteri generali</span><span class="sxs-lookup"><span data-stu-id="9f901-136">- General policies</span></span>
[<span data-ttu-id="9f901-137">Criteri per chiamate e voce</span><span class="sxs-lookup"><span data-stu-id="9f901-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="9f901-138">I criteri vocali e di chiamata gestiscono queste impostazioni tramite team come chiamate di emergenza, instradamento chiamate e ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f901-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="9f901-139">Criteri delle app</span><span class="sxs-lookup"><span data-stu-id="9f901-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="9f901-140">I criteri delle app vengono usati per controllare le applicazioni in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f901-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="9f901-141">Gli amministratori possono consentire o bloccare le app che gli utenti possono installare, aggiungere applicazioni alla barra dell'app teams di un utente e installare l'applicazione per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9f901-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="9f901-142">Criteri di messaggistica</span><span class="sxs-lookup"><span data-stu-id="9f901-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="9f901-143">I criteri di messaggistica controllano la disponibilità delle funzionalità di chat e canali.</span><span class="sxs-lookup"><span data-stu-id="9f901-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f901-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9f901-144">Related topics</span></span>

* [<span data-ttu-id="9f901-145">Gestire i criteri di feedback in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f901-145">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="9f901-146">Gestire i criteri dei team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f901-146">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="9f901-147">Visualizzare le assegnazioni dei criteri nel log attività</span><span class="sxs-lookup"><span data-stu-id="9f901-147">View policy assignments in the Activity Log</span></span>](activity-log.md)
* [<span data-ttu-id="9f901-148">Configurare gli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f901-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="9f901-149">Criteri e pacchetti di criteri di Teams for Education</span><span class="sxs-lookup"><span data-stu-id="9f901-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
