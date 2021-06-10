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
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689694"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="76400-103">Usare i file di log per monitorare e risolvere i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76400-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="76400-104">Esistono tre tipi di file di log prodotti automaticamente dal client, che possono essere utilizzati per agevolare il monitoraggio e la risoluzione dei Teams:</span><span class="sxs-lookup"><span data-stu-id="76400-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="76400-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="76400-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="76400-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="76400-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="76400-107">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="76400-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="76400-108">Questo articolo descrive questi log e come vengono usati.</span><span class="sxs-lookup"><span data-stu-id="76400-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="76400-109">Per informazioni sulla risoluzione di problemi specifici, vedere: Teams [risoluzione dei problemi](/MicrosoftTeams/troubleshoot/teams).</span><span class="sxs-lookup"><span data-stu-id="76400-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="76400-110">Per informazioni su come contattare il supporto, vedere [Ottenere supporto.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="76400-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="76400-111">Quando si crea una richiesta di supporto con il supporto tecnico Microsoft, il tecnico del supporto richiederà i log di debug.</span><span class="sxs-lookup"><span data-stu-id="76400-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="76400-112">Avere a disposizione i log di debug prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="76400-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="76400-113">**I** registri multimediali **o** desktop sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76400-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="76400-114">In questo articolo il termine **Log di debug** fa riferimento ai log usati per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="76400-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="76400-115">Tuttavia, i file generati per questi log conterranno il termine **log di diagnostica** nei nomi.</span><span class="sxs-lookup"><span data-stu-id="76400-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="76400-116">Raccogliere e abilitare la registrazione</span><span class="sxs-lookup"><span data-stu-id="76400-116">Collect and enable logging</span></span>

<span data-ttu-id="76400-117">È importante raccogliere i log non appena si verifica un problema.</span><span class="sxs-lookup"><span data-stu-id="76400-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="76400-118">I log possono essere raccolti insieme a un paio di clic.</span><span class="sxs-lookup"><span data-stu-id="76400-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="76400-119">Windows: fare clic con il pulsante destro del mouse sull'icona Teams sulla barra delle applicazioni e scegliere **Raccolta file di supporto.**</span><span class="sxs-lookup"><span data-stu-id="76400-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="76400-120">Mac: selezionare il menu ? e scegliere **Raccogli file di supporto.**</span><span class="sxs-lookup"><span data-stu-id="76400-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="76400-121">I log di debug, desktop e multimediali verranno raccolti in un'unica cartella con il nome MSTeams Diagnostics <local data and time> Log.</span><span class="sxs-lookup"><span data-stu-id="76400-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="76400-122">Questa cartella può essere compressa e condivisa quando si apre una richiesta di supporto con il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76400-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="76400-123">La cartella conterrà cartelle per Desktop, Riunione (elementi multimediali) e Debug (Web).</span><span class="sxs-lookup"><span data-stu-id="76400-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="76400-124">È possibile raccogliere i file usando le scelte rapide da tastiera seguenti:</span><span class="sxs-lookup"><span data-stu-id="76400-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="76400-125">Windows: Crtl + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="76400-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="76400-126">Mac: OPZIONE+ COMANDO + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="76400-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="76400-127">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76400-127">Media logging is turned off by default.</span></span> <span data-ttu-id="76400-128">Per abilitare la registrazione multimediale, gli utenti devono attivare l'opzione nel client Teams dati.</span><span class="sxs-lookup"><span data-stu-id="76400-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="76400-129">Passare a **Impostazioni** Generale e selezionare Abilita registrazione per diagnostica riunione  >   **(è necessario riavviare Teams).**</span><span class="sxs-lookup"><span data-stu-id="76400-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="76400-130">Il Teams client deve essere riavviato per avviare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="76400-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="76400-131">Se la registrazione multimediale è abilitata, nella cartella Riunione saranno inclusi altri file necessari per analizzare i problemi audio e video.</span><span class="sxs-lookup"><span data-stu-id="76400-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="76400-132">Se la registrazione multimediale non è abilitata, sarà disponibile un numero limitato di log.</span><span class="sxs-lookup"><span data-stu-id="76400-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="76400-133">La tabella seguente descrive i vari client e i log associati.</span><span class="sxs-lookup"><span data-stu-id="76400-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="76400-134">I file di log vengono archiviati in posizioni specifiche del client e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="76400-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="76400-135">Client</span><span class="sxs-lookup"><span data-stu-id="76400-135">Client</span></span> |<span data-ttu-id="76400-136">Debug</span><span class="sxs-lookup"><span data-stu-id="76400-136">Debug</span></span>|<span data-ttu-id="76400-137">Desktop</span><span class="sxs-lookup"><span data-stu-id="76400-137">Desktop</span></span>|<span data-ttu-id="76400-138">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="76400-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="76400-139">Web</span><span class="sxs-lookup"><span data-stu-id="76400-139">Web</span></span>    |<span data-ttu-id="76400-140">X</span><span class="sxs-lookup"><span data-stu-id="76400-140">X</span></span>         |-         |-         |
|<span data-ttu-id="76400-141">Windows</span><span class="sxs-lookup"><span data-stu-id="76400-141">Windows</span></span>     |<span data-ttu-id="76400-142">X</span><span class="sxs-lookup"><span data-stu-id="76400-142">X</span></span>         |<span data-ttu-id="76400-143">X</span><span class="sxs-lookup"><span data-stu-id="76400-143">X</span></span>         |<span data-ttu-id="76400-144">X</span><span class="sxs-lookup"><span data-stu-id="76400-144">X</span></span>         |
|<span data-ttu-id="76400-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="76400-145">Mac OSX</span></span>     |<span data-ttu-id="76400-146">X</span><span class="sxs-lookup"><span data-stu-id="76400-146">X</span></span>         |<span data-ttu-id="76400-147">X</span><span class="sxs-lookup"><span data-stu-id="76400-147">X</span></span>         |<span data-ttu-id="76400-148">X</span><span class="sxs-lookup"><span data-stu-id="76400-148">X</span></span>         |
|<span data-ttu-id="76400-149">Linux</span><span class="sxs-lookup"><span data-stu-id="76400-149">Linux</span></span>     |<span data-ttu-id="76400-150">X</span><span class="sxs-lookup"><span data-stu-id="76400-150">X</span></span>         |<span data-ttu-id="76400-151">X</span><span class="sxs-lookup"><span data-stu-id="76400-151">X</span></span>         |<span data-ttu-id="76400-152">X</span><span class="sxs-lookup"><span data-stu-id="76400-152">X</span></span>         |
|<span data-ttu-id="76400-153">iOS</span><span class="sxs-lookup"><span data-stu-id="76400-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="76400-154">Android</span><span class="sxs-lookup"><span data-stu-id="76400-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="76400-155">Per un elenco completo dei sistemi operativi e dei browser supportati, vedere Ottenere [i client per Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="76400-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="76400-156">Log di debug</span><span class="sxs-lookup"><span data-stu-id="76400-156">Debug logs</span></span>

<span data-ttu-id="76400-157">Vedere la _sezione Raccogliere e abilitare la registrazione_ per Windows istruzioni per Mac.</span><span class="sxs-lookup"><span data-stu-id="76400-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="76400-158">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre che dai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="76400-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="76400-159">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="76400-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="76400-160">Possono essere letti con qualsiasi editor basato su testo e i nuovi log vengono creati quando si accede al client.</span><span class="sxs-lookup"><span data-stu-id="76400-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="76400-161">I log di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="76400-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="76400-162">Accesso</span><span class="sxs-lookup"><span data-stu-id="76400-162">Login</span></span>

-   <span data-ttu-id="76400-163">Richieste di connessione a servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="76400-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="76400-164">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="76400-164">Call/conversation</span></span>

<span data-ttu-id="76400-165">Per raccogliere log per Linux: Scelta rapida da tastiera: CTRL+ALT+MAIUSC+1 I file saranno disponibili in ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="76400-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="76400-166">Per raccogliere i log per il browser: Scelta rapida da tastiera: Crtl + ALT + MAIUSC + 1 I file saranno disponibili in %userprofile%\Downloads</span><span class="sxs-lookup"><span data-stu-id="76400-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="76400-167">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="76400-167">Media logs</span></span>

<span data-ttu-id="76400-168">Vedere la _sezione Raccogliere e abilitare la registrazione_ per Windows istruzioni per Mac.</span><span class="sxs-lookup"><span data-stu-id="76400-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="76400-169">I log multimediali contengono dati diagnostici relativi a audio, video e condivisione dello schermo nelle Teams riunioni.</span><span class="sxs-lookup"><span data-stu-id="76400-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="76400-170">Sono necessari per i casi di supporto collegati a problemi relativi alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="76400-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="76400-171">La registrazione multimediale è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76400-171">Media logging is turned off by default.</span></span> <span data-ttu-id="76400-172">Per registrare i dati di diagnostica Teams riunioni, gli utenti devono attivare l'opzione nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="76400-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="76400-173">Passare a **Impostazioni** Generale , selezionare la casella di controllo Abilita registrazione per diagnostica riunione (è necessario riavviare Teams ), riavviare Teams e riprodurre  >  il problema. </span><span class="sxs-lookup"><span data-stu-id="76400-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="76400-174">Quando si inviano i file di log al supporto tecnico Microsoft, verificare il timestamp dei file di log per assicurarsi che i log copriranno l'intervallo di tempo in cui è stato riprodotto il problema.</span><span class="sxs-lookup"><span data-stu-id="76400-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="76400-175">Per raccogliere log per Linux: i file saranno disponibili in ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog e *~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span><span class="sxs-lookup"><span data-stu-id="76400-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="76400-176">Ecco un elenco dei file di log generati e delle informazioni che contengono.</span><span class="sxs-lookup"><span data-stu-id="76400-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="76400-177">Nome file di log</span><span class="sxs-lookup"><span data-stu-id="76400-177">Log file name</span></span>  |<span data-ttu-id="76400-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76400-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="76400-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="76400-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="76400-180">Contiene informazioni correlate allo stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="76400-180">Contains information related to the media stack.</span></span> <span data-ttu-id="76400-181">Sono inclusi lo stato del canale, ad esempio risoluzione, decodificatori e codificatori usati, il numero di frame inviati e ricevuti e lo stato della sessione di condivisione dello schermo basata su video e fotocamera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="76400-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="76400-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="76400-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="76400-183">Registra le informazioni relative alle azioni di controllo remoto, ad esempio l'indicatore data e ora quando viene fornito il controllo, e le informazioni sul puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="76400-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="76400-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="76400-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="76400-185">Registra gli eventi di traccia dello stack multimediale.</span><span class="sxs-lookup"><span data-stu-id="76400-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="76400-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="76400-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="76400-187">Contiene informazioni relative all'agente multimediale, inclusa la qualità del rendering.</span><span class="sxs-lookup"><span data-stu-id="76400-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="76400-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="76400-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="76400-189">Registra gli eventi nell'API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="76400-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="76400-190">Log del desktop</span><span class="sxs-lookup"><span data-stu-id="76400-190">Desktop logs</span></span>

<span data-ttu-id="76400-191">Vedere la _sezione Raccogliere e abilitare la registrazione_ per Windows istruzioni per Mac.</span><span class="sxs-lookup"><span data-stu-id="76400-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="76400-192">I log desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="76400-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="76400-193">Come i log multimediali, questi log sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76400-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="76400-194">I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="76400-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="76400-195">Per raccogliere i log per Linux: fare clic sull'icona Microsoft Teams sulla barra delle applicazioni e selezionare **Recupera registri**.</span><span class="sxs-lookup"><span data-stu-id="76400-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="76400-196">I file saranno disponibili in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span><span class="sxs-lookup"><span data-stu-id="76400-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="76400-197">Traccia del browser</span><span class="sxs-lookup"><span data-stu-id="76400-197">Browser trace</span></span>

<span data-ttu-id="76400-198">Per alcune categorie di errori, il supporto Tecnico Microsoft potrebbe richiedere la raccolta di una traccia del browser.</span><span class="sxs-lookup"><span data-stu-id="76400-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="76400-199">Queste informazioni possono fornire dettagli importanti sullo stato del client Teams client quando si verifica l'errore.</span><span class="sxs-lookup"><span data-stu-id="76400-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="76400-200">Prima di avviare la traccia del browser, assicurarsi di aver eseguito l'accesso a Teams.</span><span class="sxs-lookup"><span data-stu-id="76400-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="76400-201">È importante eseguire questa operazione prima di avviare la traccia in modo che la traccia non contenga informazioni di accesso riservate.</span><span class="sxs-lookup"><span data-stu-id="76400-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="76400-202">Dopo aver eseguito l'accesso, selezionare uno dei collegamenti seguenti, in base alle esigenze del browser, e seguire la procedura fornita.</span><span class="sxs-lookup"><span data-stu-id="76400-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="76400-203">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="76400-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="76400-204">Edge</span><span class="sxs-lookup"><span data-stu-id="76400-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="76400-205">Safari</span><span class="sxs-lookup"><span data-stu-id="76400-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="76400-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="76400-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="76400-207">Nei passaggi sostituire tutti i riferimenti al portale di Azure con il Teams client.</span><span class="sxs-lookup"><span data-stu-id="76400-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="76400-208">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="76400-208">Related topics</span></span>

[<span data-ttu-id="76400-209">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="76400-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
