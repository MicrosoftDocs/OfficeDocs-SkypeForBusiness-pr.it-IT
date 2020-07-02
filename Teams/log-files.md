---
title: Usare i file di log in risoluzione dei problemi di Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 7ad44af297cdfe375f28485e1c4c4e223f616666
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012192"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="d42ed-103">Usare i file di log in risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d42ed-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="d42ed-104">Ci sono tre tipi di file di log prodotti automaticamente dal client che possono essere sfruttati per facilitare la risoluzione dei problemi di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="d42ed-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="d42ed-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="d42ed-105">Debug logs</span></span>

-   <span data-ttu-id="d42ed-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="d42ed-106">Media logs</span></span>

-   <span data-ttu-id="d42ed-107">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="d42ed-107">Desktop logs</span></span>

<span data-ttu-id="d42ed-108">Quando si crea una richiesta di supporto con il supporto Microsoft, il tecnico del supporto richiederà i registri di debug.</span><span class="sxs-lookup"><span data-stu-id="d42ed-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="d42ed-109">La presenza di questi log a mano prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="d42ed-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="d42ed-110">Gli elementi multimediali o i registri desktop sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d42ed-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="d42ed-111">La tabella seguente descrive i diversi client e i registri associati.</span><span class="sxs-lookup"><span data-stu-id="d42ed-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="d42ed-112">I file di log sono archiviati in posizioni specifiche per il client e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d42ed-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="d42ed-113">Client</span><span class="sxs-lookup"><span data-stu-id="d42ed-113">Client</span></span> |<span data-ttu-id="d42ed-114">Debug</span><span class="sxs-lookup"><span data-stu-id="d42ed-114">Debug</span></span>|<span data-ttu-id="d42ed-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="d42ed-115">Desktop</span></span>|<span data-ttu-id="d42ed-116">Elementi multimediali</span><span class="sxs-lookup"><span data-stu-id="d42ed-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="d42ed-117">Web</span><span class="sxs-lookup"><span data-stu-id="d42ed-117">Web</span></span>    |<span data-ttu-id="d42ed-118">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-118">X</span></span>         |-         |-         |
|<span data-ttu-id="d42ed-119">Windows</span><span class="sxs-lookup"><span data-stu-id="d42ed-119">Windows</span></span>     |<span data-ttu-id="d42ed-120">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-120">X</span></span>         |<span data-ttu-id="d42ed-121">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-121">X</span></span>         |<span data-ttu-id="d42ed-122">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-122">X</span></span>         |
|<span data-ttu-id="d42ed-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d42ed-123">Mac OSX</span></span>     |<span data-ttu-id="d42ed-124">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-124">X</span></span>         |<span data-ttu-id="d42ed-125">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-125">X</span></span>         |<span data-ttu-id="d42ed-126">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-126">X</span></span>         |
|<span data-ttu-id="d42ed-127">Linux</span><span class="sxs-lookup"><span data-stu-id="d42ed-127">Linux</span></span>     |<span data-ttu-id="d42ed-128">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-128">X</span></span>         |<span data-ttu-id="d42ed-129">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-129">X</span></span>         |<span data-ttu-id="d42ed-130">X</span><span class="sxs-lookup"><span data-stu-id="d42ed-130">X</span></span>         |
|<span data-ttu-id="d42ed-131">iOS</span><span class="sxs-lookup"><span data-stu-id="d42ed-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="d42ed-132">Android</span><span class="sxs-lookup"><span data-stu-id="d42ed-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="d42ed-133">Per un elenco completo di sistemi operativi e browser supportati, vedere [ottenere client per Microsoft teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d42ed-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="d42ed-134">Log di debug</span><span class="sxs-lookup"><span data-stu-id="d42ed-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="d42ed-135">Questi sono i registri più comuni e sono necessari per tutti i casi di supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d42ed-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="d42ed-136">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre ai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="d42ed-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="d42ed-137">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="d42ed-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="d42ed-138">Possono essere lette usando qualsiasi editor basato su testo e vengono creati nuovi log durante l'accesso al client.</span><span class="sxs-lookup"><span data-stu-id="d42ed-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="d42ed-139">I registri di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="d42ed-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="d42ed-140">Accesso</span><span class="sxs-lookup"><span data-stu-id="d42ed-140">Login</span></span>

-   <span data-ttu-id="d42ed-141">Richieste di connessione ai servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="d42ed-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="d42ed-142">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="d42ed-142">Call/conversation</span></span>

<span data-ttu-id="d42ed-143">I log di debug vengono prodotti usando i seguenti metodi specifici per il sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="d42ed-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="d42ed-144">Windows</span><span class="sxs-lookup"><span data-stu-id="d42ed-144">Windows:</span></span>

      <span data-ttu-id="d42ed-145">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="d42ed-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="d42ed-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="d42ed-146">Mac OSX:</span></span>

      <span data-ttu-id="d42ed-147">Tasto di scelta rapida: opzione + comando + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="d42ed-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="d42ed-148">Linux</span><span class="sxs-lookup"><span data-stu-id="d42ed-148">Linux:</span></span>

      <span data-ttu-id="d42ed-149">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="d42ed-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="d42ed-150">I log di debug vengono scaricati automaticamente nelle cartelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="d42ed-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="d42ed-151">Windows:% UserProfile% \\ download</span><span class="sxs-lookup"><span data-stu-id="d42ed-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="d42ed-152">Mac OSX: download</span><span class="sxs-lookup"><span data-stu-id="d42ed-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="d42ed-153">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="d42ed-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="d42ed-154">Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita</span><span class="sxs-lookup"><span data-stu-id="d42ed-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="d42ed-155">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="d42ed-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="d42ed-156">I registri multimediali contengono dati di diagnostica relativi alla condivisione audio, video e dello schermo.</span><span class="sxs-lookup"><span data-stu-id="d42ed-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="d42ed-157">Sono necessari per i casi di supporto solo su richiesta e possono essere controllati solo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d42ed-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="d42ed-158">La tabella seguente illustra la posizione del log.</span><span class="sxs-lookup"><span data-stu-id="d42ed-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="d42ed-159">Client</span><span class="sxs-lookup"><span data-stu-id="d42ed-159">Client</span></span> |<span data-ttu-id="d42ed-160">Posizione</span><span class="sxs-lookup"><span data-stu-id="d42ed-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="d42ed-161">Windows</span><span class="sxs-lookup"><span data-stu-id="d42ed-161">Windows</span></span>     |<span data-ttu-id="d42ed-162">%appdata%\Microsoft\Teams\media-stack \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="d42ed-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="d42ed-163">%appdata%\Microsoft\Teams\skylib \\ \*. Blog</span><span class="sxs-lookup"><span data-stu-id="d42ed-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="d42ed-164">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="d42ed-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="d42ed-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d42ed-165">Mac OSX</span></span>     |<span data-ttu-id="d42ed-166">~/Libreria/Application Support/Microsoft/teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="d42ed-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="d42ed-167">~/Libreria/Application Support/Microsoft/teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="d42ed-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="d42ed-168">Linux</span><span class="sxs-lookup"><span data-stu-id="d42ed-168">Linux</span></span>       |<span data-ttu-id="d42ed-169">~/.config/Microsoft/Microsoft teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="d42ed-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="d42ed-170">~/.config/Microsoft/Microsoft teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="d42ed-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="d42ed-171">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="d42ed-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="d42ed-172">I registri desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="d42ed-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="d42ed-173">Come i registri multimediali, questi registri sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d42ed-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="d42ed-174">I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato top-down.</span><span class="sxs-lookup"><span data-stu-id="d42ed-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="d42ed-175">Windows</span><span class="sxs-lookup"><span data-stu-id="d42ed-175">Windows:</span></span>

1.  <span data-ttu-id="d42ed-176">Fare clic con il pulsante destro del mouse sull'icona di **Microsoft teams** nella barra delle applicazioni, selezionare **Ottieni log**</span><span class="sxs-lookup"><span data-stu-id="d42ed-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="d42ed-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="d42ed-177">Mac OsX:</span></span>

1.  <span data-ttu-id="d42ed-178">Scegliere **Get logs** dal menu a discesa della **Guida**</span><span class="sxs-lookup"><span data-stu-id="d42ed-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="d42ed-179">Linux</span><span class="sxs-lookup"><span data-stu-id="d42ed-179">Linux:</span></span>

1.  <span data-ttu-id="d42ed-180">Fare clic sull'icona **Microsoft teams** nella barra delle applicazioni, selezionare **Get logs**</span><span class="sxs-lookup"><span data-stu-id="d42ed-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="d42ed-181">Client</span><span class="sxs-lookup"><span data-stu-id="d42ed-181">Client</span></span> |<span data-ttu-id="d42ed-182">Posizione</span><span class="sxs-lookup"><span data-stu-id="d42ed-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="d42ed-183">Windows</span><span class="sxs-lookup"><span data-stu-id="d42ed-183">Windows</span></span>     |<span data-ttu-id="d42ed-184">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="d42ed-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="d42ed-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d42ed-185">Mac OSX</span></span>     |<span data-ttu-id="d42ed-186">~/Libreria/Application Support/Microsoft/teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="d42ed-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="d42ed-187">Linux</span><span class="sxs-lookup"><span data-stu-id="d42ed-187">Linux</span></span>       |<span data-ttu-id="d42ed-188">~/.config/Microsoft/Microsoft teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="d42ed-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |
