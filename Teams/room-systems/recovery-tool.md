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
ms.collection: M365-voice
localization_priority: Normal
description: Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.
ms.openlocfilehash: aded92fac90f20246444419bff19415922175856
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775206"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="cfabe-103">Usare lo strumento di ripristino di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="cfabe-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="cfabe-104">Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.</span><span class="sxs-lookup"><span data-stu-id="cfabe-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="cfabe-105">Si utilizzerebbe questo strumento quando la console Microsoft teams Rooms Mostra un errore "configurazione di sistema non aggiornata".</span><span class="sxs-lookup"><span data-stu-id="cfabe-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="cfabe-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="cfabe-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="cfabe-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cfabe-107">Prerequisites</span></span>

<span data-ttu-id="cfabe-108">Scaricare il pacchetto di installazione più recente di [Microsoft teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrarlo in una Memory Stick USB o in una condivisione di rete accessibile al dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="cfabe-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="cfabe-109">Potrebbe essere necessario installare anche [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="cfabe-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="cfabe-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="cfabe-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="cfabe-111">Verificare la versione di Windows</span><span class="sxs-lookup"><span data-stu-id="cfabe-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="cfabe-112">Accedere a un account di amministratore accedendo a **impostazioni> impostazione di Windows> l'accesso di amministratore** dal dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="cfabe-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="cfabe-113">Questa opzione consente di accedere alla schermata di accesso.</span><span class="sxs-lookup"><span data-stu-id="cfabe-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="cfabe-114">Accedere a un account di amministratore, `admin` con la password `sfb`dell'account di amministratore predefinito.</span><span class="sxs-lookup"><span data-stu-id="cfabe-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="cfabe-115">Fare clic sul menu Start e digitare `winver.exe` nella casella di ricerca e fare clic su \**Esegui comando* nel risultato.</span><span class="sxs-lookup"><span data-stu-id="cfabe-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="cfabe-116">Prendere nota del numero dopo ' versione ' nella seconda riga del riquadro delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="cfabe-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="cfabe-117">Se la versione visualizzata è 1607 o precedente, seguire i passaggi descritti in <a href="#Windows-up">aggiornare le finestre prima</a> di eseguire i passaggi di ripristino prima di procedere con i passaggi di <a href="#Perform">ripristino</a> .</span><span class="sxs-lookup"><span data-stu-id="cfabe-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="cfabe-118">Se la versione visualizzata è maggiore di 1607, seguire solo la procedura descritta in <a href="#Perform">eseguire un ripristino</a>.</span><span class="sxs-lookup"><span data-stu-id="cfabe-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="cfabe-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="cfabe-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="cfabe-120">Aggiornare Windows prima del ripristino (se necessario)</span><span class="sxs-lookup"><span data-stu-id="cfabe-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="cfabe-121">Durante l'accesso come utente di amministratore, avviare un prompt di PowerShell con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cfabe-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="cfabe-122">Eseguire il comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="cfabe-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="cfabe-123">Eseguire Windows Update e installare l'aggiornamento per Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="cfabe-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="cfabe-124">Dopo che l'aggiornamento a 1709 è stato completato, accedere all'account di amministratore e installare [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="cfabe-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="cfabe-125">L'aggiornamento può essere eseguito dal collegamento o tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="cfabe-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="cfabe-126">Come passaggio facoltativo, installare gli eventuali aggiornamenti aggiuntivi disponibili in Windows Update.</span><span class="sxs-lookup"><span data-stu-id="cfabe-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="cfabe-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="cfabe-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="cfabe-128">Eseguire un ripristino</span><span class="sxs-lookup"><span data-stu-id="cfabe-128">Perform a recovery</span></span>

1. <span data-ttu-id="cfabe-129">Accedere all'account di amministratore nel dispositivo Microsoft teams Rooms e avviare un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="cfabe-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="cfabe-130">Verificare dal dispositivo Microsoft teams Rooms che si è in grado di accedere `RecoveryTool.ps1` al file, incluso nei file estratti dal pacchetto di installazione di Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="cfabe-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="cfabe-131">Il kit può essere trovato nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="cfabe-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="cfabe-132">Eseguire il comando `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="cfabe-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="cfabe-133">Quando richiesto dall'opzione `1:"Repair System"`di selezione dello script.</span><span class="sxs-lookup"><span data-stu-id="cfabe-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="cfabe-134">Al termine, riavviare il dispositivo Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="cfabe-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="cfabe-135">Verrà riavviato automaticamente e verrà recuperato completamente la seconda volta.</span><span class="sxs-lookup"><span data-stu-id="cfabe-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="cfabe-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="cfabe-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="cfabe-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfabe-137">See also</span></span>
 
[<span data-ttu-id="cfabe-138">Guida di Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="cfabe-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="cfabe-139">Gestire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cfabe-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
