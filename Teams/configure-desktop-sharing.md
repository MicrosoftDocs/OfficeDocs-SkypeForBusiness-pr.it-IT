---
title: Configurare la condivisione desktop in Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Configurare un criterio di riunione per consentire agli utenti di condividere i loro desktop in chat o riunioni di Teams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f36804fc4d7c28f08ca383ddb09f22ee52f804e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236934"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="d7fcd-103">Configurare la condivisione desktop in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7fcd-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="d7fcd-104">Condivisione desktop consente agli utenti di presentare una schermata o un'app durante una riunione o una chat.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="d7fcd-105">Gli amministratori possono configurare la condivisione dello schermo in Microsoft teams per consentire agli utenti di condividere un'intera schermata, un'app o un file.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="d7fcd-106">Puoi consentire agli utenti di dare o richiedere il controllo, concedere la condivisione di PowerPoint, aggiungere una lavagna e consentire le note condivise.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="d7fcd-107">È anche possibile specificare se gli utenti anonimi o esterni possono richiedere il controllo della schermata condivisa.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="d7fcd-108">Per configurare la condivisione dello schermo, è possibile creare un nuovo criterio per le riunioni e assegnarlo agli utenti che si vuole gestire.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="d7fcd-109">**Nell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d7fcd-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d7fcd-110">Selezionare \*\*\*\* > **criteri riunione**riunioni.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Schermata che mostra i criteri riunione selezionati](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="d7fcd-112">Nella pagina **criteri riunione** selezionare **nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Schermata che mostra il messaggio criteri riunione](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="d7fcd-114">Assegnare un titolo univoco ai criteri e immettere una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="d7fcd-115">In **condivisione contenuto**scegliere una **modalità di condivisione dello schermo** nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="d7fcd-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="d7fcd-116">**Intero schermo** : consente agli utenti di condividere l'intero desktop.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="d7fcd-117">**Singola applicazione** : consente agli utenti di limitare la condivisione dello schermo a una singola applicazione attiva.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="d7fcd-118">**Disabled** -disattiva la condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Screenshot che mostra le opzioni della modalità di condivisione](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="d7fcd-120">Attivare o disattivare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7fcd-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="d7fcd-121">**Consentire a un partecipante di dare o richiedere il controllo** , consente ai membri del team di concedere o richiedere il controllo del desktop o dell'applicazione del relatore.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="d7fcd-122">**Consentire a un partecipante esterno di dare o richiedere il controllo** , consente agli utenti esterni (federati) di concedere o richiedere il controllo del desktop o dell'applicazione del relatore.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="d7fcd-123">**Consenti condivisione di PowerPoint** : consente agli utenti di creare riunioni che consentano la carica e la condivisione delle presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="d7fcd-124">**Consenti lavagna** : consente agli utenti di condividere una lavagna.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="d7fcd-125">**Consenti note condivise** : consente agli utenti di prendere note condivise.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="d7fcd-126">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="d7fcd-127">Usare PowerShell per configurare il desktop condiviso</span><span class="sxs-lookup"><span data-stu-id="d7fcd-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="d7fcd-128">Puoi anche usare il cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per controllare la condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="d7fcd-129">Impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7fcd-129">Set the following parameters:</span></span>

- <span data-ttu-id="d7fcd-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7fcd-130">Description</span></span>
- <span data-ttu-id="d7fcd-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="d7fcd-131">ScreenSharingMode</span></span>
- <span data-ttu-id="d7fcd-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d7fcd-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="d7fcd-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d7fcd-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="d7fcd-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="d7fcd-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="d7fcd-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="d7fcd-135">AllowWhiteboard</span></span>
- <span data-ttu-id="d7fcd-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="d7fcd-136">AllowSharedNotes</span></span>

<span data-ttu-id="d7fcd-137">[Altre informazioni sull'uso del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d7fcd-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

