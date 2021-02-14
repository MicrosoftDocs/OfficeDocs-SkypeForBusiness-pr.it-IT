---
title: Configurare la condivisione desktop in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come configurare un criterio di riunione per consentire agli utenti di condividere i propri desktop nelle chat o nelle riunioni di Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75e540de7e40206f0b1dd15e26adc62d6f6baa7
ms.sourcegitcommit: d27b97f012d0cb3f1690d3673d50bbaa0caae16f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47652474"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="df0bc-103">Configurare la condivisione desktop in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df0bc-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="df0bc-104">La condivisione del desktop consente agli utenti di presentare una schermata o un'app durante una riunione o in una chat.</span><span class="sxs-lookup"><span data-stu-id="df0bc-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="df0bc-105">Gli amministratori possono configurare la condivisione dello schermo in Microsoft Teams per consentire agli utenti di condividere l'intero schermo, un'app o un file.</span><span class="sxs-lookup"><span data-stu-id="df0bc-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="df0bc-106">È possibile consentire agli utenti di fornire o richiedere il controllo, consentire la condivisione di PowerPoint, aggiungere una lavagna e consentire le note condivise.</span><span class="sxs-lookup"><span data-stu-id="df0bc-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="df0bc-107">Inoltre, è possibile configurare se consentire agli utenti esterni o anonimi di richiedere il controllo dello schermo condiviso.</span><span class="sxs-lookup"><span data-stu-id="df0bc-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="df0bc-108">I partecipanti esterni nelle riunioni di Teams possono essere classificati come segue:</span><span class="sxs-lookup"><span data-stu-id="df0bc-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="df0bc-109">Utente anonimo</span><span class="sxs-lookup"><span data-stu-id="df0bc-109">Anonymous user</span></span>
- <span data-ttu-id="df0bc-110">Utenti guest</span><span class="sxs-lookup"><span data-stu-id="df0bc-110">Guest users</span></span>
- <span data-ttu-id="df0bc-111">Utente B2B</span><span class="sxs-lookup"><span data-stu-id="df0bc-111">B2B user</span></span>
- <span data-ttu-id="df0bc-112">Utente federato</span><span class="sxs-lookup"><span data-stu-id="df0bc-112">Federated user</span></span>

<span data-ttu-id="df0bc-113">Per configurare la condivisione dello schermo, creare un nuovo criterio riunioni e assegnarlo agli utenti da gestire.</span><span class="sxs-lookup"><span data-stu-id="df0bc-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="df0bc-114">**Nell'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="df0bc-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="df0bc-115">Selezionare **Riunioni** > **Criteri riunione**.</span><span class="sxs-lookup"><span data-stu-id="df0bc-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![Criteri riunione selezionati](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="df0bc-117">Nella pagina **Criteri riunione** selezionare **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="df0bc-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![Messaggio criteri riunione](media/addMeeting.png)

3. <span data-ttu-id="df0bc-119">Assegnare un titolo univoco al criterio e immettere una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="df0bc-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="df0bc-120">In **Condivisione di contenuti**, scegliere una **Modalità di condivisione dello schermo** nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="df0bc-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="df0bc-121">**Schermo intero**: consente agli utenti di condividere l'intero desktop.</span><span class="sxs-lookup"><span data-stu-id="df0bc-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="df0bc-122">**Applicazione singola**: consente agli utenti di limitare la condivisione dello schermo a una singola applicazione attiva.</span><span class="sxs-lookup"><span data-stu-id="df0bc-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="df0bc-123">**Disabilitata**: disabilita la condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="df0bc-123">**Disabled** – Turns off screen sharing.</span></span>

    ![Opzioni della modalità di condivisione](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="df0bc-125">Non è necessario abilitare il criterio di chiamata per consentire agli utenti di usare la condivisione dello schermo dalla chat.</span><span class="sxs-lookup"><span data-stu-id="df0bc-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="df0bc-126">Tuttavia, l'audio viene disattivato finché l'audio non viene riattivato.</span><span class="sxs-lookup"><span data-stu-id="df0bc-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="df0bc-127">Inoltre, l'utente che condivide lo schermo può fare clic **su Aggiungi audio** per abilitare l'audio.</span><span class="sxs-lookup"><span data-stu-id="df0bc-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="df0bc-128">Se il criterio di chiamata è disabilitato, gli utenti non saranno in grado di aggiungere audio alla condivisione dello schermo da una sessione di chat.</span><span class="sxs-lookup"><span data-stu-id="df0bc-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="df0bc-129">Abilitare o disabilitare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df0bc-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="df0bc-130">**Consentire a un partecipante di concedere o richiedere il controllo**: consente ai membri del team di concedere o richiedere il controllo dell'applicazione o del desktop del relatore.</span><span class="sxs-lookup"><span data-stu-id="df0bc-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="df0bc-131">**Consentire a un partecipante esterno di concedere o richiedere il controllo.** Si tratta di un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="df0bc-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="df0bc-132">Se un'organizzazione ha impostato questa opzione per un utente, non controlla cosa possono fare i partecipanti esterni, indipendentemente dall'impostazione configurata dall'organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="df0bc-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="df0bc-133">Questo parametro controlla se i partecipanti esterni possono ricevere o richiedere il controllo dello schermo del relatore, a seconda delle impostazioni configurate dal relatore nei criteri di riunione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df0bc-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="df0bc-134">**Consentire la condivisione di PowerPoint**: consente di creare riunioni nelle quali è possibile caricare e condividere le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="df0bc-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="df0bc-135">**Consentire la lavagna**: consente agli utenti di condividere una lavagna.</span><span class="sxs-lookup"><span data-stu-id="df0bc-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="df0bc-136">**Consentire le note condivise**: consente agli utenti di creare note condivise.</span><span class="sxs-lookup"><span data-stu-id="df0bc-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="df0bc-137">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="df0bc-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="df0bc-138">Usare PowerShell per configurare il desktop condiviso</span><span class="sxs-lookup"><span data-stu-id="df0bc-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="df0bc-139">Inoltre, è possibile usare il cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per controllare la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="df0bc-139">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="df0bc-140">Impostare i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="df0bc-140">Set the following parameters:</span></span>

- <span data-ttu-id="df0bc-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df0bc-141">Description</span></span>
- <span data-ttu-id="df0bc-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="df0bc-142">ScreenSharingMode</span></span>
- <span data-ttu-id="df0bc-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="df0bc-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="df0bc-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="df0bc-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="df0bc-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="df0bc-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="df0bc-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="df0bc-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="df0bc-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="df0bc-147">AllowWhiteboard</span></span>
- <span data-ttu-id="df0bc-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="df0bc-148">AllowSharedNotes</span></span>

<span data-ttu-id="df0bc-149">[Altre informazioni sull'utilizzo del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="df0bc-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>
