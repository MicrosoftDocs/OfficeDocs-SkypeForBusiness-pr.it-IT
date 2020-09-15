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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766760"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="938cd-103">Usare i file di log in risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="938cd-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="938cd-104">Ci sono tre tipi di file di log prodotti automaticamente dal client che possono essere sfruttati per facilitare la risoluzione dei problemi di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="938cd-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="938cd-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="938cd-105">Debug logs</span></span>

-   <span data-ttu-id="938cd-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="938cd-106">Media logs</span></span>

-   <span data-ttu-id="938cd-107">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="938cd-107">Desktop logs</span></span>

<span data-ttu-id="938cd-108">Quando si crea una richiesta di supporto con il supporto Microsoft, il tecnico del supporto richiederà i registri di debug.</span><span class="sxs-lookup"><span data-stu-id="938cd-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="938cd-109">La presenza di questi log a mano prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="938cd-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="938cd-110">Gli elementi multimediali o i registri desktop sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="938cd-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="938cd-111">La tabella seguente descrive i diversi client e i registri associati.</span><span class="sxs-lookup"><span data-stu-id="938cd-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="938cd-112">I file di log sono archiviati in posizioni specifiche per il client e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="938cd-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="938cd-113">Client</span><span class="sxs-lookup"><span data-stu-id="938cd-113">Client</span></span> |<span data-ttu-id="938cd-114">Debug</span><span class="sxs-lookup"><span data-stu-id="938cd-114">Debug</span></span>|<span data-ttu-id="938cd-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="938cd-115">Desktop</span></span>|<span data-ttu-id="938cd-116">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="938cd-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="938cd-117">Web</span><span class="sxs-lookup"><span data-stu-id="938cd-117">Web</span></span>    |<span data-ttu-id="938cd-118">X</span><span class="sxs-lookup"><span data-stu-id="938cd-118">X</span></span>         |-         |-         |
|<span data-ttu-id="938cd-119">Windows</span><span class="sxs-lookup"><span data-stu-id="938cd-119">Windows</span></span>     |<span data-ttu-id="938cd-120">X</span><span class="sxs-lookup"><span data-stu-id="938cd-120">X</span></span>         |<span data-ttu-id="938cd-121">X</span><span class="sxs-lookup"><span data-stu-id="938cd-121">X</span></span>         |<span data-ttu-id="938cd-122">X</span><span class="sxs-lookup"><span data-stu-id="938cd-122">X</span></span>         |
|<span data-ttu-id="938cd-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="938cd-123">Mac OSX</span></span>     |<span data-ttu-id="938cd-124">X</span><span class="sxs-lookup"><span data-stu-id="938cd-124">X</span></span>         |<span data-ttu-id="938cd-125">X</span><span class="sxs-lookup"><span data-stu-id="938cd-125">X</span></span>         |<span data-ttu-id="938cd-126">X</span><span class="sxs-lookup"><span data-stu-id="938cd-126">X</span></span>         |
|<span data-ttu-id="938cd-127">Linux</span><span class="sxs-lookup"><span data-stu-id="938cd-127">Linux</span></span>     |<span data-ttu-id="938cd-128">X</span><span class="sxs-lookup"><span data-stu-id="938cd-128">X</span></span>         |<span data-ttu-id="938cd-129">X</span><span class="sxs-lookup"><span data-stu-id="938cd-129">X</span></span>         |<span data-ttu-id="938cd-130">X</span><span class="sxs-lookup"><span data-stu-id="938cd-130">X</span></span>         |
|<span data-ttu-id="938cd-131">iOS</span><span class="sxs-lookup"><span data-stu-id="938cd-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="938cd-132">Android</span><span class="sxs-lookup"><span data-stu-id="938cd-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="938cd-133">Per un elenco completo di sistemi operativi e browser supportati, vedere [ottenere client per Microsoft teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="938cd-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="938cd-134">Log di debug</span><span class="sxs-lookup"><span data-stu-id="938cd-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="938cd-135">Questi sono i registri più comuni e sono necessari per tutti i casi di supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="938cd-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="938cd-136">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre ai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="938cd-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="938cd-137">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="938cd-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="938cd-138">Possono essere lette usando qualsiasi editor basato su testo e vengono creati nuovi log durante l'accesso al client.</span><span class="sxs-lookup"><span data-stu-id="938cd-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="938cd-139">I registri di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="938cd-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="938cd-140">Accesso</span><span class="sxs-lookup"><span data-stu-id="938cd-140">Login</span></span>

-   <span data-ttu-id="938cd-141">Richieste di connessione ai servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="938cd-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="938cd-142">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="938cd-142">Call/conversation</span></span>

<span data-ttu-id="938cd-143">I log di debug vengono prodotti usando i seguenti metodi specifici per il sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="938cd-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="938cd-144">Windows</span><span class="sxs-lookup"><span data-stu-id="938cd-144">Windows:</span></span>

      <span data-ttu-id="938cd-145">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="938cd-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="938cd-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="938cd-146">Mac OSX:</span></span>

      <span data-ttu-id="938cd-147">Tasto di scelta rapida: opzione + comando + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="938cd-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="938cd-148">Linux</span><span class="sxs-lookup"><span data-stu-id="938cd-148">Linux:</span></span>

      <span data-ttu-id="938cd-149">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="938cd-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="938cd-150">I log di debug vengono scaricati automaticamente nelle cartelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="938cd-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="938cd-151">Windows:% UserProfile% \\ download</span><span class="sxs-lookup"><span data-stu-id="938cd-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="938cd-152">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="938cd-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="938cd-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="938cd-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="938cd-154">Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita</span><span class="sxs-lookup"><span data-stu-id="938cd-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="938cd-155">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="938cd-155">Media logs</span></span>
---------------------------

<span data-ttu-id="938cd-156">I registri multimediali contengono dati di diagnostica relativi alla condivisione di audio, video e schermo nelle riunioni di teams.</span><span class="sxs-lookup"><span data-stu-id="938cd-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="938cd-157">Sono necessari per i casi di supporto solo su richiesta e possono essere controllati solo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="938cd-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> 

<span data-ttu-id="938cd-158">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="938cd-158">Media logging is turned off by default.</span></span> <span data-ttu-id="938cd-159">Per registrare i dati di diagnostica per le riunioni di teams, gli utenti devono attivare l'opzione nel client teams.</span><span class="sxs-lookup"><span data-stu-id="938cd-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="938cd-160">Accedere a **Impostazioni**  >  **generali**, selezionare la casella di controllo **Abilita registrazione per la diagnostica riunione (richiede**il riavvio di Team) e quindi riavviare teams.</span><span class="sxs-lookup"><span data-stu-id="938cd-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams.</span></span>

<span data-ttu-id="938cd-161">La tabella seguente illustra le posizioni dei log.</span><span class="sxs-lookup"><span data-stu-id="938cd-161">The following table outlines the log locations.</span></span>

|<span data-ttu-id="938cd-162">Client</span><span class="sxs-lookup"><span data-stu-id="938cd-162">Client</span></span> |<span data-ttu-id="938cd-163">Posizione</span><span class="sxs-lookup"><span data-stu-id="938cd-163">Location</span></span> |
|---------|---------|
|<span data-ttu-id="938cd-164">Windows</span><span class="sxs-lookup"><span data-stu-id="938cd-164">Windows</span></span>     |<span data-ttu-id="938cd-165">%appdata%\Microsoft\Teams\media-stack \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-165">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="938cd-166">%appdata%\Microsoft\Teams\skylib \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-166">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="938cd-167">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="938cd-167">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="938cd-168">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="938cd-168">Mac OSX</span></span>     |<span data-ttu-id="938cd-169">~/Libreria/Application Support/Microsoft/teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-169">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="938cd-170">~/Libreria/Application Support/Microsoft/teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-170">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="938cd-171">Linux</span><span class="sxs-lookup"><span data-stu-id="938cd-171">Linux</span></span>       |<span data-ttu-id="938cd-172">~/.config/Microsoft/Microsoft teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-172">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="938cd-173">~/.config/Microsoft/Microsoft teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-173">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="938cd-174">Ecco un elenco dei file di log generati e delle informazioni che contengono.</span><span class="sxs-lookup"><span data-stu-id="938cd-174">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="938cd-175">Nome file di log</span><span class="sxs-lookup"><span data-stu-id="938cd-175">Log file name</span></span>  |<span data-ttu-id="938cd-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="938cd-176">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="938cd-177">Teams. MSRTC-0-s1039525249. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-177">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="938cd-178">Contiene informazioni correlate allo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="938cd-178">Contains information related to the media stack.</span></span> <span data-ttu-id="938cd-179">Questo include lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, nonché il numero di fotogrammi inviati e ricevuti e lo stato della sessione di condivisione dello schermo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="938cd-179">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="938cd-180">rtmcontrol. MSRTC-0-2415069487. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-180">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="938cd-181">Registra le informazioni relative alle azioni del controllo remoto, ad esempio l'indicatore di data e ora in cui viene assegnato il controllo, e le informazioni del puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="938cd-181">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="938cd-182">Teams_MediaStackETW -2-U-xr-U. etl</span><span class="sxs-lookup"><span data-stu-id="938cd-182">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="938cd-183">Registra gli eventi di traccia dello stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="938cd-183">Records media stack trace events.</span></span>         |
|<span data-ttu-id="938cd-184">Debug-0-s2790420889. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-184">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="938cd-185">Contiene informazioni correlate all'agente multimediale, inclusa la qualità del rendering.</span><span class="sxs-lookup"><span data-stu-id="938cd-185">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="938cd-186">tscalling-0-2061129496. Blog</span><span class="sxs-lookup"><span data-stu-id="938cd-186">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="938cd-187">Registra gli eventi nell'API di chiamata TS.</span><span class="sxs-lookup"><span data-stu-id="938cd-187">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="938cd-188">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="938cd-188">Desktop logs</span></span>
---------------------

<span data-ttu-id="938cd-189">I registri desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="938cd-189">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="938cd-190">Come i registri multimediali, questi registri sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="938cd-190">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="938cd-191">I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato top-down.</span><span class="sxs-lookup"><span data-stu-id="938cd-191">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="938cd-192">Windows</span><span class="sxs-lookup"><span data-stu-id="938cd-192">Windows:</span></span>

1.  <span data-ttu-id="938cd-193">Fare clic con il pulsante destro del mouse sull'icona di **Microsoft teams** nella barra delle applicazioni, selezionare **Ottieni log**</span><span class="sxs-lookup"><span data-stu-id="938cd-193">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="938cd-194">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="938cd-194">Mac OsX:</span></span>

1.  <span data-ttu-id="938cd-195">Scegliere **Get logs** dal menu a discesa della **Guida**</span><span class="sxs-lookup"><span data-stu-id="938cd-195">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="938cd-196">Linux</span><span class="sxs-lookup"><span data-stu-id="938cd-196">Linux:</span></span>

1.  <span data-ttu-id="938cd-197">Fare clic sull'icona **Microsoft teams** nella barra delle applicazioni, selezionare **Get logs**</span><span class="sxs-lookup"><span data-stu-id="938cd-197">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="938cd-198">Client</span><span class="sxs-lookup"><span data-stu-id="938cd-198">Client</span></span> |<span data-ttu-id="938cd-199">Posizione</span><span class="sxs-lookup"><span data-stu-id="938cd-199">Location</span></span> |
|---------|---------|
|<span data-ttu-id="938cd-200">Windows</span><span class="sxs-lookup"><span data-stu-id="938cd-200">Windows</span></span>     |<span data-ttu-id="938cd-201">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="938cd-201">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="938cd-202">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="938cd-202">Mac OSX</span></span>     |<span data-ttu-id="938cd-203">~/Libreria/Application Support/Microsoft/teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="938cd-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="938cd-204">Linux</span><span class="sxs-lookup"><span data-stu-id="938cd-204">Linux</span></span>       |<span data-ttu-id="938cd-205">~/.config/Microsoft/Microsoft teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="938cd-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="938cd-206">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="938cd-206">Related topics</span></span>

[<span data-ttu-id="938cd-207">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="938cd-207">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

