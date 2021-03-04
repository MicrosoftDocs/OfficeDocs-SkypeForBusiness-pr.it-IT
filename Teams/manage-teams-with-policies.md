---
title: Gestire Teams con i criteri
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
ms.openlocfilehash: 368e71820100ba8cfccb28eef63864f47cd8ce85
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421301"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="4babb-102">Gestire Teams con i criteri</span><span class="sxs-lookup"><span data-stu-id="4babb-102">Manage Teams with policies</span></span>

<span data-ttu-id="4babb-103">I criteri sono una parte importante della gestione di Teams.</span><span class="sxs-lookup"><span data-stu-id="4babb-103">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="4babb-104">Usare questo articolo per informazioni su come usare i criteri a vantaggio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4babb-104">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="4babb-105">Per cosa si usano i criteri</span><span class="sxs-lookup"><span data-stu-id="4babb-105">What you use policies for</span></span>

<span data-ttu-id="4babb-106">I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4babb-106">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="4babb-107">Alcune delle operazioni che è possibile eseguire includono il consentire agli utenti di pianificare riunioni in un canale di Teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra dell'app di Teams.</span><span class="sxs-lookup"><span data-stu-id="4babb-107">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="4babb-108">Come assegnare criteri</span><span class="sxs-lookup"><span data-stu-id="4babb-108">How to assign policies</span></span>

<span data-ttu-id="4babb-109">I criteri possono essere assegnati in diversi modi a seconda del risultato che l'organizzazione sta cercando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="4babb-109">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="4babb-110">Puoi fare e visualizzare le attività nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="4babb-110">You can make and view assignments in the Teams admin center.</span></span>

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

<span data-ttu-id="4babb-112">Per altre informazioni sull'assegnazione dei criteri, [vedere](assign-policies.md)qui.</span><span class="sxs-lookup"><span data-stu-id="4babb-112">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="4babb-113">Come gestire i criteri</span><span class="sxs-lookup"><span data-stu-id="4babb-113">How to manage policies</span></span>

<span data-ttu-id="4babb-114">I criteri vengono gestiti con l'interfaccia di amministrazione di Microsoft Teams [o con PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="4babb-114">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="4babb-115">Ad esempio, un criterio di configurazione delle app può consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra dell'app di Teams.</span><span class="sxs-lookup"><span data-stu-id="4babb-115">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="4babb-116">Questi criteri sono configurati nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="4babb-116">These policies are configured in the Teams admin center.</span></span>

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

<span data-ttu-id="4babb-118">Inoltre, un criterio di riunione può essere usato per controllare le impostazioni audio e video nelle riunioni di Teams, ad esempio trascrizioni, registrazioni cloud e audio/video IP.</span><span class="sxs-lookup"><span data-stu-id="4babb-118">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Screenshot del criterio di riunione.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="4babb-120">Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="4babb-120">Teams for Education</span></span>

<span data-ttu-id="4babb-121">È anche possibile usare la procedura [guidata dei criteri di Teams for Education](easy-policy-setup-edu.md) per configurare e gestire facilmente i criteri per l'ambiente di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="4babb-121">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Screenshot della procedura guidata per i criteri di Teams for Education.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="4babb-123">Tipi di criteri</span><span class="sxs-lookup"><span data-stu-id="4babb-123">Types of policies</span></span>

<span data-ttu-id="4babb-124">I seguenti criteri possono essere gestiti con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4babb-124">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="4babb-125">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="4babb-125">Policy type</span></span> | <span data-ttu-id="4babb-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4babb-126">Description</span></span>
------------|------------
[<span data-ttu-id="4babb-127">Pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="4babb-127">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="4babb-128">Un pacchetto di criteri in Microsoft Teams è una raccolta di impostazioni e criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4babb-128">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="4babb-129">Criteri riunione</span><span class="sxs-lookup"><span data-stu-id="4babb-129">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="4babb-130">I criteri di riunione vengono utilizzati per controllare le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4babb-130">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="4babb-131">I criteri delle riunioni includono gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="4babb-131">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="4babb-132">- Criteri audio e video</span><span class="sxs-lookup"><span data-stu-id="4babb-132">- Audio and video policies</span></span><br> <span data-ttu-id="4babb-133">- Criteri di condivisione del contenuto e dello schermo</span><span class="sxs-lookup"><span data-stu-id="4babb-133">- Content and screen sharing policies</span></span><br> <span data-ttu-id="4babb-134">- Partecipanti, guest e criteri di accesso</span><span class="sxs-lookup"><span data-stu-id="4babb-134">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="4babb-135">- Criteri generali</span><span class="sxs-lookup"><span data-stu-id="4babb-135">- General policies</span></span>
[<span data-ttu-id="4babb-136">Criteri per chiamate e voce</span><span class="sxs-lookup"><span data-stu-id="4babb-136">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="4babb-137">I criteri vocali e di chiamata gestiscono queste impostazioni tramite team come chiamate di emergenza, instradamento chiamate e ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="4babb-137">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="4babb-138">Criteri delle app</span><span class="sxs-lookup"><span data-stu-id="4babb-138">App policies</span></span>](app-policies.md)| <span data-ttu-id="4babb-139">I criteri delle app vengono usati per controllare le applicazioni in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4babb-139">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="4babb-140">Gli amministratori possono consentire o bloccare le app che gli utenti possono installare, aggiungere applicazioni alla barra dell'app teams di un utente e installare l'applicazione per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4babb-140">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="4babb-141">Criteri di messaggistica</span><span class="sxs-lookup"><span data-stu-id="4babb-141">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="4babb-142">I criteri di messaggistica controllano la disponibilità delle funzionalità di chat e canali.</span><span class="sxs-lookup"><span data-stu-id="4babb-142">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4babb-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4babb-143">Related topics</span></span>

* [<span data-ttu-id="4babb-144">Gestire i criteri di feedback in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4babb-144">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="4babb-145">Gestire i criteri dei team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4babb-145">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="4babb-146">Configurare gli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4babb-146">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="4babb-147">Criteri e pacchetti di criteri di Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="4babb-147">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
