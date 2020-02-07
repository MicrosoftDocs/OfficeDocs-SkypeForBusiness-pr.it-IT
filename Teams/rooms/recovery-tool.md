---
title: Usare lo strumento di ripristino di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.
ms.openlocfilehash: 452f5d9d15375bec7ac25c07c865add8a01b0345
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831178"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="73e15-103">Usare lo strumento di ripristino di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="73e15-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="73e15-104">Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.</span><span class="sxs-lookup"><span data-stu-id="73e15-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="73e15-105">Questo strumento deve essere applicato quando la console Microsoft teams Rooms Mostra un errore di "configurazione di sistema non aggiornata" oppure prima di eseguire un ripristino tramite pulsante Reimposta [Factory](https://docs.microsoft.com/microsoftteams/room-systems/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span><span class="sxs-lookup"><span data-stu-id="73e15-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/room-systems/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73e15-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="73e15-106">Prerequisites</span></span>

<span data-ttu-id="73e15-107">Scaricare il pacchetto di installazione più recente di [Microsoft teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrarlo in una Memory Stick USB o in una condivisione di rete accessibile al dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="73e15-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="73e15-108">L'estrazione dei file dall'MSI può essere eseguita con molti mezzi.</span><span class="sxs-lookup"><span data-stu-id="73e15-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="73e15-109">Qualsiasi meccanismo che estrae tutti i file e mantiene la struttura della directory è accettabile.</span><span class="sxs-lookup"><span data-stu-id="73e15-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="73e15-110">Uno di questi modi consiste nell'usare il `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` comando `PathToMsi` dove rappresenta il percorso completo del pacchetto di installazione della sala Microsoft teams e `PathToTarget` rappresenta il percorso completo della cartella a cui si vogliono estrarre i file.</span><span class="sxs-lookup"><span data-stu-id="73e15-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="73e15-111">Eseguire lo strumento</span><span class="sxs-lookup"><span data-stu-id="73e15-111">Running the tool</span></span>

1) <span data-ttu-id="73e15-112">Accedere all'account di amministratore nel dispositivo Microsoft teams Rooms e avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="73e15-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="73e15-113">Verificare dal dispositivo Microsoft teams Rooms che si è in grado di accedere `RecoveryTool.ps1 file`a, incluso nei file estratti dal pacchetto di installazione di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="73e15-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="73e15-114">Il kit può essere trovato nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="73e15-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="73e15-115">Esegui `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="73e15-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="73e15-116">Se si esegue un ripristino di fabbrica:</span><span class="sxs-lookup"><span data-stu-id="73e15-116">If you are performing a factory restore:</span></span>
   - <span data-ttu-id="73e15-117">Quando richiesto dallo script, selezionare l'opzione 2: **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="73e15-117">When prompted by the script select option 2: **Reset**.</span></span>
   - <span data-ttu-id="73e15-118">Se BitLocker è attivato, seguire le istruzioni fornite alla fine dell'output dello script per disabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="73e15-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   - <span data-ttu-id="73e15-119">Eseguire il ripristino di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="73e15-119">Perform the factory restore.</span></span>
      - <span data-ttu-id="73e15-120">Aprire l'app **Impostazioni** e selezionare **Aggiorna & sicurezza**</span><span class="sxs-lookup"><span data-stu-id="73e15-120">Open the **Settings** app, and select **Update & Security**</span></span>
      - <span data-ttu-id="73e15-121">Passare alla scheda **ripristino** .</span><span class="sxs-lookup"><span data-stu-id="73e15-121">Navigate to the **Recovery** tab.</span></span>
      - <span data-ttu-id="73e15-122">Sotto **Reimposta questo PC**selezionare **inizia**</span><span class="sxs-lookup"><span data-stu-id="73e15-122">Beneath **Reset this PC**, select **Get started**</span></span>
      - <span data-ttu-id="73e15-123">Selezionare **Rimuovi tutto**, quindi **Avanti** e **Reimposta**</span><span class="sxs-lookup"><span data-stu-id="73e15-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
      - <span data-ttu-id="73e15-124">Il sistema verrà riavviato più volte.</span><span class="sxs-lookup"><span data-stu-id="73e15-124">The system will reboot multiple times.</span></span> <span data-ttu-id="73e15-125">Al termine del ripristino, il sistema sarà nella schermata della configurazione guidata di Windows.</span><span class="sxs-lookup"><span data-stu-id="73e15-125">When the reset is complete, the system will be at the Windows OOBE screen.</span></span>
5) <span data-ttu-id="73e15-126">Se si sta riparando un sistema "fuori data":</span><span class="sxs-lookup"><span data-stu-id="73e15-126">If you are repairing an "out of date" system:</span></span>
    - <span data-ttu-id="73e15-127">Quando viene richiesto dallo script, selezionare l'opzione 1: **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="73e15-127">When prompted by the script select option 1: **Repair**.</span></span>
    - <span data-ttu-id="73e15-128">Al termine, riavviare il dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="73e15-128">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="73e15-129">Verrà riavviato automaticamente e verrà recuperato completamente la seconda volta.</span><span class="sxs-lookup"><span data-stu-id="73e15-129">It will reboot again automatically and come up fully recovered the second time.</span></span>

> [!NOTE]
> <span data-ttu-id="73e15-130">Si è verificato un problema noto in cui le sale di Microsoft teams possono diventare inutilizzabili se la funzione **Mantieni file-rimuove le app e le impostazioni, ma mantiene l'opzione file personali** selezionata durante il processo di ripristino di Windows.</span><span class="sxs-lookup"><span data-stu-id="73e15-130">There is a known issue where the Microsoft Teams Rooms can become unusable if the  **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="73e15-131">Non *usare questa* opzione.</span><span class="sxs-lookup"><span data-stu-id="73e15-131">Do *not* use this option.</span></span>

## <a name="see-also"></a><span data-ttu-id="73e15-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73e15-132">See also</span></span>

[<span data-ttu-id="73e15-133">Guida di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="73e15-133">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="73e15-134">Gestire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73e15-134">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
