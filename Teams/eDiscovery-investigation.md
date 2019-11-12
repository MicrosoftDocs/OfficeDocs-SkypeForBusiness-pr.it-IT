---
title: Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams
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
description: Informazioni su cosa fare quando è necessario preformare un eDiscovery, ad esempio quando è necessario inviare tutte le info archiviate elettronicamente per il procedimento legale.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e645085130b65283a1841661c4e2885e5ea9cba4
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231117"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="0c922-103">Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c922-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="0c922-104">Le grandi imprese sono spesso esposte a procedimenti legali di pena elevata che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI).</span><span class="sxs-lookup"><span data-stu-id="0c922-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="0c922-105">Tutti i team 1:1 o chat di gruppo vengono inseriti nelle cassette postali degli utenti e tutti i messaggi di canale standard vengono inseriti nella cassetta postale del gruppo che rappresenta il team.</span><span class="sxs-lookup"><span data-stu-id="0c922-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="0c922-106">I file caricati nei canali standard sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="0c922-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="0c922-107">eDiscovery i messaggi e i file nei [canali privati](private-channels.md) funzionano in modo diverso rispetto ai canali standard.</span><span class="sxs-lookup"><span data-stu-id="0c922-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="0c922-108">Per altre informazioni, vedere [eDiscovery di canali privati](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="0c922-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

1.  <span data-ttu-id="0c922-109">Per eseguire un'analisi eDiscovery con il contenuto di Microsoft teams, esaminare [il](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) passaggio 1 in questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="0c922-109">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="0c922-110">I dati di Microsoft teams verranno visualizzati come messaggi istantanei o conversazioni nell'output di esportazione di Excel eDiscovery ed è possibile montarlo. PST in Outlook per visualizzare i messaggi dopo l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="0c922-110">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="0c922-111">Quando si monta. PST per il team, tenere presente che tutte le conversazioni vengono mantenute nella cartella chat del team in Cronologia conversazioni.</span><span class="sxs-lookup"><span data-stu-id="0c922-111">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="0c922-112">Il titolo del messaggio viene allineato al team e al canale.</span><span class="sxs-lookup"><span data-stu-id="0c922-112">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="0c922-113">Dalla revisione dell'immagine seguente è possibile visualizzare il messaggio di Roberto che ha inviato un messaggio al canale standard di Project 7 del team di specifiche di manufacturing.</span><span class="sxs-lookup"><span data-stu-id="0c922-113">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Screenshot di una cartella della chat del team nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="0c922-115">Per visualizzare le chat private nella cassetta postale di un utente, esse si trovano anche all'interno della cartella chat del team in Cronologia conversazioni.</span><span class="sxs-lookup"><span data-stu-id="0c922-115">To see private chats in a user’s mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="0c922-116">eDiscovery delle chat Guest-to-Guest</span><span class="sxs-lookup"><span data-stu-id="0c922-116">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="0c922-117">Senza una cassetta postale, le chat Guest-to-Guest (chat 1xN in cui non ci sono utenti di Home tenant) non verrebbero indicizzate e, di conseguenza, non verrebbero incluse in eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0c922-117">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="0c922-118">Per facilitare eDiscovery per le chat Guest-to-Guest, viene creata una cassetta postale basata sul cloud (o una cassetta postale fantasma) per archiviare i dati di 1xN.</span><span class="sxs-lookup"><span data-stu-id="0c922-118">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="0c922-119">Dopo che i dati della chat di teams sono archiviati nella cassetta postale basata sul cloud, è indicizzato per la ricerca di contenuto eDiscovery e conformità.</span><span class="sxs-lookup"><span data-stu-id="0c922-119">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="0c922-120">La figura seguente mostra come funziona eDiscovery per le chat Guest-to-Guest in cui non è presente una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0c922-120">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![Guest-to-Guest-chat-con-senza-cassetta postale](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="0c922-122">eDiscovery dei canali privati</span><span class="sxs-lookup"><span data-stu-id="0c922-122">eDiscovery of private channels</span></span>

<span data-ttu-id="0c922-123">I record per i messaggi inviati in un canale privato vengono recapitati alla cassetta postale di tutti i membri del canale privato, invece che a una cassetta postale del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c922-123">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="0c922-124">I titoli dei record sono formattati per indicare il canale privato da cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="0c922-124">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="0c922-125">Poiché ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre, i file in un canale privato vengono gestiti indipendentemente dal team padre.</span><span class="sxs-lookup"><span data-stu-id="0c922-125">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="0c922-126">Teams non supporta eDiscovery di un singolo canale, quindi è necessario cercare tutto il team.</span><span class="sxs-lookup"><span data-stu-id="0c922-126">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="0c922-127">Per eseguire una ricerca eDiscovery del contenuto in un canale privato, cercare in tutto il team, la raccolta siti associata al canale privato (per includere i file) e le cassette postali dei membri del canale privato (per includere i messaggi).</span><span class="sxs-lookup"><span data-stu-id="0c922-127">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="0c922-128">Seguire i passaggi seguenti per identificare i file e i messaggi in un canale privato da includere nella ricerca di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0c922-128">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="0c922-129">Includere file di canale privato in una ricerca eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0c922-129">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="0c922-130">Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="0c922-130">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="0c922-131">Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate a canali privati nel team.</span><span class="sxs-lookup"><span data-stu-id="0c922-131">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```
    Get-SPOSite
    ```
2. <span data-ttu-id="0c922-132">Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati a canali privati nel team e nell'ID del gruppo del team padre.</span><span class="sxs-lookup"><span data-stu-id="0c922-132">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="0c922-133">Per ogni ID team o gruppo, Esegui lo script di PowerShell seguente per identificare tutti i siti di canale privati rilevanti, dove $groupID è l'ID del gruppo del team.</span><span class="sxs-lookup"><span data-stu-id="0c922-133">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="0c922-134">Includere messaggi di canale privato in una ricerca eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0c922-134">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="0c922-135">Prima di eseguire questa procedura, verificare di avere installato la [versione più recente del modulo di PowerShell teams](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="0c922-135">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="0c922-136">Eseguire la procedura seguente per ottenere un elenco di canali privati nel team.</span><span class="sxs-lookup"><span data-stu-id="0c922-136">Run the following to get a list of private channels in the team.</span></span>

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="0c922-137">Eseguire la procedura seguente per ottenere un elenco dei membri del canale privato.</span><span class="sxs-lookup"><span data-stu-id="0c922-137">Run the following to get a list of private channel members.</span></span>

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="0c922-138">Includere le cassette postali di tutti i membri di ogni canale privato del team come parte della query di ricerca di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0c922-138">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c922-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0c922-139">Related topics</span></span>

- [<span data-ttu-id="0c922-140">Panoramica di PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="0c922-140">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)