---
title: Usare i file di log in risoluzione dei problemi di Microsoft Teams
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
description: Informazioni sui registri di debug, multimediali e desktop prodotti da Microsoft teams, dove possono essere trovati e come possono essere utili per la risoluzione dei problemi.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761094"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="66d7a-103">Usare i file di log in risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66d7a-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="66d7a-104">Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere sfruttati per facilitare la risoluzione dei problemi di Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="66d7a-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="66d7a-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="66d7a-105">Debug logs</span></span>

-   <span data-ttu-id="66d7a-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="66d7a-106">Media logs</span></span>

-   <span data-ttu-id="66d7a-107">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="66d7a-107">Desktop logs</span></span>

<span data-ttu-id="66d7a-108">Quando si crea una richiesta di supporto con il supporto Microsoft, il tecnico del supporto richiederà i registri di debug.</span><span class="sxs-lookup"><span data-stu-id="66d7a-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="66d7a-109">Il fatto che i log di debug vengano usati prima di creare la richiesta di supporto consentirà a Microsoft di avviare rapidamente la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="66d7a-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="66d7a-110">Gli **elementi multimediali** o i registri **Desktop** sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66d7a-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="66d7a-111">In questo articolo, il termine **log di debug** si riferisce ai log usati per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="66d7a-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="66d7a-112">Tuttavia, i file generati per questi log conterranno i **registri di diagnostica** termine nei nomi.</span><span class="sxs-lookup"><span data-stu-id="66d7a-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="66d7a-113">La tabella seguente illustra i vari client e i relativi registri associati.</span><span class="sxs-lookup"><span data-stu-id="66d7a-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="66d7a-114">I file di log sono archiviati in posizioni specifiche per il client e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="66d7a-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="66d7a-115">Client</span><span class="sxs-lookup"><span data-stu-id="66d7a-115">Client</span></span> |<span data-ttu-id="66d7a-116">Debug</span><span class="sxs-lookup"><span data-stu-id="66d7a-116">Debug</span></span>|<span data-ttu-id="66d7a-117">Desktop</span><span class="sxs-lookup"><span data-stu-id="66d7a-117">Desktop</span></span>|<span data-ttu-id="66d7a-118">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="66d7a-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="66d7a-119">Web</span><span class="sxs-lookup"><span data-stu-id="66d7a-119">Web</span></span>    |<span data-ttu-id="66d7a-120">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-120">X</span></span>         |-         |-         |
|<span data-ttu-id="66d7a-121">Windows</span><span class="sxs-lookup"><span data-stu-id="66d7a-121">Windows</span></span>     |<span data-ttu-id="66d7a-122">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-122">X</span></span>         |<span data-ttu-id="66d7a-123">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-123">X</span></span>         |<span data-ttu-id="66d7a-124">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-124">X</span></span>         |
|<span data-ttu-id="66d7a-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="66d7a-125">Mac OSX</span></span>     |<span data-ttu-id="66d7a-126">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-126">X</span></span>         |<span data-ttu-id="66d7a-127">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-127">X</span></span>         |<span data-ttu-id="66d7a-128">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-128">X</span></span>         |
|<span data-ttu-id="66d7a-129">Linux</span><span class="sxs-lookup"><span data-stu-id="66d7a-129">Linux</span></span>     |<span data-ttu-id="66d7a-130">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-130">X</span></span>         |<span data-ttu-id="66d7a-131">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-131">X</span></span>         |<span data-ttu-id="66d7a-132">X</span><span class="sxs-lookup"><span data-stu-id="66d7a-132">X</span></span>         |
|<span data-ttu-id="66d7a-133">iOS</span><span class="sxs-lookup"><span data-stu-id="66d7a-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="66d7a-134">Android</span><span class="sxs-lookup"><span data-stu-id="66d7a-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="66d7a-135">Per un elenco completo di sistemi operativi e browser supportati, vedere [ottenere client per Microsoft teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="66d7a-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="66d7a-136">Log di debug</span><span class="sxs-lookup"><span data-stu-id="66d7a-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="66d7a-137">Questi sono i registri più comuni e sono necessari per tutti i casi di supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66d7a-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="66d7a-138">I log di debug vengono prodotti dai client desktop Windows e Mac, nonché dai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="66d7a-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="66d7a-139">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="66d7a-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="66d7a-140">Possono essere lette usando qualsiasi editor basato su testo e vengono creati nuovi log durante l'accesso al client.</span><span class="sxs-lookup"><span data-stu-id="66d7a-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="66d7a-141">I registri di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="66d7a-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="66d7a-142">Accesso</span><span class="sxs-lookup"><span data-stu-id="66d7a-142">Login</span></span>

-   <span data-ttu-id="66d7a-143">Richieste di connessione ai servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="66d7a-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="66d7a-144">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="66d7a-144">Call/conversation</span></span>

<span data-ttu-id="66d7a-145">I log di debug vengono prodotti usando i metodi specifici per il sistema operativo seguenti:</span><span class="sxs-lookup"><span data-stu-id="66d7a-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="66d7a-146">Windows</span><span class="sxs-lookup"><span data-stu-id="66d7a-146">Windows:</span></span>

      <span data-ttu-id="66d7a-147">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="66d7a-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="66d7a-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="66d7a-148">Mac OSX:</span></span>

      <span data-ttu-id="66d7a-149">Tasto di scelta rapida: opzione + comando + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="66d7a-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="66d7a-150">Linux</span><span class="sxs-lookup"><span data-stu-id="66d7a-150">Linux:</span></span>

      <span data-ttu-id="66d7a-151">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="66d7a-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="66d7a-152">I log di debug vengono scaricati automaticamente nelle cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="66d7a-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="66d7a-153">Windows:% UserProfile% \\ download</span><span class="sxs-lookup"><span data-stu-id="66d7a-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="66d7a-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="66d7a-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="66d7a-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="66d7a-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="66d7a-156">Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita</span><span class="sxs-lookup"><span data-stu-id="66d7a-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="66d7a-157">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="66d7a-157">Media logs</span></span>
---------------------------

<span data-ttu-id="66d7a-158">I registri multimediali contengono dati di diagnostica relativi alla condivisione di audio, video e schermo nelle riunioni di teams.</span><span class="sxs-lookup"><span data-stu-id="66d7a-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="66d7a-159">Sono necessari per i casi di supporto collegati a problemi correlati alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="66d7a-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="66d7a-160">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="66d7a-160">Media logging is turned off by default.</span></span> <span data-ttu-id="66d7a-161">Per registrare i dati di diagnostica per le riunioni di teams, gli utenti devono attivare l'opzione nel client teams.</span><span class="sxs-lookup"><span data-stu-id="66d7a-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="66d7a-162">Accedere a **Impostazioni**  >  **generali**, selezionare la casella di controllo **Abilita registrazione per la diagnostica riunione (richiede** il riavvio di Team), riavviare teams e riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="66d7a-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="66d7a-163">La tabella seguente illustra le posizioni dei registri multimediali.</span><span class="sxs-lookup"><span data-stu-id="66d7a-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="66d7a-164">Quando si inviano i file di log al supporto Microsoft, verificare il timestamp dei file di log per verificare che i registri riguardino il periodo di tempo in cui è stato riprodotto il problema.</span><span class="sxs-lookup"><span data-stu-id="66d7a-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="66d7a-165">Client</span><span class="sxs-lookup"><span data-stu-id="66d7a-165">Client</span></span> |<span data-ttu-id="66d7a-166">Posizione</span><span class="sxs-lookup"><span data-stu-id="66d7a-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="66d7a-167">Windows</span><span class="sxs-lookup"><span data-stu-id="66d7a-167">Windows</span></span>     |<span data-ttu-id="66d7a-168">%appdata%\Microsoft\Teams\media-stack \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="66d7a-169">%appdata%\Microsoft\Teams\skylib \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="66d7a-170">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="66d7a-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="66d7a-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="66d7a-171">Mac OSX</span></span>     |<span data-ttu-id="66d7a-172">~/Libreria/Application Support/Microsoft/teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="66d7a-173">~/Libreria/Application Support/Microsoft/teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="66d7a-174">Linux</span><span class="sxs-lookup"><span data-stu-id="66d7a-174">Linux</span></span>       |<span data-ttu-id="66d7a-175">~/.config/Microsoft/Microsoft teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="66d7a-176">~/.config/Microsoft/Microsoft teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="66d7a-177">Ecco un elenco dei file di log generati e delle informazioni che contengono.</span><span class="sxs-lookup"><span data-stu-id="66d7a-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="66d7a-178">Nome file di log</span><span class="sxs-lookup"><span data-stu-id="66d7a-178">Log file name</span></span>  |<span data-ttu-id="66d7a-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66d7a-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="66d7a-180">Teams. MSRTC-0-s1039525249. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="66d7a-181">Contiene informazioni correlate allo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="66d7a-181">Contains information related to the media stack.</span></span> <span data-ttu-id="66d7a-182">Questo include lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, nonché il numero di fotogrammi inviati e ricevuti e lo stato della sessione di condivisione dello schermo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="66d7a-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="66d7a-183">rtmcontrol. MSRTC-0-2415069487. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="66d7a-184">Registra le informazioni relative alle azioni del controllo remoto, ad esempio l'indicatore di data e ora in cui viene assegnato il controllo, e le informazioni del puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="66d7a-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="66d7a-185">Teams_MediaStackETW -2-U-xr-U. etl</span><span class="sxs-lookup"><span data-stu-id="66d7a-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="66d7a-186">Registra gli eventi di traccia dello stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="66d7a-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="66d7a-187">Debug-0-s2790420889. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="66d7a-188">Contiene informazioni correlate all'agente multimediale, inclusa la qualità del rendering.</span><span class="sxs-lookup"><span data-stu-id="66d7a-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="66d7a-189">tscalling-0-2061129496. Blog</span><span class="sxs-lookup"><span data-stu-id="66d7a-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="66d7a-190">Registra gli eventi nell'API di chiamata TS.</span><span class="sxs-lookup"><span data-stu-id="66d7a-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="66d7a-191">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="66d7a-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="66d7a-192">I registri desktop, noti anche come log del programma di avvio automatico, contengono dati di log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="66d7a-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="66d7a-193">Come i registri multimediali, questi registri sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66d7a-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="66d7a-194">I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="66d7a-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="66d7a-195">Windows</span><span class="sxs-lookup"><span data-stu-id="66d7a-195">Windows:</span></span>

 - <span data-ttu-id="66d7a-196">Fare clic con il pulsante destro del mouse sull'icona di **Microsoft teams** nella barra delle applicazioni e scegliere **Ottieni log**.</span><span class="sxs-lookup"><span data-stu-id="66d7a-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="66d7a-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="66d7a-197">Mac OsX:</span></span>

 - <span data-ttu-id="66d7a-198">Scegliere **Recupera log** dal menu a discesa della **Guida** .</span><span class="sxs-lookup"><span data-stu-id="66d7a-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="66d7a-199">Linux</span><span class="sxs-lookup"><span data-stu-id="66d7a-199">Linux:</span></span>

 - <span data-ttu-id="66d7a-200">Fare clic sull'icona **Microsoft teams** nella barra delle applicazioni e selezionare **Ottieni log**.</span><span class="sxs-lookup"><span data-stu-id="66d7a-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="66d7a-201">Client</span><span class="sxs-lookup"><span data-stu-id="66d7a-201">Client</span></span> |<span data-ttu-id="66d7a-202">Posizione</span><span class="sxs-lookup"><span data-stu-id="66d7a-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="66d7a-203">Windows</span><span class="sxs-lookup"><span data-stu-id="66d7a-203">Windows</span></span>     |<span data-ttu-id="66d7a-204">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="66d7a-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="66d7a-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="66d7a-205">Mac OSX</span></span>     |<span data-ttu-id="66d7a-206">~/Libreria/Application Support/Microsoft/teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="66d7a-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="66d7a-207">Linux</span><span class="sxs-lookup"><span data-stu-id="66d7a-207">Linux</span></span>       |<span data-ttu-id="66d7a-208">~/.config/Microsoft/Microsoft teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="66d7a-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="66d7a-209">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="66d7a-209">Related topics</span></span>

[<span data-ttu-id="66d7a-210">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="66d7a-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
