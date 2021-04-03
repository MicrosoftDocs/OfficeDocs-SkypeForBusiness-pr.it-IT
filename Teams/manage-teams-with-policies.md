---
title: Gestire Teams con i criteri
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni dettagliate sui criteri di Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574185"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="ad526-103">Gestire Teams con i criteri</span><span class="sxs-lookup"><span data-stu-id="ad526-103">Manage Teams with policies</span></span>

<span data-ttu-id="ad526-104">I criteri sono una parte importante della gestione di Teams.</span><span class="sxs-lookup"><span data-stu-id="ad526-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="ad526-105">Usare questo articolo per esplorare come usare i criteri a vantaggio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad526-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="ad526-106">Per cosa si usano i criteri</span><span class="sxs-lookup"><span data-stu-id="ad526-106">What you use policies for</span></span>

<span data-ttu-id="ad526-107">I criteri vengono usati per eseguire molte attività nell'organizzazione in aree diverse, ad esempio messaggistica, riunioni e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ad526-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="ad526-108">Alcune delle operazioni che è possibile eseguire includono consentire agli utenti di pianificare riunioni in un canale di Teams, consentire agli utenti di modificare i messaggi inviati e controllare se gli utenti possono aggiungere app alla barra dell'app Teams.</span><span class="sxs-lookup"><span data-stu-id="ad526-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="ad526-109">Come assegnare criteri</span><span class="sxs-lookup"><span data-stu-id="ad526-109">How to assign policies</span></span>

<span data-ttu-id="ad526-110">I criteri possono essere assegnati in diversi modi, a seconda delle operazioni che l'organizzazione sta cercando di eseguire.</span><span class="sxs-lookup"><span data-stu-id="ad526-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="ad526-111">È possibile effettuare e visualizzare le attività nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="ad526-111">You can make and view assignments in the Teams admin center.</span></span>

![Screenshot dell'assegnazione di Criteri di gruppo.](media/group-policy-assignment.png)

<span data-ttu-id="ad526-113">Per altre informazioni sull'assegnazione di [criteri, vedere](policy-assignment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ad526-113">Learn more about assigning policies [here](policy-assignment-overview.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="ad526-114">Come gestire i criteri</span><span class="sxs-lookup"><span data-stu-id="ad526-114">How to manage policies</span></span>

<span data-ttu-id="ad526-115">I criteri vengono gestiti con l'interfaccia di amministrazione di Microsoft Teams [o con PowerShell.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="ad526-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="ad526-116">Ad esempio, i criteri di configurazione delle app possono consentire agli utenti di caricare app personalizzate, installare app per conto degli utenti e aggiungere app alla barra dell'app Teams.</span><span class="sxs-lookup"><span data-stu-id="ad526-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="ad526-117">Questi criteri sono configurati nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="ad526-117">These policies are configured in the Teams admin center.</span></span>

![Screenshot dei criteri di configurazione delle app.](media/app-setup-policy.png)

<span data-ttu-id="ad526-119">Inoltre, i criteri di riunione possono essere usati per controllare le impostazioni audio e video nelle riunioni di Teams, ad esempio trascrizioni, registrazioni cloud e audio/video IP.</span><span class="sxs-lookup"><span data-stu-id="ad526-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Screenshot dei criteri della riunione.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="ad526-121">Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="ad526-121">Teams for Education</span></span>

<span data-ttu-id="ad526-122">È anche possibile usare la procedura [guidata dei criteri di Teams for Education](easy-policy-setup-edu.md) per configurare e gestire facilmente i criteri per l'ambiente di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="ad526-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Screenshot della procedura guidata dei criteri di Teams per l'istruzione.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="ad526-124">Tipi di criteri</span><span class="sxs-lookup"><span data-stu-id="ad526-124">Types of policies</span></span>

<span data-ttu-id="ad526-125">I criteri seguenti possono essere gestiti con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad526-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="ad526-126">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="ad526-126">Policy type</span></span> | <span data-ttu-id="ad526-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad526-127">Description</span></span>
------------|------------
[<span data-ttu-id="ad526-128">Pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="ad526-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="ad526-129">Un pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad526-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="ad526-130">Criteri riunione</span><span class="sxs-lookup"><span data-stu-id="ad526-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="ad526-131">I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alla riunione per le riunioni pianificate dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad526-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="ad526-132">I criteri delle riunioni includono gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="ad526-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="ad526-133">- Criteri audio e video</span><span class="sxs-lookup"><span data-stu-id="ad526-133">- Audio and video policies</span></span><br> <span data-ttu-id="ad526-134">- Criteri di condivisione del contenuto e dello schermo</span><span class="sxs-lookup"><span data-stu-id="ad526-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="ad526-135">- Partecipanti, guest e criteri di accesso</span><span class="sxs-lookup"><span data-stu-id="ad526-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="ad526-136">- Criteri generali</span><span class="sxs-lookup"><span data-stu-id="ad526-136">- General policies</span></span>
[<span data-ttu-id="ad526-137">Criteri vocali e chiamate</span><span class="sxs-lookup"><span data-stu-id="ad526-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="ad526-138">I criteri vocali e chiamate gestiscono queste impostazioni tramite team come chiamate di emergenza, routing delle chiamate e ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="ad526-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="ad526-139">Criteri delle app</span><span class="sxs-lookup"><span data-stu-id="ad526-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="ad526-140">I criteri delle app vengono usati per controllare le applicazioni in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad526-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="ad526-141">Gli amministratori possono consentire o bloccare le app che gli utenti possono installare, aggiungere applicazioni alla barra dell'app Teams di un utente e installare l'applicazione per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ad526-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="ad526-142">Criteri di messaggistica</span><span class="sxs-lookup"><span data-stu-id="ad526-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="ad526-143">I criteri di messaggistica controllano la disponibilità delle funzionalità di chat e canali.</span><span class="sxs-lookup"><span data-stu-id="ad526-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad526-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ad526-144">Related topics</span></span>

* [<span data-ttu-id="ad526-145">Assegnare criteri in Teams - Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="ad526-145">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
* [<span data-ttu-id="ad526-146">Gestire i criteri di feedback in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad526-146">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="ad526-147">Gestire i criteri dei team in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad526-147">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="ad526-148">Configurare gli eventi live in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad526-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="ad526-149">Criteri e pacchetti di criteri di Teams per l'istruzione</span><span class="sxs-lookup"><span data-stu-id="ad526-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)