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
ms.openlocfilehash: 2c8da7e60e785d765e77e17935b60382e864a83b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833376"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="aedbf-103">Usare i file di log in risoluzione dei problemi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aedbf-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="aedbf-104">Ci sono tre tipi di file di log prodotti automaticamente dal client che possono essere sfruttati per facilitare la risoluzione dei problemi di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="aedbf-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="aedbf-105">Log di debug</span><span class="sxs-lookup"><span data-stu-id="aedbf-105">Debug logs</span></span>

-   <span data-ttu-id="aedbf-106">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="aedbf-106">Media logs</span></span>

-   <span data-ttu-id="aedbf-107">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="aedbf-107">Desktop logs</span></span>

<span data-ttu-id="aedbf-108">Quando si crea una richiesta di supporto con il supporto Microsoft, il tecnico del supporto richiederà i registri di debug.</span><span class="sxs-lookup"><span data-stu-id="aedbf-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="aedbf-109">La presenza di questi log a mano prima di creare la richiesta di supporto consentirà a Microsoft di iniziare rapidamente la risoluzione del problema.</span><span class="sxs-lookup"><span data-stu-id="aedbf-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="aedbf-110">Gli elementi multimediali o i registri desktop sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aedbf-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="aedbf-111">La tabella seguente descrive i diversi client e i registri associati.</span><span class="sxs-lookup"><span data-stu-id="aedbf-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="aedbf-112">I file di log sono archiviati in posizioni specifiche per il client e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="aedbf-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="aedbf-113">Client</span><span class="sxs-lookup"><span data-stu-id="aedbf-113">Client</span></span> |<span data-ttu-id="aedbf-114">Debug</span><span class="sxs-lookup"><span data-stu-id="aedbf-114">Debug</span></span>|<span data-ttu-id="aedbf-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="aedbf-115">Desktop</span></span>|<span data-ttu-id="aedbf-116">Contenuti multimediali</span><span class="sxs-lookup"><span data-stu-id="aedbf-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="aedbf-117">Web</span><span class="sxs-lookup"><span data-stu-id="aedbf-117">Web</span></span>    |<span data-ttu-id="aedbf-118">X</span><span class="sxs-lookup"><span data-stu-id="aedbf-118">X</span></span>         |-         |-         |
|<span data-ttu-id="aedbf-119">Windows</span><span class="sxs-lookup"><span data-stu-id="aedbf-119">Windows</span></span>     |<span data-ttu-id="aedbf-120">X</span><span class="sxs-lookup"><span data-stu-id="aedbf-120">X</span></span>         |<span data-ttu-id="aedbf-121">X</span><span class="sxs-lookup"><span data-stu-id="aedbf-121">X</span></span>         |<span data-ttu-id="aedbf-122">X</span><span class="sxs-lookup"><span data-stu-id="aedbf-122">X</span></span>         |
|<span data-ttu-id="aedbf-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="aedbf-123">Mac OSX</span></span>     |<span data-ttu-id="aedbf-124">X</span><span class="sxs-lookup"><span data-stu-id="aedbf-124">X</span></span>         |<span data-ttu-id="aedbf-125">X</span><span class="sxs-lookup"><span data-stu-id="aedbf-125">X</span></span>         |<span data-ttu-id="aedbf-126">X</span><span class="sxs-lookup"><span data-stu-id="aedbf-126">X</span></span>         |
|<span data-ttu-id="aedbf-127">iOS</span><span class="sxs-lookup"><span data-stu-id="aedbf-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="aedbf-128">Android</span><span class="sxs-lookup"><span data-stu-id="aedbf-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="aedbf-129">Per un elenco completo di sistemi operativi e browser supportati, vedere [ottenere client per Microsoft teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="aedbf-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="aedbf-130">Log di debug</span><span class="sxs-lookup"><span data-stu-id="aedbf-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="aedbf-131">Questi sono i registri più comuni e sono necessari per tutti i casi di supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aedbf-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="aedbf-132">I log di debug vengono prodotti dai client desktop Windows e Mac, oltre ai client basati su browser.</span><span class="sxs-lookup"><span data-stu-id="aedbf-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="aedbf-133">I log sono basati su testo e vengono letti dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="aedbf-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="aedbf-134">Possono essere lette usando qualsiasi editor basato su testo e vengono creati nuovi log durante l'accesso al client.</span><span class="sxs-lookup"><span data-stu-id="aedbf-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="aedbf-135">I registri di debug mostrano i flussi di dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="aedbf-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="aedbf-136">Accesso</span><span class="sxs-lookup"><span data-stu-id="aedbf-136">Login</span></span>

-   <span data-ttu-id="aedbf-137">Richieste di connessione ai servizi di livello intermedio</span><span class="sxs-lookup"><span data-stu-id="aedbf-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="aedbf-138">Chiamata/conversazione</span><span class="sxs-lookup"><span data-stu-id="aedbf-138">Call/conversation</span></span>

<span data-ttu-id="aedbf-139">I log di debug vengono prodotti usando i seguenti metodi specifici per il sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="aedbf-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="aedbf-140">Windows</span><span class="sxs-lookup"><span data-stu-id="aedbf-140">Windows:</span></span>

      <span data-ttu-id="aedbf-141">Tasto di scelta rapida: CTRL + ALT + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="aedbf-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="aedbf-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="aedbf-142">Mac OSX:</span></span>

      <span data-ttu-id="aedbf-143">Tasto di scelta rapida: opzione + comando + MAIUSC + 1</span><span class="sxs-lookup"><span data-stu-id="aedbf-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="aedbf-144">I log di debug vengono scaricati automaticamente nelle cartelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="aedbf-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="aedbf-145">Windows:% UserProfile%\\download</span><span class="sxs-lookup"><span data-stu-id="aedbf-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="aedbf-146">Mac OSX: download</span><span class="sxs-lookup"><span data-stu-id="aedbf-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="aedbf-147">Browser: verrà richiesto di salvare il log di debug nella posizione di salvataggio predefinita</span><span class="sxs-lookup"><span data-stu-id="aedbf-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="aedbf-148">Registri multimediali</span><span class="sxs-lookup"><span data-stu-id="aedbf-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="aedbf-149">I registri multimediali contengono dati di diagnostica relativi alla condivisione audio, video e dello schermo.</span><span class="sxs-lookup"><span data-stu-id="aedbf-149">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="aedbf-150">Sono necessari per i casi di supporto solo su richiesta e possono essere controllati solo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aedbf-150">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="aedbf-151">La tabella seguente illustra la posizione del log.</span><span class="sxs-lookup"><span data-stu-id="aedbf-151">The following table outlines the log location.</span></span>


|<span data-ttu-id="aedbf-152">Client</span><span class="sxs-lookup"><span data-stu-id="aedbf-152">Client</span></span> |<span data-ttu-id="aedbf-153">Posizione</span><span class="sxs-lookup"><span data-stu-id="aedbf-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="aedbf-154">Windows</span><span class="sxs-lookup"><span data-stu-id="aedbf-154">Windows</span></span>     |<span data-ttu-id="aedbf-155">%appdata%\Microsoft\Teams\media-stack\\*. Blog</span><span class="sxs-lookup"><span data-stu-id="aedbf-155">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="aedbf-156">%appdata%\Microsoft\Teams\skylib\\*. Blog</span><span class="sxs-lookup"><span data-stu-id="aedbf-156">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="aedbf-157">%appdata%\Microsoft\Teams\media-stack\\*. etl</span><span class="sxs-lookup"><span data-stu-id="aedbf-157">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="aedbf-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="aedbf-158">Mac OSX</span></span>     |<span data-ttu-id="aedbf-159">~/Libreria/Application Support/Microsoft/teams/media-stack/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="aedbf-159">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="aedbf-160">~/Libreria/Application Support/Microsoft/teams/skylib/\*. Blog</span><span class="sxs-lookup"><span data-stu-id="aedbf-160">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="aedbf-161">Registri desktop</span><span class="sxs-lookup"><span data-stu-id="aedbf-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="aedbf-162">I registri desktop, noti anche come log del programma di avvio automatico, contengono i dati del log che si verificano tra il client desktop e il browser.</span><span class="sxs-lookup"><span data-stu-id="aedbf-162">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="aedbf-163">Come i registri multimediali, questi registri sono necessari solo se richiesti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aedbf-163">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="aedbf-164">I log sono basati su testo e possono essere letti usando qualsiasi editor basato su testo in un formato top-down.</span><span class="sxs-lookup"><span data-stu-id="aedbf-164">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="aedbf-165">Windows</span><span class="sxs-lookup"><span data-stu-id="aedbf-165">Windows:</span></span>

1.  <span data-ttu-id="aedbf-166">Fare clic con il pulsante destro del mouse sull' **icona di Microsoft teams nella barra delle** applicazioni, selezionare **Ottieni log**</span><span class="sxs-lookup"><span data-stu-id="aedbf-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="aedbf-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="aedbf-167">Mac OsX:</span></span>

1.  <span data-ttu-id="aedbf-168">Scegliere **Get logs** dal menu a discesa della **Guida**</span><span class="sxs-lookup"><span data-stu-id="aedbf-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="aedbf-169">Client</span><span class="sxs-lookup"><span data-stu-id="aedbf-169">Client</span></span> |<span data-ttu-id="aedbf-170">Posizione</span><span class="sxs-lookup"><span data-stu-id="aedbf-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="aedbf-171">Windows</span><span class="sxs-lookup"><span data-stu-id="aedbf-171">Windows</span></span>     |<span data-ttu-id="aedbf-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="aedbf-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="aedbf-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="aedbf-173">Mac OSX</span></span>     |<span data-ttu-id="aedbf-174">~/Libreria/Application Support/Microsoft/teams/logs. txt</span><span class="sxs-lookup"><span data-stu-id="aedbf-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
