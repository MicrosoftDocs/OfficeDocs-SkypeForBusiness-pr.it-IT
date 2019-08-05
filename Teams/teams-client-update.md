---
title: Aggiornamenti di Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Informazioni sulla modalità di aggiornamento del client desktop teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5280e03e316dfcde3bda9b62520fa513f3157a
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "36184762"
---
# <a name="teams-update-process"></a><span data-ttu-id="0999e-103">Processo di aggiornamento di Teams</span><span class="sxs-lookup"><span data-stu-id="0999e-103">Teams update process</span></span>

<span data-ttu-id="0999e-104">L'app teams Web viene aggiornata settimanalmente.</span><span class="sxs-lookup"><span data-stu-id="0999e-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="0999e-105">Gli aggiornamenti del client desktop di teams vengono rilasciati ogni due settimane dopo un rigoroso test e convalida interni tramite il programma di adozione della tecnologia (TAP).</span><span class="sxs-lookup"><span data-stu-id="0999e-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="0999e-106">Questo avviene di solito in un martedì.</span><span class="sxs-lookup"><span data-stu-id="0999e-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="0999e-107">Se è necessario un aggiornamento critico, teams ignorerà questa programmazione e rilascerà l'aggiornamento non appena sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="0999e-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="0999e-108">Il client desktop si aggiorna automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0999e-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="0999e-109">Teams verifica la disponibilità di aggiornamenti ogni poche ore dietro le quinte, la Scarica e quindi attende che il computer sia inattivo prima di installare l'aggiornamento in modo invisibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="0999e-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="0999e-110">Gli utenti possono anche scaricare gli aggiornamenti manualmente facendo clic su **Controlla aggiornamenti** nel menu a discesa **profilo** nell'angolo in alto a destra dell'app.</span><span class="sxs-lookup"><span data-stu-id="0999e-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="0999e-111">Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.</span><span class="sxs-lookup"><span data-stu-id="0999e-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="0999e-112">Gli utenti devono essere connessi per l'accesso agli aggiornamenti da scaricare.</span><span class="sxs-lookup"><span data-stu-id="0999e-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="0999e-113">A partire dal 9 luglio 2019, gli aggiornamenti del client teams usano una larghezza di banda di rete significativamente inferiore durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0999e-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="0999e-114">Questa opzione è attivata per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.</span><span class="sxs-lookup"><span data-stu-id="0999e-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="0999e-115">Informazioni sugli aggiornamenti di Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="0999e-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="0999e-116">Per impostazione predefinita, teams viene installato con le nuove installazioni di Office 365 ProPlus, come descritto in [distribuire Microsoft teams con office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="0999e-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="0999e-117">Teams segue il proprio processo di aggiornamento come descritto sopra e non il processo di aggiornamento per le altre app di Office, come Word ed Excel.</span><span class="sxs-lookup"><span data-stu-id="0999e-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="0999e-118">Per altre informazioni, vedere [Panoramica dei canali di aggiornamento per Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="0999e-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="0999e-119">Informazioni sugli aggiornamenti di teams su VDI</span><span class="sxs-lookup"><span data-stu-id="0999e-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="0999e-120">I client teams su Virtual Desktop Infrastructure (VDI) non vengono aggiornati automaticamente come non sono i client di team non VDI.</span><span class="sxs-lookup"><span data-stu-id="0999e-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="0999e-121">È necessario aggiornare l'immagine della VM installando un nuovo MSI, come descritto nelle istruzioni per [installare teams in VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="0999e-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="0999e-122">Devi disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="0999e-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="0999e-123">Gli amministratori possono distribuire gli aggiornamenti invece dell'aggiornamento automatico dei team?</span><span class="sxs-lookup"><span data-stu-id="0999e-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="0999e-124">Teams non dà agli amministratori la possibilità di distribuire gli aggiornamenti attraverso qualsiasi meccanismo di recapito.</span><span class="sxs-lookup"><span data-stu-id="0999e-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
