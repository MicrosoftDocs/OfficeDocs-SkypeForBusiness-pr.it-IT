---
title: Usare i file di log nella risoluzione dei Microsoft Teams
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
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264876"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="96c82-103">Usare i file di log nella risoluzione dei Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="96c82-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="96c82-104">Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per facilitare la risoluzione dei problemi Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="96c82-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="96c82-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="96c82-105">Debug logs</span></span>

-   <span data-ttu-id="96c82-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="96c82-106">Media logs</span></span>

-   <span data-ttu-id="96c82-107">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="96c82-107">Desktop logs</span></span>

<span data-ttu-id="96c82-108">Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug.</span><span class="sxs-lookup"><span data-stu-id="96c82-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="96c82-109">Avere a disposizione i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="96c82-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="96c82-110">**I** registri multimediali **o** desktop sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="96c82-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="96c82-111">In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="96c82-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="96c82-112">Tuttavia, i file generati per questi log conterranno il termine **log di diagnostica** nei nomi.</span><span class="sxs-lookup"><span data-stu-id="96c82-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="96c82-113">La tabella seguente descrive i vari client e i log associati.</span><span class="sxs-lookup"><span data-stu-id="96c82-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="96c82-114">I file di log vengono archiviati in posizioni specifiche del client e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="96c82-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="96c82-115">Client</span><span class="sxs-lookup"><span data-stu-id="96c82-115">Client</span></span> |<span data-ttu-id="96c82-116">Debug</span><span class="sxs-lookup"><span data-stu-id="96c82-116">Debug</span></span>|<span data-ttu-id="96c82-117">Desktop</span><span class="sxs-lookup"><span data-stu-id="96c82-117">Desktop</span></span>|<span data-ttu-id="96c82-118">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="96c82-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="96c82-119">Web</span><span class="sxs-lookup"><span data-stu-id="96c82-119">Web</span></span>    |<span data-ttu-id="96c82-120">X</span><span class="sxs-lookup"><span data-stu-id="96c82-120">X</span></span>         |-         |-         |
|<span data-ttu-id="96c82-121">Windows</span><span class="sxs-lookup"><span data-stu-id="96c82-121">Windows</span></span>     |<span data-ttu-id="96c82-122">X</span><span class="sxs-lookup"><span data-stu-id="96c82-122">X</span></span>         |<span data-ttu-id="96c82-123">X</span><span class="sxs-lookup"><span data-stu-id="96c82-123">X</span></span>         |<span data-ttu-id="96c82-124">X</span><span class="sxs-lookup"><span data-stu-id="96c82-124">X</span></span>         |
|<span data-ttu-id="96c82-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="96c82-125">Mac OSX</span></span>     |<span data-ttu-id="96c82-126">X</span><span class="sxs-lookup"><span data-stu-id="96c82-126">X</span></span>         |<span data-ttu-id="96c82-127">X</span><span class="sxs-lookup"><span data-stu-id="96c82-127">X</span></span>         |<span data-ttu-id="96c82-128">X</span><span class="sxs-lookup"><span data-stu-id="96c82-128">X</span></span>         |
|<span data-ttu-id="96c82-129">Linux</span><span class="sxs-lookup"><span data-stu-id="96c82-129">Linux</span></span>     |<span data-ttu-id="96c82-130">X</span><span class="sxs-lookup"><span data-stu-id="96c82-130">X</span></span>         |<span data-ttu-id="96c82-131">X</span><span class="sxs-lookup"><span data-stu-id="96c82-131">X</span></span>         |<span data-ttu-id="96c82-132">X</span><span class="sxs-lookup"><span data-stu-id="96c82-132">X</span></span>         |
|<span data-ttu-id="96c82-133">iOS</span><span class="sxs-lookup"><span data-stu-id="96c82-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="96c82-134">Android</span><span class="sxs-lookup"><span data-stu-id="96c82-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="96c82-135">Per un elenco completo dei sistemi operativi e dei browser supportati, vedere Ottenere [i client per Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="96c82-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="96c82-136">Log di debug</span><span class="sxs-lookup"><span data-stu-id="96c82-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="96c82-137">Questi sono i log più comuni e sono necessari per tutti i casi di supporto Tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="96c82-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="96c82-138">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre che dai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="96c82-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="96c82-139">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="96c82-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="96c82-140">Possono essere letti con qualsiasi editor basato su testo e i nuovi log vengono creati quando si accede al client.</span><span class="sxs-lookup"><span data-stu-id="96c82-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="96c82-141">I log di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="96c82-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="96c82-142">Accesso</span><span class="sxs-lookup"><span data-stu-id="96c82-142">Login</span></span>

-   <span data-ttu-id="96c82-143">Richieste di connessione a servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="96c82-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="96c82-144">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="96c82-144">Call/conversation</span></span>

<span data-ttu-id="96c82-145">I log di debug vengono prodotti usando i metodi specifici del sistema operativo seguenti:</span><span class="sxs-lookup"><span data-stu-id="96c82-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="96c82-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="96c82-146">Windows:</span></span>

      <span data-ttu-id="96c82-147">Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="96c82-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="96c82-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="96c82-148">Mac OSX:</span></span>

      <span data-ttu-id="96c82-149">Scelta rapida da tastiera: OPZIONE+COMANDO+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="96c82-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="96c82-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="96c82-150">Linux:</span></span>

      <span data-ttu-id="96c82-151">Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1</span><span class="sxs-lookup"><span data-stu-id="96c82-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="96c82-152">I log di debug vengono scaricati automaticamente nelle cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="96c82-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="96c82-153">Windows: download di %userprofile% \\</span><span class="sxs-lookup"><span data-stu-id="96c82-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="96c82-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="96c82-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="96c82-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="96c82-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="96c82-156">Browser: verrà chiesto di salvare il log di debug nel percorso di salvataggio predefinito</span><span class="sxs-lookup"><span data-stu-id="96c82-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="96c82-157">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="96c82-157">Media logs</span></span>
---------------------------

<span data-ttu-id="96c82-158">I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle Teams riunioni.</span><span class="sxs-lookup"><span data-stu-id="96c82-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="96c82-159">Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="96c82-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="96c82-160">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="96c82-160">Media logging is turned off by default.</span></span> <span data-ttu-id="96c82-161">Per registrare i dati di diagnostica Teams riunioni, gli utenti devono attivare l'opzione nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="96c82-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="96c82-162">Passare a **Impostazioni** Generale , selezionare la casella di controllo Abilita registrazione per diagnostica riunione (è necessario riavviare Teams ), riavviare Teams e riprodurre  >  il problema. </span><span class="sxs-lookup"><span data-stu-id="96c82-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="96c82-163">La tabella seguente descrive le posizioni dei log multimediali.</span><span class="sxs-lookup"><span data-stu-id="96c82-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="96c82-164">Quando si inviano i file di log al supporto tecnico Microsoft, verificare il timestamp dei file di log per assicurarsi che i log copriranno l'intervallo di tempo in cui è stato riprodotto il problema.</span><span class="sxs-lookup"><span data-stu-id="96c82-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="96c82-165">Client</span><span class="sxs-lookup"><span data-stu-id="96c82-165">Client</span></span> |<span data-ttu-id="96c82-166">Posizione</span><span class="sxs-lookup"><span data-stu-id="96c82-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="96c82-167">Windows</span><span class="sxs-lookup"><span data-stu-id="96c82-167">Windows</span></span>     |<span data-ttu-id="96c82-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="96c82-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="96c82-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="96c82-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="96c82-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="96c82-171">Mac OSX</span></span>     |<span data-ttu-id="96c82-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="96c82-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="96c82-174">Linux</span><span class="sxs-lookup"><span data-stu-id="96c82-174">Linux</span></span>       |<span data-ttu-id="96c82-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="96c82-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="96c82-177">Ecco un elenco dei file di log generati e delle informazioni che contengono.</span><span class="sxs-lookup"><span data-stu-id="96c82-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="96c82-178">Nome file di log</span><span class="sxs-lookup"><span data-stu-id="96c82-178">Log file name</span></span>  |<span data-ttu-id="96c82-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96c82-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="96c82-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="96c82-181">Contiene informazioni correlate allo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="96c82-181">Contains information related to the media stack.</span></span> <span data-ttu-id="96c82-182">Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione dello schermo basata su video e fotocamera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="96c82-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="96c82-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="96c82-184">Registra le informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore data e ora quando viene fornito il controllo, e le informazioni sul puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="96c82-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="96c82-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="96c82-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="96c82-186">Registra gli eventi di traccia dello stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="96c82-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="96c82-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="96c82-188">Contiene informazioni relative all'agente multimediale, inclusa la qualità del rendering.</span><span class="sxs-lookup"><span data-stu-id="96c82-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="96c82-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="96c82-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="96c82-190">Registra gli eventi nell'API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="96c82-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="96c82-191">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="96c82-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="96c82-192">I log desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="96c82-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="96c82-193">Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="96c82-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="96c82-194">I log sono basati su testo e possono essere letti con qualsiasi editor basato su testo in un formato dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="96c82-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="96c82-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="96c82-195">Windows:</span></span>

 - <span data-ttu-id="96c82-196">Fare clic con il pulsante **destro Microsoft Teams'icona** della barra delle applicazioni e scegliere **Ottieni log.**</span><span class="sxs-lookup"><span data-stu-id="96c82-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="96c82-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="96c82-197">Mac OsX:</span></span>

 - <span data-ttu-id="96c82-198">Scegliere **Ottieni log** dal menu **a** discesa ?</span><span class="sxs-lookup"><span data-stu-id="96c82-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="96c82-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="96c82-199">Linux:</span></span>

 - <span data-ttu-id="96c82-200">Fare clic **sull'Microsoft Teams** sulla barra delle applicazioni e selezionare **Ottieni log.**</span><span class="sxs-lookup"><span data-stu-id="96c82-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="96c82-201">Client</span><span class="sxs-lookup"><span data-stu-id="96c82-201">Client</span></span> |<span data-ttu-id="96c82-202">Posizione</span><span class="sxs-lookup"><span data-stu-id="96c82-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="96c82-203">Windows</span><span class="sxs-lookup"><span data-stu-id="96c82-203">Windows</span></span>     |<span data-ttu-id="96c82-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="96c82-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="96c82-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="96c82-205">Mac OSX</span></span>     |<span data-ttu-id="96c82-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="96c82-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="96c82-207">Linux</span><span class="sxs-lookup"><span data-stu-id="96c82-207">Linux</span></span>       |<span data-ttu-id="96c82-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="96c82-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="96c82-209">Traccia del browser</span><span class="sxs-lookup"><span data-stu-id="96c82-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="96c82-210">Per alcune categorie di errori, il supporto Tecnico Microsoft potrebbe richiedere la raccolta di una traccia del browser.</span><span class="sxs-lookup"><span data-stu-id="96c82-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="96c82-211">Queste informazioni possono fornire dettagli importanti sullo stato del client Teams client quando si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="96c82-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="96c82-212">Prima di avviare la traccia del browser, assicurarsi di aver eseguito l'accesso a Teams.</span><span class="sxs-lookup"><span data-stu-id="96c82-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="96c82-213">È importante eseguire questa operazione prima di avviare la traccia in modo che la traccia non contenga informazioni di accesso riservate.</span><span class="sxs-lookup"><span data-stu-id="96c82-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="96c82-214">Dopo aver eseguito l'accesso, selezionare uno dei collegamenti seguenti, in base alle esigenze del browser, e seguire la procedura fornita.</span><span class="sxs-lookup"><span data-stu-id="96c82-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="96c82-215">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="96c82-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="96c82-216">Edge</span><span class="sxs-lookup"><span data-stu-id="96c82-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="96c82-217">Safari</span><span class="sxs-lookup"><span data-stu-id="96c82-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="96c82-218">Firefox</span><span class="sxs-lookup"><span data-stu-id="96c82-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="96c82-219">Nei passaggi sostituire tutti i riferimenti al portale di Azure con il Teams client.</span><span class="sxs-lookup"><span data-stu-id="96c82-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="96c82-220">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="96c82-220">Related topics</span></span>

[<span data-ttu-id="96c82-221">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="96c82-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
