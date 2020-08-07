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
ms.openlocfilehash: 857c9c4d830cb3264a83a41b555d26ee004751de
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581747"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="42f50-103">Configurare la condivisione desktop in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42f50-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="42f50-104">La condivisione del desktop consente agli utenti di presentare una schermata o un'app durante una riunione o in una chat.</span><span class="sxs-lookup"><span data-stu-id="42f50-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="42f50-105">Gli amministratori possono configurare la condivisione dello schermo in Microsoft Teams per consentire agli utenti di condividere l'intero schermo, un'app o un file.</span><span class="sxs-lookup"><span data-stu-id="42f50-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="42f50-106">È possibile consentire agli utenti di fornire o richiedere il controllo, consentire la condivisione di PowerPoint, aggiungere una lavagna e consentire le note condivise.</span><span class="sxs-lookup"><span data-stu-id="42f50-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="42f50-107">Inoltre, è possibile configurare se consentire agli utenti esterni o anonimi di richiedere il controllo dello schermo condiviso.</span><span class="sxs-lookup"><span data-stu-id="42f50-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="42f50-108">Per configurare la condivisione dello schermo, creare un nuovo criterio riunioni e assegnarlo agli utenti da gestire.</span><span class="sxs-lookup"><span data-stu-id="42f50-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="42f50-109">**Nell'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="42f50-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="42f50-110">Selezionare **Riunioni** > **Criteri riunione**.</span><span class="sxs-lookup"><span data-stu-id="42f50-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Screenshot che mostra Criteri riunione selezionato](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="42f50-112">Nella pagina **Criteri riunione**, selezionare **Nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="42f50-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Screenshot che mostra il messaggio di Criteri riunione](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="42f50-114">Assegnare un titolo univoco al criterio e immettere una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="42f50-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="42f50-115">In **Condivisione di contenuti**, scegliere una **Modalità di condivisione dello schermo** nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="42f50-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="42f50-116">**Schermo intero**: consente agli utenti di condividere l'intero desktop.</span><span class="sxs-lookup"><span data-stu-id="42f50-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="42f50-117">**Applicazione singola**: consente agli utenti di limitare la condivisione dello schermo a una singola applicazione attiva.</span><span class="sxs-lookup"><span data-stu-id="42f50-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="42f50-118">**Disabilitata**: disabilita la condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="42f50-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Screenshot che mostra le opzioni di condivisione dello schermo](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="42f50-120">Abilitare o disabilitare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42f50-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="42f50-121">**Consentire a un partecipante di concedere o richiedere il controllo**: consente ai membri del team di concedere o richiedere il controllo dell'applicazione o del desktop del relatore.</span><span class="sxs-lookup"><span data-stu-id="42f50-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="42f50-122">**Consentire a un partecipante esterno di dare o richiedere il controllo** , ovvero un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="42f50-122">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="42f50-123">Indipendentemente dal modo in cui l'organizzatore della riunione ha impostato, l'organizzazione ha impostato questo set per un utente non controlla quali partecipanti esterni possono eseguire.</span><span class="sxs-lookup"><span data-stu-id="42f50-123">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="42f50-124">Questo parametro controlla se i partecipanti esterni possono avere il controllo o richiedere il controllo dello schermo del condivisore, a seconda di quello che il condivisore ha impostato nei criteri della riunione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="42f50-124">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="42f50-125">**Consentire la condivisione di PowerPoint**: consente di creare riunioni nelle quali è possibile caricare e condividere le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="42f50-125">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="42f50-126">**Consentire la lavagna**: consente agli utenti di condividere una lavagna.</span><span class="sxs-lookup"><span data-stu-id="42f50-126">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="42f50-127">**Consentire le note condivise**: consente agli utenti di creare note condivise.</span><span class="sxs-lookup"><span data-stu-id="42f50-127">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="42f50-128">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42f50-128">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="42f50-129">Usare PowerShell per configurare il desktop condiviso</span><span class="sxs-lookup"><span data-stu-id="42f50-129">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="42f50-130">Inoltre, è possibile usare il cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per controllare la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="42f50-130">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="42f50-131">Impostare i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="42f50-131">Set the following parameters:</span></span>

- <span data-ttu-id="42f50-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42f50-132">Description</span></span>
- <span data-ttu-id="42f50-133">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="42f50-133">ScreenSharingMode</span></span>
- <span data-ttu-id="42f50-134">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="42f50-134">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="42f50-135">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="42f50-135">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="42f50-136">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="42f50-136">AllowPowerPointSharing</span></span>
- <span data-ttu-id="42f50-137">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="42f50-137">AllowWhiteboard</span></span>
- <span data-ttu-id="42f50-138">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="42f50-138">AllowSharedNotes</span></span>

<span data-ttu-id="42f50-139">[Altre informazioni sull'utilizzo del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="42f50-139">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

