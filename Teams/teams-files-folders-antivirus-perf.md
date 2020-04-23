---
title: File e cartelle di Teams da escludere dall'analisi antivirus
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Migliorare le prestazioni dei team escludendo determinati file e cartelle dalla normale analisi antivirus.
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579592"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="148e6-103">File e cartelle di Teams da escludere dall'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="148e6-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="148e6-104">Puoi migliorare le prestazioni complessive della distribuzione dei team impedendo ai programmi antivirus di analizzare file e cartelle di determinati team.</span><span class="sxs-lookup"><span data-stu-id="148e6-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="148e6-105">In questo modo, eviterai le spese delle risorse di sistema per la digitalizzazione di file e cartelle che non devono essere analizzati.</span><span class="sxs-lookup"><span data-stu-id="148e6-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="148e6-106">Quando gli utenti scaricano file o condividono file tra loro, questi file non passano attraverso i percorsi elencati nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="148e6-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="148e6-107">Le posizioni in cui gli utenti caricano, scaricano o condividono file verranno ancora regolarmente analizzate dal programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="148e6-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="148e6-108">File e cartelle da aggiungere agli elenchi di sicurezza antivirus</span><span class="sxs-lookup"><span data-stu-id="148e6-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="148e6-109">Usare le procedure supportate dal programma antivirus per aggiungere i file e le cartelle seguenti agli elenchi attendibili.</span><span class="sxs-lookup"><span data-stu-id="148e6-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="148e6-110">In questo modo le risorse di sistema verranno conservate evitando scansioni antivirus di queste posizioni.</span><span class="sxs-lookup"><span data-stu-id="148e6-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="148e6-111">Programmi</span><span class="sxs-lookup"><span data-stu-id="148e6-111">Programs</span></span>

<span data-ttu-id="148e6-112">Aggiungere i seguenti programmi teams all'elenco di indirizzi attendibili antivirus.</span><span class="sxs-lookup"><span data-stu-id="148e6-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="148e6-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="148e6-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="148e6-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="148e6-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

