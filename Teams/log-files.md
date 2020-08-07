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
ms.openlocfilehash: f13acc1a401a6753b335c17fe0cd8a7984849216
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582109"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="0de87-103">Usare i file di log in risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0de87-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="0de87-104">Ci sono tre tipi di file di log prodotti automaticamente dal client che possono essere sfruttati per facilitare la risoluzione dei problemi di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0de87-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="0de87-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="0de87-105">Debug logs</span></span>

-   <span data-ttu-id="0de87-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="0de87-106">Media logs</span></span>

-   <span data-ttu-id="0de87-107">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="0de87-107">Desktop logs</span></span>

<span data-ttu-id="0de87-108">Quando si crea una richiesta di supporto con il supporto Microsoft, il tecnico del supporto richiederà i registri di debug.</span><span class="sxs-lookup"><span data-stu-id="0de87-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="0de87-109">La presenza di questi log a mano prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="0de87-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="0de87-110">Gli elementi multimediali o i registri desktop sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0de87-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="0de87-111">La tabella seguente descrive i diversi client e i registri associati.</span><span class="sxs-lookup"><span data-stu-id="0de87-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="0de87-112">I file di log sono archiviati in posizioni specifiche per il client e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0de87-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="0de87-113">Client</span><span class="sxs-lookup"><span data-stu-id="0de87-113">Client</span></span> |<span data-ttu-id="0de87-114">Debug</span><span class="sxs-lookup"><span data-stu-id="0de87-114">Debug</span></span>|<span data-ttu-id="0de87-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="0de87-115">Desktop</span></span>|<span data-ttu-id="0de87-116">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="0de87-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="0de87-117">Web</span><span class="sxs-lookup"><span data-stu-id="0de87-117">Web</span></span>    |<span data-ttu-id="0de87-118">X</span><span class="sxs-lookup"><span data-stu-id="0de87-118">X</span></span>         |-         |-         |
|<span data-ttu-id="0de87-119">Windows</span><span class="sxs-lookup"><span data-stu-id="0de87-119">Windows</span></span>     |<span data-ttu-id="0de87-120">X</span><span class="sxs-lookup"><span data-stu-id="0de87-120">X</span></span>         |<span data-ttu-id="0de87-121">X</span><span class="sxs-lookup"><span data-stu-id="0de87-121">X</span></span>         |<span data-ttu-id="0de87-122">X</span><span class="sxs-lookup"><span data-stu-id="0de87-122">X</span></span>         |
|<span data-ttu-id="0de87-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="0de87-123">Mac OSX</span></span>     |<span data-ttu-id="0de87-124">X</span><span class="sxs-lookup"><span data-stu-id="0de87-124">X</span></span>         |<span data-ttu-id="0de87-125">X</span><span class="sxs-lookup"><span data-stu-id="0de87-125">X</span></span>         |<span data-ttu-id="0de87-126">X</span><span class="sxs-lookup"><span data-stu-id="0de87-126">X</span></span>         |
|<span data-ttu-id="0de87-127">Linux</span><span class="sxs-lookup"><span data-stu-id="0de87-127">Linux</span></span>     |<span data-ttu-id="0de87-128">X</span><span class="sxs-lookup"><span data-stu-id="0de87-128">X</span></span>         |<span data-ttu-id="0de87-129">X</span><span class="sxs-lookup"><span data-stu-id="0de87-129">X</span></span>         |<span data-ttu-id="0de87-130">X</span><span class="sxs-lookup"><span data-stu-id="0de87-130">X</span></span>         |
|<span data-ttu-id="0de87-131">iOS</span><span class="sxs-lookup"><span data-stu-id="0de87-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="0de87-132">Android</span><span class="sxs-lookup"><span data-stu-id="0de87-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="0de87-133">Per un elenco completo di sistemi operativi e browser supportati, vedere [ottenere client per Microsoft teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0de87-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="0de87-134">Log di debug</span><span class="sxs-lookup"><span data-stu-id="0de87-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="0de87-135">Questi sono i registri più comuni e sono necessari per tutti i casi di supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0de87-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="0de87-136">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre ai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="0de87-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="0de87-137">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="0de87-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="0de87-138">Possono essere lette usando qualsiasi editor basato su testo e vengono creati nuovi log durante l'accesso al client.</span><span class="sxs-lookup"><span data-stu-id="0de87-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="0de87-139">I registri di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="0de87-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="0de87-140">Accesso</span><span class="sxs-lookup"><span data-stu-id="0de87-140">Login</span></span>

-   <span data-ttu-id="0de87-141">Richieste di connessione ai servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="0de87-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="0de87-142">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="0de87-142">Call/conversation</span></span>

<span data-ttu-id="0de87-143">I log di debug vengono prodotti usando i seguenti metodi specifici per il sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="0de87-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="0de87-144">Windows</span><span class="sxs-lookup"><span data-stu-id="0de87-144">Windows:</span></span>

      <span data-ttu-id="0de87-145">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="0de87-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="0de87-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="0de87-146">Mac OSX:</span></span>

      <span data-ttu-id="0de87-147">Tasto di scelta rapida: opzione + comando + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="0de87-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="0de87-148">Linux</span><span class="sxs-lookup"><span data-stu-id="0de87-148">Linux:</span></span>

      <span data-ttu-id="0de87-149">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="0de87-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="0de87-150">I log di debug vengono scaricati automaticamente nelle cartelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="0de87-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="0de87-151">Windows:% UserProfile% \\ download</span><span class="sxs-lookup"><span data-stu-id="0de87-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="0de87-152">Mac OSX: download</span><span class="sxs-lookup"><span data-stu-id="0de87-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="0de87-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="0de87-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="0de87-154">Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita</span><span class="sxs-lookup"><span data-stu-id="0de87-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="0de87-155">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="0de87-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="0de87-156">I registri multimediali contengono dati di diagnostica relativi alla condivisione audio, video e dello schermo.</span><span class="sxs-lookup"><span data-stu-id="0de87-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="0de87-157">Sono necessari per i casi di supporto solo su richiesta e possono essere controllati solo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0de87-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="0de87-158">La tabella seguente illustra la posizione del log.</span><span class="sxs-lookup"><span data-stu-id="0de87-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="0de87-159">Client</span><span class="sxs-lookup"><span data-stu-id="0de87-159">Client</span></span> |<span data-ttu-id="0de87-160">Posizione</span><span class="sxs-lookup"><span data-stu-id="0de87-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="0de87-161">Windows</span><span class="sxs-lookup"><span data-stu-id="0de87-161">Windows</span></span>     |<span data-ttu-id="0de87-162">%appdata%\Microsoft\Teams\media-stack \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="0de87-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="0de87-163">%appdata%\Microsoft\Teams\skylib \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="0de87-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="0de87-164">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="0de87-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="0de87-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="0de87-165">Mac OSX</span></span>     |<span data-ttu-id="0de87-166">~/Libreria/Application Support/Microsoft/teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="0de87-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="0de87-167">~/Libreria/Application Support/Microsoft/teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="0de87-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="0de87-168">Linux</span><span class="sxs-lookup"><span data-stu-id="0de87-168">Linux</span></span>       |<span data-ttu-id="0de87-169">~/.config/Microsoft/Microsoft teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="0de87-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="0de87-170">~/.config/Microsoft/Microsoft teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="0de87-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="0de87-171">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="0de87-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="0de87-172">I registri desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="0de87-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="0de87-173">Come i registri multimediali, questi registri sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0de87-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="0de87-174">I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato top-down.</span><span class="sxs-lookup"><span data-stu-id="0de87-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="0de87-175">Windows</span><span class="sxs-lookup"><span data-stu-id="0de87-175">Windows:</span></span>

1.  <span data-ttu-id="0de87-176">Fare clic con il pulsante destro del mouse sull'icona di **Microsoft teams** nella barra delle applicazioni, selezionare **Ottieni log**</span><span class="sxs-lookup"><span data-stu-id="0de87-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="0de87-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="0de87-177">Mac OsX:</span></span>

1.  <span data-ttu-id="0de87-178">Scegliere **Get logs** dal menu a discesa della **Guida**</span><span class="sxs-lookup"><span data-stu-id="0de87-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="0de87-179">Linux</span><span class="sxs-lookup"><span data-stu-id="0de87-179">Linux:</span></span>

1.  <span data-ttu-id="0de87-180">Fare clic sull'icona **Microsoft teams** nella barra delle applicazioni, selezionare **Get logs**</span><span class="sxs-lookup"><span data-stu-id="0de87-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="0de87-181">Client</span><span class="sxs-lookup"><span data-stu-id="0de87-181">Client</span></span> |<span data-ttu-id="0de87-182">Posizione</span><span class="sxs-lookup"><span data-stu-id="0de87-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="0de87-183">Windows</span><span class="sxs-lookup"><span data-stu-id="0de87-183">Windows</span></span>     |<span data-ttu-id="0de87-184">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="0de87-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="0de87-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="0de87-185">Mac OSX</span></span>     |<span data-ttu-id="0de87-186">~/Libreria/Application Support/Microsoft/teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="0de87-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="0de87-187">Linux</span><span class="sxs-lookup"><span data-stu-id="0de87-187">Linux</span></span>       |<span data-ttu-id="0de87-188">~/.config/Microsoft/Microsoft teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="0de87-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="0de87-189">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0de87-189">Related topics</span></span>

[<span data-ttu-id="0de87-190">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="0de87-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

