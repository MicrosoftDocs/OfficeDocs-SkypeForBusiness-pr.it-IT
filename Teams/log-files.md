---
title: Usare i file di log nella risoluzione dei problemi di Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informazioni sui log di debug, multimediali e desktop prodotti da Microsoft Teams, dove possono essere trovati e su come possono essere utili per la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112192"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="6c928-103">Usare i file di log nella risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c928-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="6c928-104">Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per facilitare la risoluzione dei problemi di Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="6c928-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="6c928-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="6c928-105">Debug logs</span></span>

-   <span data-ttu-id="6c928-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="6c928-106">Media logs</span></span>

-   <span data-ttu-id="6c928-107">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="6c928-107">Desktop logs</span></span>

<span data-ttu-id="6c928-108">Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug.</span><span class="sxs-lookup"><span data-stu-id="6c928-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="6c928-109">Avere a disposizione i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="6c928-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="6c928-110">**I** log **multimediali o desktop** sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c928-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="6c928-111">In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="6c928-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="6c928-112">Tuttavia, i file generati per questi log conterranno il termine **log di diagnostica** nei nomi.</span><span class="sxs-lookup"><span data-stu-id="6c928-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="6c928-113">La tabella seguente descrive i vari client e i log associati.</span><span class="sxs-lookup"><span data-stu-id="6c928-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="6c928-114">I file di log vengono archiviati in posizioni specifiche del client e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6c928-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="6c928-115">Client</span><span class="sxs-lookup"><span data-stu-id="6c928-115">Client</span></span> |<span data-ttu-id="6c928-116">Debug</span><span class="sxs-lookup"><span data-stu-id="6c928-116">Debug</span></span>|<span data-ttu-id="6c928-117">Desktop</span><span class="sxs-lookup"><span data-stu-id="6c928-117">Desktop</span></span>|<span data-ttu-id="6c928-118">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="6c928-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="6c928-119">Web</span><span class="sxs-lookup"><span data-stu-id="6c928-119">Web</span></span>    |<span data-ttu-id="6c928-120">X</span><span class="sxs-lookup"><span data-stu-id="6c928-120">X</span></span>         |-         |-         |
|<span data-ttu-id="6c928-121">Windows</span><span class="sxs-lookup"><span data-stu-id="6c928-121">Windows</span></span>     |<span data-ttu-id="6c928-122">X</span><span class="sxs-lookup"><span data-stu-id="6c928-122">X</span></span>         |<span data-ttu-id="6c928-123">X</span><span class="sxs-lookup"><span data-stu-id="6c928-123">X</span></span>         |<span data-ttu-id="6c928-124">X</span><span class="sxs-lookup"><span data-stu-id="6c928-124">X</span></span>         |
|<span data-ttu-id="6c928-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="6c928-125">Mac OSX</span></span>     |<span data-ttu-id="6c928-126">X</span><span class="sxs-lookup"><span data-stu-id="6c928-126">X</span></span>         |<span data-ttu-id="6c928-127">X</span><span class="sxs-lookup"><span data-stu-id="6c928-127">X</span></span>         |<span data-ttu-id="6c928-128">X</span><span class="sxs-lookup"><span data-stu-id="6c928-128">X</span></span>         |
|<span data-ttu-id="6c928-129">Linux</span><span class="sxs-lookup"><span data-stu-id="6c928-129">Linux</span></span>     |<span data-ttu-id="6c928-130">X</span><span class="sxs-lookup"><span data-stu-id="6c928-130">X</span></span>         |<span data-ttu-id="6c928-131">X</span><span class="sxs-lookup"><span data-stu-id="6c928-131">X</span></span>         |<span data-ttu-id="6c928-132">X</span><span class="sxs-lookup"><span data-stu-id="6c928-132">X</span></span>         |
|<span data-ttu-id="6c928-133">iOS</span><span class="sxs-lookup"><span data-stu-id="6c928-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="6c928-134">Android</span><span class="sxs-lookup"><span data-stu-id="6c928-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="6c928-135">Per un elenco completo dei sistemi operativi e dei browser supportati, vedere [Ottenere client per Microsoft Teams.](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="6c928-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="6c928-136">Log di debug</span><span class="sxs-lookup"><span data-stu-id="6c928-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="6c928-137">Questi sono i log più comuni e sono necessari per tutti i casi di supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c928-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="6c928-138">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre che dai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="6c928-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="6c928-139">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="6c928-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="6c928-140">Possono essere letti con qualsiasi editor basato su testo e i nuovi log vengono creati quando si accede al client.</span><span class="sxs-lookup"><span data-stu-id="6c928-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="6c928-141">I log di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c928-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="6c928-142">Accesso</span><span class="sxs-lookup"><span data-stu-id="6c928-142">Login</span></span>

-   <span data-ttu-id="6c928-143">Richieste di connessione a servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="6c928-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="6c928-144">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="6c928-144">Call/conversation</span></span>

<span data-ttu-id="6c928-145">I log di debug vengono prodotti usando i metodi specifici del sistema operativo seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c928-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="6c928-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="6c928-146">Windows:</span></span>

      <span data-ttu-id="6c928-147">Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="6c928-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="6c928-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="6c928-148">Mac OSX:</span></span>

      <span data-ttu-id="6c928-149">Scelta rapida da tastiera: OPZIONE+COMANDO+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="6c928-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="6c928-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="6c928-150">Linux:</span></span>

      <span data-ttu-id="6c928-151">Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="6c928-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="6c928-152">I log di debug vengono scaricati automaticamente nelle cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c928-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="6c928-153">Windows: download di %userprofile% \\</span><span class="sxs-lookup"><span data-stu-id="6c928-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="6c928-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="6c928-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="6c928-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="6c928-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="6c928-156">Browser: verrà chiesto di salvare il log di debug nel percorso di salvataggio predefinito</span><span class="sxs-lookup"><span data-stu-id="6c928-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="6c928-157">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="6c928-157">Media logs</span></span>
---------------------------

<span data-ttu-id="6c928-158">I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="6c928-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="6c928-159">Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="6c928-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="6c928-160">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6c928-160">Media logging is turned off by default.</span></span> <span data-ttu-id="6c928-161">Per registrare i dati di diagnostica per le riunioni di Teams, gli utenti devono attivare l'opzione nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="6c928-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="6c928-162">Passare a **Impostazioni** generali, selezionare la casella di controllo Abilita registrazione per diagnostica riunione (richiede il riavvio di  >   **Teams),** riavviare Teams e riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="6c928-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="6c928-163">La tabella seguente descrive le posizioni dei log multimediali.</span><span class="sxs-lookup"><span data-stu-id="6c928-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="6c928-164">Quando si inviano i file di log al supporto tecnico Microsoft, verificare il timestamp dei file di log per assicurarsi che i log copriranno l'intervallo di tempo in cui è stato riprodotto il problema.</span><span class="sxs-lookup"><span data-stu-id="6c928-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="6c928-165">Client</span><span class="sxs-lookup"><span data-stu-id="6c928-165">Client</span></span> |<span data-ttu-id="6c928-166">Posizione</span><span class="sxs-lookup"><span data-stu-id="6c928-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="6c928-167">Windows</span><span class="sxs-lookup"><span data-stu-id="6c928-167">Windows</span></span>     |<span data-ttu-id="6c928-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="6c928-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="6c928-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="6c928-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="6c928-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="6c928-171">Mac OSX</span></span>     |<span data-ttu-id="6c928-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="6c928-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="6c928-174">Linux</span><span class="sxs-lookup"><span data-stu-id="6c928-174">Linux</span></span>       |<span data-ttu-id="6c928-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="6c928-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="6c928-177">Ecco un elenco dei file di log generati e delle informazioni che contengono.</span><span class="sxs-lookup"><span data-stu-id="6c928-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="6c928-178">Nome file di log</span><span class="sxs-lookup"><span data-stu-id="6c928-178">Log file name</span></span>  |<span data-ttu-id="6c928-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c928-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6c928-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="6c928-181">Contiene informazioni correlate allo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="6c928-181">Contains information related to the media stack.</span></span> <span data-ttu-id="6c928-182">Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione dello schermo basata su video e fotocamera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="6c928-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="6c928-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="6c928-184">Registra le informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore data e ora quando viene fornito il controllo, e le informazioni sul puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="6c928-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="6c928-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="6c928-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="6c928-186">Registra gli eventi di traccia dello stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="6c928-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="6c928-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="6c928-188">Contiene informazioni relative all'agente multimediale, inclusa la qualità del rendering.</span><span class="sxs-lookup"><span data-stu-id="6c928-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="6c928-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="6c928-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="6c928-190">Registra gli eventi nell'API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="6c928-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="6c928-191">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="6c928-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="6c928-192">I log desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="6c928-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="6c928-193">Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c928-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="6c928-194">I log sono basati su testo e possono essere letti con qualsiasi editor basato su testo in un formato dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="6c928-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="6c928-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="6c928-195">Windows:</span></span>

 - <span data-ttu-id="6c928-196">Fare clic con il pulsante **destro del mouse sull'icona di Microsoft Teams** nella barra delle applicazioni e scegliere Ottieni **log.**</span><span class="sxs-lookup"><span data-stu-id="6c928-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="6c928-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="6c928-197">Mac OsX:</span></span>

 - <span data-ttu-id="6c928-198">Scegliere **Ottieni log** dal menu **a** discesa ?</span><span class="sxs-lookup"><span data-stu-id="6c928-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="6c928-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="6c928-199">Linux:</span></span>

 - <span data-ttu-id="6c928-200">Fare clic **sull'icona di Microsoft Teams** nell'area di notifica e selezionare Ottieni **log.**</span><span class="sxs-lookup"><span data-stu-id="6c928-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="6c928-201">Client</span><span class="sxs-lookup"><span data-stu-id="6c928-201">Client</span></span> |<span data-ttu-id="6c928-202">Posizione</span><span class="sxs-lookup"><span data-stu-id="6c928-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="6c928-203">Windows</span><span class="sxs-lookup"><span data-stu-id="6c928-203">Windows</span></span>     |<span data-ttu-id="6c928-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="6c928-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="6c928-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="6c928-205">Mac OSX</span></span>     |<span data-ttu-id="6c928-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="6c928-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="6c928-207">Linux</span><span class="sxs-lookup"><span data-stu-id="6c928-207">Linux</span></span>       |<span data-ttu-id="6c928-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="6c928-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="6c928-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6c928-209">Related topics</span></span>

[<span data-ttu-id="6c928-210">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="6c928-210">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)