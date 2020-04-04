---
title: Eseguire un'analisi eDiscovery del contenuto
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su cosa fare quando è necessario eseguire una eDiscovery, ad esempio quando è necessario inviare tutti i dati archiviati elettronicamente per il procedimento legale.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136686"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="4b87f-103">Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b87f-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="4b87f-104">Le grandi imprese sono spesso esposte a procedimenti legali di pena elevata che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI).</span><span class="sxs-lookup"><span data-stu-id="4b87f-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="4b87f-105">Tutti i team 1:1 o chat di gruppo vengono inseriti nelle cassette postali degli utenti e tutti i messaggi di canale standard vengono inseriti nella cassetta postale del gruppo che rappresenta il team.</span><span class="sxs-lookup"><span data-stu-id="4b87f-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="4b87f-106">I file caricati nei canali standard sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="4b87f-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="4b87f-107">eDiscovery i messaggi e i file nei [canali privati](private-channels.md) funzionano in modo diverso rispetto ai canali standard.</span><span class="sxs-lookup"><span data-stu-id="4b87f-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="4b87f-108">Per altre informazioni, vedere [eDiscovery di canali privati](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="4b87f-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="4b87f-109">In questo momento, non supportiamo eDiscovery dei messaggi di chat in scenari in cui gli utenti Guest sono gli unici partecipanti in una chat di 1:1 o 1: N.</span><span class="sxs-lookup"><span data-stu-id="4b87f-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="4b87f-110">Questi tipi di chat sono anche chiamati chat *guest-to-Guest* , perché non includono utenti tenant privati.</span><span class="sxs-lookup"><span data-stu-id="4b87f-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="4b87f-111">Per eseguire un'analisi eDiscovery con il contenuto di Microsoft teams, esaminare [il](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) passaggio 1 in questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="4b87f-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="4b87f-112">I dati di Microsoft teams verranno visualizzati come messaggistica istantanea o conversazioni nell'output di esportazione di Excel eDiscovery ed è possibile aprire il file PST in Outlook per visualizzare i messaggi dopo l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="4b87f-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="4b87f-113">Quando si Visualizza il file PST per il team, tenere presente che tutte le conversazioni vengono mantenute nella cartella chat del team in Cronologia conversazioni.</span><span class="sxs-lookup"><span data-stu-id="4b87f-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="4b87f-114">Il titolo del messaggio viene allineato al team e al canale.</span><span class="sxs-lookup"><span data-stu-id="4b87f-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="4b87f-115">Dalla revisione dell'immagine seguente è possibile visualizzare il messaggio di Roberto che ha inviato un messaggio al canale standard di Project 7 del team di specifiche di manufacturing.</span><span class="sxs-lookup"><span data-stu-id="4b87f-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Screenshot di una cartella della chat del team nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="4b87f-117">Per visualizzare le chat private nella cassetta postale di un utente, esse si trovano anche nella cartella chat del team in Cronologia conversazioni.</span><span class="sxs-lookup"><span data-stu-id="4b87f-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="4b87f-118">eDiscovery dei canali privati</span><span class="sxs-lookup"><span data-stu-id="4b87f-118">eDiscovery of private channels</span></span>

<span data-ttu-id="4b87f-119">I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo.</span><span class="sxs-lookup"><span data-stu-id="4b87f-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="4b87f-120">I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="4b87f-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="4b87f-121">Poiché ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre, i file in un canale privato vengono gestiti indipendentemente dal team padre.</span><span class="sxs-lookup"><span data-stu-id="4b87f-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="4b87f-122">Teams non supporta eDiscovery di un singolo canale, quindi è necessario cercare tutto il team.</span><span class="sxs-lookup"><span data-stu-id="4b87f-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="4b87f-123">Per eseguire una ricerca eDiscovery del contenuto in un canale privato, cercare in tutto il team, la raccolta siti associata al canale privato (per includere i file) e le cassette postali dei membri del canale privato (per includere i messaggi).</span><span class="sxs-lookup"><span data-stu-id="4b87f-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="4b87f-124">Seguire i passaggi seguenti per identificare i file e i messaggi in un canale privato da includere nella ricerca di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4b87f-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="4b87f-125">Includere file di canale privato in una ricerca eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4b87f-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="4b87f-126">Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="4b87f-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="4b87f-127">Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate a canali privati nel team.</span><span class="sxs-lookup"><span data-stu-id="4b87f-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="4b87f-128">Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati a canali privati nel team e nell'ID del gruppo del team padre.</span><span class="sxs-lookup"><span data-stu-id="4b87f-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="4b87f-129">Per ogni ID team o gruppo, Esegui lo script di PowerShell seguente per identificare tutti i siti di canale privati rilevanti, dove $groupID è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="4b87f-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="4b87f-130">Includere messaggi di canale privato in una ricerca eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4b87f-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="4b87f-131">Prima di eseguire questa procedura, verificare di avere installato la [versione più recente del modulo di PowerShell teams](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="4b87f-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="4b87f-132">Eseguire la procedura seguente per ottenere un elenco di canali privati nel team.</span><span class="sxs-lookup"><span data-stu-id="4b87f-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="4b87f-133">Eseguire la procedura seguente per ottenere un elenco dei membri del canale privato.</span><span class="sxs-lookup"><span data-stu-id="4b87f-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="4b87f-134">Includere le cassette postali di tutti i membri di ogni canale privato del team come parte della query di ricerca di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4b87f-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b87f-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4b87f-135">Related topics</span></span>

- [<span data-ttu-id="4b87f-136">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="4b87f-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
