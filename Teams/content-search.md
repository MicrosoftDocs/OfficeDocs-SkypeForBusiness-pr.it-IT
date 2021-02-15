---
title: Usare Ricerca contenuto in Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Informazioni sull'uso di Ricerca contenuto nel Centro conformità di Microsoft 365 per cercare contenuto di Microsoft Teams archiviato in Exchange Online, SharePoint Online, OneDrive for Business e OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980440"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="94fa6-103">Usare la ricerca di contenuto in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94fa6-103">Use Content search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="94fa6-104">La ricerca di contenuti di messaggi e file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard.</span><span class="sxs-lookup"><span data-stu-id="94fa6-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="94fa6-105">Per altre informazioni, vedere [Ricerca di contenuti di canali privati.](#content-search-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="94fa6-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="94fa6-106">La ricerca contenuto consente di eseguire query sulle informazioni di Microsoft Teams che interessano Exchange, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="94fa6-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="94fa6-107">Per altre informazioni, vedere [Ricerca contenuto in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search)</span><span class="sxs-lookup"><span data-stu-id="94fa6-107">To learn more, see [Content search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="94fa6-108">Ad esempio,  usando la ricerca di contenuto per la cassetta postale Delle specifiche di produzione e il sito di SharePoint Specifiche di produzione, è possibile eseguire ricerche nelle conversazioni di canale standard di Teams da Exchange, caricare file e apportare modifiche da SharePoint Online e modifiche di OneNote.</span><span class="sxs-lookup"><span data-stu-id="94fa6-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="94fa6-109">È anche possibile aggiungere criteri di query alla **ricerca contenuto per** limitare i risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="94fa6-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="94fa6-110">Nell'esempio precedente è possibile cercare il contenuto in cui sono state usate le parole chiave **"Nuove** specifiche di fabbrica".</span><span class="sxs-lookup"><span data-stu-id="94fa6-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="94fa6-111">Dopo aver aggiunto condizioni di ricerca, è possibile esportare un report o il contenuto effettivo nel computer per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="94fa6-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="94fa6-112">Ricerca di contenuti di canali privati</span><span class="sxs-lookup"><span data-stu-id="94fa6-112">Content search of private channels</span></span>

<span data-ttu-id="94fa6-113">I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo.</span><span class="sxs-lookup"><span data-stu-id="94fa6-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="94fa6-114">I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="94fa6-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="94fa6-115">Poiché ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre, i file in un canale privato vengono gestiti in modo indipendente dal team padre.</span><span class="sxs-lookup"><span data-stu-id="94fa6-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="94fa6-116">Teams non supporta la ricerca di contenuto in un singolo canale, quindi è necessario cercare l'intero team.</span><span class="sxs-lookup"><span data-stu-id="94fa6-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="94fa6-117">Per eseguire una ricerca di contenuto di un canale privato, eseguire una ricerca in tutto il team, nella raccolta siti associata al canale privato (per includere i file) e nelle cassette postali dei membri del canale privato (per includere i messaggi).</span><span class="sxs-lookup"><span data-stu-id="94fa6-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="94fa6-118">Usare la procedura seguente per identificare i file e i messaggi in un canale privato da includere nella ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="94fa6-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="94fa6-119">Includere i file dei canali privati in una ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="94fa6-119">Include private channel files in a content search</span></span>

<span data-ttu-id="94fa6-120">Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="94fa6-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="94fa6-121">Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate ai canali privati del team.</span><span class="sxs-lookup"><span data-stu-id="94fa6-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="94fa6-122">Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati ai canali privati del team e all'ID del gruppo di team padre.</span><span class="sxs-lookup"><span data-stu-id="94fa6-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="94fa6-123">Per ogni ID team o gruppo, eseguire il seguente script di PowerShell per identificare tutti i siti dei canali privati pertinenti.</span><span class="sxs-lookup"><span data-stu-id="94fa6-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="94fa6-124">Includere messaggi di canale privato in una ricerca di contenuto</span><span class="sxs-lookup"><span data-stu-id="94fa6-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="94fa6-125">Prima di eseguire questa procedura, assicurarsi di avere installato [l'ultima versione del modulo Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="94fa6-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="94fa6-126">Esegui la procedura seguente per ottenere un elenco di canali privati nel team.</span><span class="sxs-lookup"><span data-stu-id="94fa6-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="94fa6-127">Eseguire la procedura seguente per ottenere un elenco dei membri del canale privato.</span><span class="sxs-lookup"><span data-stu-id="94fa6-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="94fa6-128">Includere le cassette postali di tutti i membri di ogni canale privato nel team come parte della query di ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="94fa6-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="94fa6-129">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="94fa6-129">Related topics</span></span>

- [<span data-ttu-id="94fa6-130">Casi di eDiscovery nel Centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94fa6-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 