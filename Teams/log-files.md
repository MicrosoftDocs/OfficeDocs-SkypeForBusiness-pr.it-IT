---
title: Usare i file di log per la risoluzione dei problemi di Microsoft Teams
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
description: Informazioni sui log di debug, multimediali e desktop prodotti da Microsoft Teams, dove è possibile trovarne i file e su come possono essere utili per la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761094"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="fa049-103">Usare i file di log per la risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa049-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="fa049-104">Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per agevolare la risoluzione dei problemi di Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="fa049-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="fa049-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="fa049-105">Debug logs</span></span>

-   <span data-ttu-id="fa049-106">Log multimediali</span><span class="sxs-lookup"><span data-stu-id="fa049-106">Media logs</span></span>

-   <span data-ttu-id="fa049-107">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="fa049-107">Desktop logs</span></span>

<span data-ttu-id="fa049-108">Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug.</span><span class="sxs-lookup"><span data-stu-id="fa049-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="fa049-109">Avere a portata di mano i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="fa049-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="fa049-110">**I** log multimediali **o desktop** sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa049-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="fa049-111">In questo articolo il termine **log di debug fa** riferimento ai log usati per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fa049-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="fa049-112">Tuttavia, i file generati per questi log conterranno i termini **log diagnostici** nei loro nomi.</span><span class="sxs-lookup"><span data-stu-id="fa049-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="fa049-113">La tabella seguente illustra i vari client e i log associati.</span><span class="sxs-lookup"><span data-stu-id="fa049-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="fa049-114">I file di log sono archiviati in posizioni specifiche del client e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fa049-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="fa049-115">Client</span><span class="sxs-lookup"><span data-stu-id="fa049-115">Client</span></span> |<span data-ttu-id="fa049-116">Debug</span><span class="sxs-lookup"><span data-stu-id="fa049-116">Debug</span></span>|<span data-ttu-id="fa049-117">Desktop</span><span class="sxs-lookup"><span data-stu-id="fa049-117">Desktop</span></span>|<span data-ttu-id="fa049-118">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="fa049-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="fa049-119">Web</span><span class="sxs-lookup"><span data-stu-id="fa049-119">Web</span></span>    |<span data-ttu-id="fa049-120">X</span><span class="sxs-lookup"><span data-stu-id="fa049-120">X</span></span>         |-         |-         |
|<span data-ttu-id="fa049-121">Windows</span><span class="sxs-lookup"><span data-stu-id="fa049-121">Windows</span></span>     |<span data-ttu-id="fa049-122">X</span><span class="sxs-lookup"><span data-stu-id="fa049-122">X</span></span>         |<span data-ttu-id="fa049-123">X</span><span class="sxs-lookup"><span data-stu-id="fa049-123">X</span></span>         |<span data-ttu-id="fa049-124">X</span><span class="sxs-lookup"><span data-stu-id="fa049-124">X</span></span>         |
|<span data-ttu-id="fa049-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fa049-125">Mac OSX</span></span>     |<span data-ttu-id="fa049-126">X</span><span class="sxs-lookup"><span data-stu-id="fa049-126">X</span></span>         |<span data-ttu-id="fa049-127">X</span><span class="sxs-lookup"><span data-stu-id="fa049-127">X</span></span>         |<span data-ttu-id="fa049-128">X</span><span class="sxs-lookup"><span data-stu-id="fa049-128">X</span></span>         |
|<span data-ttu-id="fa049-129">Linux</span><span class="sxs-lookup"><span data-stu-id="fa049-129">Linux</span></span>     |<span data-ttu-id="fa049-130">X</span><span class="sxs-lookup"><span data-stu-id="fa049-130">X</span></span>         |<span data-ttu-id="fa049-131">X</span><span class="sxs-lookup"><span data-stu-id="fa049-131">X</span></span>         |<span data-ttu-id="fa049-132">X</span><span class="sxs-lookup"><span data-stu-id="fa049-132">X</span></span>         |
|<span data-ttu-id="fa049-133">iOS</span><span class="sxs-lookup"><span data-stu-id="fa049-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="fa049-134">Android</span><span class="sxs-lookup"><span data-stu-id="fa049-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="fa049-135">Per un elenco completo dei sistemi operativi e dei browser supportati, vedere [Ottenere i client per Microsoft Teams.](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="fa049-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="fa049-136">Log di debug</span><span class="sxs-lookup"><span data-stu-id="fa049-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="fa049-137">Si tratta dei log più comuni e sono necessari per tutti i casi di supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa049-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="fa049-138">I log di debug vengono prodotti dai client desktop Windows e Mac, nonché dai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="fa049-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="fa049-139">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="fa049-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="fa049-140">Possono essere letti con qualsiasi editor basato su testo e vengono creati nuovi log quando si accede al client.</span><span class="sxs-lookup"><span data-stu-id="fa049-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="fa049-141">I log di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa049-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="fa049-142">Accesso</span><span class="sxs-lookup"><span data-stu-id="fa049-142">Login</span></span>

-   <span data-ttu-id="fa049-143">Richieste di connessione ai servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="fa049-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="fa049-144">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="fa049-144">Call/conversation</span></span>

<span data-ttu-id="fa049-145">I log di debug vengono prodotti usando i metodi specifici del sistema operativo seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa049-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="fa049-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="fa049-146">Windows:</span></span>

      <span data-ttu-id="fa049-147">Scelta rapida da tastiera: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="fa049-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="fa049-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="fa049-148">Mac OSX:</span></span>

      <span data-ttu-id="fa049-149">Scelta rapida da tastiera: OPZIONE+COMANDO+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="fa049-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="fa049-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="fa049-150">Linux:</span></span>

      <span data-ttu-id="fa049-151">Scelta rapida da tastiera: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="fa049-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="fa049-152">I log di debug vengono scaricati automaticamente nelle cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa049-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="fa049-153">Windows: %userprofile% \\ Download</span><span class="sxs-lookup"><span data-stu-id="fa049-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="fa049-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fa049-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="fa049-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fa049-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="fa049-156">Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita</span><span class="sxs-lookup"><span data-stu-id="fa049-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="fa049-157">Log multimediali</span><span class="sxs-lookup"><span data-stu-id="fa049-157">Media logs</span></span>
---------------------------

<span data-ttu-id="fa049-158">I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle riunioni di Teams.</span><span class="sxs-lookup"><span data-stu-id="fa049-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="fa049-159">Sono obbligatori per i casi di supporto collegati a problemi correlati alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fa049-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="fa049-160">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fa049-160">Media logging is turned off by default.</span></span> <span data-ttu-id="fa049-161">Per registrare i dati di diagnostica per le riunioni di Teams, gli utenti devono attivare l'opzione nel client di Teams.</span><span class="sxs-lookup"><span data-stu-id="fa049-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="fa049-162">Vai a **Impostazioni** generali, seleziona la casella di controllo Attiva registrazione per la diagnostica delle riunioni (richiede il riavvio di Teams), riavvia  >  Teams e riproduci il problema. </span><span class="sxs-lookup"><span data-stu-id="fa049-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="fa049-163">La tabella seguente illustra i percorsi dei log multimediali.</span><span class="sxs-lookup"><span data-stu-id="fa049-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="fa049-164">Quando si inviano i file di log al supporto Microsoft, verificare la data e l'ora dei file di log per assicurarsi che coprono l'intervallo di tempo durante il periodo in cui è stato riprodotto il problema.</span><span class="sxs-lookup"><span data-stu-id="fa049-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="fa049-165">Client</span><span class="sxs-lookup"><span data-stu-id="fa049-165">Client</span></span> |<span data-ttu-id="fa049-166">Posizione</span><span class="sxs-lookup"><span data-stu-id="fa049-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fa049-167">Windows</span><span class="sxs-lookup"><span data-stu-id="fa049-167">Windows</span></span>     |<span data-ttu-id="fa049-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="fa049-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="fa049-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="fa049-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="fa049-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fa049-171">Mac OSX</span></span>     |<span data-ttu-id="fa049-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fa049-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="fa049-174">Linux</span><span class="sxs-lookup"><span data-stu-id="fa049-174">Linux</span></span>       |<span data-ttu-id="fa049-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fa049-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="fa049-177">Ecco un elenco dei file di log generati e delle informazioni in essi contenute.</span><span class="sxs-lookup"><span data-stu-id="fa049-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="fa049-178">Nome file di log</span><span class="sxs-lookup"><span data-stu-id="fa049-178">Log file name</span></span>  |<span data-ttu-id="fa049-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa049-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fa049-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="fa049-181">Contiene informazioni correlate allo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="fa049-181">Contains information related to the media stack.</span></span> <span data-ttu-id="fa049-182">Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione schermo basata su video e fotocamera.</span><span class="sxs-lookup"><span data-stu-id="fa049-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="fa049-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="fa049-184">Registra informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore di data e ora quando viene assegnato il controllo e le informazioni del puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="fa049-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="fa049-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="fa049-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="fa049-186">Registra gli eventi di traccia dello stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="fa049-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="fa049-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="fa049-188">Contiene informazioni relative all'agente multimediale, inclusa la qualità di rendering.</span><span class="sxs-lookup"><span data-stu-id="fa049-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="fa049-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="fa049-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="fa049-190">Registra gli eventi nell'API per la chiamata ts.</span><span class="sxs-lookup"><span data-stu-id="fa049-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="fa049-191">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="fa049-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="fa049-192">I log desktop, noti anche come log del programma di avvio automatico, contengono dati di log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="fa049-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="fa049-193">Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa049-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="fa049-194">I log sono basati sul testo e possono essere letti usando qualsiasi editor basato su testo in formato dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="fa049-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="fa049-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="fa049-195">Windows:</span></span>

 - <span data-ttu-id="fa049-196">Fare clic con il pulsante **destro del mouse sull'icona** di Microsoft Teams sulla barra delle applicazioni e scegliere Ottieni **registri.**</span><span class="sxs-lookup"><span data-stu-id="fa049-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="fa049-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="fa049-197">Mac OsX:</span></span>

 - <span data-ttu-id="fa049-198">Scegliere **Ottieni registri** dal menu **a** discesa?</span><span class="sxs-lookup"><span data-stu-id="fa049-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="fa049-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="fa049-199">Linux:</span></span>

 - <span data-ttu-id="fa049-200">Fare clic **sull'icona di Microsoft Teams** sulla barra delle applicazioni e selezionare Ottieni **registri.**</span><span class="sxs-lookup"><span data-stu-id="fa049-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="fa049-201">Client</span><span class="sxs-lookup"><span data-stu-id="fa049-201">Client</span></span> |<span data-ttu-id="fa049-202">Posizione</span><span class="sxs-lookup"><span data-stu-id="fa049-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fa049-203">Windows</span><span class="sxs-lookup"><span data-stu-id="fa049-203">Windows</span></span>     |<span data-ttu-id="fa049-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="fa049-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="fa049-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fa049-205">Mac OSX</span></span>     |<span data-ttu-id="fa049-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fa049-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="fa049-207">Linux</span><span class="sxs-lookup"><span data-stu-id="fa049-207">Linux</span></span>       |<span data-ttu-id="fa049-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fa049-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="fa049-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fa049-209">Related topics</span></span>

[<span data-ttu-id="fa049-210">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="fa049-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
