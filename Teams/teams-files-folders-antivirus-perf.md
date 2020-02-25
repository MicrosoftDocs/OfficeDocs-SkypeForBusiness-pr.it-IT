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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1519038cb2393687a031e9b2c1ea828f999728
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265621"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="4b99c-103">File e cartelle di Teams da escludere dall'analisi antivirus</span><span class="sxs-lookup"><span data-stu-id="4b99c-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="4b99c-104">Puoi migliorare le prestazioni complessive della distribuzione dei team impedendo ai programmi antivirus di analizzare file e cartelle di determinati team.</span><span class="sxs-lookup"><span data-stu-id="4b99c-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="4b99c-105">In questo modo, eviterai le spese delle risorse di sistema per la digitalizzazione di file e cartelle che non devono essere analizzati.</span><span class="sxs-lookup"><span data-stu-id="4b99c-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="4b99c-106">Quando gli utenti scaricano file o condividono file tra loro, questi file non passano attraverso i percorsi elencati nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="4b99c-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="4b99c-107">Le posizioni in cui gli utenti caricano, scaricano o condividono file verranno ancora regolarmente analizzate dal programma antivirus.</span><span class="sxs-lookup"><span data-stu-id="4b99c-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="4b99c-108">File e cartelle da aggiungere agli elenchi di sicurezza antivirus</span><span class="sxs-lookup"><span data-stu-id="4b99c-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="4b99c-109">Usare le procedure supportate dal programma antivirus per aggiungere i file e le cartelle seguenti agli elenchi attendibili.</span><span class="sxs-lookup"><span data-stu-id="4b99c-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="4b99c-110">In questo modo le risorse di sistema verranno conservate evitando scansioni antivirus di queste posizioni.</span><span class="sxs-lookup"><span data-stu-id="4b99c-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="4b99c-111">Programmi</span><span class="sxs-lookup"><span data-stu-id="4b99c-111">Programs</span></span>

<span data-ttu-id="4b99c-112">Aggiungere i seguenti programmi teams all'elenco di indirizzi attendibili antivirus.</span><span class="sxs-lookup"><span data-stu-id="4b99c-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="4b99c-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="4b99c-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="4b99c-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="4b99c-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="4b99c-115">Cartelle</span><span class="sxs-lookup"><span data-stu-id="4b99c-115">Folders</span></span>

<span data-ttu-id="4b99c-116">Aggiungere le cartelle teams seguenti all'elenco di indirizzi attendibili antivirus.</span><span class="sxs-lookup"><span data-stu-id="4b99c-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="4b99c-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="4b99c-117">Category</span></span>  |<span data-ttu-id="4b99c-118">Posizione</span><span class="sxs-lookup"><span data-stu-id="4b99c-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="4b99c-119">File di programma</span><span class="sxs-lookup"><span data-stu-id="4b99c-119">Program files</span></span>  |<span data-ttu-id="4b99c-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="4b99c-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="4b99c-121">File di dati</span><span class="sxs-lookup"><span data-stu-id="4b99c-121">Data files</span></span>     |<span data-ttu-id="4b99c-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="4b99c-122">%appdata%\Microsoft\Teams</span></span>\ |
