---
title: Usare lo strumento di ripristino di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.
ms.openlocfilehash: bc35dc744dac5f04d537f023e790bc89c2c649d0
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675350"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="c811b-103">Usare lo strumento di ripristino di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c811b-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="c811b-104">Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.</span><span class="sxs-lookup"><span data-stu-id="c811b-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="c811b-105">Si utilizzerebbe questo strumento quando la console Microsoft teams Rooms Mostra un errore "configurazione di sistema non aggiornata".</span><span class="sxs-lookup"><span data-stu-id="c811b-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="c811b-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="c811b-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="c811b-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c811b-107">Prerequisites</span></span>

<span data-ttu-id="c811b-108">Scaricare il pacchetto di installazione più recente di [Microsoft teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrarlo in una Memory Stick USB o in una condivisione di rete accessibile al dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c811b-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="c811b-109">Potrebbe essere necessario installare anche [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="c811b-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="c811b-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="c811b-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="c811b-111">Verificare la versione di Windows</span><span class="sxs-lookup"><span data-stu-id="c811b-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="c811b-112">Accedere a un account di amministratore accedendo a **impostazioni> impostazione di Windows> l'accesso di amministratore** dal dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c811b-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="c811b-113">Questa opzione consente di accedere alla schermata di accesso.</span><span class="sxs-lookup"><span data-stu-id="c811b-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="c811b-114">Accedere a un account di amministratore, `admin` con la password `sfb`dell'account di amministratore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c811b-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="c811b-115">Fare clic sul menu Start e digitare `winver.exe` nella casella di ricerca e fare clic su \**Esegui comando* nel risultato.</span><span class="sxs-lookup"><span data-stu-id="c811b-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="c811b-116">Prendere nota del numero dopo ' versione ' nella seconda riga del riquadro delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="c811b-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="c811b-117">Se la versione visualizzata è 1607 o precedente, seguire i passaggi descritti in <a href="#Windows-up">aggiornare le finestre prima</a> di eseguire i passaggi di ripristino prima di procedere con i passaggi di <a href="#Perform">ripristino</a> .</span><span class="sxs-lookup"><span data-stu-id="c811b-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="c811b-118">Se la versione visualizzata è maggiore di 1607, seguire solo la procedura descritta in <a href="#Perform">eseguire un ripristino</a>.</span><span class="sxs-lookup"><span data-stu-id="c811b-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="c811b-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="c811b-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="c811b-120">Aggiornare Windows prima del ripristino (se necessario)</span><span class="sxs-lookup"><span data-stu-id="c811b-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="c811b-121">Durante l'accesso come utente di amministratore, avviare un prompt di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c811b-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="c811b-122">Eseguire il comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="c811b-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="c811b-123">Eseguire Windows Update e installare l'aggiornamento per Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="c811b-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="c811b-124">Dopo che l'aggiornamento a 1709 è stato completato, accedere all'account di amministratore e installare [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="c811b-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="c811b-125">L'aggiornamento può essere eseguito dal collegamento o tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="c811b-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="c811b-126">Come passaggio facoltativo, installare gli eventuali aggiornamenti aggiuntivi disponibili in Windows Update.</span><span class="sxs-lookup"><span data-stu-id="c811b-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="c811b-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="c811b-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="c811b-128">Eseguire un ripristino</span><span class="sxs-lookup"><span data-stu-id="c811b-128">Perform a recovery</span></span>

1. <span data-ttu-id="c811b-129">Accedere all'account di amministratore nel dispositivo Microsoft teams Rooms e avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c811b-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="c811b-130">Verificare dal dispositivo Microsoft teams Rooms che si è in grado di accedere `RecoveryTool.ps1` al file, incluso nei file estratti dal pacchetto di installazione di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c811b-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="c811b-131">Il kit può essere trovato nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="c811b-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="c811b-132">Eseguire il comando `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="c811b-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="c811b-133">Quando richiesto dall'opzione `1:"Repair System"`di selezione dello script.</span><span class="sxs-lookup"><span data-stu-id="c811b-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="c811b-134">Al termine, riavviare il dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="c811b-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="c811b-135">Verrà riavviato automaticamente e verrà recuperato completamente la seconda volta.</span><span class="sxs-lookup"><span data-stu-id="c811b-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="c811b-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="c811b-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="c811b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c811b-137">See also</span></span>
 
[<span data-ttu-id="c811b-138">Guida di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="c811b-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="c811b-139">Gestire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c811b-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
