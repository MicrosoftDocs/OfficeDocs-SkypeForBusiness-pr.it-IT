---
title: Usare lo strumento Microsoft Teams Rooms ripristino
ms.author: dstrome
author: dstrome
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
description: Questo articolo illustra come usare lo strumento di ripristino per Microsoft Teams Rooms, che è possibile usare per portare un sistema non aggiornato in uno stato supportato.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117494"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="27bee-103">Usare lo strumento Microsoft Teams Rooms ripristino</span><span class="sxs-lookup"><span data-stu-id="27bee-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="27bee-104">Questo articolo illustra come usare lo strumento di ripristino per Microsoft Teams Rooms, che è possibile usare per portare un sistema non aggiornato in uno stato supportato.</span><span class="sxs-lookup"><span data-stu-id="27bee-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="27bee-105">Questo strumento deve essere applicato quando nella console di Microsoft Teams Rooms viene visualizzato un errore "Configurazione di sistema non aggiornata" o prima di eseguire un ripristino factory con un [pulsante di comando.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="27bee-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27bee-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="27bee-106">Prerequisites</span></span>

<span data-ttu-id="27bee-107">Scaricare il pacchetto [Microsoft Teams Rooms di installazione](https://go.microsoft.com/fwlink/?linkid=851168) più recente ed estrarlo in una memory stick USB o in una condivisione di rete accessibile al Microsoft Teams Rooms dispositivo.</span><span class="sxs-lookup"><span data-stu-id="27bee-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="27bee-108">L'estrazione dei file dal file MSI può essere eseguita in molti modi.</span><span class="sxs-lookup"><span data-stu-id="27bee-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="27bee-109">Qualsiasi meccanismo che estrae tutti i file e mantiene la struttura della directory è accettabile.</span><span class="sxs-lookup"><span data-stu-id="27bee-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="27bee-110">Uno di questi modi è usare il comando dove rappresenta il percorso completo del pacchetto di installazione di Microsoft Teams Room e rappresenta il percorso completo della cartella in cui si desidera estrarre i `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` file.</span><span class="sxs-lookup"><span data-stu-id="27bee-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="27bee-111">Esecuzione dello strumento</span><span class="sxs-lookup"><span data-stu-id="27bee-111">Running the tool</span></span>

1) <span data-ttu-id="27bee-112">Accedere all'account di amministratore nel dispositivo Microsoft Teams Rooms e avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="27bee-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="27bee-113">Verificare dal dispositivo Microsoft Teams Rooms che sia possibile accedere a , che è incluso nei file estratti dal pacchetto `RecoveryTool.ps1 file` Microsoft Teams Rooms di installazione.</span><span class="sxs-lookup"><span data-stu-id="27bee-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="27bee-114">Il kit è disponibile nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="27bee-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="27bee-115">Eseguire `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .</span><span class="sxs-lookup"><span data-stu-id="27bee-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="27bee-116">Per eseguire un ripristino in fabbrica:</span><span class="sxs-lookup"><span data-stu-id="27bee-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="27bee-117">Quando richiesto dallo script, selezionare l'opzione 2: **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="27bee-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="27bee-118">Se BitLocker è attivata, seguire le istruzioni fornite alla fine dell'output dello script per disabilitarlo.</span><span class="sxs-lookup"><span data-stu-id="27bee-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="27bee-119">Eseguire il ripristino in fabbrica.</span><span class="sxs-lookup"><span data-stu-id="27bee-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="27bee-120">Aprire **l'app Impostazioni** e selezionare **Aggiorna & sicurezza**</span><span class="sxs-lookup"><span data-stu-id="27bee-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="27bee-121">Passare alla **scheda** Ripristino.</span><span class="sxs-lookup"><span data-stu-id="27bee-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="27bee-122">Sotto **Reimposta questo PC,** seleziona **Inizia**</span><span class="sxs-lookup"><span data-stu-id="27bee-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="27bee-123">Seleziona **Rimuovi tutto,** quindi **Avanti e** **Reimposta**</span><span class="sxs-lookup"><span data-stu-id="27bee-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="27bee-124">Il Microsoft Teams Rooms può diventare inutilizzabile se l'opzione Mantieni i file personali - Rimuove app e **impostazioni,** ma mantiene i file personali è selezionata durante il processo di Windows reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="27bee-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="27bee-125">Non selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="27bee-125">Do not select this option.</span></span>
      5. <span data-ttu-id="27bee-126">Il sistema verrà riavviato più volte.</span><span class="sxs-lookup"><span data-stu-id="27bee-126">The system will reboot multiple times.</span></span> <span data-ttu-id="27bee-127">Al termine del ripristino, il sistema si trova nella schermata Windows "Esperienza fuori campo" (OOBE).</span><span class="sxs-lookup"><span data-stu-id="27bee-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="27bee-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27bee-128">See also</span></span>

[<span data-ttu-id="27bee-129">Microsoft Teams Rooms guida</span><span class="sxs-lookup"><span data-stu-id="27bee-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

<span data-ttu-id="27bee-130">[Gestire Microsoft Teams Rooms](rooms-manage.md).</span><span class="sxs-lookup"><span data-stu-id="27bee-130">[Manage Microsoft Teams Rooms](rooms-manage.md)</span></span>