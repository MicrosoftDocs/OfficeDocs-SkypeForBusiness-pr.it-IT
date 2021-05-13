---
title: Usare i file di log nella risoluzione dei Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informazioni sui log di debug, multimediali e desktop prodotti da Microsoft Teams, dove possono essere trovati e su come possono essere utili per il monitoraggio e la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337743"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="ae4be-103">Usare i file di log per monitorare e risolvere i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae4be-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="ae4be-104">Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per agevolare il monitoraggio e la risoluzione dei Teams:</span><span class="sxs-lookup"><span data-stu-id="ae4be-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="ae4be-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="ae4be-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="ae4be-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="ae4be-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="ae4be-107">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="ae4be-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="ae4be-108">Questo articolo descrive i tre log e il modo in cui vengono usati.</span><span class="sxs-lookup"><span data-stu-id="ae4be-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="ae4be-109">Per informazioni sulla risoluzione di problemi specifici, vedere: Teams [risoluzione dei problemi](/MicrosoftTeams/troubleshoot/teams).</span><span class="sxs-lookup"><span data-stu-id="ae4be-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="ae4be-110">Per informazioni su come contattare il supporto, vedere [Ottenere supporto.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="ae4be-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="ae4be-111">Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug.</span><span class="sxs-lookup"><span data-stu-id="ae4be-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="ae4be-112">Avere a disposizione i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="ae4be-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="ae4be-113">**I** registri multimediali **o** desktop sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae4be-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="ae4be-114">In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="ae4be-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="ae4be-115">Tuttavia, i file generati per questi log conterranno il termine **log di diagnostica** nei nomi.</span><span class="sxs-lookup"><span data-stu-id="ae4be-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="ae4be-116">La tabella seguente descrive i vari client e i log associati.</span><span class="sxs-lookup"><span data-stu-id="ae4be-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="ae4be-117">I file di log vengono archiviati in posizioni specifiche del client e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ae4be-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="ae4be-118">Client</span><span class="sxs-lookup"><span data-stu-id="ae4be-118">Client</span></span> |<span data-ttu-id="ae4be-119">Debug</span><span class="sxs-lookup"><span data-stu-id="ae4be-119">Debug</span></span>|<span data-ttu-id="ae4be-120">Desktop</span><span class="sxs-lookup"><span data-stu-id="ae4be-120">Desktop</span></span>|<span data-ttu-id="ae4be-121">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="ae4be-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="ae4be-122">Web</span><span class="sxs-lookup"><span data-stu-id="ae4be-122">Web</span></span>    |<span data-ttu-id="ae4be-123">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-123">X</span></span>         |-         |-         |
|<span data-ttu-id="ae4be-124">Windows</span><span class="sxs-lookup"><span data-stu-id="ae4be-124">Windows</span></span>     |<span data-ttu-id="ae4be-125">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-125">X</span></span>         |<span data-ttu-id="ae4be-126">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-126">X</span></span>         |<span data-ttu-id="ae4be-127">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-127">X</span></span>         |
|<span data-ttu-id="ae4be-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="ae4be-128">Mac OSX</span></span>     |<span data-ttu-id="ae4be-129">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-129">X</span></span>         |<span data-ttu-id="ae4be-130">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-130">X</span></span>         |<span data-ttu-id="ae4be-131">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-131">X</span></span>         |
|<span data-ttu-id="ae4be-132">Linux</span><span class="sxs-lookup"><span data-stu-id="ae4be-132">Linux</span></span>     |<span data-ttu-id="ae4be-133">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-133">X</span></span>         |<span data-ttu-id="ae4be-134">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-134">X</span></span>         |<span data-ttu-id="ae4be-135">X</span><span class="sxs-lookup"><span data-stu-id="ae4be-135">X</span></span>         |
|<span data-ttu-id="ae4be-136">iOS</span><span class="sxs-lookup"><span data-stu-id="ae4be-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="ae4be-137">Android</span><span class="sxs-lookup"><span data-stu-id="ae4be-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="ae4be-138">Per un elenco completo dei sistemi operativi e dei browser supportati, vedere Ottenere [i client per Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ae4be-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="ae4be-139">Log di debug</span><span class="sxs-lookup"><span data-stu-id="ae4be-139">Debug logs</span></span>

<span data-ttu-id="ae4be-140">Questi sono i log più comuni e sono necessari per tutti i casi di supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae4be-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="ae4be-141">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre che dai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="ae4be-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="ae4be-142">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="ae4be-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="ae4be-143">Possono essere letti con qualsiasi editor basato su testo e i nuovi log vengono creati quando si accede al client.</span><span class="sxs-lookup"><span data-stu-id="ae4be-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="ae4be-144">I log di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae4be-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="ae4be-145">Accesso</span><span class="sxs-lookup"><span data-stu-id="ae4be-145">Login</span></span>

-   <span data-ttu-id="ae4be-146">Richieste di connessione a servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="ae4be-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="ae4be-147">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="ae4be-147">Call/conversation</span></span>

<span data-ttu-id="ae4be-148">I log di debug vengono prodotti usando i metodi specifici del sistema operativo seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae4be-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="ae4be-149">Windows:</span><span class="sxs-lookup"><span data-stu-id="ae4be-149">Windows:</span></span>

      <span data-ttu-id="ae4be-150">Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="ae4be-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="ae4be-151">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="ae4be-151">Mac OSX:</span></span>

      <span data-ttu-id="ae4be-152">Scelta rapida da tastiera: OPZIONE+COMANDO+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="ae4be-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="ae4be-153">Linux:</span><span class="sxs-lookup"><span data-stu-id="ae4be-153">Linux:</span></span>

      <span data-ttu-id="ae4be-154">Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="ae4be-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="ae4be-155">I log di debug vengono scaricati automaticamente nelle cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae4be-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="ae4be-156">Windows: download di %userprofile% \\</span><span class="sxs-lookup"><span data-stu-id="ae4be-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="ae4be-157">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="ae4be-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="ae4be-158">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="ae4be-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="ae4be-159">Browser: verrà chiesto di salvare il log di debug nel percorso di salvataggio predefinito</span><span class="sxs-lookup"><span data-stu-id="ae4be-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="ae4be-160">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="ae4be-160">Media logs</span></span>

<span data-ttu-id="ae4be-161">I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle Teams riunioni.</span><span class="sxs-lookup"><span data-stu-id="ae4be-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="ae4be-162">Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="ae4be-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="ae4be-163">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ae4be-163">Media logging is turned off by default.</span></span> <span data-ttu-id="ae4be-164">Per registrare i dati di diagnostica Teams riunioni, gli utenti devono attivare l'opzione nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="ae4be-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="ae4be-165">Passare a **Impostazioni** Generale , selezionare la casella di controllo Abilita registrazione per diagnostica riunione (è necessario riavviare Teams ), riavviare Teams e riprodurre  >  il problema. </span><span class="sxs-lookup"><span data-stu-id="ae4be-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="ae4be-166">La tabella seguente descrive le posizioni dei log multimediali.</span><span class="sxs-lookup"><span data-stu-id="ae4be-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="ae4be-167">Quando si inviano i file di log al supporto tecnico Microsoft, verificare il timestamp dei file di log per assicurarsi che i log copriranno l'intervallo di tempo in cui è stato riprodotto il problema.</span><span class="sxs-lookup"><span data-stu-id="ae4be-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="ae4be-168">Client</span><span class="sxs-lookup"><span data-stu-id="ae4be-168">Client</span></span> |<span data-ttu-id="ae4be-169">Posizione</span><span class="sxs-lookup"><span data-stu-id="ae4be-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="ae4be-170">Windows</span><span class="sxs-lookup"><span data-stu-id="ae4be-170">Windows</span></span>     |<span data-ttu-id="ae4be-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="ae4be-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="ae4be-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="ae4be-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="ae4be-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="ae4be-174">Mac OSX</span></span>     |<span data-ttu-id="ae4be-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="ae4be-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="ae4be-177">Linux</span><span class="sxs-lookup"><span data-stu-id="ae4be-177">Linux</span></span>       |<span data-ttu-id="ae4be-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="ae4be-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="ae4be-180">Ecco un elenco dei file di log generati e delle informazioni che contengono.</span><span class="sxs-lookup"><span data-stu-id="ae4be-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="ae4be-181">Nome file di log</span><span class="sxs-lookup"><span data-stu-id="ae4be-181">Log file name</span></span>  |<span data-ttu-id="ae4be-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae4be-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ae4be-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="ae4be-184">Contiene informazioni correlate allo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="ae4be-184">Contains information related to the media stack.</span></span> <span data-ttu-id="ae4be-185">Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione dello schermo basata su video e fotocamera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="ae4be-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="ae4be-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="ae4be-187">Registra le informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore data e ora quando viene fornito il controllo, e le informazioni sul puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="ae4be-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="ae4be-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="ae4be-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="ae4be-189">Registra gli eventi di traccia dello stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="ae4be-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="ae4be-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="ae4be-191">Contiene informazioni relative all'agente multimediale, inclusa la qualità del rendering.</span><span class="sxs-lookup"><span data-stu-id="ae4be-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="ae4be-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="ae4be-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="ae4be-193">Registra gli eventi nell'API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="ae4be-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="ae4be-194">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="ae4be-194">Desktop logs</span></span>

<span data-ttu-id="ae4be-195">I log desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="ae4be-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="ae4be-196">Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae4be-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="ae4be-197">I log sono basati su testo e possono essere letti con qualsiasi editor basato su testo in un formato dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="ae4be-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="ae4be-198">Windows:</span><span class="sxs-lookup"><span data-stu-id="ae4be-198">Windows:</span></span>

 - <span data-ttu-id="ae4be-199">Fare clic con il pulsante **destro Microsoft Teams'icona** della barra delle applicazioni e scegliere **Ottieni log.**</span><span class="sxs-lookup"><span data-stu-id="ae4be-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="ae4be-200">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="ae4be-200">Mac OsX:</span></span>

 - <span data-ttu-id="ae4be-201">Scegliere **Ottieni log** dal menu **a** discesa ?</span><span class="sxs-lookup"><span data-stu-id="ae4be-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="ae4be-202">Linux:</span><span class="sxs-lookup"><span data-stu-id="ae4be-202">Linux:</span></span>

 - <span data-ttu-id="ae4be-203">Fare clic **sull'Microsoft Teams** sulla barra delle applicazioni e selezionare **Ottieni log.**</span><span class="sxs-lookup"><span data-stu-id="ae4be-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="ae4be-204">Client</span><span class="sxs-lookup"><span data-stu-id="ae4be-204">Client</span></span> |<span data-ttu-id="ae4be-205">Posizione</span><span class="sxs-lookup"><span data-stu-id="ae4be-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="ae4be-206">Windows</span><span class="sxs-lookup"><span data-stu-id="ae4be-206">Windows</span></span>     |<span data-ttu-id="ae4be-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="ae4be-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="ae4be-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="ae4be-208">Mac OSX</span></span>     |<span data-ttu-id="ae4be-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="ae4be-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="ae4be-210">Linux</span><span class="sxs-lookup"><span data-stu-id="ae4be-210">Linux</span></span>       |<span data-ttu-id="ae4be-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="ae4be-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="ae4be-212">Traccia del browser</span><span class="sxs-lookup"><span data-stu-id="ae4be-212">Browser trace</span></span>

<span data-ttu-id="ae4be-213">Per alcune categorie di errori, il supporto Tecnico Microsoft potrebbe richiedere la raccolta di una traccia del browser.</span><span class="sxs-lookup"><span data-stu-id="ae4be-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="ae4be-214">Queste informazioni possono fornire dettagli importanti sullo stato del client Teams client quando si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="ae4be-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="ae4be-215">Prima di avviare la traccia del browser, assicurarsi di aver eseguito l'accesso a Teams.</span><span class="sxs-lookup"><span data-stu-id="ae4be-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="ae4be-216">È importante eseguire questa operazione prima di avviare la traccia in modo che la traccia non contenga informazioni di accesso riservate.</span><span class="sxs-lookup"><span data-stu-id="ae4be-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="ae4be-217">Dopo aver eseguito l'accesso, selezionare uno dei collegamenti seguenti, in base alle esigenze del browser, e seguire la procedura fornita.</span><span class="sxs-lookup"><span data-stu-id="ae4be-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="ae4be-218">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="ae4be-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="ae4be-219">Edge</span><span class="sxs-lookup"><span data-stu-id="ae4be-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="ae4be-220">Safari</span><span class="sxs-lookup"><span data-stu-id="ae4be-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="ae4be-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="ae4be-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="ae4be-222">Nei passaggi sostituire tutti i riferimenti al portale di Azure con il Teams client.</span><span class="sxs-lookup"><span data-stu-id="ae4be-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="ae4be-223">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ae4be-223">Related topics</span></span>

[<span data-ttu-id="ae4be-224">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="ae4be-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
